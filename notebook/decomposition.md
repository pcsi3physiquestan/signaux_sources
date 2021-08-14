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

# Décomposition spectrale d'un signal physique

## Principe de la décomposition spectrale


````{admonition} Principe général
:class: important
Le principe de la décomposition spectrale est de décomposer un signal $s(t)$ en une somme de signaux sinusoïdaux de __fréquences différentes.__
````

Ce principe présente énormément d'intérêt que nous verrons par la suite. 

Citons déjà qu'une fois un signal décomposé en somme de sinusoïde (on parle de __composantes spectrales__), on obtient plusieurs __gammes de fréquences__ associées à chaque composante spectrale qui vont donner des informations sur le type de signal étudié.

````{admonition} Exemples de décomposition spectrale : cas fini
:class: note

On peut décomposer un signal en une somme finie de signaux sinusoïdaux. Le signal $s(t) = A sin^3 (t)$ peut s'écrire comme la somme :

$$
s(t) = \frac{3A}{4} \sin t - \frac{A}{4} \sin 3t 
$$
````

````{admonition} Exemples de décomposition spectrale : cas infini discret
:class: note

On peut décomposer un signal en une somme infinie discrète de signaux sinusoïdaux. Le signal définie sur $[0 ;T]$ par

$$
s(t) = \begin{cases} A \textrm{ si }x \in [0;T/2]\\ -A  \textrm{ si }x \in [T/2;T]\end{cases}
$$
	et reproduit à l'infini (signal créneau) peut s'écrire comme la somme :

$$
s(t) = \frac{4 A}{\pi} \sum\limits_{n=0}^{+ \infty} \frac{1}{2n + 1} \sin{[(2n+1) \frac{2 \pi}{T}t]}
$$

````

````{dropdown} Complément - Cas infini continu
On peut décomposer un signal en une somme infinie continue de signaux sinusoïdaux, c'est-à-dire que la somme s'effectue sur toutes les valeurs de fréquences appartenant à $\mathbb{R}$. Une telle somme est plus délicate à écrire avec les connaissances actuelles car cela nécessite l'utilisation d'intégrale et des nombres complexes.

Néanmoins, à titre d'exemple, la fonction $s(t) = \frac{sin(t)}{t}$ peut se décomposer comme une somme de sinusoïde de toutes les fréquences (réelles) comprises entre $f = 0$ et $f = 1/2 Hz$ avec la même amplitude pour chacune. Dans ce cas, on parlera de __spectre continu__.

````


````{attention}
:class: dropdown
Comme le montre l'exemple du signal créneau, il convient de ne pas confondre la  __période/fréquence/pulsation__ du signal si celui-ci est périodique et la __période/fréquence/pulsation__ d'une composante spectrale de la décomposition. Il y a un lien entre ces grandeurs comme on le verra par la suite mais elles sont différentes et ne représentent pas la même chose.
````

## Spectre d'une fonction

````{admonition} Fondamental : Spectre d'un signal
:class: important

Pour une fonction s(t) à spectre discret, on appelle spectre de s, l'ensemble des couples $\{(f_s,c_S(f))\}$ associant chaque fréquence f des sinusoïdes de la décomposition spectrale à leur amplitude $c_S(f)$.

On représente le spectre d'une fonction s(t)  en représentant chaque coefficient $c_S(f)$ en fonction de la fréquence correspondante $f_s$.

L'indice s est marqué ici pour bien montrer que les fréquences et les amplitudes dépendent du signal s considéré.
````

````{admonition} Cas de la fonction sinus cube
:class: note

```{figure} ./images/spectre_sinus_cube.png
:name: sinus_cube
:align: center
Spectre du sinus cube
```
Le spectre de la fonction $sin^3$ est $\{(f_1 = \frac{1}{2\pi}, c(f_1) =\frac{3}{4}),(f_2 = \frac{3}{2\pi}, c(f_2) =\frac{1}{4})\}$.

```{dropdown} Remarques
* On pourrait écrire plus simplement $\{(\frac{1}{2\pi}, \frac{3}{4}),( \frac{3}{2\pi}, \frac{1}{4})\}$
* On tient pas compte du signe (-) car__ l'amplitude est toujours définie comme positive__. Le signe modifie la phase à l'origine (de $\pi$) mais celà n'apparaît pas dans le spectre.
```
````

````{admonition} Cas de la fonction créneau
:class: note
```{figure} ./images/spectre_creneau.png
:name: spectre_creneau
:align: center
Spectre d'un créneau
```
Le spectre de la fonction créneau $s(t) = \begin{cases} A \textrm{ si }x \in [0;T/2]\\ -A  \textrm{ si }x \in [T/2;T]\end{cases}$ fait correspondre aux fréquences $\frac{2n+1}{T}$ l'amplitude $\frac{4A}{\pi(2n+1)}$ avec $n \in \mathbb{N}$.

On peut tracer le spectre en remarquant qu'il s'agit de tracer la fonction $\frac{4A}{\pi T f}$ en fonction de la fréquence $f$ et de ne prendre que les valeurs entières impaires.
````

