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

# Exemples de spectres usuels

## Spectres des signaux électromagnétiques

### Gammes spectrales

Pour un signal lumineux, la décomposition en série de Fourier de la grandeur associée au signal lumineux va donner les différences fréquences du signal $\nu$. La relation: $\lambda \nu =c$ avec c la célérité de la lumière dans le vide associe donc à chaque fréquence une longueur d'onde dans le vide, donc, pour le visible, une couleur: on obtient le spectre du signal lumineux.

On peut en général détailler plusieurs types signaux électromagnétiques. Ces types correspondants en réalité à des gammes de fréquences propres à des types d'utilisation ou d'effets observés. On pourra distinguer en augmentant la fréquence (les valeurs limites sont approximatives):

* $\nu < 300MHz (1m < \lambda )$:] Ondes radios. C'est sur ces fréquences que les antennes radios émettent des signaux électromagnétiques modulés par une information (son, image... ). Les ondes radios sont très diverses et on divise en général les gammes de fréquences suivant les utilisations: AM, FM, mobile...  pour la partie grand public.

* $300MHz <\nu < 300GHz (1mm < \lambda <1m)$:] Micro-ondes: ondes utilisées pour les radars, les communications par satellite et bien sûr le micro-onde.

* $300GHz <\nu < 30THz (10 \rm{\mu m} < \lambda <1mm)$:] Terahertz (ou infrarouge lointain). Domaine relativement peu utilisé mais en pleine essor.

* $30THz <\nu < 400THz (750nm < \lambda <10 \rm{\mu m})$:] infrarouge. Très utilisé en spectroscopie car de nombreuses liaisons chimiques absorbent souvent ce rayonnement. Il est aussi le rayonnement électromagnétique émis spontanément par les corps à température ambiante (corps humain par exemple).

* $400THz <\nu < 770THz (390nm < \lambda < 750nm)$:] lumière visible.

* $770THz <\nu < 30PHz (10nm < \lambda < 390nm)$:] Ultra-violet: partie (faible: $5\%$) du spectre émis par le soleil, ils sont en grande partie absorbée par la couche d'ozone, protégeant la Terre (enfin nous!). Les UV sont utilisées pour certaines études ou révélations (circuits imprimés).

* $30PHz <\nu < 30EHz (10pm < \lambda <10nm)$:] Rayons X. Rayonnement ionisant principalement utilisé en radiologie ou en cristallographie.

* $30EHz <\nu (\lambda <10pm)$:] Rayon gamma. Emis notamment lors de réactions nucléaires, ils sont l'un des principaux dangers lors d'une catastrophe nucléaires car ionisant et difficile à absorber

### Types de sources (détails en ligne)

Parmi les différents domaines présentés précédemment, l'un des plus simples à étudier d'un point de vue expérimental est bien évidemment le rayonnement du visible. On rappelle que les différentes longueurs d'onde correspondent à différentes couleurs (du violet au rouge quand on augment la longueur d'onde). Les sources lumineuses sont nombreuses et variées et leur spectre aussi. Trois exemples sont assez caractéristiques et à savoir reconnaître:
* Lampes à incandescence (spectre continu)
* Lampes spectrales (spectre discret)
* LASER (quasi-monochromatique)


````{topic} Les lampes à incandescence.
Issues de l'échauffement d'un filament, elles se base sur l'émission d'un corps noir. Un corps à la température T va émettre un spectre continue de longueur d'onde. La loi de Wien prévoit que le maximum d'émission a lieu autour de la longueur d'onde: $\lambda_{\max} = \frac{2,898 \times 10^{-3}}{T}$.

Par exemple la température des ampoules à incandescence classique ou halogène tourne autour de 3000K. La longueur d'onde associée est $\lambda \approx 960nm$: le maximum d'émission est donc dans l'infrarouge.
```{figure} ./images/Signaux_SpectreCorpsNoir.jpg
:name: corps_noir
:align: center
:width: 60%
Spectre d'un corps noir
```
````

````{topic} Les lampes spectrales.
Constituée d'un gaz d'atomes particuliers, elle utilise les transitions énergétiques des électrons de ces atomes dont certaines correspondent à des longueurs du visible. Les niveaux d'énergie (mécanique quantique) étant discrets, les longueurs d'onde émise sont discrètes. On parle de spectre discret.
```{figure} ./images/Signaux_raies_balmer.jpg
:name: discret
:align: center
Spectre discret
```
````
````{topic} Les LASERs
(Light Amplification by Stimulated Emission of Radiation) Source lumineuse basée sur l'émission stimulée d'une transition énergétique particulière au moyen d'un amplification dans une cavité résonante. Les Lasers ont de nombreuses propriétés dont celle, pour la plupart d'être monochromatique c'est-à-dire qu'il n'émettent qu'une seule longueur d'onde (en réalité une raie fine).
````

````{topic} Spectres dans le visible de différentes sources lumineuses.
:class: remove-output
_Attention, certaines sources émettent aussi dans les autres gammes de longueur d'onde._

```{figure} ./images/Signaux_spectres_lumiere.jpg
:name: spectres_lum
:align: center
Différentes spectres
```
````

## Spectres des signaux acoustiques


### Gammes spectrales
````{sidebar} Origine de la propagation
Les signaux acoustiques sont en général émis grâce à la vibration de systèmes mécaniques: corde vibrante (instruments à cordes), membrane vibrante (percussions, haut-parleur... )...  En modifiant la pression du milieu environnant (en général l'air), il font naître des oscillations de pression/vitesse qui vont se propager de proche en proche. Comme nous l'avons expliqué précédemment, les instruments de musique sont construits généralement pour pouvoir sortir une note de hauteur donnée (fréquence du fondamental) et possédant un timbre (harmoniques).

````
Pour un signal sonore, la décomposition en série de Fourier permet de déterminer __la hauteur et le timbre du son.__ Si l'on superpose deux notes différentes, on retrouvera en terme de composante spectrale la hauteur des deux notes séparées, ce qui n'est pas le cas dans le signal temporel.

* En moyenne, les sons "audibles" par l'oreille humaine possèdent des fréquences comprises entre 20Hz et 20kHz.
* En dessous de 20Hz, on parle d'infrasons. En dessus on parle d'ultrasons. Si les infrasons sont peu utilisés, les ultrasons sont très utilisés (télémétrie...)

````{topic} Exemple d'un Sol d'une flûte
On remarquera sur les tracés que pour un signal complexe, il est délicat de déterminer les composantes spectrales sur le tracé temporel. Par contre, on se rapproche d'un spectre discret constituée de fréquences proportionnelles au fondamentales : un signal périodique.

```{figure} ./images/Signaux_SolTempo.png
:name: soltempo
:align: center
Son d'une flûte
```
```{figure} ./images/Signaux_Sol_Flute.png
:name: sol_freq
:align: center
:width: 60%
Spectre du signal sonore
```
````


## Signaux électriques
Les signaux électriques peuvent aussi être décomposés. En général, les signaux électrique (qu'on décompose) servent au transport d'information et le spectre du signal est lié à l'information transportée. Comme on le verra, la décomposition spectrale sert à isoler les fréquences qu'on veut garder des fréquences qu'on veut supprimer (bruit...): on parle de __filtrage.__