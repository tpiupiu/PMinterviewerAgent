# pm_references.md — Références PM pour le coach d'entretien

Ce fichier contient des exemples de réponses Excellent, frameworks et formulations
extraits des ressources d'entraînement. L'agent le lit pour calibrer ses évaluations
et enrichir ses feedbacks avec des exemples concrets et sourcés.

**Sources intégrées :**
- Ben Erez (Lenny's Newsletter) — The definitive guide to mastering product sense interviews (2025)
- Ben Erez (Lenny's Newsletter) — The definitive guide to mastering analytical thinking interviews (2025)
- Marily Nika (Lenny's Newsletter) — Building AI product sense, part 2 (2026)
- Jules Walter (Lenny's Newsletter) — How to develop product sense (2022)
- Tal Raviv (Lenny's Newsletter) — How to build AI product sense (2026)
- Miles K. (Medium) — How to prepare for PM interviews in 2026
- Diana Stepner (Medium) — Product Sense: What is it, why it's needed, and how to keep it fresh
- Product Sense Course — Mindmap (Motivation Theory, Cognitive Empathy, Taste, Creativity)
- Lenny AT Template — Instagram Reels (Set Goal + Tradeoff)

---

## TRANSVERSAL — OUVERTURE STRUCTURÉE & MISSION STATEMENT

### Source : Ben Erez — Product Sense + Analytical Thinking guides

**Ce que fait un candidat Excellent dès l'ouverture :**
1. Poser 2-4 assumptions pour cadrer l'exercice sans fermer l'espace solution
2. Annoncer le game plan et vérifier l'alignement avec l'interviewer
3. Créer des verbal waypoints à chaque transition entre sections

**Formulation exacte du game plan (Product Sense) :**
> "Before I dive in, I'd like to walk you through my plan for our time together:
> I'll start by describing the product and why it matters.
> Then I'll break down the target audience and define a segment to focus on.
> From there, I'll identify key problems for that segment and prioritize one.
> I'll then brainstorm solutions and pick one.
> If we have time, I'd love to describe a v1 implementation.
> Does this plan sound good to you?"

**Formulation exacte du game plan (Analytical Thinking) :**
> "I want to start by reviewing the product's landscape and reason for existing,
> then identify key stakeholders and ecosystem health metrics, define a North Star metric
> with guardrails, and finally set specific team goals. We can discuss tradeoffs along
> the way at any point. Does that sound like a good plan for our time together?"

**Pourquoi c'est Excellent :**
L'interviewer est un PM occupé qui doit collecter des signaux spécifiques pour compléter
son évaluation. Annoncer le game plan lui assure que le candidat va générer ces signaux —
et lui donne l'opportunité de rediriger si nécessaire. C'est comme s'asseoir pour jouer
à un jeu avec quelqu'un qui sait y jouer vs quelqu'un qui ne sait pas.

**Exemples d'assumptions (question : "Build a podcast product for Netflix") :**
> - I'll assume I'm the PM for a new zero-to-one podcast product at Netflix.
> - I'll focus on the U.S. market initially, though Netflix is global.
> - I'll aim to build within Netflix's existing platform/ecosystem.
> - I'll focus on audio for this exercise, since most podcasting usage is via audio.
> - I'll limit our exercise to serving existing Netflix subscribers.

**Pièges à éviter sur l'ouverture :**
- Brainstormer sans framework → l'interviewer ne peut pas suivre le raisonnement
- Demander fréquemment "What would you like me to do next?" → signal de manque d'ownership
- Assumptions trop narrowing → ferment l'espace solution trop tôt

---

## FAMILLE 1 — PRODUCT SENSE

### Source : Ben Erez — The definitive guide to mastering product sense interviews

**Structure de l'entretien Product Sense (35 min effectifs) :**

| Section | Durée | Signal évalué |
|---------|-------|---------------|
| Clear communication | 3-5 min | Structure, assumptions, game plan |
| Product motivation | 3-5 min | Mission, contexte stratégique |
| Segmentation | 8-10 min | Ecosystem thinking, persona |
| Problem identification | 8-10 min | Journey mapping, priorisation |
| Solution development | 8-10 min | Créativité, impact/effort, V1 |

**Règle fondamentale :** L'excellence dans une dimension ne compense pas la faiblesse
dans une autre. Un score solide dans chaque dimension est nécessaire pour passer.

---

### Sous-skill 1.2 — Product Motivation & Mission Statement

**Ce que fait un candidat Excellent :**
Il va au-delà de la description des features pour articuler la purpose profonde.

Au lieu de :
> "This product helps users share photos."

Il dit :
> "This product enables people to maintain meaningful connections with loved ones
> through visual storytelling, even when physically apart."

**3 composantes de la Product Motivation (Ben Erez) :**
1. Description + valeur (pourquoi ce produit compte pour les utilisateurs)
2. Contexte stratégique et compétitif
3. Mission statement — North Star pour guider les décisions du reste de l'entretien

**Exemple Excellent — Mission Statement (Meta Gardening) :**
> "To empower people to connect and thrive through the shared experience of gardening,
> creating communities that grow together both online and in their gardens."

**Exemple Excellent — Mission Statement (Netflix Podcast) :**
> "To enrich people's entertainment experience beyond the screen by delivering captivating
> audio content that can be enjoyed wherever they go."

**Exemple Excellent — Mission Statement (Claude Projects) :**
> "To empower users to create AI assistants with specialized knowledge and capabilities
> tailored to their unique needs, making AI more personally relevant and useful
> in their daily lives and work."

**Pièges fréquents :**
- Mission trop vague : "help users be more productive" → ne guide pas les décisions
- Mission trop narrow : ferme l'espace créatif trop tôt
- Décrire les features sans articuler la purpose → manque de strategic thinking

---

### Sous-skill 1.1 — Segmentation

**Principe clé (Ben Erez) :**
Segmenter par motivations et comportements — pas par démographie.
Test de qualité : chaque segment doit être mutuellement exclusif. Si un utilisateur
peut appartenir à deux segments simultanément, la segmentation n'est pas assez précise.

**Framework de segmentation :**
1. Mapper les ecosystem players (pas juste les end users)
2. Choisir un player avec rationale explicite
3. Identifier les motivations primaires de ce player
4. Définir 3 segments basés sur ces motivations
5. Évaluer sur matrice Reach × Underserved degree
6. Choisir un segment et créer un persona vivant

**Exemple Excellent — Ecosystem players (Netflix Podcast) :**
> "Major stakeholders I would consider include:
> - Listeners: Netflix subscribers consuming podcast content
> - Content creators: podcast hosts, producers, storytellers
> - Advertisers: potential monetization partners
> - Netflix internal teams: content, tech, marketing
> - Competing podcast platforms: Spotify, Apple, etc.
>
> For this discussion, I'd like to focus on the listeners as our primary ecosystem group,
> as they represent the demand side of this product. Focusing on listeners aligns with
> Netflix's customer-centric approach and would help us understand what type of podcast
> offering would drive the most engagement and value."

**Exemple Excellent — Check-in après ecosystem avant segmentation :**
> "I'd like to focus on [chosen ecosystem player] for these reasons [brief rationale].
> Before I dive into defining segments within this group, I want to pause to make sure
> this line of thinking is making sense?"

**Exemple Excellent — Motivations pour segmenter (Netflix Podcast, listeners) :**
> "Motivation groupings for listeners:
> - Education/learning
> - Entertainment/narrative
> - Community/fandom
>
> Based on these motivations, I could define segments that factor in content types
> they consume, viewing behavior, and engagement level with specific content."

**Exemple Excellent — Persona (Netflix Podcast, "Educational-content extenders") :**
> "I'd like to focus on educational-content extenders because this segment leverages
> Netflix's growing investment in documentary content, has high underserved degree
> despite significant reach, and differentiates from competitors.
>
> For our persona, let's consider Alex. Alex watches Netflix documentaries about science,
> technology, and history regularly and often researches topics further after watching.
> They listen to educational podcasts during commutes and would value expert discussions
> that build upon the documentaries they've recently watched."

**Pièges fréquents :**
- Segmentation démographique ("millennials en zone urbaine") → trop faible
- Sauter l'ecosystem analysis → signal de manque de systems thinking
- Segments non mutuellement exclusifs → décisions de priorisation floues

---

### Sous-skill 1.2 — Problem Identification

**Principe clé (Ben Erez) :**
Distinguer Need (désir) vs Problem (obstacle).
- Need : "I want beautiful flowers in my apartment"
- Problem : "It's challenging to find flowers that thrive in my apartment's limited lighting conditions"

**Le meilleur problem identification pense "day in the life" — pas une liste générique.**
Chaque étape du journey doit être spécifique au persona.

**Exemple Excellent — User Journey (Casey, novice urban gardener, Meta) :**
> "User journey for Casey:
> - Inspiration: Sees friend's plants or online content that sparks interest
> - Research: Searches for what plants might work in her space
> - Planning: Decides what to grow and what supplies are needed
> - Purchasing: Buys plants, containers, soil, and basic tools
> - Setup: Sets up her gardening space
> - Care and maintenance: Daily/weekly care of plants
> - Troubleshooting: Addressing issues like pests or plant health problems
> - Harvest/enjoyment: Enjoying the results of her efforts"

**Exemple Excellent — Priorisation d'un problème (Meta Gardening) :**
> "Based on both high frequency and high severity, I'd like to prioritize solving the
> knowledge matching gap problem. It occurs at a critical early stage that determines
> whether Casey will even get started successfully with gardening."

**Pièges fréquents :**
- Confondre needs et problems → "users need better search"
  au lieu de "users struggle to find relevant content because..."
- Journey générique (pre/during/post) applicable à n'importe quel produit
- Problem-solution conflation : "users need a better recommendation algorithm"

---

### Sous-skill 1.3 — Solution Development

**3 composantes (Ben Erez) :**
1. Brainstorming de solutions distinctes (pas des variantes du même concept)
2. Évaluation Impact × Effort → choix défendable
3. Définition V1 + go-to-market + risques/mitigations

**Exemple Excellent — Solution choisie (Meta Gardening) :**
> "I'd prioritize the plant match AI assistant for the following reasons:
> - Has high impact with moderate effort
> - It directly addresses the knowledge gap with personalized recommendations,
>   while leveraging Meta's existing AI capabilities to make implementation feasible
> - This solution would fundamentally change how novice urban gardeners like Casey
>   approach plant selection, moving from overwhelming generic research to personalized,
>   confidence-building recommendations"

**Exemple Excellent — V1 + risques (Meta Gardening) :**
> "We'd build a simple questionnaire within Instagram and Facebook asking users about
> their location, space, light conditions, time available, experience level and preferences.
> The AI would recommend 3-5 plants with care instructions, growth timelines, and photos.
> We'd start with the 50 most common houseplants and container-friendly edibles.
>
> Risk: Inaccurate recommendations could lead to plant failure and user disappointment.
> Mitigation: Partner with gardening experts to verify recommendations and implement
> a feedback system where users report successes/failures."

**Pièges fréquents :**
- Solution jumping → une seule solution sans explorer plusieurs approches
- Feature obsession → lister des features plutôt qu'expliquer comment ça résout le problème
- Platform mismatch → solution qui ne tire pas parti des forces de l'entreprise

---

### Source : Jules Walter — How to develop product sense (Lenny's Newsletter, 2022)

**Définition fondamentale :**
> "Product sense is the skill of consistently being able to craft products (or make changes
> to existing products) that have the intended impact on their users. Product sense relies on
> (1) empathy to discover meaningful user needs and (2) creativity to come up with solutions
> that effectively address those needs."

**4 pratiques pour développer le product sense :**
1. Observer des gens utiliser des produits (user research sessions, coffee shops)
2. Déconstruire des produits du quotidien (1-2h par mois, comparer des produits concurrents)
3. Apprendre de grands product thinkers (Stewart Butterfield, Julie Zhuo)
4. Être curieux des changements technologiques et du domaine

**5 leçons comportementales clés de Jules Walter (Slack) :**
- Les utilisateurs sont pressés et distraits — ils ne lisent pas les labels
- Les utilisateurs abandonnent dès qu'ils se sentent confus ou nerveux
- Trop d'information à la fois → ils partent
- Le contexte impacte les décisions (comparaisons, social proof)
- S'assurer que le goal du produit et les actions possibles sont clairs

**Principe de Stewart Butterfield (via Jules Walter) :**
> "The details are not the details. They make the design."
Un candidat Excellent s'intéresse aux micro-détails — pas juste aux grandes étapes.

---

### Source : Diana Stepner — Product Sense: What is it, why it's needed

**Définition complémentaire :**
> "Product sense is understanding what makes for a high-quality product for your customers
> (empathy) and having strong, validated opinions about what solutions will be successful
> (creativity)."

**Le product sense peut devenir obsolète.** Si tu quittes une industrie et y reviens,
les dynamiques compétitives ont changé, les technologies ont évolué, les attentes
des utilisateurs se sont transformées.

---

### Source : Product Sense Course — Mindmap

**Structure globale du Product Sense (4 dimensions) :**
- **Mindset** : Motivation Theory (motivation, friction, satisfaction, nudge) + Cognitive Empathy (metacognition, intellectual flexibility, simulation)
- **Taste** : Understanding Taste, Components of Product Taste, Building Taste, Taste Workout & Examples
- **Creativity** : Strategic Thinking (positioning, segmentation, differentiation) + Creative Execution (creative mindset, team creativity, techniques)
- **Domain Expertise** : très spécifique — traiter en Q&A
- **(Bonus) Communication** : Product artifacts, Influence, Interviewing for Product Sense

**Implication pour les entretiens :**
Un candidat Excellent démontre du goût produit — une opinion fondée sur une
compréhension profonde des motivations utilisateur (Motivation Theory) et une
capacité à se mettre dans la peau de l'utilisateur (Cognitive Empathy / Simulation).

---

## FAMILLE 2 — ANALYTICAL THINKING

### Source : Ben Erez — The definitive guide to mastering analytical thinking interviews

**Structure de l'entretien Analytical Thinking (35 min effectifs) :**

| Section | Durée | Signal évalué |
|---------|-------|---------------|
| Assumptions + game plan | 1-2 min | Structure, scope management |
| Product rationale | ~2 min | Compréhension stratégique, mission |
| Metric framework | ~10 min | Ecosystem thinking, NSM, guardrails |
| Goal-setting | ~5 min | Altitude shift, leading indicators |
| Tradeoff evaluation | ~10 min | Décision sous contrainte, rationale |

---

### Sous-skill 2.1 — Ecosystem Metrics Framework

**3 composantes (Ben Erez) :**
1. Ecosystem value : identifier les players ET leurs actions clés
2. Metric definition : métriques précises avec timeframe (formulables en query SQL)
3. Critique NSM : identifier 1-2 façons dont la croissance du NSM pourrait endommager l'écosystème → guardrail metrics

**Règle du NSM :**
- Refléter la création de valeur pour tous les ecosystem players
- Pouvoir croître indéfiniment avec le succès du produit
- Toujours inclure un timeframe ("weekly", "monthly")
- Éviter les moyennes et ratios → peuvent croître même si l'écosystème rétrécit (false positive)

**Exemple Excellent — NSM (Spotify) :**
> NSM : "Total streaming hours per week"
> Mesure le volume total de l'action unificatrice bénéficiant à tous les players,
> avec un timeframe correspondant aux patterns d'engagement réels.
> Guardrail : éviter de devenir une plateforme passive sans valeur réelle pour les créateurs.

**Exemple Excellent — NSM (Instagram Reels) :**
> NSM : "Total Reels watch time per week"
> Guardrail : éviter d'optimiser le watch time au détriment de la qualité du contenu
> ou de l'adoption large.

**Exemple Excellent — NSM (DoorDash) :**
> NSM : "Total completed deliveries per week"
> Guardrail metrics : order satisfaction (qualité), retention rates (durabilité),
> profit margins (éviter la croissance non profitable).

**Piège critique :**
Utiliser une moyenne ou un ratio comme NSM. Exemple : "average session duration"
peut augmenter même si la base d'utilisateurs rétrécit → false positive.

---

### Sous-skill 2.2 — Goal-Setting (Altitude Shift)

**Principe clé (Ben Erez) :**
L'altitude shift = passer des métriques produit/company-level (50,000 pieds)
aux objectifs team-level (ground level).

**Séquence correcte :**
1. Choisir l'ecosystem player qui peut driver le plus de croissance du NSM
2. Mapper le user journey de ce player en travaillant en arrière depuis l'event NSM
3. Identifier 3 opportunités le long du journey
4. Scorer sur Impact × Ability to influence
5. Prendre une décision claire — pas hedger

**Exemple Excellent — Goal-Setting (Instagram Reels, nouveaux créateurs) :**
> "I would prioritize improving new creator retention — defined as the percentage
> of first-time creators who publish a second Reel within 14 days of their first publication.
>
> We can influence this through better post-publishing guidance, enhanced performance
> dashboards, success stories, and personalized prompts. This goal will expand our
> creator base sustainably, increasing content supply which directly drives total watch time."

Annotations :
- Métrique précise avec timeframe (14 jours) — formulable en query
- Double justification : influence + impact
- Lien causal explicite : créateurs → contenu → watch time
- Leading indicator, pas lagging indicator

**Exemple Excellent — Goal-Setting (DoorDash, cart-to-checkout conversion) :**
> Objectif : améliorer la conversion cart-to-checkout.
> Rationale : friction point précis avec intention déjà présente — les paniers abandonnés
> représentent de l'intent existant qu'on peut capturer directement.

**Exemple Excellent — Goal-Setting (Spotify, session continuation) :**
> Objectif : augmenter le taux de continuation de session
> (% d'utilisateurs qui démarrent une nouvelle chanson après la fin d'une playlist).
> Rationale : high impact sur NSM total streaming hours, high ability to influence
> via recommendation engine.

---

### Sous-skill 2.3 — Tradeoff Evaluation

**5 étapes (Ben Erez) :**
1. Clarifier le tradeoff (1 phrase de description)
2. Identifier le common goal des deux options — AVANT les pros/cons
3. Framer : pros et cons de chaque option
4. Décider clairement avec rationale ancré dans mission + métriques
5. Spécifier les conditions de révision

**Exemple Excellent — Tradeoff complet (Reels vs Stories, Instagram) :**

Étape 1 — Clarification :
> "We're considering whether to place Reels at the top of the Instagram app interface,
> replacing Stories which currently occupies that prime position."

Étape 2 — Common Goal :
> "Both Reels and Stories contribute to Instagram's mission of connecting people through
> creative expression, but they do so differently. Stories enable ephemeral, authentic
> sharing between friends, while Reels focuses on entertainment and discovery from a
> broader creator ecosystem."

Étape 3 — Frame the Tradeoff :

| | Pros | Cons |
|---|---|---|
| **Reels en haut** | Accélère la croissance video / Augmente la découverte de créateurs / S'aligne sur les tendances entertainment | Réduit les connexions authentiques / Risque d'aliéner les utilisateurs social-focused / Peut cannibaliser Stories |
| **Stories en haut** | Maintient le focus social / Préserve l'UX familière / Protège les patterns d'engagement | Limite la croissance de Reels / Affaiblit la position face à TikTok |

Étape 4 — Décision :
> "Keep Stories at top. This aligns with Meta's mission to 'build the future of human
> connection' by prioritizing authentic social interactions. While Reels advances our
> entertainment technology, Stories better fulfills our core mission of fostering meaningful
> human connections."

Étape 5 — Conditions de révision :
> "I would revisit if: Stories engagement plateaus while Reels grows rapidly; users show
> strong preference for entertainment; or TikTok significantly erodes our user base."

**Exemple Excellent — Tradeoff (Spotify, breadth vs depth) :**
> Décision : prioriser breadth (plus d'utilisateurs, engagement modéré).
> Rationale : aligné avec la mission Spotify, réduit le risque de concentration.
> Conditions de révision : si les heavy users génèrent disproportionnellement plus
> de revenus publicitaires.

**Annotations clés :**
- Le common goal est identifié AVANT les pros/cons — séquence obligatoire
- La décision est prise — pas de hedging
- Le rationale ancre dans la mission — pas juste dans les données
- Les conditions de révision montrent que la décision est contextualisée, pas dogmatique

**Pièges fréquents :**
- Lister pros/cons sans décider → l'interviewer attend une position
- Décision sans lien avec la mission → manque de throughline stratégique
- Pas de conditions de révision → décision qui paraît absolue

---

### Source : Miles K. — How to prepare for PM interviews in 2026

**Les 6 erreurs les plus communes :**
1. Over-indexing on memorized frameworks
2. Not defining metrics clearly
3. Jumping into solutions too fast
4. No clear prioritization logic
5. No strong behavioral examples
6. **Talking about features instead of impact** (la plus importante)

> "Features are outputs. Impact is what gets you hired."

**Ce que cherchent les interviewers en 2026 :**
- Think clearly under ambiguity
- Connect product decisions to measurable outcomes
- Articulate tradeoffs across quality, cost, and speed
- Reason about AI systems responsibly and pragmatically

---

## FAMILLE 3 — TECHNICAL AI

### Source : Marily Nika — Building AI product sense, part 2 (2026)

**Contexte :** Meta a ajouté "Product Sense with AI" à son loop PM — première modification
majeure en plus de 5 ans. Les candidats sont évalués sur leur capacité à travailler
avec l'incertitude, pas sur leur connaissance du modèle.

**L'AI product sense** = comprendre ce qu'un modèle peut faire et où il échoue,
et travailler dans ces contraintes pour construire un produit que les gens aiment.

---

### Sous-skill 3.3 — AI Evals & MVQ

**Définition MVQ — Minimum Viable Quality (Marily Nika) :**
Trois seuils à définir explicitement :
1. **Acceptable bar** : assez bon pour de vrais utilisateurs
2. **Delight bar** : la feature semble magique
3. **Do-not-ship bar** : les taux d'échec qui vont briser la confiance

Plus une enveloppe de coût.

**Les 5 facteurs qui font monter ou descendre le bar MVQ :**
- Conséquence de l'erreur (healthcare vs entertainment)
- Responsabilité légale
- Sensibilité des données
- Niveau d'autonomie de l'agent
- Calibration de la confiance utilisateur

**Exemple Excellent — MVQ Speaker Identification :**

Acceptable bar :
> "Correctly identifies the speaker x% of the time in typical home conditions.
> Recovers gracefully when unsure: 'I'm not sure who's speaking — should I use
> your profile or continue as a guest?'"

Delight bar (signaux comportementaux, pas juste un pourcentage) :
> "Users stop repeating themselves or rephrasing commands.
> 'No, I meant...' corrections drop sharply."

Règle empirique : si 8-9 tentatives sur 10 fonctionnent sans retry en conditions
réelles, ça semble magique. Si 1 sur 5 nécessite un retry, la confiance s'érode.

Do-not-ship bar :
> "Misidentifies the speaker more than y% in critical flows (purchases, messages,
> personalized actions)."

**Implication pour les entretiens :**
Quand un candidat propose une feature AI, il doit être capable de définir son MVQ —
pas juste dire "on mesurera la satisfaction utilisateur".

---

### Sous-skill 3.4 — Agent Design & Failure Modes

**Les 3 rituels pour mapper les failure modes (Marily Nika) :**

**Ritual 1 : Demander au modèle de faire quelque chose d'évidemment faux (2 min)**
Pattern de failure le plus dangereux :
> "When confronted with mess, they confidently invent structure."
Exemple : demander d'extraire "strategic decisions" d'un thread Slack chaotique.
Le modèle hallucine une roadmap, assigne les mauvais owners.

**Ritual 2 : Demander quelque chose d'ambigu (3 min)**
Fragilité sémantique = le modèle comprend techniquement les mots mais rate l'intent.
Si le modèle ne comprend pas pleinement l'intent, il comble les lacunes → hallucinations.

**Ritual 3 : Demander quelque chose d'unexpectedly difficult (3 min)**
Objectif : trouver le premier point de rupture pour savoir où le produit
a besoin de structure organisationnelle.

**Exemple Excellent — Guardrail concret (Marily Nika) :**
Problème : un agent de résumé Slack assignait des owners pour des action items
alors que personne n'avait accepté de responsabilité.
Solution — une ligne dans le system prompt :
> "Only assign an owner if someone explicitly volunteers or is directly asked
> and confirms. Otherwise, surface themes and ask the user what to do next."
Résultat : a éliminé le plus grand problème de confiance presque immédiatement.

---

### Sous-skill 3.1 — LLM Fundamentals & Cost Envelope

**Source : Marily Nika — Estimating the cost envelope**

> "Cost envelope = the rough range of what this feature will cost to run at scale."

Questions à se poser :
- What's the model cost per call?
- How often will users trigger it per day/month?
- What's the worst-case scenario (power users)?
- Can caching, smaller models, or distillation bring this down?
- If usage 10x's, does the math still work?

**Exemple concret — AI meeting notes :**
- Per-call cost : ~$0.02 pour un transcript de 30 min
- Average usage : 20 meetings/user/month → ~$0.40/month/user
- Heavy users : 100 meetings/month → ~$2.00/month/user
- Avec caching et smaller model : ~$0.25-0.30/month/user

Une feature à $0.30/user/month qui drive la rétention = no-brainer.
Une feature à $5/user/month avec impact incertain = problème business.

---

### Source : Tal Raviv — How to build AI product sense (2026)

**Tool calling — ce que ça implique pour le product design :**
Un LLM ne peut que produire du texte. Quand il prend une action (éditer un fichier,
fetch des données), il appelle des tools.

Séquence d'un agent :
1. LLM décrit ce qu'il veut faire
2. L'agent harness exécute le tool
3. Le résultat est retourné au LLM qui décide quoi faire ensuite

**MCP (Model Context Protocol) en une phrase :**
Standard qui permet à chaque service SaaS de construire un seul connecteur
fonctionnant avec tous les LLMs — comme USB pour les agents.

---

### Source : Miles K. — 6 concepts AI à maîtriser avant d'interviewer (2026)

1. **LLM basics** : ce que la technologie peut et ne peut pas faire
2. **Hallucinations** : failure modes et implications pour la confiance utilisateur
3. **Prompt engineering** : comment les utilisateurs interagissent avec les systèmes AI
4. **RAG** : comment ancrer les réponses AI dans des données réelles
5. **AI evaluation metrics** : mesurer la qualité AI au-delà de "ça semble bien"
6. **Responsible AI** : biais, sécurité, tradeoffs éthiques avant le ship

**Comment les questions AI apparaissent en entretien :**
- "Design an AI feature for X"
- "How would you evaluate a chatbot?"
- "What risks come with adding AI here?"

Ce que l'interviewer veut entendre : tradeoffs quality/cost/latency/risk —
pas du buzzword-dropping.

---

## FAMILLE 4 — LEADERSHIP

### À compléter au fil de la préparation

**Format pour les stories behavioral :**
```
### Story [ID] — [Sous-skill 4.X ciblé]
Situation : [2-3 phrases, enjeu concret en premier — pas le contexte macro]
Mes actions : [séquence en "je", pas "on"]
Résultat : [mesurable]
Leçon : [ce que ça dit de moi comme leader]
Statut : Draft | À affiner | Prête
```

**Format pour les insights resources :**
```
### Source : [Nom]
Sous-skill [ID] : insight clé
Exemple Excellent : [formulation de référence]
```

---

## NOTES DE CALIBRATION POUR L'AGENT

**Ce qui distingue Excellent de Good dans toutes les familles :**
1. Une opinion défendable — pas "ça dépend" sans décision
2. Un throughline — chaque décision connectée à la mission établie au début
3. Des conditions de révision — la décision est contextualisée, pas absolue
4. Des métriques précises — formulables en query SQL, avec timeframe
5. L'anticipation des objections — le candidat les adresse proactivement

**Sur le profil penseur systémique :**

Force à activer :
La capacité à voir les interdépendances est un avantage structurel sur les tradeoffs
et les goal-setting questions. L'exploiter explicitement :
> "Ce que j'apprécie dans cette approche, c'est qu'elle crée un effet flywheel entre X et Y."

Risque à surveiller :
Partir sur le contexte macro avant d'ancrer dans le concret.
Correctif : commencer par une métrique spécifique ou un persona vivant.
Le macro vient en justification, pas en introduction.

**Rappel Ben Erez :**
> "No one wings these interviews successfully. Deliberate practice makes all the difference."
La structure sans entraînement verbal ne suffit pas. Chaque framework doit être
pratiqué à voix haute jusqu'à ce que les transitions soient naturelles.
