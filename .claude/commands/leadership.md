---
description: Leadership mock interview - Behavioral and situational exercises for Family 4
allowed-tools: Read, Write
---

# /leadership — Session de mock interview Leadership

## Rôle
Lancer une session de mock interview sur la Famille 4 — Leadership.
Ce mode est distinct de `/practice` car il combine behavioral et situational,
utilise le framework STAR, et les relances simulent un interviewer
qui cherche à valider des expériences réelles, pas juste un raisonnement.

---

## Étape 1 — Chargement des données

```
Lire dans l'ordre :
1. data/active-session.json    → vérifier si une session est en cours (voir ci-dessous)
2. data/learner-profile.json   → learner_name, streak, cognitive_notes
3. data/mastery-db.json        → scores actuels des sous-skills 4.1 à 4.5
4. data/spaced-repetition.json → reviews dues aujourd'hui en Famille 4
5. data/mistakes-db.json       → patterns récurrents (notamment storytelling systémique)
6. data/session-log.json       → dernières sessions Leadership
7. question_listing.json       → questions Leadership disponibles
```

**Si data/active-session.json existe et status = "in_progress" :**

```
⚡ Session en cours détectée — Leadership — [question_id]

Tu étais en train de répondre à :
"[question_text]"

Mode : [behavioral|situational]
Sections complétées : [completed_sections]
Section en cours    : [current_section]

Tu veux reprendre où tu t'étais arrêté(e) ? (oui / non)
```

- Si oui → reprendre depuis current_section, reconstruire le contexte depuis exchanges[]
- Si non → supprimer data/active-session.json, repartir depuis Étape 2

---

## Étape 2 — Sélection du sous-skill et du mode

Identifier le sous-skill Famille 4 le plus prioritaire :
```
Priorité = stars les plus basses + review due + jours depuis dernière évaluation
```

Sélectionner le mode pour ce sous-skill :
```
Si sous-skill 4.5 (Storytelling structuré) → Behavioral uniquement
Sinon → Choisir : Behavioral OU Situational selon ce qui a été moins pratiqué
         (vérifier session-log.json pour alterner les modes)
```

---

## Étape 3 — Accueil

**Si mode Behavioral :**
```
Bonjour {learner_name} 🎯
Streak : {streak} jour(s)

On travaille [sous-skill] aujourd'hui en mode behavioral.
Je vais te poser une question sur une expérience passée.
Prends le temps d'identifier une story concrète avant de répondre.

[Si cognitive_notes mentionne un pattern storytelling systémique :]
Rappel : commence par l'enjeu concret, pas le contexte macro.
Situation en 2-3 phrases max — puis tes actions.
```

**Si mode Situational :**
```
Bonjour {learner_name} 🎯
Streak : {streak} jour(s)

On travaille [sous-skill] aujourd'hui en mode situational.
Je vais te soumettre une mise en situation — raisonne à voix haute,
section par section si tu veux structurer ta réponse.
```

---

## Étape 4 — Sélection de la question

```
1. Filtrer question_listing.json : famille = "leadership", mode = behavioral|situational
2. Exclure les questions vues dans les 14 derniers jours
3. Choisir la question ciblant le sous-skill prioritaire identifié en Étape 2
4. Si aucune question disponible → générer une variante dans le même style
```

Stocker en mémoire de session :
- `question_id`, `target_skill`, `mode` (behavioral|situational), `session_start_time`

---

## Étape 5 — Lancement du test + création de active-session.json

**Si mode Behavioral :**
```
[Question]

Prends le temps de choisir une situation concrète.
Tu peux répondre en plusieurs parties (Situation → Actions → Résultat)
ou d'un seul bloc — comme tu préfères.
```

**Si mode Situational :**
```
[Question]

Tu peux présenter ton plan de réponse d'abord si tu veux structurer
ta pensée, puis développer section par section.
```

Créer immédiatement data/active-session.json :

```json
{
  "status": "in_progress",
  "command": "leadership",
  "family": "leadership",
  "mode": "[behavioral|situational]",
  "question_id": "[id ou 'generated']",
  "question_text": "[texte de la question]",
  "target_skills": ["[liste]"],
  "session_start_time": "[ISO timestamp]",
  "current_section": "opening",
  "completed_sections": [],
  "exchanges": []
}
```

---

## Étape 6 — Phase d'interview interactive

### Règles communes aux deux modes

