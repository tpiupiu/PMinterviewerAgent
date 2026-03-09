# PM Skills — Référence d'évaluation pour entretiens Senior PM

> Ce document est la référence qualitative de l'agent PM Coach.
> Pour chaque skill, il définit : ce que c'est, ce que l'interviewer teste réellement,
> les signaux weak/good/excellent, et les pièges fréquents.
> Il sera enrichi au fur et à mesure des sessions.

---

## Note sur les modes d'évaluation

Trois modes coexistent selon les familles :

- **Situational** : on te donne une question ou un problème en live — tu raisonnes en temps réel.
  Familles 1, 2, 3 uniquement.
- **Behavioral** : "Tell me about a time when..." — tu racontes une expérience réelle.
  Famille 4 uniquement.
- **Behavioral + Situational** : les deux formats peuvent apparaître.
  Famille 4 — chaque sous-skill est évalué sur les deux modes.

---

## Sous-skill transversal — Ouverture structurée & Mission Statement

> Ce sous-skill s'applique à toutes les familles situationnelles (1, 2, 3).
> Il n'est pas réévalué séparément dans chaque famille — mais l'agent
> doit vérifier sa présence au début de chaque exercice.

**Ce que c'est**
Ouvrir un entretien avec des assomptions claires, annoncer son plan,
formuler un mission statement qui guidera toute la réponse,
et utiliser des waypoints verbaux tout au long de l'exercice.

**Ce que l'interviewer teste**
Le candidat sait-il structurer sa pensée avant de plonger ?
Drive-t-il la conversation ou attend-il qu'on le guide ?

**Weak**
Plonge directement dans le contenu sans annoncer de plan.
Demande à l'interviewer "par où je commence ?".
Pas d'assomptions énoncées. Pas de mission statement.

**Good**
Énonce 2-3 assomptions, annonce son plan, check-in avec l'interviewer.
Formule un mission statement utilisable.

**Excellent**
Assomptions qui réduisent le scope sans fermer l'espace de solution.
Plan articulé en 60 secondes avec waypoints verbaux explicites.
Mission statement suffisamment spécifique pour guider les décisions
mais suffisamment large pour permettre des solutions créatives.
Y revient explicitement lors des étapes suivantes.
Reste adaptable si l'interviewer redirige.

**Pièges fréquents**
- Assomptions trop restrictives qui éliminent des solutions créatives plus tard
- Annoncer un plan mais ne pas le suivre
- Mission statement générique applicable à n'importe quel produit
- Trop demander la validation de l'interviewer (signal de manque de leadership)

---

## Famille 1 — Product Sense

> Mode : **Situational**
> La famille la plus universellement testée. Adoptée par la majorité des entreprises tech.
> Durée typique : 45 min, dont ~35 min pour l'exercice.
> L'interviewer évalue 3 dimensions en séquence après l'ouverture structurée.
> Excellence dans l'une ne compense pas une faiblesse dans une autre.

---

### 1.1 — Segmentation

**Ce que c'est**
Identifier tous les stakeholders de l'écosystème, créer des segments
basés sur les motivations et comportements (pas la démographie),
les prioriser avec un framework Reach × Underserved,
et créer un persona vivant.

**Ce que l'interviewer teste**
Le candidat pense-t-il en système ou seulement en end-user ?
Ses segments sont-ils actionnables ?

**Weak**
Segments démographiques ("millennials en zone urbaine").
Saute directement aux end-users sans mapper l'écosystème.
Segments qui se chevauchent.

**Good**
Mappe 4-5 stakeholders.
Segments basés sur des motivations distinctes.
Justifie le choix du segment cible avec reach/underserved.

**Excellent**
Passe le test de mutual exclusivity — un utilisateur ne peut appartenir
qu'à un seul segment.
Persona spécifique et vivant (prénom, contexte, contraintes réelles).
Lien explicite entre le segment choisi et le mission statement.

**Pièges fréquents**
- Segmentation démographique pure → faible signal PM
- Segments non mutuellement exclusifs → choix de priorisation impossible
- Persona générique sans contexte ni contraintes spécifiques

---

### 1.2 — Problem Identification

**Ce que c'est**
Mapper le parcours utilisateur ("day in the life", pas pre/during/post générique),
identifier des problèmes spécifiques avec leur contexte émotionnel,
les prioriser par Frequency × Severity,
et les relier au mission statement.

**Ce que l'interviewer teste**
Le candidat distingue-t-il needs (désirs) et problems (obstacles) ?
Va-t-il au-delà du symptôme ?

**Weak**
Confond needs et problems ("les utilisateurs veulent une meilleure recherche").
Journey map générique applicable à n'importe quel produit.
Problème non priorisé ou choix sans justification.

