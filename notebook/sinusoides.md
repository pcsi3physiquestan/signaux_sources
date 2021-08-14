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

# Signaux sinusoïdaux


````{admonition} Définition : Forme mathématique d'un signal sinusoïdal
:class: tip

Un signal analogique est dit sinusoïdal, si la fonction décrivant la grandeur associée est de la forme :

\begin{equation}
s(t) = S_m \cos \left ( \omega t +\phi_0 \right )
\end{equation}
````

````{admonition} Fondamental : Caractéristiques d'un signal sinusoïdal
:class: important

L'expression mathématique précédente fait apparaître des caractéristiques d'un sinusoïde :

* $S_m$ est appelée amplitude du signal.
* $\omega t +\phi$ est appellée phase du signal.
* $\omega$ est la pulsation du signal, elle est reliée à la période et la fréquence du signal $T=\frac{2 \pi}{\omega}=\frac{1}{f}$
* $\phi$ est appelée phase à l'origine. Il correspond à la phase du signal à $t=0$ (ou à l'écart de phase, déphasage, (en radians) avec une fonction sinusoïdal qui serait ici maximale en $t=0$).

```{figure} ./images/sinusoide_vm_0.png
:name: sinusoide
:align: center
Sinusoïde
```
````

````{note}
:class: dropdown
* On peut utilise la fonction $sin$ au lieu de la fonction cosinus. Il faudra néanmoins adapter la notion de phase à l'origine.

* Il arrive qu'on désigne comme signal sinusoïdal un signal de forme $s(t) = S_m \cos{(\omega t +\phi)} + S_0$ où $S_0$ est appelé valeur moyenne. Ceci est notamment important en TP. Le terme de valeur moyenne a, comme on le verra ensuite, le même sens que la définition précédente.

* Un signal constant $S_0$ peut être vu comme un signal sinusoïdal de fréquence\ldots  nulle. Cette conception sera fondamental pour la suite.
````


````{attention}
:class: dropdown
__L'amplitude n'est PAS l'écart à l'axe des abscisses dans le cas général.__ Si l'on considère le cas où l'on a ajouté une valeur moyenne, ce n'est pas vrai.
```{figure} ./images/sinusoide_vm_1.png
:name: sinusoide_l
:align: center
:width: 50%
Sinusoïde avec valeur moyenne
```
````

## Signal sinusoïdal - Représentation de Fresnel

````{admonition} Fondamental : Représentation de Fresnel d'un signal sinusoïdal
:class: important

La représentation de Fresnel de la grandeur sinusoïdale s(t) à l'instant t est la représentation dans un plan d'un vecteur $\overrightarrow{S}$ tel que :
* la norme est l'amplitude de s(t) $S_m$
* le vecteur fait avec l'axe des abscisses un angle $\phi = \omega t + \phi_0$ soit la phase du signal.

```{figure} ./images/fresnel_fixe.png
:name: fresnel_fixe
:align: center
:width: 50%
Représentation de Fresnel
```

Très souvent, on travaillera avec la représentation de Fresnel à l'instant $t=0$.
````

````{note}
:class: dropdown

```{figure} ./images/fresnel.gif
:name: fresnel_mobile
:align: center
Evolution temporelle
```
Remarquons que lorsque le temps avance, la phase augmente et l'amplitude est constante. La représentation de Fresnel tourne. La vitesse angulaire de rotation dans le plan de Fresnel est la pulsation $\omega$. D'où l'intérêt de cette grandeur.

Au bout d'une période, la phase a tourner de $2\pi$ soit une variation de phase $\Delta \phi = \omega T = 2 \pi$. D'où la relation entre période et pulsation.
````

### Méthode - Etudier les caractéristiques d'un sinusoïde

L'objectif est
* d'apprendre à écrire correctement l'expression mathématique d'un sinusoïde connaissant ou en mesurant ses caractéristiques.
* de faire l'inverse : obtenir les caractéristiques d'un sinusoïde et tracer son graphique à partir de son expression mathématique.

````{admonition} Exercice 
:class: attention
Donner l'expression mathématique s(t):
1. d'un sinusoïde de pulsation $4\omega$, d'amplitude 2a et de phase à l'origine $-\pi/5$.
2. d'un sinusoïde de période $2T/3$, d'amplitude 4a (si rien n'est précisé, on considère que la phase à l'origine est nulle).
3. d'un sinusoïde de fréquence 3f, d'amplitude 2a, de valeur moyenne - $S_1$ et de phase à l'origine $\pi/3$.
````