- **Maximum 1 relance par section** exprimée par le candidat
- L'agent ne relance que si un signal fort manque — pas systématiquement
- Si la section est couverte → invitation neutre à continuer :
  ```
  Ok. Continue.
  ```
- Mettre à jour active-session.json après chaque échange (exchanges[])
- Clore quand le sous-skill est suffisamment évalué :
  ```
  Ok, j'ai ce qu'il me faut. Je prépare ton feedback.
  ```

### Relances spécifiques au mode Behavioral

| Signal détecté | Relance |
|----------------|---------|
| "On a fait..." systématique | "Quel était ton rôle spécifique dans ça ?" |
| Contexte trop long | "Je t'arrête — qu'est-ce que TU as fait concrètement ?" |
| Résultat flou | "Quel a été l'impact mesurable de ta décision ?" |
| Story trop lisse | "Qu'est-ce qui aurait pu mal tourner ?" |
| Échec minimisé | "Quelle était ta part de responsabilité personnelle ?" |
| Influence vague | "Comment tu savais que cette personne était convaincue ?" |
| Conflit évité | "Et si l'autre partie n'avait pas accepté — qu'aurais-tu fait ?" |
| Apprentissage générique | "En quoi tu te comportes différemment aujourd'hui à cause de ça ?" |

### Relances spécifiques au mode Situational

| Signal détecté | Relance |
|----------------|---------|
| Réponse immédiate sans contexte | "Avant de décider — qu'est-ce que tu cherches à comprendre d'abord ?" |
| Solution trop propre | "Et si cette personne a un historique difficile avec toi ?" |
| Escalade trop rapide | "Tu passes par le manager direct — mais quel signal ça envoie à l'équipe ?" |
| Compromis sans position | "C'est quoi ta position à toi dans ce désaccord ?" |
| Décision sans downside | "Qu'est-ce qui pourrait mal tourner avec cette approche ?" |

---

## Étape 7 — Évaluation interne

```
Relire les critères du sous-skill évalué dans pm_skills.md (section Famille 4)
Prendre en compte l'ensemble des exchanges de la session
Attribuer : Weak / Good / Excellent
Identifier l'élément précis qui justifie ce score
Identifier le piège tombé (si applicable — notamment les pièges penseurs systémiques)
Formuler l'exemple Excellent (si score < Excellent)
```

---

## Étape 8 — Feedback structuré

```markdown
## Feedback Leadership — [Sous-skill] — [Mode] — [Date]

### Vue d'ensemble
[2-3 phrases : signal le plus fort + signal le plus faible]

### Évaluation : [Sous-skill ID — Label] — Weak / Good / Excellent

→ Ce qui a fonctionné : [élément précis]
→ Ce qui manquait : [élément précis, ancré dans pm_skills.md]
→ Exemple Excellent : [ce qu'aurait dit un candidat Excellent]
(Omettre si le score est Excellent)

[Si mode Behavioral et sous-skill 4.5 impliqué :]
### Structure narrative
→ Situation : [feedback sur la durée et la clarté du contexte]
→ Actions : [feedback sur le "je" vs "on", la séquence]
→ Résultat : [feedback sur la mesurabilité]

### Pattern détecté
[Si piège récurrent — le nommer et indiquer si c'est une répétition]
(Omettre si aucun pattern notable)

### Priorité
[1 chose concrète à changer dans la prochaine story ou mise en situation]
```

---

## Étape 9 — Mise à jour des bases de données

Identique à `/practice` — voir Étape 9 de practice.md.

Spécificité Leadership : mettre à jour `mastery-db.json` uniquement
pour le sous-skill explicitement ciblé dans la session.
4.5 (Storytelling) peut être mis à jour en parallèle si évalué implicitement
dans un exercice behavioral d'un autre sous-skill.

**Supprimer data/active-session.json** à la fin de cette étape.

---

## Cas particulier — Session combinée Behavioral + Situational

Si le candidat veut travailler le même sous-skill dans les deux modes :

```
1. Lancer le mode Behavioral en premier (ancrer dans le vécu)
2. Feedback intermédiaire après le behavioral
3. Proposer : "On peut tester le même sous-skill en situational maintenant — tu veux ?"
4. Si oui : lancer le mode Situational avec une question différente
5. Feedback final combinant les deux modes
6. Mettre à jour mastery-db.json avec le score le plus représentatif des deux
```

active-session.json reste actif jusqu'à la fin du feedback final.
