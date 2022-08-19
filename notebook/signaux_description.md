---
jupytext:
  encoding: '# -*- coding: utf-8 -*-'
  formats: ipynb,md:myst
  split_at_heading: true
  text_representation:
    extension: .md
    format_name: myst
    format_version: 0.13
    jupytext_version: 1.10.3
kernelspec:
  display_name: Python 3
  language: python
  name: python3
---

# Description générale

## Signal physique

````{sidebar} Signal et grandeurs
La grande variété des signaux physiques et des systèmes pouvant être étudiés implique des technologies très différentes et des domaines d'études variés (optique et électromagnétisme, mécanique, thermodynamique... ).  
Si les principes et définitions fondamentaux à l'étude de tel ou tel phénomène physique nécessite une présentation plus approfondies du domaine et ne seront étudiés que dans des chapitres ultérieurs, on peut néanmoins faire ressortir un certain nombre de caractéristiques générales utiles à l'étude de ces différents domaines.

Ainsi, __tout signal physique peut être associé à une ou plusieurs grandeurs physiques supposées mesurables__. La variation de l'intensité de ces grandeurs est la mesure de l'information transportée.
````
````{important} __Signal physique__
Un signal physique est une représentation physique qui transporte une "information" depuis une source vers un destinataire.
````


````{topic} Exemples de signaux physiques et grandeurs associées
Les signaux présentés ici ne sont pas exhaustifs et les grandeurs associées non plus:

* __Signal électrique.__ Grandeur associées: Tension (V) et Intensité (A)
* __Signal électromagnétique.__ Grandeur associées: Champ magnétique (T) et Champ électrique ($V.m^{-1}$)
* __Signal acoustique.__ Grandeur associées: Surpression (Pa) et Vitesse ($m.s^{-1}$)
* __Signal mécanique.__ Grandeur associées: Position (m) et Vitesse ($m.s^{-1}$)
````

````{topic} Types de signaux
* __Signal analogique__
    *Un signal analogique est un signal à "temps continu", c'est-à-dire qu'il peut être représenté par une fonction mathématique à variable réelle (en général le temps):

\begin{align}
	s:	\mathbb{R}	&\longrightarrow \mathbb{R}\\
	    t  &\longrightarrow s(t)
\end{align}

* __Signal numérique__
    *Un signal numérique est un signal à "temps discret", c'est-à-dire qu'il n'est connu que pour des instants successifs. Sa représentation est alors une série de valeur successive (une suite):

\begin{align*}
	s:	\mathbb{N}	&\longrightarrow \mathbb{R}\\
		n 			&\longrightarrow s_{n}
\end{align*}
En général, l'indice n est associé à un temps de mesure.
````

## Signal périodique

````{important} __Signal périodique__

Un signal analogique est dit périodique s'il existe une grandeur T telle que pour tout instant t on a l'égalité: $s(t+T)=s(t)$

La grandeur T est appelée __période__ du signal et son inverse f=1/T est la __fréquence__ du signal (nombre de fois où le signal réalise les mêmes variations en une seconde).

````

````{important} __Valeur moyenne et efficace d'un signal périodique__

* La valeur moyenne d'un signal périodique est définie par:

$$
\left\langle S \right\rangle = \frac{1}{T} \int_{t=0}^{t=T}S(t) dt
$$

On peut interpréter une telle valeur comme la valeur constante que devrait avoir une fonction constante qui aurait la même aire sous la courbe. D'où le nom de valeur moyenne.

* La valeur efficace d'un signal périodique est définie par:

$$
S_{eff} = \sqrt{\left\langle S^2 \right\rangle} = \sqrt{\frac{1}{T} \int_{t=0}^{t=T}S^2(t) dt}
$$

L'interprétation de cette grandeur est plus délicate (considérations énergétiques). Elle sera présentée par la suite.
````

````{important} __Propriété de la valeur moyenne (Admis)__
La valeur moyenne est un opérateur linéaire. Ainsi pour deux signaux $s_1(t)$ et $s_2(t)$. La valeur moyenne du signal $s(t) = \lambda_1 s_1(t) + \lambda_2 s_2(t)$ est :

$$
\left\langle s \right\rangle = \lambda_1 \left\langle s_1 \right\rangle + \lambda_2 \left\langle s_2 \right\rangle
$$

__Ce n'est pas le cas de la valeur efficace.__
````