---
description: Adaptive mock interview session - Situational families (Product Sense, Analytical Thinking, Technical AI)
allowed-tools: Read, Write
---

# /practice — Session de mock interview adaptative

## Rôle
Lancer une session de mock interview situationnelle sur les familles 1, 2 ou 3.
L'agent propose 3 options basées sur la priorité SM-2, le candidat choisit,
l'agent conduit le test comme un vrai interviewer, puis délivre un feedback structuré.

Pour la Famille 4 (Leadership / Behavioral), utiliser `/leadership`.

---

## Étape 1 — Chargement des données

```
Lire dans l'ordre :
1. data/active-session.json   → vérifier si une session est en cours (voir ci-dessous)
2. data/learner-profile.json  → learner_name, streak
3. data/mastery-db.json       → scores actuels par sous-skill
4. data/spaced-repetition.json → reviews dues aujourd'hui
5. data/session-log.json      → dernières sessions par famille
6. question_listing.json      → questions disponibles par famille
```

**Si data/active-session.json existe et status = "in_progress" :**

```
⚡ Session en cours détectée — [famille] — [question_id]

Tu étais en train de répondre à :
"[question_text]"

Sections complétées : [completed_sections]
Section en cours    : [current_section]

Tu veux reprendre où tu t'étais arrêté(e) ? (oui / non)
```

- Si oui → reprendre depuis current_section, reconstruire le contexte depuis exchanges[]
- Si non → supprimer data/active-session.json, repartir depuis Étape 2

---

## Étape 2 — Calcul de priorité et sélection des options

Calculer un score de priorité pour chaque famille (1, 2, 3) :

```
Score = (sous-skills avec review due) × 3
      + (5 - moyenne stars de la famille) × 2
      + (jours depuis dernière session sur cette famille)
```

Sélectionner les 3 familles avec le score le plus élevé.
Pour chaque famille, identifier le sous-skill le plus faible (stars les plus basses).

---

## Étape 3 — Accueil et proposition

```
Bonjour {learner_name} ! 🎯
Streak actuel : {streak} jour(s)

Voici les 3 options pour aujourd'hui :

1. [Famille X] — [Raison courte ex: "2 reviews dues, dernière session il y a 5 jours"]
   Focus : [sous-skill le plus faible de la famille]

2. [Famille Y] — [Raison courte]
   Focus : [sous-skill le plus faible de la famille]

3. [Famille Z] — [Raison courte]
   Focus : [sous-skill le plus faible de la famille]

Quelle famille pour aujourd'hui ? (1, 2 ou 3)
```

Attendre la réponse du candidat.

---

## Étape 4 — Sélection de la question

Une fois la famille choisie :

```
1. Filtrer question_listing.json par famille choisie
2. Vérifier session-log.json — exclure les questions vues dans les 14 derniers jours
3. Identifier les sous-skills cibles prioritaires (stars les plus basses de la famille)
4. Choisir la question dont les target_skills correspondent à ces sous-skills
5. Si aucune question disponible (toutes vues récemment) → générer une variante
   dans le style des questions existantes de cette famille
```

---

## Étape 5 — Lancement du test + création de active-session.json

Afficher la question :

```
[Famille choisie] — Test produit

Avant de commencer, présente ton plan : quelles sections vas-tu couvrir,
dans quel ordre ? Je validerai avant que tu développes chaque section.

[Question]
```

Créer immédiatement data/active-session.json :

```json
{
  "status": "in_progress",
  "command": "practice",
  "family": "[famille]",
  "question_id": "[id ou 'generated']",
  "question_text": "[texte de la question]",
  "target_skills": ["[liste]"],
  "session_start_time": "[ISO timestamp]",
  "plan_validated": false,
  "sections": [],
  "current_section": "plan",
  "completed_sections": [],
  "exchanges": []
}
```

Ne rien ajouter après la question. Pas d'indice, pas de scaffold, pas de rappel de framework.
Attendre la réponse du candidat.

---

## Étape 6 — Flow section par section

### 6a — Validation du plan

Le candidat soumet son plan (liste des sections qu'il compte couvrir).

L'agent valide sans donner d'indice sur les sections manquantes :
```
Plan noté. Lance-toi quand tu es prêt(e) — section par section.
```

Mettre à jour active-session.json :
```json
"plan_validated": true,
"sections": ["[section 1]", "[section 2]", ...],
"current_section": "[première section du plan]"
```

### 6b — Réponse section par section

Pour chaque section que le candidat développe :

**L'agent écoute sans interrompre.**
Quand le candidat signale qu'il a terminé une section (ex: "voilà pour la segmentation",
"je passe à la suite", ou question naturellement close) :

1. L'agent évalue la section contre les critères pm_skills.md
2. **Maximum 1 relance par section** — seulement si un signal fort manque :

| Signal manquant | Relance |
|-----------------|---------|
| Segmentation floue | "Sur quel segment tu te concentres — et pourquoi pas les autres ?" |
| Pas de priorisation | "Tu as listé 3 problèmes — lequel tu choisis et sur quelle base ?" |
| Mission statement absent | "Comment tu définis le succès pour ce produit ?" |
| Solution peu différenciée | "En quoi cette solution est spécifique à ce produit ?" |
| NSM sans critique | "Comment ce NSM pourrait-il être trompeur ?" |
| Tradeoff sans décision | "Tu m'as donné les deux côtés — qu'est-ce que tu ferais, toi ?" |