````{dropdown} Correction
> 1. $s(t) = 2a \cos {(4 \omega t - \frac{\pi}{5})}$
> 2. La pulsation vaut alors $\omega = \frac{6\pi}{2T}$ donc $s(t) = 4a \cos {(\frac{3\pi}{T} t )}$
> 3. La pulsation vaut alors $\omega = 2\pi \times 3f$ donc $s(t) = 2a \cos {(6\pi f t + \frac{\pi}{3})} - S_1$
````

````{attention}
:class: dropdown
Il faut faire attention à bien différencier le sens physique d'une grandeur et les notations utilisées. Ainsi, même si dans cet exercice on utilise les notations T et f, elles __ne correspondent pas__ aux périodes et fréquences des signaux. Le sens physique s'obtient par analyse des équations mathématiques, pas par analyse du nom de la grandeur.

On essaiera par contre de conserver des noms de grandeurs cohérentes avec l'unité (T reste un temps et f une fréquence). Mais même sur ce point, le sens physique est très important (une même notation pouvant être utilisée pour deux grandeurs : R peut être un rayon ou une résistance électrique...
````

````{admonition} Exercice 
:class: attention
Réaliser la représentation graphique de s(t) pour les expressions précédentes. On prendra a=1, T=1, $\omega = \pi$, f=1, $S_1=2$
````

````{dropdown} Correction
```{figure} ./images/sinusoide_trace.png
:name: sinus_trace
:align: center
```
````

````{note}
:class: dropdown
__Lien retard temporel et phase__

La valeur moyenne déterminer l'axe de symétrie du sinusoïde et l'amplitude l'écart à cet axe de symétrie (les valeurs extrêmes).

On a utilisé la relation $\phi_0 = - \omega t_1$ pour calculer le retard temporel où $t_1$ est le temps où la fonction cosinus sera maximale (puisque la phase est alors nulle).

On a ensuite représenté des points particuliers pour faciliter le tracé (points extrêmes, passage par la valeur moyenne) en utilisant la valeur de la période de chaque signal à partir de $t_1$.
````

````{admonition} Exercice 
:class: attention