**Good**
Identifie 3 problèmes distincts.
Utilise frequency/severity pour prioriser.
Distingue explicitement need et problem.

**Excellent**
Journey "day in the life" avec contexte spécifique au persona.
Problèmes formulés avec contexte émotionnel ET conséquence concrète.
Lien explicite au mission statement pour justifier la priorisation.

**Pièges fréquents**
- "Les utilisateurs ont besoin de X" → c'est un need, pas un problem
- Journey map trop générique (pre/during/post)
- Choisir le problème le plus facile à résoudre, pas le plus impactant

---

### 1.3 — Solution Development

**Ce que c'est**
Générer des approches vraiment différentes (pas des variations du même concept),
prioriser avec Impact × Effort, définir une V1 concrète avec go-to-market,
et identifier les risques principaux avec leurs mitigations.

**Ce que l'interviewer teste**
La créativité est-elle réelle ou superficielle ?
Le candidat peut-il atterrir sur quelque chose de concret et réaliste ?

**Weak**
Une seule solution proposée immédiatement.
Solutions trop similaires entre elles.
V1 floue ("on pourrait construire une feature qui...").
Pas de lien avec les capacités de l'entreprise.

**Good**
3 solutions distinctes.
Priorisation Impact × Effort justifiée.
V1 délimitée.
Un ou deux risques identifiés.

**Excellent**
Solutions qui exploitent les avantages compétitifs spécifiques de l'entreprise.
V1 suffisamment concrète pour être prototypable.
Risques avec mitigations réalistes.
Lien explicite entre la solution et le mission statement établi au début.

**Pièges fréquents**
- Solutions qui sont en réalité des features, pas des approches différentes
- Ignorer les contraintes de l'entreprise (distribution, tech, business model)
- V1 trop ambitieuse → signal de manque de sens du delivery

---

## Famille 2 — Analytical Thinking

> Mode : **Situational**
> Framework en 4 étapes séquentielles + 1 compétence transversale.
> Durée typique : 45 min, dont ~35 min de travail effectif.
> Questions types : "How would you measure success for Spotify ?",
> "You're a PM at Meta. Set a goal for Instagram Reels.",
> "What should be the North Star metric for DoorDash ?"
>
> ⚠️ Calibrée principalement pour des entretiens de type Big Tech.
> À ajuster selon la cible (startup, scale-up européenne, entreprise AI-first).

---

### 2.1 — Ecosystem Metrics Framework

**Ce que c'est**
Identifier toutes les personas qui tirent de la valeur du produit, définir leurs actions clés,
construire des métriques actionnables, choisir un North Star Metric (NSM),
le critiquer et le protéger avec des guardrail metrics.

**Ce que l'interviewer teste**
Le candidat pense-t-il en système ou uniquement du point de vue d'une seule persona ?
Son NSM est-il honnête sur ses limites ?

**Weak**
Métriques sans timeframe ("nombre d'utilisateurs actifs" sans préciser DAU/WAU/MAU).
NSM basé sur une moyenne ou un ratio — peut croître même si le produit se dégrade.
Oublie des personas clés (ex : créateurs dans une plateforme de contenu).
Aucune guardrail metric.

**Good**
Mappe 3-4 personas avec leurs actions clés.
NSM scalable avec timeframe explicite.
1-2 guardrail metrics identifiées.

**Excellent**
Pour chaque persona : valeur reçue + action clé + métrique actionnable.
Timeframe DWM (daily/weekly/monthly) choisi selon le comportement réel de la persona.
NSM unifie la valeur créée pour toutes les personas ET peut croître indéfiniment.
Critique proactive du NSM : identifie 1-2 façons dont il pourrait être trompeur.
Guardrails qui adressent précisément ces failles — pas des métriques génériques.

**Pièges fréquents**
- NSM basé sur une moyenne ou ratio → faux positif possible
- Guardrails trop génériques ("satisfaction utilisateur") → non actionnables
- Timeframe qui ne reflète pas le comportement réel
  (ex : Spotify = weekly streaming hours, pas daily)

---

### 2.2 — Goal-Setting (Altitude Shift)

**Ce que c'est**
Passer du niveau produit/company au niveau équipe (3-6 mois).
Choisir une persona, mapper son journey en partant du NSM,
identifier des opportunités, les scorer, et décider d'un objectif clair.

**Structure attendue**
1. Choisir une persona + justification (levier sur le NSM)
2. Mapper le journey de cette persona en remontant depuis le NSM event
3. Identifier 3 opportunités de friction ou d'amélioration
4. Scorer chaque opportunité : impact sur NSM × ability to influence
5. Décision claire et assumée + rationale

