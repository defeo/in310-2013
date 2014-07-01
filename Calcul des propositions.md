---
layout: post
title: Calcul des propositions
---

Le **calcul propositionnel** (sporadiquement appelé **logique d'ordre zéro**) est une [théorie *formelle*](Logique mathématique) (au sens où il s'agit de manipuler des *formules*) qui modélise des raisonnements mathématiques simples du type *"si A alors B"*.

Le [Calcul des prédicats](Calcul des prédicats) constitue une généralisation du calcul des propositions à des formules plus complexes du type *"pour tout n, si n a la propriété X alors n a la propriété Y"*.


## Concepts de base

Une **proposition** est une phrase dont on peut affirmer qu'elle est vraie ou fausse. Ainsi "il pleut", "$$n$$ est pair", "$$n>0$$" sont des propositions, mais "le nombre de doigts de la main", "4", "$$f(n)$$" ne le sont pas.

Le calcul des propositions modélise la façon dont le mathématicien raisonne sur la vérité et la fausseté en faisant abstraction des propositions spécifiques qui forment le raisonnement concret. Ce qui compte est exclusivement la forme du raisonnement, ainsi l'affirmation

> **S'il** pleut **ou** il neige, **alors** il y a des nuages

et l'affirmation

> **Si** $$n > 0$$ **ou** $$n < 0$$, **alors** $$n\ne0$$

sont représentées par la même **formule**

> **Si** A **ou** B, **alors** C

où les *variables* A, B, C représentent à la fois les *propositions* "il pleut", "il neige", "$$n > 0$$", etc.

De plus, les **connecteurs** logiques *si*, *alors*, *ou*, etc. sont exprimés par des symboles plutôt que par des mots. Par convention, on utilise les symboles suivants:

|--------------------   |------------------------------------------------------------
|Formule                |Interprétation
|:--------------------: |------------------------------------------------------------
|$$A\to B$$             |  **si** $$A$$ **alors** $$B$$,
|$$A\leftrightarrow B$$ |  $$A$$ **si et seulement si** $$B$$, 
|$$A\wedge B$$          |  $$A$$ **et** $$B$$,
|$$A\vee B$$            |  $$A$$ **ou** $$B$$,
|$$\neg A$$             |  **il n'est pas vrai que** $$A$$. 
|--------------------   |-------------------------------------------------------------

De tous les opérateurs, seul le "ou" mérite quelques mots d'explication en plus. Par $$A$$ **ou** B l'on entend le *ou inclusif* du français c'est à dire qu'au moins l'une des propositions $$A$$ ou $$B$$ doit être vraie, mais possiblement les deux sont vraies. On appelle *ou exclusif* ce qui est souvent exprimé en français par "soit... soit...", ce type d'opérateur est parfois ajouté à la logique propositionnelle avec la notation $$A\oplus B$$. Voici des exemples

|Type de ou  |Notation      |Exemple
|----------- |-----------   |-------------------------------------------------------
|ou inclusif |$$A\vee B$$   |j'y vais, ou bien on y va ensemble
|ou exclusif |$$A\oplus B$$ |tu manges le potage ou tu vas te coucher immédiatement!
|----------- |-----------   |-------------------------------------------------------



## Définitions

