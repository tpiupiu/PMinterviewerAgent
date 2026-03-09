# Librairie de Critères — Mock Tests PM AI
> Thomas Piussan — Préparation entretiens Senior PM / AI Product Builder
> Généré le : Mars 2026

---

## Contexte & Objectif

Ce document synthétise les critères d'évaluation calibrés à partir de sessions de mock tests réels.
Il sert de référence pour l'agent Claude Code chargé de générer et évaluer les tests d'entretien.

**Profil cible :** Senior PM avec forte composante technique / AI
**Marchés visés :** Scale-ups européennes, entreprises style Datadog
**Niveaux de difficulté :** 3 niveaux par module (Junior / Senior / Lead)

---

## MODULE 1 — Product Case

### Type de question
Mesure du succès, priorisation de features, stratégie produit, amélioration d'un produit existant.

### Exemples de questions réelles (Datadog / scale-ups EU)
- "On vient de lancer un nouveau produit de monitoring. Comment tu mesures le succès ?"
- "Tu es PM chez Kayak. Comment tu mesures le succès de la boîte ?"
- "Comment tu améliorerais Facebook Feed ?"
- "Tu dois prioriser 5 features avec des ressources limitées. Comment tu procèdes ?"

### Critères d'évaluation

| Critère | ❌ Junior (0 pt) | ✅ Senior (1 pt) | 🚀 Lead (2 pts) |
|---|---|---|---|
| **Contextualisation** | Plonge directement dans les métriques | Clarifie business model, pricing, objectif utilisateur avant de répondre | Identifie aussi les contraintes organisationnelles et le contexte marché |
| **North Star Metric** | Liste exhaustive de métriques sans choix | Choisit UNE métrique principale et la justifie | Articule la hiérarchie de métriques et les dépendances |
| **Leading vs Lagging** | Uniquement des lagging metrics (revenue, churn) | Identifie des leading metrics prédictives | Définit un système de métriques avec signaux d'alerte précoce |
| **Guardrails** | Ignore les effets de bord | Identifie au moins une contre-métrique à ne pas dégrader | Définit un tableau de bord complet succès + risques |
| **Temporalité** | Vague ("à terme", "après le lancement") | Timeframe précis par phase (J+30, J+90, J+180) | Roadmap de métriques évolutive selon la maturité du produit |
| **Pensée système** | Métrique isolée | Anticipe les effets de bord entre métriques | Modélise l'impact sur l'ensemble du funnel produit |

### Score d'évaluation
- **0-4 pts** : Niveau Junior — retravailler la structure de base
- **5-8 pts** : Niveau Senior — affiner North Star et guardrails
- **9-12 pts** : Niveau Lead — prêt pour des rôles Head of Product

### Pattern de faiblesse identifié chez Thomas
> ✅ Contextualisation forte  
> ✅ Leading vs Lagging bien maîtrisé  
> ⚠️ North Star Metric : tendance à lister sans choisir  
> ⚠️ Guardrails : absent dans la première itération  
> ⚠️ Timeframe : mentionné mais pas précisé  

---

## MODULE 2 — Technical AI PM

### Type de question
Architecture AI, choix technologiques LLM/RAG, trade-offs techniques, évaluation d'un système AI.

### Exemples de questions réelles
- "LLM off-the-shelf vs RAG — comment tu décides ?"
- "Quand utilises-tu du rule-based vs un modèle ML vs un LLM ?"
- "Comment tu mesures la qualité d'un système RAG ?"
- "Ton LLM hallucine. Comment tu diagnostiques et corriges ?"
- "Un ingénieur propose de fine-tuner le modèle. Comment tu évalues cette décision ?"

### Concepts clés à maîtriser

#### LLMs & Fondamentaux
- Différence déterministe (code classique) vs probabiliste (LLM)
- Temperature, tokens, context window
- Prompt engineering : zero-shot, few-shot, chain-of-thought