**Ce que l'interviewer teste**
Le candidat peut-il opérer au niveau exécution, pas seulement stratégie ?
Ses objectifs sont-ils réalistes et directement influençables par une équipe ?

**Weak**
Objectif trop large ("améliorer l'expérience utilisateur").
Pas de lien entre l'objectif et le NSM.
Ne considère pas la faisabilité ou les dépendances cross-teams.
Hésite entre plusieurs options sans trancher.

**Good**
Choisit une persona avec justification.
Identifie 2-3 opportunités et en sélectionne une.
Objectif actionnable sur 3-6 mois.

**Excellent**
Lien explicite entre la persona choisie et le plus grand levier sur le NSM.
Journey mappé en partant du NSM event vers les points de friction en amont.
Scoring appliqué de façon cohérente aux 3 opportunités.
Décision claire — pas de hedging.
Mentionne ce qui pourrait le faire changer d'avis.

**Pièges fréquents**
- Objectifs que l'équipe ne contrôle pas directement
- Choisir l'objectif le plus facile, pas le plus impactant
- Rester au niveau stratégique sans atterrir sur quelque chose d'actionnable

---

### 2.3 — Tradeoff Evaluation

**Ce que c'est**
Structurer une décision analytique sous contraintes — deux options explicites,
données métriques disponibles — identifier la tension, peser les options,
décider clairement en s'appuyant sur le NSM et la mission.

> Distinct de 4.3 Décision sous incertitude (Leadership) qui porte sur des décisions
> humaines et organisationnelles où les données manquent.
> Ici : les données existent, la tension est entre deux directions mesurables.

**Structure attendue (séquence rituelle)**
1. Clarify : décrire la tension concrètement
2. Common Goal : identifier ce que les deux options cherchent à accomplir
3. Frame : pros/cons pour chaque option + impact sur personas et métriques
4. Decision : choix assumé + rationale ancré dans NSM et mission
5. Revisit condition : "I would revisit if..."

**Ce que l'interviewer teste**
Le candidat peut-il décider sous pression avec des données imparfaites ?
Assume-t-il ses choix ou hedge-t-il ?

**Weak**
Présente les pros/cons sans jamais décider.
Décision sans lien avec la mission ou les métriques établies.
Ignore les effets secondaires sur les autres personas.

**Good**
Identifie clairement la tension.
Décide avec une justification cohérente liée au NSM.
Mentionne 1-2 risques de sa décision.

**Excellent**
Formule explicitement le common goal avant de comparer les options.
Effets secondaires sur toutes les personas impactées considérés.
Décision connectée au NSM et à la mission établie en début d'entretien.
Condition de révision précise et crédible.

**Pièges fréquents**
- Hedger ("ça dépend du contexte...") sans jamais trancher
- Ignorer les effets secondaires sur les personas non ciblées
- Décision déconnectée du framework métrique établi en début d'entretien

---

### 2.4 — Debugging / Root Cause Analysis

**Ce que c'est**
Face à une chute de métrique, structurer une investigation :
clarifier le problème, décomposer par dimensions,
générer des hypothèses multiples et ordonnées, identifier comment les tester.

**Ce que l'interviewer teste**
Le candidat est-il méthodique ou intuitif ?
Génère-t-il des hypothèses multiples ou fixe-t-il sur la première explication ?

**Weak**
Fixe immédiatement sur une hypothèse sans décomposer.
Hypothèses sans méthode pour les tester.
Ignore les dimensions clés (géographie, plateforme, segment, temporalité).

**Good**
Clarifie l'ampleur et le timeframe du problème.
Décompose par 2-3 dimensions.
Génère 3-4 hypothèses ordonnées du plus simple au plus complexe.

**Excellent**
Commence par les causes simples avant les complexes
(bug technique avant comportement utilisateur).
Décompose systématiquement : géo, plateforme, segment, temporalité, interne/externe.
Hypothèses formulées de façon testable
("si c'est X, on devrait voir Y dans les données").
Identifie les données nécessaires pour chaque test.
Ne confond pas corrélation et causalité.

**Pièges fréquents**
- Sauter à une hypothèse complexe sans vérifier les causes simples d'abord
- Oublier les causes externes (compétiteurs, événements marché, saisonnalité)
- Hypothèses non testables → signal de pensée floue

---

### 2.5 — Quantitative Reasoning

**Ce que c'est**
Raisonner avec des chiffres en live : estimer un impact, détecter une corrélation
trompeuse, interpréter des métriques en tension sans sauter à une conclusion hâtive.

**Ce que l'interviewer teste**
Le candidat est-il à l'aise avec les chiffres sous pression ?
Distingue-t-il ce que les données disent de ce qu'elles semblent dire ?

