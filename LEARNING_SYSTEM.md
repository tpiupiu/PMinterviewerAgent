# LEARNING_SYSTEM.md — Méthodologie complète du PM Interview Coach

> Ce fichier est la référence méthodologique de l'agent.
> Il définit comment sélectionner les exercices, conduire les sessions,
> évaluer les réponses, et mettre à jour les données de progression.
> L'agent DOIT lire ce fichier au démarrage de chaque session.

---

## 1. Architecture du système d'apprentissage

### 1.1 Unité fondamentale : le test produit

Contrairement à un système de flashcards, l'unité d'apprentissage ici
est un **test produit complet** — une question ouverte qui simule
un entretien réel et évalue **1 à plusieurs sous-skills simultanément**.

Un test Product Sense peut évaluer en une seule session :
- Sous-skill transversal : Ouverture structurée & Mission Statement
- 1.1 Segmentation
- 1.2 Problem Identification
- 1.3 Solution Development

Un test Analytical Thinking peut évaluer :
- 2.1 Ecosystem Metrics Framework
- 2.2 Goal-Setting
- 2.3 Tradeoff Evaluation (si la question l'inclut)

Chaque test a une **liste de sous-skills cibles** définie avant le lancement.
L'évaluation post-test met à jour chaque sous-skill indépendamment.

### 1.2 Source des questions

L'agent utilise `question_listing.json` de deux façons :

**Mode "question réelle"** : l'agent pioche une question existante dans le fichier,
correspondant à la famille sélectionnée et au niveau de difficulté approprié.

**Mode "variante générée"** : l'agent s'inspire du style, du format et du niveau
de difficulté des questions du fichier pour générer une question originale.
Utile pour éviter la mémorisation des questions déjà vues.

Règle de sélection : si {learner_name} a déjà vu une question exacte dans les 14 derniers jours,
l'agent génère une variante plutôt que de la réutiliser.

---

## 2. Flow d'une session complète

### 2.1 Démarrage

```
1. Lire learner-profile.json
2. Lire mastery-db.json → identifier les sous-skills prioritaires (score < 3)
3. Lire spaced-repetition.json → identifier les reviews dues aujourd'hui
4. Accueillir {learner_name} : prénom + streak + focus recommandé
5. Proposer 2-3 options de famille selon la priorité (voir section 4)
6. Attendre le choix de {learner_name}
```

### 2.2 Lancement du test

```
1. Sélectionner une question dans question_listing.json
   (ou générer une variante si nécessaire)
2. Identifier les sous-skills cibles du test (1 à 4 sous-skills max)
3. Annoncer à {learner_name} :
   - La question
   - Le temps recommandé pour préparer (5-10 min)
   - Le format attendu ("prends le temps de structurer ta réponse complète")
4. Attendre la réponse de {learner_name}
```

### 2.3 Phase d'interview interactive

Après la première réponse du candidat, l'agent joue le rôle de l'interviewer.

**Règles critiques :**
- **5 questions complémentaires maximum** — pas une de plus
- Chaque question doit servir à évaluer un sous-skill spécifique encore non couvert
  ou à creuser un point faible identifié dans la réponse initiale
- L'agent peut clore le test **avant** 5 questions si les sous-skills cibles
  sont suffisamment évalués
- Les questions de l'agent doivent être réalistes — ce qu'un vrai interviewer poserait

**Types de relances possibles :**
- **Challenge** : "Tu as dit X — pourquoi pas Y dans ce contexte ?"
- **Approfondissement** : "Tu as mentionné [concept] — peux-tu être plus précis ?"
- **Mise sous pression** : "L'interviewer n'est pas convaincu par ta priorisation — défends-la"
- **Pivot** : "Et si le contexte changeait — l'entreprise est une startup, pas Meta ?"
- **Silence** : silence volontaire de l'agent pour laisser {learner_name} compléter

**Condition de clôture :**
L'agent clôt le test quand :
- Il a posé 5 questions complémentaires, OU
- Tous les sous-skills cibles ont été suffisamment évalués
  (au moins 2 signaux clairs par sous-skill : un fort et un faible)

Signal de clôture : "Ok, on a ce qu'il faut. Je prépare ton feedback."

### 2.4 Feedback post-test

Structure obligatoire du feedback :

```
## Résultat du test — [Nom du test] — [Date]

### Vue d'ensemble
[2-3 phrases sur l'impression globale — signal le plus fort et le plus faible]

### Évaluation par sous-skill

**[Sous-skill X.X — Nom]** : [Weak / Good / Excellent]
→ Ce qui a fonctionné : [élément précis de la réponse]
→ Ce qui manquait : [élément précis manquant, référencé dans pm_skills.md]
→ Exemple Excellent : [ce qu'aurait dit un candidat Excellent sur ce point]

[Répéter pour chaque sous-skill évalué]

### Pattern identifié
[Si un piège récurrent s'est manifesté — le nommer explicitement]
[Référencer si c'est la 2e ou 3e fois que ce pattern apparaît]

### Prochaine priorité
[1 sous-skill spécifique à travailler en priorité + pourquoi]
```

### 2.5 Mise à jour des bases de données

Après chaque feedback, mettre à jour dans l'ordre :
1. `mastery-db.json` — scores des sous-skills évalués
2. `spaced-repetition.json` — intervalles de révision selon SM-2
3. `mistakes-db.json` — patterns d'erreurs identifiés
4. `progress-db.json` — statistiques globales et streak
5. `session-log.json` — log de la session
6. Créer `results/session-[date]-[famille].md` — résultats détaillés

---

## 3. Algorithme de spaced repetition (SM-2 adapté PM)

### 3.1 Principe

L'algorithme SM-2 détermine quand un sous-skill doit être revu.
Un sous-skill maîtrisé revient moins souvent.
Un sous-skill faible revient rapidement.

### 3.2 Mapping des scores

| Résultat | Score SM-2 (q) | Interprétation |
|----------|---------------|----------------|
| Excellent | 5 | Maîtrisé avec aisance |
| Good | 3 | Acquis mais pas solide |
| Weak | 1 | Non acquis |

### 3.3 Calcul des intervalles

```
Si q < 2 (Weak) :
  → Revoir dans 1 jour
  → Réinitialiser l'easiness factor à 1.3

Si q = 3 (Good) :
  → Intervalle suivant = intervalle actuel × easiness factor
  → Easiness factor inchangé

Si q >= 4 (Excellent) :
  → Intervalle suivant = intervalle actuel × easiness factor
  → Easiness factor += 0.1 (rend le sous-skill moins prioritaire)

Intervalles initiaux :
  1ère répétition → 1 jour
  2ème répétition → 3 jours
  3ème répétition → 7 jours
  Ensuite → intervalle × easiness factor
```

### 3.4 Adaptation au contexte PM

Contrairement au langage (où on révise des mots isolés), ici un sous-skill
est évalué dans le contexte d'un test complet. Conséquences :

- Un sous-skill peut être évalué dans différentes familles
  (ex : Ouverture structurée est évalué dans tout test situationnel)
- Le score SM-2 est mis à jour uniquement quand le sous-skill est
  **explicitement ciblé** dans le test — pas quand il apparaît en périphérie
- Un test peut donc "toucher" 4 sous-skills mais n'en mettre à jour
  que 2 dans SM-2 si les 2 autres n'étaient pas assez exposés

---

## 4. Algorithme de sélection des sessions

### 4.1 Calcul de priorité

Quand {learner_name} lance `/practice`, l'agent calcule un score de priorité
pour chaque famille de skills :

```
Score priorité = (Poids SM-2) × (Poids niveau actuel) × (Poids temps écoulé)

Poids SM-2 : nombre de sous-skills avec review due aujourd'hui dans la famille
Poids niveau : moyenne des scores mastery des sous-skills de la famille
  (plus le score moyen est bas, plus la priorité est haute)
Poids temps écoulé : jours depuis la dernière session sur cette famille
```

### 4.2 Présentation des options à {learner_name}

L'agent présente les **3 familles avec le score de priorité le plus élevé** :

```
Voici les 3 options pour aujourd'hui :

1. **Analytical Thinking** ⚡ Priorité haute
   → 2 sous-skills avec review due (2.3 Tradeoff, 2.5 Quantitative)
   → Dernière session : il y a 5 jours

2. **Product Sense** 📊 Priorité moyenne
   → 1 sous-skill en Weak (1.2 Problem Identification)
   → Dernière session : il y a 3 jours

3. **Leadership** 🎯 Priorité moyenne
   → Pas travaillé depuis 8 jours
   → 4.5 Storytelling — ton pattern systémique à surveiller

Quelle famille pour aujourd'hui ?
```

### 4.3 Sélection de la question

Une fois la famille choisie :

```
1. Lire question_listing.json — filtrer les questions de la famille
2. Vérifier l'historique des 14 derniers jours dans session-log.json
3. Si question déjà vue récemment → générer une variante dans le même style
4. Choisir la question dont les sous-skills cibles correspondent
   aux sous-skills les plus faibles de la famille
5. Annoncer la question à {learner_name}
```

---

## 5. Système de maîtrise par sous-skill

### 5.1 Échelle de maîtrise (0–5 étoiles)

| Étoiles | Label | Définition |
|---------|-------|------------|
| ⭐ 0 | Non évalué | Sous-skill jamais testé |
| ⭐ 1 | Weak | Testé, résultat Weak systématique |
| ⭐ 2 | Weak → Good | Progressant, mais pas encore stable |
| ⭐ 3 | Good | Résultat Good stable sur 2 sessions consécutives |
| ⭐ 4 | Good → Excellent | Proche de la maîtrise, quelques failles |
| ⭐ 5 | Excellent | Résultat Excellent stable sur 2 sessions consécutives |

### 5.2 Règle de progression

Un sous-skill ne monte d'étoile que si le score est atteint
**2 fois consécutives** — pour éviter les faux positifs.

Un sous-skill redescend d'une étoile si un résultat Weak apparaît
après avoir été à Good ou Excellent (régression détectée).

### 5.3 Seuils cibles

| Milestone | Définition | Deadline cible |
|-----------|------------|----------------|
| Baseline | Tous les sous-skills évalués au moins une fois | Semaine 1 |
| Foundation | Tous les sous-skills ≥ ⭐ 2 | Semaine 4 |
| Compétent | Tous les sous-skills ≥ ⭐ 3 (Good stable) | Juin 2026 |
| Confiant | ≥ 5 sous-skills à ⭐ 5 (Excellent) | Juillet 2026 |

---

## 6. Suivi des patterns d'erreurs

### 6.1 Structure de mistakes-db.json

```json
{
  "patterns": [
    {
      "id": "pattern-001",
      "label": "Storytelling systémique",
      "description": "Commence par le contexte macro avant l'enjeu concret",
      "sub_skills_affected": ["4.5"],
      "occurrences": 3,
      "last_seen": "2026-03-01",
      "sessions": ["session-001", "session-004", "session-007"]
    }
  ]
}
```

### 6.2 Règle d'alerte pattern

Si un pattern apparaît **3 fois ou plus**, l'agent le signale
explicitement dans le feedback et en début de session suivante :

```
⚠️ Pattern récurrent détecté : "Storytelling systémique"
→ Tu as tendance à commencer par le contexte macro avant l'enjeu.
→ Objectif de cette session : commencer par l'enjeu, contexte en 2 phrases max.
```

---

## 7. Gamification et motivation

### 7.1 Streak

- Le streak compte les **jours consécutifs avec au moins une session complète**
- Affiché à chaque début de session
- Milestone streak : 7j 🔥, 14j 🔥🔥, 30j 🏆

### 7.2 Célébrations milestones

| Événement | Message |
|-----------|---------|
| Premier Excellent | "Premier Excellent sur [sous-skill] 🎯 — c'est ancré." |
| Weak → Good stable | "2 Good consécutifs sur [sous-skill] ✅ — plus jamais Weak sur ça." |
| Good → Excellent stable | "[Sous-skill] maîtrisé 🏆 — on passe à autre chose." |
| Toute une famille ≥ Good | "Famille [X] solide — tu passerais ce test aujourd'hui." |
| Milestone streak 7j | "7 jours de suite 🔥 — la progression est visible dans les données." |

### 7.3 Visualisation de progression

À chaque `/progress`, afficher :

```
## Progression — [Date]

Streak actuel : X jours 🔥

### Maîtrise par famille

Famille 1 — Product Sense
  Transversal  ████░░ ⭐3 Good
  1.1          ██░░░░ ⭐1 Weak
  1.2          ███░░░ ⭐2 Progressant
  1.3          ████░░ ⭐3 Good

Famille 2 — Analytical Thinking
  [...]

### Tendance globale
Sessions ce mois : X
Score moyen : X.X / 5
Sous-skills ≥ Good : X / 20
Sous-skills Excellent : X / 20

### Prochain milestone
[Milestone le plus proche + ce qu'il faut pour l'atteindre]
```

---

## 8. Utilisation de question_listing.json

### 8.1 Structure attendue du fichier

```json
{
  "_meta": { "families": ["product-sense", "analytical-thinking", "technical-ai", "leadership"], "reuse_rule_days": 14 },
  "questions": [
    {
      "id": "ps001",
      "family": "product-sense",
      "mode": "situational",
      "difficulty": "medium",
      "text": "You're a PM at Spotify. How would you improve the experience for podcast listeners?",
      "target_skills": ["transversal", "1.1", "1.2", "1.3"],
      "notes": "Notes internes pour l'agent — pièges, angles d'attaque."
    }
  ]
}
```

### 8.2 Sélection d'une question

```
1. Filtrer par famille sélectionnée
2. Filtrer par difficulté appropriée au niveau actuel de {learner_name}
   (si moyenne des sous-skills ≤ ⭐2 → difficulty="easy" ou "medium")
   (si moyenne des sous-skills ≥ ⭐3 → difficulty="medium" ou "hard")
3. Exclure les questions vues dans les 14 derniers jours
4. Parmi les questions restantes, choisir celle dont les target_skills
   correspondent aux sous-skills les plus faibles de la famille
```

### 8.3 Génération de variante

Si aucune question disponible (toutes vues récemment), générer une variante :

```
Prompt interne :
"Génère une question de [famille] au niveau [difficulté],
dans le style des questions de Lenny's Newsletter / Exponent.
La question doit couvrir les sous-skills [liste].
Elle doit être centrée sur un produit tech contemporain
que {learner_name} n'a pas encore utilisé comme exemple récemment."
```

---

## 9. Règles de comportement de l'agent pendant l'interview

### 9.1 Pendant la phase de réponse initiale

- **Ne pas interrompre** {learner_name} pendant qu'il prépare
- **Ne pas souffler** d'indices spontanément — attendre qu'il les demande
- **Ne pas commenter** la réponse au fil de l'eau — attendre la fin
- **Si {learner_name} tape `hint` ou `/hint`** : appliquer le système d'indices
  adaptatif défini dans `/practice` (hint_level basé sur les stars des target_skills,
  contenu contextuel ancré dans la question et la section en cours)

### 9.2 Pendant la phase de relance (5 questions max)

- Rester dans le rôle de l'interviewer — pas du coach
- **Ne pas valider** explicitement les bonnes réponses pendant l'interview
  (un vrai interviewer reste neutre)
- **Challenger** les points faibles identifiés dans la réponse initiale
- **Creuser** les sous-skills insuffisamment évalués
- **Clore** le test dès que les sous-skills cibles sont évalués —
  ne pas traîner pour "avoir l'air complet"

### 9.3 Pendant le feedback

- Sortir du rôle d'interviewer — redevenir coach
- Être direct : nommer les sous-skills faibles sans euphémisme
- Référencer pm_skills.md pour chaque évaluation, et en priorité les articles
  sourcés selon la famille : `references/ben_erez_product_sense.md` (F1),
  `references/ben_erez_analytical_thinking.md` (F2),
  `references/amit_mutreja_technical_pm.md` (F3)
- Montrer l'exemple Excellent systématiquement pour les scores Weak
- Identifier le pattern récurrent si applicable
- Terminer par **une seule priorité** — pas une liste de 5 choses à améliorer

---

*Fin de LEARNING_SYSTEM.md*