````{important}
:class: dropdown
__Valeur moyenne__

Sur une représentation spectrale, la valeur moyenne se lit à la fréquence 0.
````

## Méthode : étudier une modulation en amplitude.

Nous allons étudier le principe sur un cas simple où un signal se décompose en une somme finie de composantes spectrales\footnote{__Composante spectrale__ - Une composante spectrale est une fonction sinusoïdale sommée avec d'autres composantes pour donner un signal s(t).

La __méthode de linéarisation__ des produits de sinusoïdes, basées sur les relations usuelles en trigonométrie est à maîtriser impérativement. La méthode de tracé du signal est aussi très important.

On considère deux signaux sinusoïdaux $u_1(t)$ et $u_2(t)$ de fréquence $f_1$ et $f_2$ d'amplitude $u_{1m}$ et $u_{2m}$ de phase à l'origine nulle tous les deux. On multiplie les deux signaux $u_S(t) = k u_1(t) \times u_2(t)$ avec k une constante connue.


````{admonition} Exercice 
:class: attention

* Donner les expressions de $u_1(t)$ et $u_2(t)$ puis de $u_S(t)$
* On prend $f_1 = 10 f_2$ et $u_{2m} = 2 u_{1m}$, représenter graphiquement $u_S$. Justifier le terme de modulation en amplitude. Où ce principe est utilisé?
* Montrer que le signal se décompose comme la somme de deux composantes spectrales dont on déterminera la fréquence et l'amplitude.
* Représenter le spectre du signal $u_S$.
````

````{dropdown} Correction
>__1.__
>Les deux signaux entrant s'écrivent : $u_1(t) = u_{1m} \cos (2 \pi f_1 t)$ et $u_2(t) = u_{2m} \cos (2 \pi f_2 t)$

>Il vient pour le signal de sortie : $u_S(t) = k u_{1m} u_{2m} \cos (2 \pi f_1 t) \cos (2 \pi f_2 t) $

>__2.__
```{admonition} Méthode
:class: tip
On doit savoir quand on est face à une telle fonction : il s'agit d'un __produit__ de sinusoïde et __la fréquence de l'un est grande devant la fréquence de l'autre__.

On peut écrire $u_S(t)$ sous la forme : $ \left [ k u_{1m} u_{2m} \cos (2 \pi f_2 t) \right ] \cos (2 \pi f_1 t)$. Puisque $f_2$ est faible, on peut considérer que sur une période du signal rapide de fréquence $f_1$, la grandeur $k u_{1m} u_{2m} \cos (2 \pi f_2 t)$ est quasi-constante et représente donc sur une période, l'amplitude du sinusoïde $ \cos (2 \pi f_1 t)$. Mais comme d'une période à l'autre l'amplitude varie, on parle de __modulation d'amplitude__.

Le signal lent de fréquence $f_2$ est appelé __signal modulant__ et le signal rapide est appelé __signal porteur.__ Le signal sortant est appelé __signal modulé__.
```

>Le tracé d'une telle fonction ne doit pas nécessiter une calculatrice et doit faire apparaître des caractéristiques précises :
>* On commence par tracer l'__enveloppe__ (trait discontinu) qui correspond à l'amplitude variable $k u_{1m} u_{2m} \cos (2 \pi f_2 t)$ et son opposé (la fonction $u_S(t)$ atteindra ces enveloppes quand $\cos (2 \pi f_1 t)$ sera égale à 1 et -1. Cela dessine les valeurs maximales accessibles, d'où le nom d'enveloppe. Il faut repérer les valeurs maximales et minimales de l'enveloppe, ici $k u_{1m} u_{2m}$ et  $-k u_{1m} u_{2m}$
>* On trace alors la fonction comme un sinusoïde contenu dans l'enveloppe. Il faut faire attention au nombre de sinusoïde dans une période (il doit ici y en avoir 10 car $f_1 = 10 f_2$)

```{figure} ./images/temporelle_module.png
:name: modulation
:align: center
Modulation d'amplitude
```
>__3.__
> Pour obtenir le spectre lorsque le signal est un produit de sinusoïde, il faut procéder par __linéarisation__.
>
>$$
u_S(t) = \frac{k u_{1m} u_{2m} }{2} \left( \cos(2 \pi (f_1 + f_2) t) + \cos(2\pi (f_1 - f_2)t) \right)
$$
>
>Le spectre est donc composée de deux composantes de fréquences $f_1 + f_2 = 11 f_2$ et $f_1 - f_2 = 9 f_2$. Elles ont toutes les deux une amplitude $ \frac{k u_{1m} u_{2m} }{2} $.

```{figure} ./images/spectre_module.png
:name: spectre_mod
:align: center
Spectre du signal modulé
```
````
 

## Décomposition des signaux périodiques : Série de Fourier

````{admonition} Fondamental : Décomposition en série de Fourier
:class: important

Tout signal périodique s(t) de période T se décompose en une somme infinie (série) de cosinus et de sinus de périodes T/n où n est un entier. On appelle la série correspondante: série de Fourier.

$$
s(t) = a_0 + \sum\limits_{n=1}^{+ \infty} (a_s(n) \cos(\frac{2 \pi n}{T}t)+b_s(n) \sin(\frac{2 \pi n}{T}t))
$$

Ou, comme on l'écrira souvent pour pouvoir représenter le spectre :

$$
s(t) = a_0 + \sum\limits_{n=1}^{+ \infty} (c_s(n) \cos(\frac{2 \pi n}{T}t + \phi_s(n)))
$$

$$
s(t) = a_0 + \sum\limits_{n=1}^{+ \infty} (c_s(n) \sin(\frac{2 \pi n}{T}t + \psi_s(n)))
$$

Les coefficients $c_s(n)$ sont les amplitudes des composantes spectrales comme étudiées précédemment. On les définit ici directement en fonction de n qui correspond au rang de la n-ième composante spectrale et on les appelle des __coefficients de Fourier__.

Dans le cas d'un signal périodique, ces composantes sont appelées des __harmoniques__. La composante spectrale de même période que le signal (elle existe forcément) est appelée __fondamental.__

On reconnaîtra que $a_0$ correspond à la valeur moyenne du signal.
````

````{admonition} Exemple : Spectre du signal triangle
:class: note
Outre le cas du signal créneau, on peut aussi citer le cas du signal triangle $s(t) = \begin{cases} a (t - \frac{T}{4})  \textrm{ si }x \in [0;T/2]\\ -a (t - \frac{3T}{4})  \textrm{ si }x \in [T/2;T]\end{cases}$ dont les coefficients de Fourier sont $c_s(n) = \frac{8aT}{\pi^2 n^2}$ lorsque n est impaire et 0 sinon.

On remarquera et c'est important de le retenir que les harmoniques du signal créneau ont une amplitude qui décroît en $1/n$ et les harmoniques du triangle ont une amplitude qui décroît en $1/n^2$ : on tend donc plus vite vers la forme triangle que vers la forme créneau.
````

````{hint}
:class: dropdown
Vous pourrez trouver ici une [simulation réalisée en Geogebra](https://www.geogebra.org/m/R4FGkE3u) permettant de construction une fonction périodique par sommation de ses composantes de Fourier.
````

## Méthode : Tracer le spectre d'un signal périodique

````{admonition} Exercice 
:class: attention

On reprend le signal triangle :

$$
s(t) = \begin{cases} a (t - \frac{T}{4})  \textrm{ si }x \in [0;T/2]\\ -a (t - \frac{3T}{4})  \textrm{ si }x \in [T/2;T]\end{cases}
$$

dont la décomposition en série de Fourier est :

$$
s(t) = \frac{8 a T}{\pi^2} \sum\limits_{n=0}^{+ \infty} \frac{1}{(2n + 1)^2} \sin{[(2n+1) \frac{2 \pi}{T}t]}
$$

1. Justifier que ce signal est périodique de période T.
2. Représenter le spectre du signal.
````

````{dropdown} Correction - Méthode
1. __Période du signal__ : Dans une décomposition en série de Fourier, la période du signal correspond à la période du fondamental, donc de la composante de plus basse fréquence. Ici, c'est pour n=0, soit une pulsation (on ne peut lire directement qu'une pulsation) $\frac{2\pi}{T}$ donc une période T
2. __Tracé du spectre__ : La méthode pour tracé un spectre connaissant la décomposition spectrale est :
	1. _Déterminer les pulsations puis les fréquences qui composent le spectre._ On a ici une série. La pulsation de chaque terme se lit dans le sinus $\sin[\boxed{(2 n +1) \frac{2\pi}{T}} t]$. Les pulsations du signal sont donc les pulsations $(2 n +1) \frac{2\pi}{T}$ donc les fréquences $f_n = \frac{2n+1}{T}$. On peut alors placer les fréquences sur un graphique.
```{figure} ./images/spectre_triangle_freq.png
:name: triangle_freq
:align: center
Fréquences du signal
```

2. _Déterminer les amplitudes associées à des fréquences._ Si les fréquences sont isolées, on lit l'amplitude comme le facteur devant le sinus/cosinus. Dans le cas d'une somme, on va déterminer la fonction qui associe le n-ième rang (puis la fréquence) à l'amplitude. Ici l'amplitude de chaque sinusoïde a pour expression $c(n) = \frac{8aT}{\pi^2(2n+1)^2}$. L'étude précédente ($2n+1 = f_n T$) permet d'exprimer $c_n$ en fonction de $f_n$:

$c(f_n) = \frac{8aT}{\pi^2 T^2 f_n^2}$

On trace alors la fonction $c(f)$ et on trace des traits représentant les amplitudes pour les composantes spectrales réellement présentes.

```{figure} ./images/spectre_triangle.png
:name: triangle_freq_2
:align: center
Fréquences du signal
```
````