---
layout: post
title: Définitions récursives
---

## Suites récurrentes

**Rappel :** On définit les [nombres de Fibonacci](Induction et récursion#suite-de-fibonacci) par la récurrence suivante :

- $$F(0) = 0$$,
- $$F(1) = 1$$,
- $$F(n) = F(n-1) + F(n-2)$$.

Prouver les identités suivantes:

1. $$\sum_{i=0}^n F(i) = F(n+2) - 1$$ pour tout $$n\ge0$$.

1. $$\sum_{i=0}^n F(i)^2 = F(n)F(n+1)$$ pour tout $$n\ge0$$.

1. $$F(n)^2 = F(n-1)F(n+1) + (-1)^{n+1}$$ pour tout $$n>0$$.

1. $$1 < \frac{F(n+1)}{F(n)} < 2$$ pour tout $$n>2$$.


## Définitions récursives

Donner une définition récursive des fonctions $$f:\mathbb{N}\to\mathbb{N}$$ suivantes :

1. $$f(n) = 2^n$$,
1. $$f(n) = n!$$.

-----

Donner une définition récursive des propriétés suivantes :

1. $$n$$ est une puissance de $$10$$.
1. $$n$$ est pair.
1. L'écriture décimale de $$n$$ ne contient que des $$1$$.


## Ordres bien fondés

**Rappel :** un ordre sur un ensemble $$A$$ est *bien fondé* si tout sous-ensemble de $$A$$ contient (au moins) un élément minimal (i.e., un élément n'ayant pas d'élément plus petit que lui dans le sous-ensemble). De façon équivalente, un ordre est bien fondé s'il n'existe pas de chaîne strictement décroissante infinie.

Dire si les ordres suivants sont bien fondés :

1. L'ordre usuel sur les nombres naturels.
1. L'ordre usuel sur les nombres rationnels.
1. L'ordre sur $$\mathbb{N}\times\mathbb{N}$$ (les paires de naturels) défini par $$(a,b)<(c,d)$$ si et seulement si $$a<c$$ et $$b<d$$.
1. L'ordre alphabétique sur les mots.
1. Un ordre quelconque sur un ensemble fini.


## Entiers de Peano

**Rappel :** Les entiers de Peano sont définis récursivement à partir des seuls symboles $$0$$ (zéro) et $$S$$ (successeur). L'addition de deux entiers de Peano est définie récursivement par

- $$n + 0 = n$$,
- $$n + S(m) = S(n + m)$$.

Définir le produit de deux entiers de Peano.