**Weak**
Évite les chiffres ou utilise des approximations sans justification.
Confond corrélation et causalité ("DAU monte donc le produit va bien").
Face à deux métriques en tension, choisit arbitrairement sans expliquer.

**Good**
Fait des estimations d'ordre de grandeur raisonnées.
Identifie qu'une corrélation ne prouve pas une causalité.
Reconnaît la tension entre métriques et pose les bonnes questions avant de conclure.

**Excellent**
Calcule un impact approximatif en live avec des hypothèses explicitées
("si rétention +5% sur une base de 10M users, ça représente ~X sessions/semaine").
Identifie proactivement les pièges dans les données présentées.
Face à des métriques en tension (ex : DAU monte, session length baisse),
formule plusieurs interprétations possibles avant de conclure
et identifie ce qu'il faudrait vérifier pour trancher.

**Pièges fréquents**
- Sauter à une conclusion positive sur une seule métrique qui monte
- Faire des calculs trop précis au lieu d'ordres de grandeur (perte de temps)
- Ignorer qu'une métrique peut être manipulée sans que le produit s'améliore réellement

---

## Famille 3 — Technical AI

> Mode : **Situational uniquement**
> Ce n'est pas une évaluation de connaissance pure — c'est une évaluation
> de raisonnement PM face à des contraintes techniques réelles.

---

### 3.1 — LLM Fundamentals

**Ce que c'est**
Comprendre les limites fondamentales des LLMs et traduire ces limites
en décisions produit concrètes.

**Ce que l'interviewer teste**
Le candidat comprend-il les contraintes réelles des LLMs et peut-il
en déduire des implications produit sans qu'on les lui donne ?

**Concepts clés à maîtriser**
- Context window : limite de mémoire par session, implications sur les workflows longs
- Hallucinations : le modèle invente avec confiance — quand c'est acceptable, quand c'est bloquant
- Latence vs qualité : modèles plus puissants = plus lents et plus chers
- Temperature : déterminisme vs créativité selon le use case
- Prompt sensitivity : résultats différents selon la formulation — implications sur la robustesse produit

**Critères Situational**

*Weak* — Utilise le jargon sans pouvoir expliquer les implications produit.
Choisit un modèle sans justification. Ignore les contraintes de coût et latence.
Ne sait pas quand les hallucinations sont critiques vs acceptables.

*Good* — Explique les limites principales en langage clair.
Fait le lien entre limite technique et décision produit.
Identifie quand une hallucination est critique selon le contexte.

