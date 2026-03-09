---
description: Display progression dashboard - scores, streaks, milestones and next priorities
allowed-tools: Read
---

# /progress — Tableau de bord de progression

## Rôle
Afficher une vue complète et lisible de la progression du candidat :
maîtrise par sous-skill, tendances, streak, milestones atteints et prochaine priorité.
Commande en lecture seule — aucune mise à jour des bases de données.

---

## Étape 1 — Chargement des données

```
Lire dans l'ordre :
1. data/learner-profile.json → learner_name, streak, target_date, target_location
2. data/mastery-db.json → stars par sous-skill
3. data/progress-db.json → stats globales, family_stats, milestones_reached
4. data/spaced-repetition.json → reviews dues aujourd'hui
5. data/mistakes-db.json → patterns récurrents (occurrences >= 2)
```

---

## Étape 2 — Affichage du dashboard

```markdown
# Progression — {learner_name} — [Date du jour]

## Streak
🔥 {streak} jour(s) consécutifs
Sessions ce mois : {total_sessions_this_month}
Tests complétés au total : {total_tests_completed}

---

## Maîtrise par famille

### Transversal — Ouverture structurée & Mission Statement
  {barre_progression} {stars}⭐ — {label: Non évalué|Weak|Progressant|Good|Excellent}

### Famille 1 — Product Sense
  1.1 Segmentation               {barre} {stars}⭐
  1.2 Problem Identification     {barre} {stars}⭐
  1.3 Solution Development       {barre} {stars}⭐
  Moyenne famille : {avg}/5

### Famille 2 — Analytical Thinking
  2.1 Ecosystem Metrics          {barre} {stars}⭐
  2.2 Goal-Setting               {barre} {stars}⭐
  2.3 Tradeoff Evaluation        {barre} {stars}⭐
  2.4 Debugging / RCA            {barre} {stars}⭐
  2.5 Quantitative Reasoning     {barre} {stars}⭐
  Moyenne famille : {avg}/5

### Famille 3 — Technical AI
  3.1 LLM Fundamentals           {barre} {stars}⭐
  3.2 RAG & Context Engineering  {barre} {stars}⭐
  3.3 AI Evals & Observabilité   {barre} {stars}⭐
  3.4 Agent Design & Deployment  {barre} {stars}⭐
  3.5 High-Stakes Agent Reasoning {barre} {stars}⭐
  3.6 AI Product Design          {barre} {stars}⭐
  Moyenne famille : {avg}/5

### Famille 4 — Leadership
  4.1 Influence sans autorité    {barre} {stars}⭐
  4.2 Gestion de conflits        {barre} {stars}⭐
  4.3 Décision sous incertitude  {barre} {stars}⭐
  4.4 Échec & apprentissage      {barre} {stars}⭐
  4.5 Storytelling structuré     {barre} {stars}⭐
  Moyenne famille : {avg}/5

---

## Sous-skills maîtrisés (⭐ 5)
{liste ou "Aucun pour l'instant — ça viendra."}

## Sous-skills à travailler en priorité
{top 3 sous-skills avec stars les plus basses et review due}

---

## Milestones
{liste des milestones atteints avec date}
{prochain milestone : label + ce qu'il faut pour l'atteindre}

---

## Patterns récurrents détectés
{liste des patterns avec occurrences >= 2, ou "Aucun pattern récurrent identifié."}

---

## Reviews dues aujourd'hui
{nombre} sous-skill(s) à revoir selon le spaced repetition
→ Tape /review pour les traiter
```

---

## Format des barres de progression

Utiliser des blocs Unicode pour représenter visuellement les étoiles :

```
0 étoile  : ░░░░░
1 étoile  : █░░░░
2 étoiles : ██░░░
3 étoiles : ███░░
4 étoiles : ████░
5 étoiles : █████
```

---

## Notes d'implémentation

- Si un sous-skill n'a jamais été évalué (stars = 0), afficher "—" à la place de la barre
- Ne pas afficher les fichiers JSON bruts — uniquement le dashboard formaté
- Si target_date est renseigné, afficher le nombre de jours restants
  en bas du dashboard : "Objectif : {target_location} — {X} jours restants"