#### RAG (Retrieval-Augmented Generation)
- Pourquoi : LLMs ne connaissent pas les données privées de l'entreprise
- Composants : data ingestion → vector database → retrieval → LLM → réponse
- Quand utiliser RAG vs fine-tuning vs off-the-shelf
- Limites : chunking, qualité du retrieval, hallucinations résiduelles

#### AI Evals
- Pourquoi les métriques classiques ne fonctionnent pas (output non-déterministe)
- LLM-as-Judge : utiliser un modèle pour évaluer un autre modèle
- Métriques : latence, hallucination rate, task success rate, bias
- Golden set : jeu de test de référence

#### Agents & Workflows
- Différence LLM simple vs agent (planification, outils, mémoire)
- Safety guards et guardrails pour les agents
- Orchestration : LangChain, LlamaIndex, n8n

### Critères d'évaluation

| Critère | ❌ Junior (0 pt) | ✅ Senior (1 pt) | 🚀 Lead (2 pts) |
|---|---|---|---|
| **Challenge de la prémisse** | Accepte la question telle quelle | Questionne si le LLM est le bon outil pour le problème | Propose des alternatives et justifie avec des données |
| **Compréhension RAG** | Cite le terme sans l'expliquer | Explique pourquoi RAG vs off-the-shelf selon le contexte données privées | Articule les composants et les limites du RAG |
| **Contraintes non-fonctionnelles** | Ignore privacy, coût, latence | Adresse au moins 2 contraintes (RGPD, coût/requête, latence) | Quantifie les trade-offs et propose une matrice de décision |
| **Validation du POC** | "On teste et on voit" | Définit des critères de succès du POC avant de commencer | Définit un plan d'évaluation complet avec golden set |
| **Pensée séquentielle** | Solution directe sans validation | POC → validation → architecture cible | Roadmap itérative avec gates de décision explicites |

### Score d'évaluation
- **0-4 pts** : Concepts AI à consolider — priorité au projet pratique (agent relocalisation)
- **5-7 pts** : Niveau Senior — approfondir RAG et AI Evals
- **8-10 pts** : Niveau Lead — maîtrise de l'architecture AI produit

### Pattern de faiblesse identifié chez Thomas
> ✅ Challenge de la prémisse : réflexe naturel fort  
> ✅ Pensée séquentielle : POC avant architecture complexe  
> ⚠️ Compréhension RAG : à construire par la pratique (projet relocalisation)  
> ⚠️ Contraintes non-fonctionnelles : RGPD, coût/requête absents  
> ⚠️ Critères de succès du POC : "valider les hypothèses" trop vague  

---

## MODULE 3 — Behavioral / Leadership

### Type de question
Gestion de conflits, décisions difficiles, leadership sans autorité, échecs et apprentissages.

### Exemples de questions réelles
- "Raconte une fois où tu n'étais pas d'accord avec l'engineering."
- "Raconte un produit que tu as construit de 0 à 1."
- "Comment tu gères des stakeholders qui ont des priorités contradictoires ?"
- "Quel est ton plus grand échec produit et qu'est-ce que tu en as appris ?"
- "Comment tu convaincs une équipe sans avoir d'autorité directe ?"

### Framework STAR (obligatoire)
```
S — Situation    : Contexte précis (entreprise, moment, enjeu)
T — Tâche        : Ton rôle et ta responsabilité spécifique
A — Action       : Ce que TU as fait (pas "on a fait")
R — Résultat     : Impact concret, chiffré si possible
```

### Critères d'évaluation