En calcul des propositions, comme dans tout autre [système formel](Logique mathématique), on fait une distinction minutieuse entre [*syntaxe*, *sémantique* et *métalogique*](Logique mathématique#syntaxe-sémantique-méta). Ainsi, la **syntaxe** décrit la façon correcte de former les formules, la **sémantique** donne l'interprétation des formules, et la **métalogique** est le processus de raisonner sur le système formel avec des outils externes (la pensée mathématique, en général, ou plus formellement une autre logique formelle plus puissante que le calcul des propositions).


### Syntaxe

La syntaxe du calcul propositionnel est composée des éléments suivants:

- Une liste infinie (mais [dénombrable](Cardinalité)) de **propositions atomiques** (ou **formules atomiques**), en général représentées par les lettres de l'alphabet $$A, B, \ldots$$,
- Des **opérateurs logiques**, en général $$\wedge, \vee, \to, \neg$$.

Une **proposition** (ou **formule**, ou **formule bien formée**) est

- soit une proposition atomique,
- soit le résultat de la combinaison d'un opérateur logique avec deux (ou une dans le cas de $$\neg$$) propositions (non nécessairement atomiques).

Ainsi $$A$$, $$A\wedge B$$, $$(A\wedge B)\vee (\neg C)$$ sont des propositions, mais $$A B$$, $$\wedge\wedge A$$ ne le sont pas.

**Remarque:** les parenthèses ne font pas partie du calcul des propositions, elles sont simplement là pour rendre les formules non-ambiguës, i.e. pour indiquer dans quel ordre les opérateurs ont été appliqués pour obtenir la formule.

Pour réduire le nombre de parenthèses, on assigne une précédence par défaut aux opérateurs. Ainsi $$\neg$$ a la précédence la plus haute, ensuite viennent $$\wedge$$ et $$\vee$$ avec la même précédence, et enfin $$\to$$. Par conséquent la formule

$$\neg A \wedge B \to C$$

doit être lue comme

$$((\neg A) \wedge B) \to C.$$

Puisque on peut démontrer que $$\wedge$$ et $$\vee$$ sont associatifs, un autre usage courant consiste à ne pas écrire les parenthèses d'une chaîne de ces opérateurs, à moins que l'on ne s'intéresse à l'arbre de formation d'une formule. Ainsi

$$A \wedge B \wedge C$$

peut être aussi bien interprété comme

$$(A \wedge B) \wedge C,$$

que comme

$$A \wedge (B \wedge C),$$

ce qui ne change rien dans un contexte où l'on s'intéresse à la vérité de la formule puisque ces deux formules sont *sémantiquement équivalentes*.

**Attention:** Par contre, il est toujours incorrect d'écrire

$$A \vee B \wedge C,$$

puisque les deux parenthésages possibles de la formule n'ont pas la même sémantique. De la même façon, la formule

$$A \to B \to C$$

est ambiguë pusique les deux parenthésages ne sont pas équivalents. Beaucoup de textes adoptent la convention de l'*associativité à droite*, ainsi la seule lecture possible de la formule ci-dessus serait

$$A \to (B \to C)$$

mais remarquez que ceci est purement une convention, que nous allons éviter d'utiliser dans ce texte.

De manière générale on inclut aussi dans la syntaxe des **axiomes** et des **règles d'inférence**. Ces deux derniers éléments seront détaillés plus loin lorsque nous parlerons de [preuves](#preuve).


### Sémantique

La sémantique consiste à attacher des *interprétations* aux formules du calcul propositionnel. Le système qui est obtenu en considérant toutes les interprétations possibles est aussi appelée *logique Boléenne* ou *algèbre de Boole*.

Formellement, un **modèle** (parfois on dit une **interprétation**) d'une proposition est l'affectation d'une valeur $$0$$ ou $$1$$ (appelée **valeur de vérité**) à chacune de ses propositions atomiques. En général, affecter $$A$$ à $$1$$ est interprété comme l'affirmation "il est vrai que $$A$$", affecter $$A$$ à $$0$$ comme "il n'est pas vrai que $$A$$".

On parle aussi de **modèle du calcul propositionnel** lorsque on assigne une valeur de vérité à chacune de ses propositions atomiques (souvenez-vous qu'il y en a une infinité). 

Un modèle d'une formule $$\phi$$ lui associe une valeur de vérité définie [inductivement](Récursivité) de la façon suivante:

- Si $$\phi = A$$ pour une formule atomique $$A$$, alors la valeur de vérité de $$\phi$$ est la valeur de vérité de $$A$$;
- Si $$\phi = \neg\psi$$ pour une formule $$\psi$$, alors $$\phi$$ vaut $$1$$ si et seulement si $$\psi$$ vaut $$0$$;
- Si $$\phi = \psi \wedge \chi$$ pour deux formules $$\psi$$ et $$\chi$$, alors $$\phi$$ vaut $$1$$ si et seulement si $$\psi$$ et $$\chi$$ valent $$1$$;
- Si $$\phi = \psi \vee \chi$$ pour deux formules $$\psi$$ et $$\chi$$, alors $$\phi$$ vaut $$0$$ si et seulement si $$\psi$$ et $$\chi$$ valent $$0$$;
- Si $$\phi = \psi \to \chi$$ pour deux formules $$\psi$$ et $$\chi$$, alors $$\phi$$ vaut $$0$$ si et seulement si $$\psi$$ vaut $$1$$ et $$\chi$$ vaut $$0$$.

Les quatre dernières règles peuvent être résumées de façon très simple par la méthode familière des **tableaux de vérité**:

| $$\psi$$ | $$\neg\psi$$ 
|:--------:|:------------:
|   0      |   1
|   1      |   0

| $$\psi$$ | $$\chi$$ | $$\psi\wedge\chi$$
|:--------:|:--------:|:------------------:
|   0      |   0      |      0
|   0      |   1      |      0
|   1      |   0      |      0
|   1      |   1      |      1

| $$\psi$$ | $$\chi$$ | $$\psi\vee\chi$$
|:--------:|:--------:|:------------------:
|   0      |   0      |      0
|   0      |   1      |      1
|   1      |   0      |      1
|   1      |   1      |      1

| $$\psi$$ | $$\chi$$ | $$\psi\to\chi$$
|:--------:|:--------:|:------------------:
|   0      |   0      |      1
|   0      |   1      |      1
|   1      |   0      |      0
|   1      |   1      |      1


**Remarque:** Dans ce qui précède nous avons utilisé des lettres grecques $$\phi,\psi,\chi$$ pour indiquer des formules quelconques. Ces lettres *ne font pas partie de la syntaxe* du calcul propositionnel: elles sont plutôt une notation que nous nous donnons en dehors du calcul (i.e., à un niveau méta) pour parler du calcul.

Si un modèle $$\mathcal{M}$$ associe la valeur $$1$$ à une formule donnée, on dit que la formule est *vraie dans le modèle $$\mathcal{M}$$*. On dit qu'une formule est

- **satisfaisable** s'il existe un modèle qui la rend vraie;
- une **tautologie** si elle est vraie dans tout modèle (on dit aussi que la formule est **valide**);
- **falsifiable** s'il existe un modèle qui la rend fausse;
- une **antilogie** s'il n'existe aucun modèle qui la rend vraie.

Par example $$A\wedge B$$ est *satisfaisable* et *falsifiable* car $$A=1$$ et $$B=1$$ la rendent vraie, mais $$A=0$$ et $$B=1$$ la rendent fausse. $$A \vee \neg A$$ est non seulement *satisfaisable*, mais aussi une tautologie. $$A\wedge\neg A$$ est une *antilogie*.


## Théorie de la preuve

### Vérité

La notion de **vérité** est une notion purement sémantique. On a déjà discuté de la notion de *tautologie*, introduisons maintenant un peu de notation. Soit $$\phi$$ une formule, l'écriture

$$\models\phi$$

signifie que $$\phi$$ est une tautologie. Si $$\phi$$ et $$\psi$$ sont deux formules, on dit que $$\phi$$ est une **conséquence logique** de $$\psi$$ (ou **conséquence sémantique** ou, plus informellement, que $$\psi$$ **implique** $$\phi$$) si tout modèle qui satisfait $$\psi$$ satisfait aussi $$\phi$$. Si $$\phi$$ est une conséquence logique de $$\psi$$ on écrit

$$\psi\models\phi;$$

intuitivement, ceci signifie que $$\phi$$ est vraie *sous l'hypothèse* $$\psi$$. Plus généralement, si $$\Gamma$$ est un ensemble de formules on dit que $$\phi$$ est une conséquence logique de $$\Gamma$$, et on note $$\Gamma\models\phi$$, si tout modèle qui satisfait *toutes* les formules de $$\Gamma$$ satisfait aussi $$\phi$$.

Lorsque on a $$\phi\models\psi$$ et $$\psi\models\phi$$, on dit que $$\phi$$ et $$\psi$$ sont **(sémantiquement) équivalentes**, ce qui, selon les textes, est noté

$$\phi\equiv\psi \quad\text{ou}\quad \phi\Leftrightarrow\psi \quad\text{ou}\quad \phi=\psi$$

**Attention:** aucun des symboles $$\models,\equiv,\Leftrightarrow,=$$ ne fait partie de la logique. Ce sont tous des symboles *métalogiques* qui permettent d'exprimer des propriétés qu'on a démontrées *en dehors* de la syntaxe du calcul des propositions (par exemple en lisant les tables de vérité). On fera surtout attention à ne pas confondre $$A\to B$$ et $$A\leftrightarrow B$$, qui sont des propositions du calcul des propositions, avec $$A\models B$$ et $$A\Leftrightarrow B$$.

Pour donner un exemple, il suffit de regarder les tables de vérité pour se rendre compte que $$A\wedge B\models A\vee B$$, mais que la réciproque n'est pas vraie ($$A\wedge B$$ n'est pas une conséquence logique de $$A\vee B$$). 

#### Équivalences remarquables

Voici une liste de formules qui peuvent être prouvées *sémantiquement équivalentes* en comparant leur tables de vérité (remarquez qu'à la place de $$A$$ et $$B$$ on peut substituer n'importe quelles formules $$\phi$$ et $$\psi$$ non nécessairement atomiques).

|Propriété | Formules équivalentes
|-|:-:|:-:
|Double négation    |$$A$$                    |$$\neg\neg A$$
|Commutativité      |$$A\wedge B$$            |$$B\wedge A$$
|                   |$$A\vee B$$              |$$B\vee A$$
|Associativité      |$$(A\wedge B)\wedge C$$  |$$A\wedge(B\wedge C)$$
|                   |$$(A\vee B)\vee C$$      |$$A\vee(B\vee C)$$
|Distributivité     |$$A\wedge(B\vee C)$$     |$$(A\wedge B)\vee(B\wedge C)$$
|                   |$$A\vee(B\wedge C)$$     |$$(A\vee B)\wedge(B\vee C)$$
|Lois de de Morgan  |$$\neg(A\wedge B)$$      |$$\neg A\vee\neg B$$
|                   |$$\neg(A\vee B)$$        |$$\neg A\wedge\neg B$$
|Implication        |$$A\to B$$               |$$\neg A \vee B$$
|Transposition      |$$A\to B$$               |$$\neg B \to \neg A$$
|Exportation        |$$(A \wedge B) \to C$$   |$$A \to (B \to C)$$

**Exercice:** écrivez les tables de vérité des formules ci-dessus et vérifiez qu'elles sont effectivement équivalentes.


#### Implication sémantique et implication matérielle

On appelle **implication matérielle** le connecteur logique $$\to$$, pour le distinguer du 
concept de **conséquence logique** (aussi dite **implication sémantique** ou **logique**) défini plus haut. De la table de vérité de l'implication matérielle, et de la définition même de conséquence logique, on déduit immédiatement que

$$\psi\models\phi \quad\text{si et seulement si} \models\psi\to\phi.$$

Ce métathéorème constitue la justification sémantique du [raisonnement hypothétique](#preuve) qu'on va définir plus tard.


### Preuve

Les notions de *modèle* et de *vérité* permettent de vérifier aisément (et en temps fini) si une formule donnée est valide ou pas. Néanmoins, quand un mathématicien veut montrer un théorème il ne commence pas par énumérer toutes les possibilités et vérifier que son énoncé reste vrai pour n'importe quel choix. C'est pour modéliser la façon de raisonner du mathématicien qu'on a développé le concept de **preuve formelle**.

La méthode de démonstration universellement acceptée en mathématiques est la **méthode axiomatique**. Un ensemble de *vérités élémentaires*, appelées **axiomes**, est initialement établi et accepté comme *vrai* sans aucune preuve. En général sont choisis comme axiomes des énoncés qui paraissent évidents et consensuels, comme par exemple *"deux droites parallèles ne se rencontrent en aucun point"*.

À partir des axiomes, le mathématicien s'autorise à déduire des **théorèmes** en appliquant un nombre restreint et universellement accepté de *formes de raisonnement* appelées **règles d'inférence** ou **de déduction**. La **preuve** est donc une opération purement **syntaxique** qui transforme des formules vraies en d'autres formules vraies indépendamment de la notion sémantique de **vérité**.

On appelle **système de déduction** (ou **de preuve**) le choix d'un ensemble d'axiomes et de règles d'inférence. Pour tout système formel ce choix n'est pas unique, et plusieurs systèmes de preuve différents vont aboutir aux mêmes théorèmes.

#### Exemple

Un exemple de système de preuve (incomplet) pour le calcul des propositions est donné par ce *schéma d'axiomes*:

$$\phi\to\phi$$

et par les trois règles d'inférence suivantes:

$$\dfrac{\phi\wedge\psi}{\phi}G_\wedge,
\qquad\dfrac{\phi\wedge\psi}{\psi}D_\wedge,
\qquad\dfrac{\phi\quad\psi}{\phi\wedge\psi}I_\wedge.$$

**Note:** Un **schéma d'axiomes** est une façon compacte de représenter l'infinité d'axiomes obtenus en substituant $$\phi,\psi,\dots$$ par des formules quelconques.

**Note:** Les règles d'inférence se lisent de la façon suivante: en haut de la barre il y a les **prémisses**, c'est à dire les formules qu'on suppose déjà démontrées (ou des axiomes); en bas de la barre il y a la **conséquence**, c'est à dire la formule qui découle des prémisses; à droite de la barre il y a (éventuellement) le **nom** de la règle, qui sert à l'identifier dans une preuve complète.

Un exemple de preuve correcte dans ce système est le suivant:

1. **Axiome:** $$A\to A$$
2. **Axiome:** $$B\to B$$
3. **Règle $$I_\wedge$$ appliquée à 1 et 2:** $$(A\to A)\wedge(B\to B)$$
4. **Règle $$I_\wedge$$ appliquée à 3 et 2:** $$((A\to A)\wedge(B\to B))\wedge(B\to B)$$


#### Définitions et notations

Un **système de preuve** pour le calcul propositionnel est la donne d'un ensemble (éventuellement infini ou même vide) de formules appelées **axiomes**, et d'un nombre fini de **règles d'inférence**. Une formule est un **théorème**

- si elle est un *axiome*, ou
- si elle est la conséquence d'une *règle d'inférence* dont les premisses sont elles mêmes des théorèmes.

La suite des applications des *règles d'inférence* qui permettent de dériver un *théorème* $$\phi$$ est appelée une **preuve** de $$\phi$$. Si on a une preuve de $$\phi$$, on dit aussi qu'on a **démontré** $$\phi$$.

Si une formule $$\phi$$ est un théorème on écrit

$$\vdash\phi.$$

Si $$\Gamma$$ est un ensemble de formules, et si en ajoutant $$\Gamma$$ aux axiomes on peut démontrer une formule $$\phi$$, on dit que $$\phi$$ est **dérivable** de $$\Gamma$$ (ou que $$\phi$$ est une **conséquence syntaxique** de $$\Gamma$$) et on écrit

$$\Gamma\vdash\psi.$$

Ces notations vont être utiles par la suite pour définir des règles d'inférence un peu plus complexes.

On dit qu'un système de preuve est

- **correct** si tout théorème est une tautologie,
- **complet** si toute tautologie est un théorème,
- **syntactiquement complet** si pour toute formule $$\phi$$, au moins une formule parmi $$\phi$$ et $$\neg\phi$$ est démontrable.

Le système de preuve donné dans l'exemple précédent n'est pas complet car on ne peut pas, par exemple, prouver $$A\vee\neg A$$. Nous étudions maintenant quelques systèmes de preuves complets classiques.

#### Systèmes à la Hilbert

Les systèmes à la Hilbert se caractérisent par l'emploi d'un nombre relativement grand d'axiomes (de trois jusqu'à la dizaine) et d'une seule règle d'inférence

$$\dfrac{\phi\to\psi\qquad\phi}{\psi}$$

appelée *modus ponens* ou *coupure*.

Voici un exemple de système à la Hilbert dû à Frege:

1. $$\phi \to (\psi \to \phi)$$,
2. $$(\phi \to (\psi \to \chi)) \to ((\phi\to\psi) \to (\phi\to\chi))$$,
3. $$(\phi \to (\psi \to \chi)) \to (\psi \to (\phi\to\chi))$$,
4. $$(\phi\to\psi) \to (\neg\psi\to\neg\phi)$$,
5. $$\neg\neg\phi \to \phi$$,
6. $$\phi \to \neg\neg\phi$$.

Un exemple de *preuve* dans le système de Frege est le suivant:

$$
\dfrac{
  (A\to(B\to A)) \to ((A\to B) \to (A\to A))
  \qquad
  A\to(B\to A)
}{(A\to B) \to (A\to A)}
$$

où les deux prémisses du *modus ponens* sont obtenues par instanciation des axiomes 2 et 1 respectivement. On conclut que

$$\vdash(A\to B) \to (A\to A).$$

Dans un système à la Hilbert on peut facilement démontrer des résultats conditionnels où un théorème est *dérivable* d'une ou plusieurs hypothèses. Par exemple on montre qu'à partir des hypothèses $$A\to B$$ et $$A$$ on peut prouver $$A$$ (ce qui est un peu bête, admettons); en symboles:

$$(A\to B),A \vdash A.$$

La preuve procède ainsi (par convention, on met une barre au dessus des prémisses qui ne sont pas des axiomes):

$$
\dfrac{
  \dfrac{
    \dfrac{
      (A\to(B\to A)) \to ((A\to B) \to (A\to A))
      \qquad
      A\to(B\to A)
    }{(A\to B) \to (A\to A)}
    \qquad
    \overline{A\to B}
  }{A\to A}
  \qquad
  \overline{A}
}{A}
$$

##### Théorème de déduction

Dans tous les systèmes à la Hilbert on peut prouver un *méta-théorème*, dit **théorème de déduction** qui permet de simplifier grandement les preuves. Ce théorème affirme que si $$\phi$$ et $$\psi$$ sont deux formules on peut prouver

$$\phi\vdash\psi$$

si et seulement si on peut prouver

$$\vdash\phi\to\psi.$$

La construction explicite qui permet de passer d'une preuve à l'autre est assez longue et compliquée, mais il est important (et confortant) de savoir qu'elle existe et est automatique.

On remarque que le théorème de déduction donne un fondement formel à une technique de preuve utilisée largement en mathématiques: pour prouver un énoncé de la forme $$A\to B$$, on commence par supposer $$A$$ et on démontre $$B$$.

##### Système de Łukasiewicz

Łukasiewicz démontre que les trois schémas d'axiomes suivants

1. $$\phi \to (\psi \to \phi)$$,
2. $$(\phi \to (\psi \to \chi)) \to ((\phi\to\psi) \to (\phi\to\chi))$$,
3. $$(\neg\phi\to\neg\psi) \to (\psi\to\phi)$$,

avec le *modus ponens* sont suffisants à définir un système de preuve complet (et correct). Dans les [Exercices](Exercices) on peut trouver quelques questions autour de systèmes similaires à celui de Łukasiewicz.


##### Extensions conservatives des systèmes à la Hilbert

Par souci de coincision, il est classique de présenter les systèmes à la Hilbert en utilisant seulement les symboles $$\to$$ et $$\neg$$. Il est bien évidemment possible d'étendre ces systèmes en ajoutant les symboles $$\wedge,\vee,\leftrightarrow$$, etc. Pour cela, il suffit d'ajouter quelques axiomes de plus; par exemple:

1. $$(\phi\to\psi) \leftrightarrow (\neg\phi\vee\psi)$$,
2. $$(\phi\vee\psi) \leftrightarrow \neg(\neg\phi\wedge\neg\psi)$$,
3. $$(\phi\leftrightarrow\psi) \to (\phi\to\psi)$$,
4. $$(\phi\leftrightarrow\psi) \to (\psi\to\phi)$$.



#### Déduction naturelle

Les systèmes à la Hilbert ont attiré deux critiques majeures. Prémièrement, l'utilisation exclusive des symboles $$\to$$ et $$\neg$$ donne lieu à un langage assez aride et difficile à manier. Deuxièmement, et de façon plus importante, les preuves dans ces systèmes ont tendence à faire un usage massif du *théorème de déduction* afin d'en réduire la longueur. Ceci introduit un argument *méta-logique* à l'intérieur de la preuve formelle, qui ne peut être éliminé qu'en appliquant une construction longue et compliquée.

La **déduction naturelle** est un système de preuve complet qui s'efforce d'imiter la façon naturelle de penser. Son élément caractéristique est l'**internalisation** du *théorème de déduction* dans une règle d'inférence appelée **règle de déduction**: ceci transporte le théorème de déduction du niveau de la *méta-logique* à celui de la *logique formelle*.

L'ensemble d'axiomes de la *déduction naturelle* est **vide**, ses règles d'inférence sont les suivantes.

|Affaiblissement           |$$\dfrac{\Gamma\vdash\phi}{\Gamma\cup\{\psi\}\vdash\phi}W$$
|Tiers exclus              |$$\dfrac{}{\Gamma\vdash\phi\vee\neg\phi}T$$
|Preuve par l'absurde      |$$\dfrac{\Gamma\cup\{\phi\}\vdash\psi\wedge\neg\psi}{\Gamma\vdash\neg\phi}A$$
|Introduction du *et*      |$$\dfrac{\Gamma\vdash\phi \qquad\Gamma\vdash\psi}{\Gamma\vdash\phi\wedge\psi}I_\wedge$$
|Élimination du *et*       |$$\dfrac{\Gamma\vdash\phi\wedge\psi}{\Gamma\vdash\phi}L_\wedge$$
|                          |$$\dfrac{\Gamma\vdash\phi\wedge\psi}{\Gamma\vdash\psi}R_\wedge$$
|Introduction du *ou*      |$$\dfrac{\Gamma\vdash\phi}{\Gamma\vdash\phi\vee\psi}L_\vee$$
|                          |$$\dfrac{\Gamma\vdash\psi}{\Gamma\vdash\phi\vee\psi}R_\vee$$
|Élimination du *ou*       |$$\dfrac{\Gamma\vdash\phi\vee\psi \qquad \Gamma\vdash\phi\to\chi\quad \Gamma\vdash\psi\to\chi}{\Gamma\vdash\chi}E_\vee$$
|Modus ponens              |$$\dfrac{\Gamma\vdash\phi \qquad\Gamma\vdash\phi\to\psi}{\Gamma\vdash\psi}M$$
|Déduction                 |$$\dfrac{\Gamma\cup\{\phi\}\vdash\psi}{\Gamma\vdash\phi\to\psi}D$$

La notation est quelque peu alourdie par la nécessité d'exprimer la *règle de déduction*. Par exemple la règle de déduction dit que si $$\Gamma$$ est un ensemble de formules, et si on peut prouver $$\psi$$ sous les hypothèses de $$\Gamma\cup\{\phi\}$$, alors on prouve $$\phi\to\psi$$ sous les hypothèses de $$\Gamma$$ seul.


## Complétude et correction

## Bibliographie

Pour les définitions de base et les algèbres de Boole, on pourra consulter un quelconque des ouvrages conseillés dans la [Bibliographie](Bibliographie).

Pour une exposition claire et complète sur la distinction entre syntaxe et sémantique et sur la théorie de la preuve, je conseille les chapitres 4 et 5 du livre *Mathématiques pour l’Informatique* de *Arnold* et *Guessarian*, en particulier la section 5.2: à quelques choix de nomenclature et de notation près (par exemple le symbole $$\to$$ est remplacé par $$\supset$$), les arguments y sont traités de la même façon que dans cette page. Malheureusement ce livre contient assez peu d'exercices sur cette partie.

*Introduction à la logique* de *David*, *Nour* et *Raffali* est un autre très bon texte. Le chapitre 1 couvre toute la théorie de la preuve faite dans ce cours, plus la théorie de la preuve du [Calcul des prédicats](Calcul des prédicats). Il propose aussi beaucoup d'exercices pour vous entraîner avec les séquents. Le chapitre 2 couvre la sémantique et les théorèmes de complétude. L'étudiant intéressé pourra les lire rapidement.

Allez voir aussi les pages des [Exercices](Exercices) et des [Exercices Corrigés](Exercices Corrigés).