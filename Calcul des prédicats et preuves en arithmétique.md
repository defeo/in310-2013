---
layout: post
title: Calcul des prédicats et preuves en arithmétique
---

## Sémantique du calcul des prédicats

Les propositions suivantes sont-elles équivalentes ? Si non, est-ce que l'une
implique (sémantiquement) l'autre ?

1. $$\neg(\exists x. P(x))$$ et $$(\forall x. \neg P(x))$$.

1. $$(\forall x. P(x) \wedge Q(x))$$ et $$((\forall x. P(x)) \wedge (\forall x. Q(x)))$$.

1. $$((\forall x. P(x)) \vee (\forall x. Q(x))$$ et $$(\forall x. P(x) \vee Q(x))$$.

1. $$(\exists x. P(x) \vee Q(x))$$ et $$((\exists x. P(x)) \vee (\exists x. Q(x))$$.

1. $$(\exists x. P(x) \wedge Q(x))$$ et $$((\exists x. P(x)) \wedge (\exists x. Q(x)))$$.

1. $$(\exists x. \forall y. P(x,y))$$ et $$(\forall y. \exists x. P(x,y))$$.


## Forme prénexe

**Rappel :** Une variable est dite *libre* si elle n'est quantifiée par aucun quantificateur (dans son sous-arbre de formation). Elle est dite *liée* sinon. Par exemple, dans le prédicat

$$\forall x. (P(x) \vee Q(y))$$

la variable $$x$$ est liée, tandis que $$y$$ est libre. De façon moins évidente, dans le prédicat

$$(\forall x. P(x)) \vee Q(x)$$

la première occurrence de la variable $$x$$ est liée, tandis que la deuxième est libre (en effet, le quantificateur $$\forall$$ ne porte pas sur elle, car il est dans un sous-arbre différent de l'arbre de formation).

**Pour chacun des prédicats suivants, dessiner l'arbre de formation, puis remplacer chaque variable liée par une nouvelle variable (choisir une lettre pas encore employée).**

1. $$P(x) \vee Q(y)$$.

1. $$(\forall x. P(x)) \vee \neg Q(y)$$.

1. $$\forall x. (P(x) \vee Q(y))$$.

1. $$(\forall x. P(x)) \vee (\exists x. Q(x))$$.

1. $$\forall x. (P(x) \vee Q(x))$$.

----

**Rappel :** Un prédicat est dit en *forme normale prénexe* (en anglais, PNF) s'il est de la forme

$$\Theta a. \Theta b. \dots \Theta z. P(a,b,\dots,z)$$

où les $$\Theta$$ sont des quantificateurs $$\forall$$ ou $$\exists$$, et $$P(a,b,\dots,z)$$ est un prédicat sans quantificateurs. Pour tout prédicat il existe un prédicat sémantiquement équivalent (en logique classique) en PNF ; ce prédicat peut être obtenu à l'aide de quelques transformations élémentaires, que nous listons ci-dessous.

Les équivalences remarquables du calcul des propositions :

- Lois de De Morgan : $$\neg (A \vee B) \equiv \neg A \wedge \neg B, \quad \neg (A \wedge B) \equiv \neg A \vee \neg B$$ ;

- Distributivité : $$A \wedge (B \vee C) \equiv (A \wedge B) \vee (A \wedge C), \quad A \vee (B \wedge C) \equiv (A \vee B) \wedge (A \vee C)$$ ;

- Implication : $$A \to B \equiv \neg A \vee B$$ ;

- Double négation : $$\neg\neg A \equiv A$$.


Les équivalences du calcul des prédicats vues plus haut, en particulier :

- $$\neg\forall x.P \equiv \exists x.\neg P$$ ;

- $$\neg\exists x.P \equiv \forall x.\neg P$$.


Les équivalences concernant la conjonction et disjonction des prédicats :

- $$(\forall x. P) \wedge Q \equiv \forall x. (P \wedge Q)$$ seulement si $$x$$ n'est pas libre dans $$Q$$ ;

- $$(\forall x. P) \vee Q \equiv \forall x. (P \vee Q)$$ seulement si $$x$$ n'est pas libre dans $$Q$$.

Moyennant un rennomage de la variable $$x$$ dans $$P$$, ces deux dernières règles peuvent être appliquées en toute circonstance.

D'autres règles de transformation peuvent être déduites à partir de celles que nous venons de donner.


**Mettre les prédicats suivants en forme normale prénexe.**

1. $$\neg (\forall x. \exists y. (x + y = 1))$$.

1. $$\neg((\forall x. R(x)) \wedge (\forall x. S(x)))$$.

1. $$(\forall x. (R(x) \vee S(y))) \to (\exists x. R(x))$$.

1. $$((\forall x. x \ge y) \wedge (\forall x. x \le y)) \to (\forall x. x = y)$$.


**Prouver les équivalences suivantes.**

1. $$(\exists x. P) \wedge Q \equiv \exists x. (P \wedge Q)$$ seulement si $$x$$ n'est pas libre dans $$Q$$ ;

1. $$(\exists x. P) \vee Q \equiv \exists x. (P \vee Q)$$ seulement si $$x$$ n'est pas libre dans $$Q$$ ;

1. $$(\forall x. P) \to Q \equiv \exists x. (P \to Q)$$ seulement si $$x$$ n'est pas libre dans $$Q$$ ;

1. $$P \to (\forall x. Q) \equiv \forall x. (P \to Q)$$ seulement si $$x$$ n'est pas libre dans $$P$$.


## Prédicats en arithmétique

**Rappel :** lorsqu'on sort du cadre strictement logique pour s'intéresser à d'autres domaines, telle l'arithmétique, on enrichit la notation du calcul des prédicats avec des notations de commodité. Les plus courantes sont

- $$\forall x, y. P(x,y)$$ pour $$\forall x.\forall y. P(x,y)$$ ;
- $$\forall P(x). Q(x)$$, pour $$\forall x. P(x) \to Q(x)$$ ;
- $$\exists P(x). Q(x)$$, pour $$\exists x. P(x) \wedge Q(x)$$ ;

utilisées par exemple pour écrire $$\forall x,y \in \mathbb{N}. (x + y \ge 0)$$. Une autre convention courante consiste à utiliser le symbole $$\Rightarrow$$ pour l'implication, à la place du symbole $$\to$$ qui a déjà trop d'utilisations en algèbre.

Enfin, lorsque un prédicat contient des variables libres, il est sous-entendu que celles-ci sont *quantifiées universellement*. Par exemple, l'affirmation « Si $$n$$ et $$m$$ sont pairs, alors $$n+m$$ est pair » est à entendre comme « Pour tout $$n$$ et $$m$$, si... ».

**Modéliser le langage des mathématiques.**

En utilisant la *signature* $$+,-,\times,=,\ge$$ et les constantes numérales, traduire en langage logique les phrases suivantes.

1. Le carré de tout nombre est positif.
1. $$n$$ divise $$m$$.
2. Un nombre divisible par 8 est divisible par 2.
3. Il existe un nombre pair divisible par 3.
4. Le produit de deux nombres réels est positif si et seulement si ces deux nombres réels sont positifs.
5. Les deux seules solutions de l'équation $$x^2 - 5x + 6 = 0$$ sont 2 et 3.
1. $$a$$ est l'inverse multiplicatif de $$b$$.
1. L'inverse (multiplicatif) de tout nombre est unique.

**Prouver les énoncés suivants.**

1. Il n'existe pas de contre-exemple $$a$$ à l'affirmation « si pour tout $$b$$ le produit $$ab$$ équivaut à 0, alors $$a$$ vaut 0 ».
1. Pour tout couple $$n,m$$ d'entiers, si $$n$$ est pair et $$m$$ est impair, alors $$1+1=2$$.
1. $$\forall a\in\mathbb{Z}. (\exists b.(a = 2b) \wedge \exists c.(a = 2c+1)) \Rightarrow 1+1=0$$.
1. Si le reste de la division de $$a$$ par 3 est 1, et si le reste de la division de $$b$$ par 3 est 2, alors $$a+b$$ est divisible par 3.
1. L'opposé de tout nombre est unique (**suggestion :** utilisez l'absurde).

