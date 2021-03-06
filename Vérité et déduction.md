---
layout: post
title: Vérité et déduction
---

## Vérité et implication sémantique

**Rappel:** une *tautologie* est une formule qui prend la valeur vrai
dans toutes les interprétations (pour chaque manière d’affecter des
valeurs de vérité à ses variables). Une formule est *satisfaisable*
ssi elle prend la valeur vrai pour au moins une interprétation,
*falsifiable* si elle prend la valeur faux pour au moins une
interprétation. C’est une *antilogie* ssi elle ne prend la valeur vrai
pour aucune valuation.

**Parmi les formules suivantes, indiquer lesquelles sont des
*tautologies*, des *antilogies*, *satisfaisables* ou *falsifiables*.**

1. $$\neg p \vee p$$,
1. $$\neg p \wedge q$$,
1. $$\neg p \wedge p$$,
1. $$(p \to q) \vee (q \to p)$$,
1. $$p \wedge p$$.
1. $$(p \to q) \to (\neg q \to \neg q)$$,

--------

**Soient $$p$$ et $$q$$ deux formules. Parmi les affirmations suivantes,
lesquelles sont vraies (au niveau metalogique)?**

Si l'affirmation est vraie, montrer un exemple à l'aide des tables de
vérité et justifier pourquoi c'est vrai dans le cas général. Si
l'affirmation est fausse, donner un contre-exemple à l'aide des tables
de vérité.

1. $$p$$ est une *tautologie* si et seulement si sa négation est une
*antilogie*.
1. Si $$p$$ et $$q$$ sont *satisfaisables*, alors $$p\wedge q$$ est *satisfaisable*.
1. Si $$p$$ et $$q$$ sont des *tautologies*, alors $$p\wedge q$$ est une tautologie.
1. Si $$p\vee q$$ est une tautologie, alors au moins l'une de $$p$$ ou $$q$$ est une tautologie.
1. Si $$p\leftrightarrow q$$ est une tautologie, alors $$p$$ et $$q$$ sont des tautologies.

---------

**Rappel:** Dans la suite on va utiliser la notation $$\models p$$ pour
signifier "$$p$$ est une tautologie". Soit $$q$$ une autre formule, on dit
que $$p$$ est une *conséquence logique* de $$q$$ si toutes les
interprétations qui rendent vraie $$q$$ rendent aussi vraie $$p$$. On
utilise la notation $$q\models p$$ pour signfier $$p$$ est une conséquence
logique de $$q$$. Plus généralement, on peut mettre plusieurs formules
en prémisse, ainsi $$q,r,s\models p$$ veut dire que toute interprétation
qui rend vraies $$q$$, $$r$$ et $$s$$ **simultanément** rend aussi vraie $$p$$.

**Attention:** le symbole $$\models$$ est un symbole meta: il ne fait
pas partie du [Calcul des propositions](). Ainsi il est strictement
interdit d'écrire des horreurs du style $$(A \models B)\to(\models A\to
B)$$.

**Soient $$p$$ et $$q$$ deux formules. Parmi les affirmations suivantes,
lesquelles sont vraies (au niveau metalogique, bien sûr)?**

1. $$p \models p$$,
1. $$p\wedge q \models p$$,
1. $$p,q\models p$$,
1. $$p\vee q \models p$$,
1. $$p\to q \models p$$,
1. $$(p \vee \neg p) \to q \models q$$,
1. $$\neg p \wedge p\models q$$.


Même exercice qu'avant, mais esquissez seulement les preuves.

1. $$p,q\models r$$ si et seulement si $$(p\wedge q)\models r$$,
1. $$p\models q$$ si et seulement si $$p\to q$$ est une tautologie,
1. Si $$p\models r$$, alors $$p\wedge q \models r$$,
1. Si $$p\models r$$, alors $$p\vee q \models r$$,
1. Si $$p\models r$$ et $$q\models r$$, alors $$p\vee q\models r$$,
1. $$p\models q$$ et $$p\models r$$ si et seulement si $$p\models q\wedge r$$,
1. $$p\models q$$ si et seulement si $$p\models q\vee r$$,
1. Si $$p\models r$$ et $$\neg p\models r$$, alors $$r$$ est une tautologie,
1. Si $$p\models q$$ et $$p\models \neg q$$, alors $$\models\neg p$$,
1. Si $$p\models q$$ et $$q\models r$$, alors $$p\models r$$,