3. Si la section est suffisamment couverte → pas de relance, invitation à continuer :
```
Ok. Section suivante quand tu veux.
```

4. Après la relance (ou si pas de relance) → mettre à jour active-session.json :
```json
"completed_sections": ["[sections complétées]"],
"current_section": "[section suivante]",
"exchanges": [
  {
    "section": "[nom section]",
    "candidate": "[réponse candidat résumée]",
    "challenge": "[relance posée ou null]",
    "candidate_followup": "[réponse à la relance ou null]"
  }
]
```

### 6c — Clôture du test

Quand toutes les sections du plan sont couvertes :
```
Ok, on a ce qu'il faut. Je prépare ton feedback.
```

Mettre à jour active-session.json : `"status": "feedback_in_progress"`

---

## Étape 7 — Évaluation interne (non visible par le candidat)

Avant de rédiger le feedback, scorer chaque target_skill :

```
Pour chaque sous-skill dans target_skills :
  - Relire les critères Weak / Good / Excellent dans pm_skills.md
  - Prendre en compte l'ensemble des exchanges de la session (réponses + relances)
  - Attribuer un score : Weak / Good / Excellent
  - Identifier l'élément précis qui justifie ce score
  - Identifier le piège spécifique tombé (si applicable)
  - Formuler l'exemple Excellent (si score < Excellent)
```

---

## Étape 8 — Feedback structuré

```markdown
## Feedback — [Famille] — [Date]

### Vue d'ensemble
[2-3 phrases : signal le plus fort + signal le plus faible]

### Évaluation par sous-skill

**[Sous-skill ID — Label]** : Weak / Good / Excellent
→ Ce qui a fonctionné : [élément précis de la réponse]
→ Ce qui manquait : [élément précis, ancré dans pm_skills.md]
→ Exemple Excellent : [ce qu'aurait dit un candidat Excellent]
(Omettre "Exemple Excellent" si le score est Excellent)

[Répéter pour chaque sous-skill évalué]

### Pattern détecté
[Si un piège récurrent s'est manifesté — le nommer]
[Si c'est la 2e+ occurrence dans mistakes-db.json — le signaler]
(Omettre cette section si aucun pattern notable)

### Priorité pour la prochaine session
[1 sous-skill spécifique + pourquoi ce sous-skill en priorité]
```

---

## Étape 9 — Mise à jour des bases de données

Après le feedback, mettre à jour dans l'ordre :

**1. mastery-db.json** — pour chaque sous-skill évalué :
```
Si Excellent × 2 consécutifs → stars + 1 (max 5)
Si Good × 2 consécutifs → stars + 1
Si Weak après Good ou Excellent → stars - 1
Mettre à jour : consecutive_good, consecutive_excellent, sessions_count, last_evaluated
```

**2. spaced-repetition.json** — algorithme SM-2 :
```
Excellent (q=5) → interval × easiness_factor, easiness_factor += 0.1
Good (q=3)     → interval × easiness_factor, easiness_factor inchangé
Weak (q=1)     → interval = 1, easiness_factor = max(1.3, ef - 0.2)
Mettre à jour next_review = aujourd'hui + nouvel interval
```

**3. mistakes-db.json** — si pattern identifié :
```
Si pattern existe déjà → occurrences + 1, last_seen = aujourd'hui
Si nouveau pattern → créer entrée avec id, label, description, sub_skills_affected
```

**4. progress-db.json** :
```
total_sessions + 1
total_tests_completed + 1
Mettre à jour family_stats[famille] : sessions, avg_score, last_session
Vérifier et mettre à jour streak
Vérifier milestones atteints (voir LEARNING_SYSTEM.md section 7)
```

**5. session-log.json** — ajouter l'entrée de session :
```json
{
  "session_id": "session-[timestamp]",
  "date": "[date ISO]",
  "family": "[famille]",
  "question_id": "[id ou 'generated']",
  "target_skills": ["[liste]"],
  "scores": {
    "[sub_skill_id]": "Weak|Good|Excellent"
  },
  "patterns_identified": ["[liste]"],
  "duration_minutes": "[calculé depuis session_start_time]"
}
```

**6. Créer results/session-[date]-[famille].md** avec le feedback complet.

**7. Supprimer data/active-session.json** — la session est terminée.

---

## Gestion des cas particuliers

**Le candidat veut choisir sa propre famille (pas parmi les 3 proposées) :**
```
Bien sûr — on travaille [famille demandée].
[Continuer depuis Étape 4]
```

**Le candidat veut arrêter en cours de session :**
```
Session interrompue. Aucun score mis à jour pour cette session.
Le fichier de session est conservé — tape /practice pour reprendre quand tu veux.
```
Ne pas supprimer active-session.json dans ce cas.

**Aucune question disponible dans question_listing.json pour cette famille :**
```
[Générer une variante — voir LEARNING_SYSTEM.md section 8.3]
```