*Excellent* — Raisonne sur les trade-offs modèle selon le use case
(rapidité vs qualité vs coût).
Identifie proactivement les cas où le LLM n'est pas la bonne solution.
Traduit chaque limite en contrainte de design spécifique
("context window limitée → on ne peut pas charger tout l'historique
→ on doit implémenter une stratégie de résumé ou de RAG").

**Pièges fréquents**
- Traiter les LLMs comme des bases de données déterministes
- Sous-estimer l'impact des hallucinations sur la confiance utilisateur
- Ignorer le coût à l'échelle ("ça marche en démo" ≠ "ça marche à 1M users")

---

### 3.2 — RAG & Context Engineering

**Ce que c'est**
Comprendre l'architecture RAG, savoir quand l'utiliser,
et raisonner sur ses implications produit — qualité, coût, maintenance.

**Ce que l'interviewer teste**
Le candidat peut-il expliquer pourquoi on utilise RAG et quelles décisions
produit en découlent — sans entrer dans l'implémentation technique ?

**Concepts clés à maîtriser**
- RAG = retrieval + augmentation + generation
- Chunking : découpage des documents — impact direct sur la pertinence des résultats
- Vector DB : stockage sémantique — cherche par sens, pas par mot-clé
- RAG vs fine-tuning : RAG pour données changeantes, fine-tuning pour comportement stable
- Échecs RAG : mauvais retrieval → bonne génération sur mauvais contexte → réponse confiante mais fausse

**Critères Situational**

*Weak* — Confond RAG et fine-tuning.
Ne sait pas pourquoi on utilise RAG plutôt qu'un simple prompt avec tout le contexte.
Ignore les cas d'échec du retrieval.

*Good* — Explique le principe de RAG clairement.
Distingue RAG et fine-tuning avec un exemple.
Identifie que la qualité du retrieval détermine la qualité de la réponse finale.

*Excellent* — Raisonne sur le choix RAG vs fine-tuning selon le use case.
Identifie les failure modes spécifiques au RAG
(mauvais chunking → retrieval irrelevant → réponse fausse mais confiante).
Traduit en décisions produit : comment tester la qualité du retrieval,
comment monitorer les dégradations, comment communiquer à l'utilisateur
quand le système ne trouve pas de contexte pertinent.

**Pièges fréquents**
- Croire que RAG résout les hallucinations — il les réduit mais ne les élimine pas
- Ignorer que le chunking est une décision produit autant que technique
- Sous-estimer le coût de maintenance d'une base documentaire (données qui vieillissent)

---

### 3.3 — AI Evals & Observabilité

**Ce que c'est**
Définir ce que "bon" signifie pour un produit AI, construire un système
d'évaluation, et monitorer la qualité en production — pas juste au lancement.

**Ce que l'interviewer teste**
Le candidat peut-il définir le succès d'un produit AI de façon mesurable ?
Comprend-il que l'évaluation ne s'arrête pas au lancement ?

**Concepts clés à maîtriser**
- LLM-as-Judge : utiliser un LLM pour évaluer les outputs d'un autre LLM
- Golden dataset : ensemble de cas de référence avec réponses attendues
- Métriques de qualité : hallucination rate, relevance, faithfulness, groundedness
- Métriques opérationnelles : latence P50/P95, coût par inference, error rate
- Observabilité : tracer les inputs/outputs en production pour détecter les dégradations
- MVQ (Minimum Viable Quality) : acceptable bar / delight bar / do-not-ship bar

**Critères Situational**

*Weak* — Définit le succès uniquement par des métriques business.
Pas de réflexion sur comment mesurer la qualité des outputs AI.
"On verra en production" — pas de stratégie d'évaluation pré-lancement.

*Good* — Identifie des métriques de qualité AI au-delà du business.
Comprend le principe du LLM-as-Judge.
Distingue évaluation offline (avant lancement) et monitoring online (après).

*Excellent* — Définit un MVQ avec les trois seuils
(acceptable / delight / do-not-ship) adaptés au contexte.
Propose un golden dataset pour les cas critiques.
Raisonne sur les dégradations progressives en production
(model updates, data drift, edge cases qui s'accumulent).
Connecte les métriques AI aux métriques business
("si hallucination rate dépasse X%, on s'attend à Y impact sur la rétention").

**Pièges fréquents**
- Confondre "ça marche en démo" avec "ça marche en production"
- LLM-as-Judge sans golden dataset → évaluation circulaire
- Ignorer que les modèles changent (updates fournisseur)
  et peuvent dégrader silencieusement

---

### 3.4 — Agent Design & Deployment

**Ce que c'est**
Raisonner sur l'architecture d'un agent AI : planning, tools, memory, MCP.
Identifier les failure modes spécifiques aux agents
et concevoir les guardrails appropriés.

**Ce que l'interviewer teste**
Le candidat comprend-il ce qui distingue un agent d'un simple LLM ?
Peut-il anticiper comment un agent va échouer avant que les utilisateurs
ne le découvrent ?

**Concepts clés à maîtriser**
- Agent = LLM + tools + memory + planning loop
- Tools : ce que l'agent peut faire (chercher, écrire, appeler une API, modifier un fichier)
- Memory : court terme (context window) vs long terme (base de données externe)
- MCP (Model Context Protocol) : interface standardisée pour connecter des outils externes
- Planning : comment l'agent décompose une tâche en sous-étapes
- Failure modes : boucles infinies, hallucination d'actions, sur-autonomie, context rot

**Critères Situational**

*Weak* — Confond agent et chatbot.
Ne sait pas identifier les failure modes spécifiques aux agents.
Propose un agent pour tout sans questionner si c'est le bon outil.

*Good* — Explique la différence agent vs LLM simple.
Identifie 2-3 failure modes concrets.
Propose des guardrails basiques (confirmation humaine, limites d'actions).

*Excellent* — Raisonne sur le niveau d'autonomie approprié selon le contexte
(fully autonomous vs human-in-the-loop vs human-on-the-loop).
Identifie proactivement les failure modes selon le type de tools utilisés.
Conçoit les guardrails comme des décisions produit — pas juste techniques :
quand interrompre l'agent, comment communiquer l'incertitude à l'utilisateur,
comment logger pour debugger.
Questionne si un agent est vraiment nécessaire
ou si un workflow déterministe suffit.

**Pièges fréquents**
- Proposer un agent quand un workflow simple suffit — complexité inutile
- Ignorer le context rot : l'agent se dégrade sur les tâches longues
- Sous-estimer l'importance du logging pour debugger les agents en production

---

### 3.5 — High-Stakes Agent Reasoning

**Ce que c'est**
Raisonnement PM spécifique à la construction d'agents dans des domaines
à fortes contraintes — healthcare, legal, finance, éducation.
Comment les contraintes du domaine transforment chaque décision de design.

**Ce que l'interviewer teste**
Le candidat adapte-t-il son raisonnement PM aux contraintes du domaine ?
Comprend-il que les mêmes décisions de design ont des implications
radicalement différentes selon le contexte ?

**Les 5 questions clés à se poser dans un domaine contraint**
1. Quelle est la conséquence d'une erreur ? (bénigne vs irréversible)
2. Qui est responsable légalement si l'agent se trompe ?
3. Quelles données sont utilisées — sont-elles sensibles, réglementées (RGPD, HIPAA) ?
4. Quel niveau d'autonomie est acceptable — et pour qui ?
5. Comment l'utilisateur sait-il quand faire confiance à l'agent vs quand vérifier ?

**Critères Situational**

*Weak* — Applique le même raisonnement que pour un produit grand public.
Ignore les contraintes réglementaires ou les mentionne sans impact sur le design.
MVQ identique quel que soit le domaine.
Ne questionne pas qui est responsable en cas d'erreur.

*Good* — Identifie que les contraintes du domaine changent le design.
Ajuste le MVQ selon la criticité des erreurs.
Mentionne la nécessité de human-in-the-loop dans les cas critiques.

*Excellent* — Raisonne systématiquement sur les 5 questions clés
avant de proposer une solution.
Différencie les décisions où l'agent peut être autonome
de celles qui requièrent une validation humaine obligatoire.
Conçoit l'expérience utilisateur autour de la confiance calibrée.
Anticipe les questions réglementaires comme des contraintes de design.
Propose un plan de validation spécifique au domaine
(experts métier, golden dataset domaine-spécifique, shadow mode avant déploiement).

**Pièges fréquents**
- Traiter la conformité réglementaire comme une checklist post-design
- Proposer une autonomie maximale dans un domaine où l'erreur est critique
- Ignorer que la confiance utilisateur dans un domaine sensible
  se construit différemment — et se perd beaucoup plus vite

---

### 3.6 — AI Product Design (UX d'un produit probabiliste)

**Ce que c'est**
Concevoir l'expérience utilisateur d'un produit dont les outputs sont probabilistes —
gérer l'incertitude dans l'UI, communiquer les erreurs, onboarder un utilisateur
qui ne comprend pas encore ce que le produit peut ou ne peut pas faire.

**Ce que l'interviewer teste**
Le candidat pense-t-il à l'UX d'un produit AI au-delà de "l'IA répond" ?
Comprend-il que le design d'un produit probabiliste est fondamentalement
différent d'un produit déterministe ?

**Concepts clés à maîtriser**
- Confiance calibrée : l'utilisateur doit savoir quand faire confiance et quand vérifier
- Progressive disclosure : ne pas exposer la complexité du modèle d'entrée
- Error states : comment communiquer une erreur AI sans détruire la confiance
- Human-in-the-loop UX : intégrer une validation humaine sans friction excessive
- Onboarding d'un produit probabiliste : calibrer les attentes dès le départ

**Critères Situational**

*Weak* — Design identique à un produit déterministe.
Pas de réflexion sur comment communiquer l'incertitude à l'utilisateur.
Erreurs AI traitées comme des bugs techniques — pas des expériences à designer.

*Good* — Identifie que l'UX d'un produit AI doit gérer l'incertitude explicitement.
Propose des états d'erreur spécifiques aux outputs AI.
Réfléchit à comment calibrer les attentes utilisateur.

*Excellent* — Conçoit une expérience de confiance progressive :
l'utilisateur gagne confiance au fur et à mesure que le produit prouve sa fiabilité.
Distingue les moments où l'UI doit montrer l'incertitude (stakes élevés)
de ceux où elle peut la masquer (stakes faibles).
Onboarding qui calibre les attentes sans sur-promettre.
Error states qui préservent la confiance et guident vers une action corrective.

**Pièges fréquents**
- Masquer systématiquement l'incertitude → destroy trust au premier échec
- Afficher systématiquement l'incertitude → anxiété et réduction de l'adoption
- Onboarding qui promet trop → churn au premier résultat décevant

---

## Famille 4 — Leadership

> Mode : **Behavioral + Situational**
> Deux formats coexistent dans les entretiens Leadership :
> - Behavioral : "Tell me about a time when..." → storytelling ancré dans des expériences réelles
> - Situational : "Imagine que..." → raisonnement en live face à une mise en situation
>
> L'agent peut combiner les deux dans une même session :
> situational d'abord (tester le raisonnement), behavioral ensuite (ancrer dans le vécu).

---

### 4.1 — Influence sans autorité

**Ce que c'est**
Convaincre et aligner des équipes ou stakeholders sans pouvoir hiérarchique.

**Mode Behavioral — ce que l'interviewer teste**
As-tu des preuves réelles d'influence ? Ta story montre-t-elle que tu comprends
les motivations des autres ?

**Critères Behavioral**

*Weak* — Story vague, influence réduite à "j'ai présenté mes arguments", résultat absent.

*Good* — Contexte clair, approche adaptée à la personne, résultat mentionné.

*Excellent* — Identifie explicitement les motivations de l'autre partie.
Actions spécifiques et créatives. Résultat mesurable.
Réflexion sur ce qu'il a appris sur comment influencer ce type de personne.

**Mode Situational — ce que l'interviewer teste**
Ton raisonnement est-il réaliste ? Identifies-tu les enjeux cachés avant d'agir ?

**Critères Situational**

*Weak* — Répond immédiatement sans poser de questions.
Solution idéale sur le papier mais irréaliste.
Ignore les motivations de l'autre partie.

*Good* — Pose 1-2 questions de contexte avant de répondre.
Identifie que l'autre partie a ses propres contraintes.
Propose une approche adaptée.

*Excellent* — Identifie les enjeux cachés (pression de son manager, contraintes techniques,
historique relationnel). Approche différenciée selon le profil.
Anticipe les objections et prépare des réponses.
Sait quand escalader vs quand persister.

**Pièges fréquents**
- Confondre influence et escalade hiérarchique
- Story où le candidat avait en réalité le pouvoir de décider
- En situational : solution trop propre qui ignore la complexité humaine

---

### 4.2 — Gestion de conflits & alignement

**Ce que c'est**
Naviguer un désaccord réel et en sortir avec une décision assumée
et des relations préservées.

**Mode Behavioral — ce que l'interviewer teste**
As-tu géré de vrais conflits ? Maintiens-tu ta position tout en restant ouvert ?

**Critères Behavioral**

*Weak* — Conflit mineur ou évité. Candidat a cédé sans justification. Résolution floue.

*Good* — Conflit réel, position maintenue avec arguments, résolution claire.

*Excellent* — Distingue les moments où il a tenu sa position de ceux où il a changé d'avis
et pourquoi. Préserve la relation tout en assumant la décision.
Réflexion sur ce qu'il ferait différemment.

**Mode Situational — ce que l'interviewer teste**
Comment raisonnes-tu face à un désaccord en temps réel ?

**Critères Situational**

*Weak* — Évite le conflit ou escalade immédiatement.
Cherche un compromis sans identifier la source du désaccord.
Pas de distinction entre désaccord factuel et désaccord de valeurs.

*Good* — Cherche d'abord à comprendre la position de l'autre.
Distingue les faits des opinions.
Propose un processus de résolution clair.

*Excellent* — Identifie le type de conflit (données, priorités, valeurs, ego) avant d'agir.
Approche différente selon le type.
Sait quand un désaccord doit être escaladé vs résolu en bilatéral.
Pense à l'après — comment préserver la relation et la crédibilité des deux parties.

**Pièges fréquents**
- Story où le candidat a toujours raison
- En situational : solution universelle qui ignore le contexte
- Confondre compromis (les deux perdent) et alignement (les deux gagnent)

---

### 4.3 — Décision sous incertitude

**Ce que c'est**
Prendre une décision organisationnelle ou humaine avec des données incomplètes,
assumer ce choix, et l'ajuster si nécessaire.

> Distinct de 2.3 Tradeoff Evaluation (Analytical Thinking) qui porte sur des décisions
> analytiques avec deux options explicites et des métriques disponibles.
> Ici : les données manquent, l'enjeu est humain ou organisationnel,
> la pression vient des personnes et des délais — pas des chiffres.

**Mode Behavioral — ce que l'interviewer teste**
As-tu des preuves que tu agis sous ambiguïté sans attendre la certitude ?

**Critères Behavioral**

*Weak* — Décision prise avec toutes les données disponibles. Résultat toujours positif.
Pas de vraie prise de risque.

*Good* — Incertitude réelle identifiée. Décision assumée avec justification.
Mentionne ce qui aurait pu mal tourner.

*Excellent* — Articule ce qu'il savait vs ne savait pas sur les personnes et l'organisation.
Agit sans attendre la certitude tout en gérant le downside humain.
Assume si la décision était mauvaise.
Réflexion sur comment il calibre son seuil de décision dans des contextes d'équipe.

**Mode Situational — ce que l'interviewer teste**
Comment structures-tu une décision organisationnelle quand les données manquent ?

**Critères Situational**

*Weak* — Demande plus d'information avant de décider.
Reporte la décision. Pas de framework explicite.

*Good* — Identifie ce qu'il sait vs ne sait pas sur le contexte humain.
Propose un framework de décision adapté à l'enjeu organisationnel.
Assume un choix avec réserves.

*Excellent* — Distingue les décisions réversibles (agir vite, corriger après)
des irréversibles (prendre le temps nécessaire) dans un contexte d'équipe.
Identifie le minimum d'information pour décider sans paralyser l'équipe.
Anticipe comment il détectera si la décision est mauvaise
et comment il communiquera le changement de cap.

**Pièges fréquents**
- Décision présentée comme évidente après coup
- En situational : attendre des données parfaites → signal de paralysie managériale
- Toujours un happy ending — signal que le candidat filtre ses stories

---

### 4.4 — Échec & apprentissage

**Ce que c'est**
Parler d'un vrai échec avec lucidité sur ta responsabilité
et ce que ça a changé concrètement.

**Mode Behavioral — ce que l'interviewer teste**
As-tu la maturité d'assumer tes erreurs sans te défausser ni t'auto-flageller ?

**Critères Behavioral**

*Weak* — Fausse faiblesse. Échec collectif sans responsabilité personnelle.
Apprentissage générique. Happy ending qui efface l'échec.

*Good* — Échec réel, responsabilité assumée, apprentissage concret.

*Excellent* — Échec significatif avec impact réel.
Responsabilité précise ("j'ai pris cette décision qui a causé X").
Apprentissage observable dans un comportement changé.
Ton calme et lucide — pas défensif, pas dans l'auto-flagellation.

**Mode Situational — ce que l'interviewer teste**
Comment réagis-tu quand quelque chose se passe mal en temps réel ?

**Critères Situational**

*Weak* — Cherche d'abord à expliquer pourquoi ce n'est pas sa faute.
Minimise l'impact. Pas de plan d'action clair.

*Good* — Assume rapidement sa part de responsabilité.
Identifie les actions correctives immédiates.
Communique proactivement aux stakeholders.

*Excellent* — Distingue ce qui est de sa responsabilité de ce qui ne l'est pas
— sans se défausser ni sur-assumer.
Plan d'action immédiat ET apprentissage systémique pour éviter la récurrence.
Réfléchit à comment communiquer l'échec de façon constructive
à l'équipe et aux stakeholders.

**Pièges fréquents**
- Se défausser sur le contexte ou les autres
- En situational : mode crisis management sans réflexion sur les causes
- Apprentissage qui sonne appris par cœur plutôt que vécu

---

### 4.5 — Storytelling structuré

**Ce que c'est**
Raconter une expérience de façon linéaire, spécifique et mémorable —
avec un contexte clair, des actions concrètes à la première personne,
et un résultat mesurable.

> Sous-skill transversal — s'applique comme couche sur tous les autres
> sous-skills behavioral de la Famille 4. Mode Behavioral uniquement.

**Pourquoi c'est difficile pour les penseurs systémiques**
Tu vois les connexions complexes, les causes multiples, les nuances.
L'entretien demande l'inverse : une ligne narrative simple et séquentielle.
Le risque est de sur-expliquer le contexte ou de sauter aux conclusions
en omettant les étapes intermédiaires — laissant l'interviewer sans fil conducteur.

**Structure attendue (STAR comme outil, pas comme fin)**
- **Situation** : contexte minimal suffisant pour comprendre l'enjeu (30 sec max)
- **Task** : ce qui était attendu de toi spécifiquement
- **Action** : ce que TU as fait — séquentiel, à la première personne
- **Result** : résultat mesurable ou observable + réflexion optionnelle

**Critères**

*Weak* — Mélange contexte général et actions spécifiques sans distinction.
Utilise "on" systématiquement — impossible de voir la contribution personnelle.
Résultat absent, vague ou invérifiable.
Soit trop long (noie l'essentiel), soit trop court (manque de substance).

*Good* — Structure globalement suivie. Actions personnelles identifiables.
Résultat mentionné même si peu précis.

*Excellent* — Situation en 2-3 phrases max.
Actions séquentielles à la première personne.
Résultat avec un chiffre ou signal observable
("l'équipe a livré 2 semaines avant", "le stakeholder a changé de position en réunion").
Capable de raconter la même story en 2 min ou 5 min selon la demande.
Chaque détail choisi sert la démonstration — rien de superflu.

**Pièges spécifiques aux penseurs systémiques**
- Commencer par le contexte macro avant l'enjeu concret → l'interviewer décroche
- Expliquer pourquoi le système a échoué plutôt que ce que tu as fait personnellement
- Ajouter des nuances et des "mais aussi" qui diluent le message principal
- Conclure sur une réflexion complexe plutôt qu'un résultat simple et clair
