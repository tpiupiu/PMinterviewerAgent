---
description: Interactive onboarding - Set up your personalized PM interview coaching profile
allowed-tools: Read, Write
---

# PM Interview Coach — Setup

## Rôle
Initialiser l'environnement complet du PM Interview Coach pour un nouveau candidat.
Cette commande crée tous les fichiers `/data/` nécessaires au fonctionnement de l'agent
à travers un échange conversationnel.

---

## Étape 1 — Vérification préalable

Vérifier si `/data/learner-profile.json` existe déjà.

Si oui :
```
Un profil existe déjà pour {learner_name}.
Veux-tu le réinitialiser complètement ? Toute ta progression sera perdue.
Tape "RESET" pour confirmer, ou /practice pour reprendre là où tu en étais.
```

Si non : démarrer le workflow ci-dessous.

---

## Étape 2 — Collecte des informations

Poser les questions **une par une**. Attendre la réponse avant de passer à la suivante.

**Question 1 : Prénom**
```
Bienvenue dans le PM Interview Coach 🎯

Je vais te poser 3 questions rapides pour configurer ton espace d'entraînement.

Première question : comment tu t'appelles ?
```
→ Stocker : `learner_name`

---

**Question 2 : Date cible**
```
Bonjour {learner_name} !

Pour calibrer le rythme de ta préparation :
quelle est ta date cible pour être prêt(e) en entretien ?

(Exemple : "juillet 2026", "dans 3 mois")
```
→ Convertir en date ISO si possible, sinon stocker la valeur brute
→ Stocker : `target_date`

---

**Question 3 : Marché cible**
```
Dans quelle ville ou région cherches-tu des opportunités ?
```
→ Stocker : `target_location`

---

## Étape 3 — Confirmation et création

```
Parfait. Voici ton profil :

- Nom : {learner_name}
- Date cible : {target_date}
- Marché cible : {target_location}

Je crée ton espace d'entraînement...
```

Créer tous les fichiers `/data/` (voir section Fichiers ci-dessous).

```
✅ Profil créé
✅ Base de progression initialisée (20 sous-skills à 0 étoile)
✅ Système de révision prêt
✅ Historique de sessions vide

Tout est prêt, {learner_name}.

Tape /practice pour ta première session
ou /progress pour voir ton tableau de bord de départ.
```

---

## Fichiers à créer

### `data/learner-profile.json`

```json
{
  "learner_name": "",
  "target_date": "",
  "target_location": "",
  "setup_date": "",
  "streak": 0,
  "last_session_date": null,
  "total_sessions": 0,
  "cognitive_notes": ""
}
```

---

### `data/mastery-db.json`

