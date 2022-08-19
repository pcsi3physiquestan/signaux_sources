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
# Activité : Etudier une modulation en amplitude.
_La correction est en ligne et une simulation permet de joueur sur les paramètres d'une modulation est disponible [ici](https://stanislas.edunao.com/mod/resource/view.php?id=12802)._

Nous allons étudier le principe de décomposition sur un cas simple où un signal se décompose en une somme finie de composantes spectrales.

_La __méthode de linéarisation__ des produits de sinusoïdes, basées sur les relations usuelles en trigonométrie est à maîtriser impérativement. La méthode de tracé du signal est aussi très important._



````{admonition} Exercice 
:class: attention

On considère deux signaux sinusoïdaux $u_1(t)$ et $u_2(t)$ de fréquence $f_1$ et $f_2$ d'amplitude $u_{1m}$ et $u_{2m}$ de phase à l'origine nulle tous les deux. On multiplie les deux signaux $u_S(t) = k u_1(t) \times u_2(t)$ avec k une constante connue.

* Donner les expressions de $u_1(t)$ et $u_2(t)$ puis de $u_S(t)$
* On prend $f_1 = 10 f_2$ et $u_{2m} = 2 u_{1m}$, représenter graphiquement $u_S$. Justifier le terme de modulation en amplitude. Où ce principe est utilisé?
* Montrer que le signal se décompose comme la somme de deux composantes spectrales dont on déterminera la fréquence et l'amplitude.
* Représenter le spectre du signal $u_S$.
````

````{topic} Correction
>__1.__
>Les deux signaux entrant s'écrivent : $u_1(t) = u_{1m} \cos (2 \pi f_1 t)$ et $u_2(t) = u_{2m} \cos (2 \pi f_2 t)$

>Il vient pour le signal de sortie : $u_S(t) = k u_{1m} u_{2m} \cos (2 \pi f_1 t) \cos (2 \pi f_2 t) $

>__2.__

>Le tracé d'une telle fonction ne doit pas nécessiter une calculatrice et doit faire apparaître des caractéristiques précises :
>* On commence par tracer l'__enveloppe__ (trait discontinu) qui correspond à l'amplitude variable $k u_{1m} u_{2m} \cos (2 \pi f_2 t)$ et son opposé (la fonction $u_S(t)$ atteindra ces enveloppes quand $\cos (2 \pi f_1 t)$ sera égale à 1 et -1. Cela dessine les valeurs maximales accessibles, d'où le nom d'enveloppe. Il faut repérer les valeurs maximales et minimales de l'enveloppe, ici $k u_{1m} u_{2m}$ et  $-k u_{1m} u_{2m}$
>* On trace alors la fonction comme un sinusoïde contenu dans l'enveloppe. Il faut faire attention au nombre de sinusoïde dans une période (il doit ici y en avoir 10 car $f_1 = 10 f_2$)

```{figure} ./images/temporelle_module.png
:name: modulation
:align: center
:width: 50%
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
:width: 50%
Spectre du signal modulé
```
````

```{important} 
A retenir

Il faut savoir :
* reconnaître un cas de modulation d'amplitude : un __produit__ de sinusoïdes dont __la fréquence de l'un est grande devant la fréquence de l'autre__.
    * On peut écrire $u_S(t)$ sous la forme : $ \left [ k u_{1m} u_{2m} \cos (2 \pi f_2 t) \right ] \cos (2 \pi f_1 t)$. Puisque $f_2$ est faible, on peut considérer que sur une période du signal rapide de fréquence $f_1$, la grandeur $k u_{1m} u_{2m} \cos (2 \pi f_2 t)$ est quasi-constante et représente donc sur une période, l'amplitude du sinusoïde $ \cos (2 \pi f_1 t)$. Mais comme d'une période à l'autre l'amplitude varie, on parle de __modulation d'amplitude__.
* Le signal lent de fréquence $f_2$ est appelé __signal modulant__ et le signal rapide est appelé __signal porteur.__ Le signal sortant est appelé __signal modulé__.
* réaliser un tracé correct d'un signal modulé en amplitude en tenant du rapport de fréquences
* Linéariser le produit pour obtenir le spectre du signal.
```