| Critère | ❌ Junior (0 pt) | ✅ Senior (1 pt) | 🚀 Lead (2 pts) |
|---|---|---|---|
| **Structure STAR** | Narrative floue, mélange général et spécifique | STAR respecté avec résultat concret | STAR avec résultat chiffré et apprentissage explicite |
| **Signal d'ouverture** | "J'ai rarement été dans cette situation..." | Posture claire dès le début + exemple ciblé | Contexte stratégique de la situation avant l'exemple |
| **Spécificité** | Exemple générique ou theoretical | Exemple réel, technique, avec noms et contexte | Exemple avec détails qui prouvent la crédibilité |
| **Résultat** | Absent ou vague ("ça s'est bien passé") | Concret : ce qu'on a livré, l'impact sur le produit | Chiffré : impact business, timeline, apprentissage capitalisé |
| **Posture leadership** | Défensive, soumise, ou au contraire trop assertive | Confiance par défaut + intervention ciblée et justifiée | Montre une évolution de posture entre Junior et aujourd'hui |

### Score d'évaluation
- **0-4 pts** : Retravailler la structure STAR et les résultats
- **5-7 pts** : Niveau Senior — affiner le signal d'ouverture et la spécificité
- **8-10 pts** : Niveau Lead — storytelling Senior PM convaincant

### Pattern de faiblesse identifié chez Thomas
> ✅ Posture leadership : confiance par défaut, intervention ciblée  
> ✅ Exemples concrets et techniques (Kafka/MoovOne)  
> ⚠️ Structure STAR : mélange général et spécifique  
> ⚠️ Résultat : systématiquement absent ou vague  
> ⚠️ Signal d'ouverture : "j'ai rarement..." — à reformuler  

---

## Synthèse — Profil actuel de Thomas

| Module | Points forts | Gaps prioritaires | Score estimé actuel |
|---|---|---|---|
| Product Case | Contextualisation, leading/lagging | North Star, guardrails, timeframe | 3/5 critères |
| Technical AI PM | Challenge prémisse, pensée séquentielle | RAG, contraintes NF, critères POC | 2/5 critères |
| Behavioral | Posture, exemples concrets | STAR, résultats, signal ouverture | 3/5 critères |

### Priorités d'entraînement recommandées
1. **Court terme (semaines 1-2)** : Structure STAR sur tous les exemples comportementaux
2. **Court terme (semaines 1-2)** : North Star Metric — s'entraîner à choisir ET justifier
3. **Moyen terme (semaines 3-6)** : Concepts RAG + AI Evals — via le projet agent relocalisation
4. **Moyen terme (semaines 3-6)** : Guardrails et contre-métriques sur chaque Product Case

---

## Instructions pour l'agent Claude Code

### Comportement attendu

```
1. GÉNÉRER un test : choisir aléatoirement une question par module
   → Calibrer la difficulté selon le niveau cible (Junior / Senior / Lead)
   → Indiquer le temps recommandé (Product Case : 15 min, Technical : 10 min, Behavioral : 5 min)

2. ÉVALUER la réponse : appliquer les critères du module correspondant
   → Scorer chaque critère (0 / 1 / 2)
   → Identifier les 2-3 points forts
   → Identifier le gap prioritaire à corriger
   → Donner un exemple de ce qu'aurait dit un Senior PM

3. TRACKER le progrès : mémoriser les patterns de faiblesse récurrents
   → Générer un rapport hebdomadaire d'évolution
   → Suggérer le module à prioriser la semaine suivante

4. ADAPTER la difficulté : augmenter progressivement
   → Semaines 1-2 : questions de base
   → Semaines 3-4 : questions avec contexte AI
   → Semaines 5+ : questions combinées (Product Case + dimension technique)
```

### Sources de référence
- **Product Case** : Prepfully Datadog, NextSprints, IGotAnOffer
- **Technical AI PM** : IGotAnOffer AI PM guide, Product School RAG guide
- **Behavioral** : Structure STAR standard, Leland interview guides
- **Concepts AI** : AI PM Skill Roadmap 2026 (Medium/Agile Insider)

---

*Document généré dans le cadre du programme de coaching "Guide d'évolution de carrière"*
*À mettre à jour après chaque session de mock test*