```json
{
  "last_updated": "",
  "sub_skills": {
    "transversal": { "label": "Ouverture structurée & Mission Statement", "family": "transversal", "stars": 0, "consecutive_good": 0, "consecutive_excellent": 0, "sessions_count": 0, "last_evaluated": null },
    "1.1": { "label": "Segmentation", "family": "1", "stars": 0, "consecutive_good": 0, "consecutive_excellent": 0, "sessions_count": 0, "last_evaluated": null },
    "1.2": { "label": "Problem Identification", "family": "1", "stars": 0, "consecutive_good": 0, "consecutive_excellent": 0, "sessions_count": 0, "last_evaluated": null },
    "1.3": { "label": "Solution Development", "family": "1", "stars": 0, "consecutive_good": 0, "consecutive_excellent": 0, "sessions_count": 0, "last_evaluated": null },
    "2.1": { "label": "Ecosystem Metrics Framework", "family": "2", "stars": 0, "consecutive_good": 0, "consecutive_excellent": 0, "sessions_count": 0, "last_evaluated": null },
    "2.2": { "label": "Goal-Setting (Altitude Shift)", "family": "2", "stars": 0, "consecutive_good": 0, "consecutive_excellent": 0, "sessions_count": 0, "last_evaluated": null },
    "2.3": { "label": "Tradeoff Evaluation", "family": "2", "stars": 0, "consecutive_good": 0, "consecutive_excellent": 0, "sessions_count": 0, "last_evaluated": null },
    "2.4": { "label": "Debugging / Root Cause Analysis", "family": "2", "stars": 0, "consecutive_good": 0, "consecutive_excellent": 0, "sessions_count": 0, "last_evaluated": null },
    "2.5": { "label": "Quantitative Reasoning", "family": "2", "stars": 0, "consecutive_good": 0, "consecutive_excellent": 0, "sessions_count": 0, "last_evaluated": null },
    "3.1": { "label": "LLM Fundamentals", "family": "3", "stars": 0, "consecutive_good": 0, "consecutive_excellent": 0, "sessions_count": 0, "last_evaluated": null },
    "3.2": { "label": "RAG & Context Engineering", "family": "3", "stars": 0, "consecutive_good": 0, "consecutive_excellent": 0, "sessions_count": 0, "last_evaluated": null },
    "3.3": { "label": "AI Evals & Observabilité", "family": "3", "stars": 0, "consecutive_good": 0, "consecutive_excellent": 0, "sessions_count": 0, "last_evaluated": null },
    "3.4": { "label": "Agent Design & Deployment", "family": "3", "stars": 0, "consecutive_good": 0, "consecutive_excellent": 0, "sessions_count": 0, "last_evaluated": null },
    "3.5": { "label": "High-Stakes Agent Reasoning", "family": "3", "stars": 0, "consecutive_good": 0, "consecutive_excellent": 0, "sessions_count": 0, "last_evaluated": null },
    "3.6": { "label": "AI Product Design", "family": "3", "stars": 0, "consecutive_good": 0, "consecutive_excellent": 0, "sessions_count": 0, "last_evaluated": null },
    "4.1": { "label": "Influence sans autorité", "family": "4", "stars": 0, "consecutive_good": 0, "consecutive_excellent": 0, "sessions_count": 0, "last_evaluated": null },
    "4.2": { "label": "Gestion de conflits & alignement", "family": "4", "stars": 0, "consecutive_good": 0, "consecutive_excellent": 0, "sessions_count": 0, "last_evaluated": null },
    "4.3": { "label": "Décision sous incertitude", "family": "4", "stars": 0, "consecutive_good": 0, "consecutive_excellent": 0, "sessions_count": 0, "last_evaluated": null },
    "4.4": { "label": "Échec & apprentissage", "family": "4", "stars": 0, "consecutive_good": 0, "consecutive_excellent": 0, "sessions_count": 0, "last_evaluated": null },
    "4.5": { "label": "Storytelling structuré", "family": "4", "stars": 0, "consecutive_good": 0, "consecutive_excellent": 0, "sessions_count": 0, "last_evaluated": null }
  }
}
```

---

### `data/spaced-repetition.json`

```json
{
  "last_updated": "",
  "sub_skills": {
    "transversal": { "interval": 1, "easiness_factor": 2.5, "next_review": "", "repetitions": 0 },
    "1.1": { "interval": 1, "easiness_factor": 2.5, "next_review": "", "repetitions": 0 },
    "1.2": { "interval": 1, "easiness_factor": 2.5, "next_review": "", "repetitions": 0 },
    "1.3": { "interval": 1, "easiness_factor": 2.5, "next_review": "", "repetitions": 0 },
    "2.1": { "interval": 1, "easiness_factor": 2.5, "next_review": "", "repetitions": 0 },
    "2.2": { "interval": 1, "easiness_factor": 2.5, "next_review": "", "repetitions": 0 },
    "2.3": { "interval": 1, "easiness_factor": 2.5, "next_review": "", "repetitions": 0 },
    "2.4": { "interval": 1, "easiness_factor": 2.5, "next_review": "", "repetitions": 0 },
    "2.5": { "interval": 1, "easiness_factor": 2.5, "next_review": "", "repetitions": 0 },
    "3.1": { "interval": 1, "easiness_factor": 2.5, "next_review": "", "repetitions": 0 },
    "3.2": { "interval": 1, "easiness_factor": 2.5, "next_review": "", "repetitions": 0 },
    "3.3": { "interval": 1, "easiness_factor": 2.5, "next_review": "", "repetitions": 0 },
    "3.4": { "interval": 1, "easiness_factor": 2.5, "next_review": "", "repetitions": 0 },
    "3.5": { "interval": 1, "easiness_factor": 2.5, "next_review": "", "repetitions": 0 },
    "3.6": { "interval": 1, "easiness_factor": 2.5, "next_review": "", "repetitions": 0 },
    "4.1": { "interval": 1, "easiness_factor": 2.5, "next_review": "", "repetitions": 0 },
    "4.2": { "interval": 1, "easiness_factor": 2.5, "next_review": "", "repetitions": 0 },
    "4.3": { "interval": 1, "easiness_factor": 2.5, "next_review": "", "repetitions": 0 },
    "4.4": { "interval": 1, "easiness_factor": 2.5, "next_review": "", "repetitions": 0 },
    "4.5": { "interval": 1, "easiness_factor": 2.5, "next_review": "", "repetitions": 0 }
  }
}
```

