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

# Exercices d'applications. signaux physiques

Contrairement aux exercices du cours qui détaillent les raisonnements pour expliquer les méthodes, seules les réponses finales sont données ici. __Il faut s'entraîner à résoudre soi-même tous les exercices proposés ici AVANT DE REGARDER LES RÉPONSES.__

## Modulation d'amplitude

````{admonition} Exercice 
:class: attention

On considère un signal $u_1$ sinusoïdal de période $T_1$ et d'amplitude $u_{1m}$ et un signal $u_2$ sinusoïdal de période $T_2 = T_1 / 10$ et amplitude $u_{2m} = u_{1m}$. On crée à partir de ces deux signaux un troisième signal de la forme : $u_S = u_2 \times ( 1 + m u_1 )$.

1. Donner les expressions temporelles des signaux $u_1$ et $u_2$ en fonction de $T_1, u_{1m}$ et du temps.
2. Justifier que $u_S$ peut être vu comme un signal modulé en amplitude et représenter graphiquement l'allure temporelle de $u_S$.
3. Déterminer le spectre de $u_S$.
````

````{dropdown} Eléments de correction
__1.__
\begin{align}
	u_1(t) = u_{1m} \cos \left ( \frac{2\pi}{T_1} t \right )\\
	u_2(t) = u_{1m} \cos \left ( \frac{20\pi}{T_1} t \right )
\end{align}

__2.__
```{figure} ./images/exo_temporelle_module.png
:name: temporelle_mod
:align: center
```
__3.__
```{figure} ./images/exo_freq_module.png
:name: freq_mod
:align: center
:width: 50%
```
````

## Tracé de spectres

````{admonition} Exercice 
:class: attention
```{figure} ./images/exo_dent_scie_tempo.jpg
:name: dent_scie
:align: center
:width: 50%
Signal dent de scie
```

On considère le signal ``dent de scie'' dont le tracé temporel est donné ci-contre. On donne aussi sa décomposition en série de Fourier :

$$
u(t) = \sum_{n=1}^{+\infty} \frac{2V_m}{\pi} \frac{(-1)^n}{n} \sin n \omega t
$$

1. Relier $\omega$ et T. Le justifier.
2. Représenter le spectre de Fourier du signal.
3. Que vaut la valeur moyenne du signal ?
````
````{dropdown} Eléments de correction
__1.__
$T = \frac{2\pi}{\omega}$ attention à bien le justifier.

__2.__
```{figure} ./images/exo_freq_scie.png
:name: freq_scie
:align: center
:width: 60%
```

__3.__
Valeur moyenne nulle.
````

````{admonition} Exercice 
:class: attention

```{figure} ./images/exo_redressement_tempo.jpg
:name: redressement
:align: center
:width: 50%
Signal redressé
```
On considère le signal ``redressé simple alternance'' dont le tracé temporel est donné ci-contre. On donne aussi sa décomposition en série de Fourier :

$$
u(t) = \frac{V_m}{\pi} + \frac{V_m}{2} \cos \omega t + \sum_{n=1}^{+\infty} \frac{2V_m}{\pi} \frac{1}{4n^2 - 1} \sin 2 n \omega t
$$

1. Relier $\omega$ et T. Le justifier.
2. Représenter le spectre de Fourier du signal.
3. Que vaut la valeur moyenne du signal ?
````

````{dropdown}
__1.__
$T = \frac{2\pi}{\omega}$ attention à bien le justifier.

__2.__
```{figure} ./images/exo_freq_redress.png
:name: freq_redressement
:align: center
:width: 60%
```

__3.__
Valeur moyenne $\frac{V_m}{\pi}$.
````