Donner les caractéristiques (période, fréquence, pulsation, amplitude, valeur moyenne, phase à l'origine) des signaux suivants :

1. $s(t) = \frac{1}{2k + 1} \sin{(2k+1) \omega t}$
2. $s(t) = 7\omega \cos(2f t + 3)$
3. $s(t) = 3a \cos(\frac{2\pi n}{T}t) + 4c$
````

````{dropdown} Correction
> La lecture des caractéristiques ne se fait pas par rapport au nom des grandeurs mais à leur position dans la structure mathématique. Ainsi :
> * L'amplitude est le facteur multiplicatif du sinusoïde $\boxed{A}\sin \omega t + \phi$.
> * La pulsation est le facteur multiplicatif devant le temps $A\sin \boxed{\omega} t + \phi$.
>	1. $s(t) = \boxed{\frac{1}{2k + 1}} \sin{\boxed{(2k+1) \omega} t} $ donc
>		* Amplitude : $\frac{1}{2k + 1}$
>		* Pulsation$(2k + 1) \omega$
>		* Période : $\frac{2\pi}{(2k+1)\omega}$
>		* Fréquence : $\frac{(2k+1) \omega}{2 \pi}$
>		* Valeur moyenne nulle
>		* Phase à l'origine nulle
>	2. $s(t) = \boxed{7\omega} \cos(\boxed{2f} t + 3)$
>		* Amplitude : $7 \omega$
>		* Pulsation$2f$
>		* Période : $\frac{2\pi}{2f}$
>		* Fréquence : $\frac{f}{\pi}$
>		* Valeur moyenne nulle
>		* Phase à l'origine : 3
>	3. $s(t) = \boxed{3a} \cos(\boxed{\frac{2\pi n}{T}}t) + 4c$
>		* Amplitude : $3a$
>		* Pulsation$\frac{2 \pi n}{T}$
>		* Période : $T/n$
>		* Fréquence : $\frac{n}{T}$
>		* Valeur moyenne 4c
>		* Phase à l'origine : nulle
```` 

## Propriété : Valeurs moyennes et efficaces des sinusoïdes

````{admonition} Fondamental
:class: important

La valeur moyenne d'un signal sinusoïdal de la forme $s(t) = S_m \cos{(\omega t + \phi)}$ est __nulle__.

Si l'on ajoute au signal une valeur constante $S_0$, alors__ la valeur moyenne est ____$S_0$__, d'où le nom de valeur moyenne.

La valeur efficace d'un signal sinusoïdal de la forme $s(t) = S_m \cos{(\omega t + \phi)}$ est :

$$
\frac{S_m}{\sqrt{2}}
$$
````

> __Démonstration__
> * Pour la valeur moyenne :
>
> \begin{align*}
\left\langle s \right\rangle &= \frac{1}{T} \int_{t=0}^{t=T} S_m \cos{(\omega t + \phi)} dt\\
&= \frac{S_m}{T} \left[ \frac{1}{\omega} \sin{(\omega t + \phi)}\right]_{0}^{T}\\
&= 0
\end{align*}
> 
> La valeur moyenne d'une constante $S_0$ est cette constante. Comme la valeur moyenne est un opérateur linéaire, la valeur moyenne de la fonction $s(t) = S_m \cos{(\omega t + \phi)} + S_0$ est donc bien $S_0$.
>
> * Pour la valeur efficace :
>
> \begin{align*}
S_{eff} & = \sqrt{\frac{2}{T} \int_{t=0}^{t=T/2} S_m^2 \cos^2{(\omega t + \phi)} dt}\\
& =  \sqrt{\frac{2S_m^2 }{T} \int_{t=0}^{t=T/2} \frac{1}{2} \left ( \cos{2(\omega t + \phi)} + 1 \right) dt }\\
& = \sqrt{\frac{S^2_m}{T} {\left[ \frac{1}{2\omega} \sin{2(\omega t + \phi)}+ t\right]}_{0}^{T/2}}\\
& = \sqrt{\frac{S^2_m}{T} 2T} = \frac{S_m}{\sqrt{2}}
\end{align*}


````{admonition} Fondamental : Valeur efficace d'une somme de deux sinusoïdes
:class: important
Si l'on somme deux sinusoïdes de __fréquences différentes__ et d'amplitude respectives $S_{1,eff}$ et $S_{2,eff}$ alors la valeur efficace de la somme sera :

$$
S_{eff} = \sqrt{S_{1,eff}^2 + S_{2,eff}^2}
$$
````
> __Démonstration__
>
> \begin{align}
S_{eff} &= \sqrt{\left\langle {(S_1(t) + S_2(t))}^2\right\rangle}\\
			&= \sqrt{\left\langle {S_1(t)}^2 + {S_2(t)}^2 + 2 S_1(t) S_2(t)\right\rangle}\\
			&= \sqrt{\left\langle{S_1(t)}^2\right\rangle + \left\langle{S_2(t)}^2\right\rangle + \left\langle2 S_1(t) S_2(t)\right\rangle}\\
			&= \sqrt{S_{1,eff}^2 + S_{2,eff}^2 + 2 S_1m S_2m \left\langle \cos{(\omega_1 t + \varphi_1)} \cos{(\omega_2 t + \varphi_2)} \right\rangle}\\
			&= \sqrt{S_{1,eff}^2 + S_{2,eff}^2 + S_1m S_2m \left\langle \cos{((\omega_1 + \omega_2) t + \varphi_1+\varphi_2)} \right\rangle + S_1m S_2m \left\langle  \cos{((\omega_1 - \omega_2) t + \varphi_1 - \varphi_2)} \right\rangle} \\
			&= \sqrt{S_{1,eff}^2 + S_{2,eff}^2 + 0 + 0}
\end{align}

````{attention}
:class: dropdown
__Si les deux sinusoïdes sont de même pulsation, la propriété n'est plus vraie,__ on peut s'en rendre compte en remarquant que le dernier terme (différences des phases) est alors un terme constant dont la valeur moyenne n'est pas forcément nulle.
````

## Déphasage en signaux sinusoïdaux

````{admonition} Définition : Déphasage
:class: tip

On considère deux signaux sinusoïdaux dont les phases sont $\varphi_1$ et $\varphi_2$. Le déphasage $\Delta \varphi_{2/1}$ du signal 2 sur le signal 1 est défini par

$$
\Delta  \varphi_{2/1} = \varphi_2 - \varphi_1
$$
````

On peut noter $\varphi_1 = \omega_1 t + \phi_{10} $ et $\varphi_2 = \omega_2 t + \phi_{20}$. Il vient que le déphasage s'écrit :

$$
\Delta \varphi_{2/1} = (\omega_2 - \omega_1) t + (\phi_{20} - \phi_{10})
$$

On observe que si les deux signaux sont de même fréquence/pulsation/période, alors le déphasage entre les deux est constant. Sinon, il varie.


````{admonition} Exemple
:class: note
* Si le déphasage entre deux signaux est nul, on dit que les signaux sont __en phase__.
* Si le déphasage entre deux signaux est égal à $\pi$, on dit que les signaux sont __en opposition de phase__: le maximum de l'un coïncide avec le minimum de l'autre et réciproquement.
* Si le déphasage entre deux signaux est égal à $\pm \pi/2$, on dit que les signaux sont __en quadrature de phase__: le maximum/minimum de l'un coïncide avec le 0 (ou le passage par la valeur moyenne) de l'autre et réciproquement.
````

### Méthode: Calculer un déphasage

Le but de cet exercice est de comprendre la notion de déphasage et les méthodes d'études associées.


````{admonition} Fondamental : Relation entre déphasage et retard temporel
:class: important
Soit deux signaux sinusoïdaux de même pulsation $\omega$, d'amplitude respectives $S_1$ et $S_2$ et de phase à l'origine respectives $\phi_1$ et $\phi_2$. Le retard temporel $\Delta t$ du signal 2 sur le signal 1, représentant l'écart temporel relatif entre deux points des signaux ayant la valeur est relié au déphasage par:

$$
\Delta \phi = - \omega  \Delta t
$$
````

> __Démonstration__
> On cherche $\Delta t$ tel que : $S_1 \cos (\omega t + \phi_1) = S_2 \cos (\omega (t + \Delta t) + \phi_2)$ soit $\omega t + \phi_1 = \omega (t + \Delta t) + \phi_2$ donc : $\omega \Delta t = \phi_1 - \phi_2 = - \Delta \phi_{2/1}$


````{attention}
:class: dropdown
Dans le système d'unités S.I., l'unité d'angle est le __radian__.
````

````{admonition} Exercice 
:class: attention
Déterminer expérimentalement le déphasage du signal vert sur le signal rouge.

```{figure} ./images/dephasage.png
:name: dephasage
:align: center
:width: 75%
```
````

````{attention}
:class: dropdown
Attention, __on ne peut mesurer directement un déphasage (en radian) sur un graphique temporel. On mesure un retard temporel.__
````

````{dropdown} Correction
> Commençons par mesurer le __retard temporel__ du signal vert sur le signal rouge. C'est une grandeur algébrique, il faut donc tenir compte de l'ordre des deux signaux. Ici, __le signal vert est en avance, donc le retard est négatif.__
> 
>	Ce retard se mesure entre deux points ayant la même valeur en ordonnée. Il est conseillé de mesurer le retard entre deux points où la fonction s'annule (ou atteint sa valeur moyenne) pour des questions de précision. On mesure ici $\Delta t = - 1.8 s$.
>
>	On doit ensuite utiliser la relation prouvée précédemment $\Delta \phi = - \omega \Delta t$. La pulsation s'obtient en mesurant la période. Ici T = 6s donc $\omega = \pi / 3= 1 \rm{rad.s^{-1}}$.
>
>	Il vient $\Delta \phi = 1.8 \rm{rad}$

```{figure} ./images/dephasage_c.png
:name: dephasage_c
:align: center
:width: 50%
```
````


## Intérêt des signaux sinusoïdaux
Les signaux sinusoïdaux sont extrêmement importants en physique. En effet, on les retrouve dans deux cas très répandus:

* Les oscillateurs harmoniques. A l'exemple des systèmes masse-ressort, ces systèmes ont une évolution sinusoïdal. Or nous verrons dans le cours de l'année que les oscillateurs harmoniques se retrouvent partout en physique.
* Tout signal physique peut être vu comme une somme de sinusoïdes d'amplitude, de fréquence et de phase à l'origine bien définie. C'est le principe de la décomposition spectrale qui va être présentée ensuite.
