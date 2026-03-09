---
description: Focus session on the 3 weakest sub-skills - Intensive targeted practice
allowed-tools: Read, Write
---

# /weak — Session intensive sur les sous-skills les plus faibles

## Rôle
Identifier les 3 sous-skills avec les scores les plus bas et lancer
une session de mock interview ciblée dessus. Commande à utiliser
quand le candidat veut travailler ses points faibles directement,
sans passer par la sélection adaptative de `/practice`.

---

## Étape 1 — Chargement des données

```
Lire dans l'ordre :
1. data/learner-profile.json → learner_name, streak
2. data/mastery-db.json → stars par sous-skill
3. data/mistakes-db.json → patterns récurrents
4. data/session-log.json → dernières sessions
```

---

## Étape 2 — Identification des 3 sous-skills les plus faibles

```
Filtrer mastery-db.json :
  - Exclure les sous-skills jamais évalués (stars = 0, sessions_count = 0)
    sauf si TOUS les sous-skills sont à 0 (début de parcours)
  - Trier par stars croissantes
  - En cas d'égalité : prioriser le sous-skill le plus ancien (last_evaluated)

Résultat : top 3 sous-skills avec stars les plus basses
```

**Cas particulier — début de parcours (tout à 0) :**
```
Sélectionner les 3 premiers sous-skills du plan de progression standard :
  transversal → 1.1 → 1.2
```

---

## Étape 3 — Annonce

```
{learner_name}, voici tes 3 sous-skills prioritaires :

1. [Sous-skill ID — Label] — {stars}⭐
   {Si pattern récurrent associé : "⚠️ Pattern récurrent détecté : [label]"}

2. [Sous-skill ID — Label] — {stars}⭐

3. [Sous-skill ID — Label] — {stars}⭐

On peut les travailler dans une session combinée ou les aborder séparément.

Comment tu veux procéder ?
  A — Session combinée (les 3 dans un même test produit si possible)
  B — Un sous-skill à la fois (3 sessions courtes)
```

Attendre le choix du candidat.

---

## Étape 4A — Session combinée

Si les 3 sous-skills appartiennent à la même famille :
```
→ Lancer un test produit complet sur cette famille (flow identique à /practice)
  avec les 3 sous-skills comme target_skills explicites
```

Si les 3 sous-skills appartiennent à des familles différentes :
```
→ Choisir la famille qui contient le sous-skill le plus faible
→ Lancer le test sur cette famille
→ Informer le candidat que les 2 autres seront couverts dans les sessions suivantes
```

---

## Étape 4B — Un sous-skill à la fois

Pour chaque sous-skill dans la liste des 3 :

```
1. Annoncer le sous-skill travaillé
2. Rappeler brièvement ce que teste ce sous-skill (1 phrase)
3. Si pattern récurrent associé → le rappeler avant la question
4. Lancer une question ciblée (format révision — voir /review Étape 4.2)
5. Max 3 relances (plus qu'une révision standard, moins qu'un test complet)
6. Feedback immédiat
7. Proposer de continuer avec le sous-skill suivant
```

**Rappel du pattern avant la question :**
```
Rappel avant de commencer : sur ce sous-skill, tu as tendance à [pattern].
Garde ça en tête dans ta réponse.

[Question]
```

---

## Étape 5 — Bilan

```
## Bilan /weak — [Date]

Sous-skills travaillés :
1. [Label] : {score obtenu} {flèche si amélioration vs score précédent}
2. [Label] : {score obtenu}
3. [Label] : {score obtenu}

{Si amélioration sur au moins un sous-skill :}
✅ Progression détectée sur [sous-skill] — continuez comme ça.

{Si Weak sur tous :}
Ces sous-skills résistent. Ce n'est pas un problème de capacité —
c'est un problème d'exposition. Reviens dessus demain.

Prochaine session recommandée : /practice ou /review
```

---

## Étape 6 — Mise à jour des bases de données

Identique à `/practice` — voir Étape 9 de practice.md.