## Déduction naturelle

**Rappel:** Soit $$\Gamma$$ une liste de formules (éventuellement vide)
et soit $$p$$ une formule. On dit que $$\Gamma$$ **prouve** $$p$$, et on
note $$\Gamma\vdash p$$, si $$p$$ peut être déduit par *déduction
naturelle* à partir des formules de $$\Gamma$$. On rappelle ici un
ensemble de *règles* pour la déduction naturelle.

|Hypothèse                 |$$\dfrac{}{\Gamma,\phi\vdash\phi}H$$
|Affaiblissement           |$$\dfrac{\Gamma\vdash\phi}{\Gamma,\psi\vdash\phi}W$$
|Tiers exclus              |$$\dfrac{}{\Gamma\vdash\phi\vee\neg\phi}T$$
|Double négation           |$$\dfrac{}{\neg\neg p\vdash p}D_\neg$$
|Preuve par l'absurde      |$$\dfrac{\Gamma,p\vdash q \wedge\neg q}{\Gamma\vdash\neg p }A$$
|Introduction du *et*      |$$\dfrac{\Gamma\vdash\phi \qquad\Gamma\vdash\psi}{\Gamma\vdash\phi\wedge\psi}I_\wedge$$
|Élimination du *et*       |$$\dfrac{\Gamma\vdash\phi\wedge\psi}{\Gamma\vdash\phi}L_\wedge$$
|                          |$$\dfrac{\Gamma\vdash\phi\wedge\psi}{\Gamma\vdash\psi}R_\wedge$$
|Introduction du *ou*      |$$\dfrac{\Gamma\vdash\phi}{\Gamma\vdash\phi\vee\psi}L_\vee$$
|                          |$$\dfrac{\Gamma\vdash\psi}{\Gamma\vdash\phi\vee\psi}R_\vee$$
|Élimination du *ou*       |$$\dfrac{\Gamma\vdash\phi\vee\psi \qquad \Gamma\vdash\phi\to\chi\quad \Gamma\vdash\psi\to\chi}{\Gamma\vdash\chi}E_\vee$$
|Modus ponens              |$$\dfrac{\Gamma\vdash\phi \qquad\Gamma\vdash\phi\to\psi}{\Gamma\vdash\psi}M$$
|Déduction                 |$$\dfrac{\Gamma,\phi\vdash\psi}{\Gamma\vdash\phi\to\psi}D$$



**Écrire les preuves formelles des affirmations suivantes.**

1. $$p\wedge q \vdash p$$,
1. $$p\vdash p\vee q$$,
1. $$\vdash (p\wedge q) \to p$$,
1. $$p\to q, p \vdash q$$,
1. $$p \vdash q \to p$$ (**suggestion:** considérer l'affaiblissement),
1. $$p \vdash \neg\neg p$$ (**suggestion:** utiliser l'absurde),
1. $$\vdash p \to (q \to p)$$,
1. $$p,\neg p \vdash \neg q$$,
1. $$p,\neg p \vdash q$$ (**suggestion:** utiliser la double négation et le modus ponens),
1. $$\vdash (p\to q) \to (\neg p \to \neg q)$$ (très dur, l'absurde est la clef).

**En vous appuyant sur les preuves formelles prouvées auparavant,
démontrer les affirmations suivantes**

1. Si $$n$$ est strictement positif, alors $$n\ne 0$$.
1. $$n=3m$$ implique que $$n$$ est pair, mais $$n$$ est impair alors $$3m\ne n$$.

## Purs et pires

Un petit exercice pour vous distraire. Sur l’île de Puro-Pira, il y a
deux types d’habitants : les Purs, qui disent toujours la vérité, et
les Pires, qui mentent toujours.

**Que peut-on déduire des rencontres suivantes?**

1. Bob dit: nous sommes tous les deux des Pires.
1. Alice dit: je suis une Pure et Bob est un Pire.
1. Alice dit: si je suis une Pure, alors Bob est un Pire.

**Trouver une phrase qui…**

1. ne peut être dite ni par un Pur ni par un Pire.
1. peut être dite par un Pur mais aussi par un Pire.
