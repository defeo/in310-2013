---
layout: post
title: Calculs avec les permutations
---

**Rappel :** une permutation de $$S_n$$ est une bijection de
l'ensemble $$\{1,2,\ldots,n\}$$ vers lui même. La notation la plus
simple pour les permutations est la notation *à deux lignes*: par
exemple la permutation

$$
\sigma = 
\begin{pmatrix}
  1 & 2 & 3 & 4 & 5\\
  2 & 3 & 1 & 5 & 4
\end{pmatrix}
$$

correspond à la fonction $$\sigma(1) = 2$$, $$\sigma(2) = 3$$, $$\sigma(3)
= 1$$, etc.

## Calculer avec les permutations

Soient

$$\sigma_1 =
\begin{pmatrix}
  1 & 2 & 3 & 4\\
  2 & 4 & 3 & 1
\end{pmatrix}
, \quad
\sigma_2 =
\begin{pmatrix}
  1 & 2 & 3 & 4\\
  2 & 1 & 4 & 3
\end{pmatrix}
, \quad
\sigma_3 =
\begin{pmatrix}
  1 & 2 & 3 & 4\\
  3 & 1 & 4 & 2
\end{pmatrix}
$$

1. Calculer $$\sigma_1\circ\sigma_2$$ et $$\sigma_2\circ\sigma_1$$.
2. Cacluler $$(\sigma_1\circ\sigma_2)\circ\sigma_3$$ et $$\sigma_1\circ(\sigma_2\circ\sigma_3)$$.
3. Calculer $$\sigma_1^{-1}$$, $$\sigma_2^{-1}$$ et $$\sigma_3^{-1}$$.

Une *loi binaire* est une loi qui à deux éléments d'un même ensemble
associe un troisième élément. Autrement dit, si $$A$$ est un ensemble,
une loi binaire sur $$A$$ est une fonction $$f:A\times A\to
A$$. L'addition et la multiplication sont des exemples de loi binaire.

4. Une loi binaire $$\bullet$$ est dite *commutative* si $$a\bullet b =
b\bullet a$$ pour tout $$a$$ et tout $$b$$. La loi de composition
sur les permutations est-elle commutative ?
5. Une loi binaire $$\bullet$$ est dite *associative* si $$(a\bullet b)\bullet c =
a\bullet(b\bullet c)$$ pour tout $$a$$, $$b$$ et $$c$$. La loi de composition
sur les permutations est-elle associative ?
6. On dit qu'une loi binaire $$\bullet$$ a un *élément neutre* s'il
existe un $$x$$ tel que $$a\bullet x=x\bullet a=a$$ pour tout $$a$$. La loi
de composition a-t-elle un élément neutre ? Lequel ?

## Décomposition en cycles

**Rappel :** Toute permutation peut être écrite comme une composition
de *cycles* disjoints, de façon unique (à l'ordre des cycles
près). Souvent dans ce contexte on omet le symbole $$\circ$$ pour la
composition et on écrit directement $$(a\;b\;c)(d\;f)$$ à la place de
$$(a\;b\;c)\circ(d\;f)$$. Pour confondre encore plus les idées, on dit
parfois *produit* de cycles à la place de *composition* de cycles,
mais il s'agit bien de la même chose.

1. Décomposer $$\sigma_1$$, $$\sigma_2$$ et $$\sigma_3$$ de l'exercice
précédent en produit de cycles.

2. Exercice inverse : écrire les décompositions en cycles suivantes en
notation à deux lignes:

	- $$(1\;3\;6\;2)$$,
    - $$(1\;2\;6)(4\;5)(3)(6\;7)$$,
    - $$(1\;6)(2)(3\;4\;7\;5)$$,
    - $$(1)(2\;6)(3\;4)(7\;5)$$.

    L'ordre des cycles est-il important ? 

3. Même exercice pour les produits de cycles suivants (non-disjoints,
cette fois-ci) :

	- $$(1\;3)(3\;2)$$,
	- $$(1\;2\;5)(4\;5)(3)(4\;6)$$,
	- $$(1\;2)(2\;3)(3\;4)(3\;4)$$.

	L'ordre des cycles est-il important, maintenant ?

4. Écrire la décomposition en cycles de $$\sigma^{-1}$$ pour chacune des
permutations suivantes :
	
	- $$\sigma = (1\;3\;6\;2)$$,
    - $$\sigma = (1\;2\;6)(4\;5)$$,
    - $$\sigma = (1\;4)(2)(3\;6\;5\;7)$$,
    - $$\sigma = (1)(2\;4)(7\;5)(3\;106)$$.


## Transposition

**Rappel:** Un cycle de longueur deux est aussi appelé une
*transposition*. Il n'est pas difficile de montrer que toute
permutation peut être décomposée (de façon non unique) en produit de
transpositions.

1. Calculer les produits de transpositions suivantes, en
représentation à deux lignes et en décomposition en cycles.

	- $$(1\;2)(4\;3)(2\;5)(3\;6)$$,
	- $$(2\;5)(4\;3)(1\;2)(3\;6)$$,
	- $$(1\;6)(6\;1)(2\;4)(4\;5)$$.

2. Décomposer les cycles suivants en produits de transpositions

	- $$(1\;3\;6\;2)$$,
    - $$(1\;2\;6)(4\;5)(3)(6\;7)$$,
    - $$(1\;6\;2)(3\;4\;7\;5)$$.
	
3. Décomposer $$\sigma_1$$ et $$\sigma_2$$ du premier exercice en produits
de transpositions.

4. Décomposer $$\sigma^{-1}$$ en produits de transpositions pour les
permutations suivantes:

	- $$\sigma = (1\;2)$$,
	- $$\sigma = (1\;2)(3\;4)$$,
	- $$\sigma = (1\;2)(2\;3)$$,
	- $$\sigma = (1\;6)(6\;1)(2\;4)(4\;501)$$.


## Jeu de taquin

Sam Loyd, un auteur de jeux mathématiques américain, est réputé avoir
commercialisé à la fin du XIXième siècle le puzzle suivant, en offrant
une prime de 1000 dollars au premier qui trouverait la solution. Il
s'agit d'une variante du jeu de taquin, inventé par Noyes Chapman vers
1874, comportant 16 cases numérotées, où les cases 14 et 15 sont
inversées et où la 16ième case est manquante.

![](http://upload.wikimedia.org/wikipedia/commons/thumb/9/91/15-puzzle.svg/200px-15-puzzle.svg.png)

Il s'agit de replacer les cases dans le bon ordre, en faisant glisser
une pièce touchant un trou à la place du trou. On se propose dans cet
exercice de vérifier si la résolution de ce puzzle est possible, ou si
monsieur Loyd était sûr de garder ses 1000 dollars. Pour cela, nous
allons étudier utiliser permutations. On admettra le résultat suivant.

**Théorème :** Si $$\sigma$$ est une permutation de $$\mathcal{S}_n$$ qui peut
s'écrire comme produit de transpositions de deux manières différentes
$$\sigma = \tau_1 \circ \cdots\circ\tau_r$$ et $$\sigma = \tau_1 \circ
\cdots\circ\tau_r$$, alors $$r$$ et $$s$$ ont la même parité.

1. Proposer une façon de représenter un mouvement du jeu par une
permutation. Quel est l'ensemble de toutes les permutations ?

1. Comment exprimer la configuration la configuration de départ ?

1. Comment exprimer la configuration recherchée ?

1. Observer les mouvements de la case vide, qu'on va numéroter 16. Que
peut-on dire d'une série de transpositions qui ramène 16 a sa place
(de sa parité, en particulier) ?

1. Conclure.