---

### `data/progress-db.json`

```json
{
  "last_updated": "",
  "total_sessions": 0,
  "total_tests_completed": 0,
  "current_streak": 0,
  "longest_streak": 0,
  "scores_history": [],
  "family_stats": {
    "transversal": { "sessions": 0, "avg_score": null, "last_session": null },
    "1": { "sessions": 0, "avg_score": null, "last_session": null },
    "2": { "sessions": 0, "avg_score": null, "last_session": null },
    "3": { "sessions": 0, "avg_score": null, "last_session": null },
    "4": { "sessions": 0, "avg_score": null, "last_session": null }
  },
  "milestones_reached": []
}
```

---

### `data/mistakes-db.json`

```json
{
  "last_updated": "",
  "patterns": []
}
```

---

### `data/session-log.json`

```json
{
  "last_updated": "",
  "sessions": []
}
```

---

### `data/active-session.json`

Ce fichier n'est **pas créé au setup** — il est créé dynamiquement par `/practice`
et `/leadership` au moment où une session démarre (Étape 5 de ces commandes).

Il est supprimé automatiquement à la fin de chaque session (après l'Étape 9).

**Structure de référence — `/practice` :**

```json
{
  "status": "in_progress",
  "command": "practice",
  "family": "product-sense",
  "question_id": "ps001",
  "question_text": "Texte exact de la question posée.",
  "target_skills": ["transversal", "1.1", "1.2", "1.3"],
  "session_start_time": "2026-03-10T14:00:00Z",
  "plan_validated": false,
  "sections": [],
  "current_section": "plan",
  "completed_sections": [],
  "exchanges": [
    {
      "section": "plan",
      "candidate_response": "Texte verbatim de la réponse du candidat.",
      "agent_challenge": null,
      "candidate_followup": null,
      "section_status": "completed"
    },
    {
      "section": "segmentation",
      "candidate_response": "Texte verbatim de la réponse du candidat sur cette section.",
      "agent_challenge": "Sur quel segment tu te concentres — et pourquoi pas les autres ?",
      "candidate_followup": "Texte verbatim de la réponse du candidat à la relance.",
      "section_status": "completed"
    },
    {
      "section": "problem_identification",
      "candidate_response": "Texte verbatim en cours — section non encore clôturée.",
      "agent_challenge": null,
      "candidate_followup": null,
      "section_status": "in_progress"
    }
  ]
}
```

**Structure de référence — `/leadership` :**

```json
{
  "status": "in_progress",
  "command": "leadership",
  "family": "leadership",
  "mode": "behavioral",
  "question_id": "ldr001",
  "question_text": "Texte exact de la question posée.",
  "target_skills": ["4.1", "4.5"],
  "session_start_time": "2026-03-10T14:00:00Z",
  "current_section": "situation",
  "completed_sections": [],
  "exchanges": [
    {
      "section": "situation",
      "candidate_response": "Texte verbatim de la réponse du candidat.",
      "agent_challenge": "Quel était ton rôle spécifique dans ça ?",
      "candidate_followup": "Texte verbatim de la réponse à la relance.",
      "section_status": "completed"
    },
    {
      "section": "actions",
      "candidate_response": "Texte verbatim en cours.",
      "agent_challenge": null,
      "candidate_followup": null,
      "section_status": "in_progress"
    }
  ]
}
```

**Règles de mise à jour :**
- `candidate_response` : toujours le texte **verbatim** complet — jamais résumé
- `section_status` passe à `"completed"` quand le candidat clôt la section
- La section `"in_progress"` est toujours la dernière entrée dans `exchanges[]`
- Si la session est interrompue volontairement (`/practice` → "non" à la reprise) :
  mettre `"status": "abandoned"` avant de supprimer

---

## Notes d'implémentation

- Remplir tous les champs `""` et `last_updated` avec la date ISO du jour
- Créer le dossier `/results/` (vide) pour les rapports de session à venir
- Ne jamais créer `data/active-session.json` au setup — ce fichier est géré dynamiquement
- Si la création d'un fichier échoue, le signaler et réessayer avant de conclure
- Ne jamais afficher le JSON brut au candidat — uniquement les confirmations ✅
