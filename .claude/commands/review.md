---
description: Spaced repetition review session - Practice sub-skills with reviews due today
allowed-tools: Read, Write
---

# /review — Session de révision spaced repetition

## Rôle
Traiter les sous-skills dont la review est due aujourd'hui selon l'algorithme SM-2.
Contrairement à `/practice` qui lance un test produit complet, `/review` cible
directement les sous-skills en retard avec des questions courtes et ciblées.

---

## Étape 1 — Chargement des données

```
Lire dans l'ordre :
1. data/learner-profile.json → learner_name, streak
2. data/spaced-repetition.json → next_review par sous-skill
3. data/mastery-db.json → stars et derniers scores par sous-skill
4. question_listing.json → questions disponibles par famille
```

---

## Étape 2 — Identification des reviews dues

```
Filtrer spaced-repetition.json :
  sous-skills où next_review <= date du jour

Trier par priorité :
  1. Sous-skills Weak (stars <= 1) en premier
  2. Ensuite par ancienneté de la review (les plus en retard d'abord)
```

---

## Étape 3 — Annonce

**Si aucune review due :**
```
Aucune review due aujourd'hui, {learner_name}.

Sous-skill le plus proche : [label] dans {X} jour(s).

Tape /practice pour une nouvelle session si tu veux avancer.
```

**Si reviews dues :**
```
{learner_name}, {X} sous-skill(s) à revoir aujourd'hui :

{liste des sous-skills avec leur niveau actuel}

On les traite un par un. Prêt(e) ?
```

Attendre confirmation avant de démarrer.

---

## Étape 4 — Flow de révision par sous-skill

Pour chaque sous-skill dans la file de révision :

### 4.1 Sélection de la question

```
Choisir une question dans question_listing.json ciblant ce sous-skill
Exclure les questions vues dans les 7 derniers jours pour ce sous-skill
Si aucune disponible → générer une question ciblée sur ce sous-skill uniquement
```

### 4.2 Format de la question

Les questions de révision sont plus courtes qu'un test complet.
Elles ciblent **un seul sous-skill** — pas un test de famille entière.

```
Révision — [Sous-skill ID : Label]

[Question ciblée sur ce sous-skill]
```

Attendre la réponse. Pas de temps de préparation annoncé —
les révisions sont plus spontanées qu'un test produit complet.

### 4.3 Relances (max 2 pour une révision)

Une révision n'est pas un test complet — 2 relances maximum.
L'objectif est de vérifier rapidement si le sous-skill est ancré.

### 4.4 Feedback immédiat

```
[Sous-skill] : Weak / Good / Excellent

→ [1-2 phrases de justification]
→ [Exemple Excellent si score < Excellent — court, 2-3 phrases max]
```

### 4.5 Transition vers le sous-skill suivant

```
[Si sous-skills restants dans la file :]
Sous-skill suivant : [label]. On continue ?

[Si dernier sous-skill :]
Toutes les reviews du jour sont traitées.
```

---

## Étape 5 — Bilan de session

```
## Bilan révisions — [Date]

Sous-skills révisés : {X}
{liste avec score obtenu}

Reviews mises à jour :
{liste des prochaines dates de review par sous-skill}

{Si amélioration détectée :}
✅ Progression sur [sous-skill] : {ancien score} → {nouveau score}
```

---

## Étape 6 — Mise à jour des bases de données

Identique à `/practice` — voir Étape 9 de practice.md.

Spécificité `/review` :
- Mettre à jour uniquement les sous-skills effectivement révisés dans la session
- Si le candidat abandonne en cours de session, mettre à jour uniquement
  les sous-skills déjà traités — pas ceux non atteints
