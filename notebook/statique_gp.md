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
# Cas des gaz parfait: Atmopshère isotherme

_On va maintenant supposer que le fluide est un gaz parfait. On va donc pouvoir utiliser l'équation d'état des gaz parfaits pour relier la masse volumique et la pression. Le problème est qu'on fait apparaître la température qui peut aussi varier dans l'espace. On va donc devoir faire une hypothèse sur la température. Dans le cadre du cours, on suppose pour faire simple que l'atmosphère est isotherme, c'est-à-dire que la température est uniforme. On reviendra sur cette hypothèse par la suite._

## Champ de pression pour un atmosphère isotherme d'un gaz parfait.

````{hint}
_Rappel :Equation d'état d'un gaz parfait._
On rappelle que l'équation d'état d'un gaz parfait s'écrit:

\begin{align*}
PV &= nRT\\
P \frac{m}{\rho} &= nRT\\
\frac{P}{\rho} &= \frac{n}{m}RT\\
\frac{P}{\rho} &= \frac{RT}{M}
\end{align*}
avec M la masse molaire du gaz parfait et R la constante des gaz parfaits.
````

````{important} __Champ de pression pour un gaz parfait sous l'hypothèse isotherme.__

Une atmosphère de gaz parfait à température uniforme dans un champ de pesanteur uniforme possède pour champ de pression P(z) (où z est l'__altitude__):

\begin{align*}
P(z) &= P(z=0) \exp(-\frac{Mgz}{RT})\\
 &= P(z=0) \exp(-\frac{M_P gz}{k_B T})
\end{align*}
où $M_P$ est la masse d'une particule du gaz, M sa masse molaire, $R = 8.314 \rm{J.K^{-1}.mol^{-1}}$ la constante des gaz parfaits et $k_B = 1.38 \times 10^{-23} \rm{J.K^{-1}}$. On remarquera que $R = N_A k_B$.
````

````{admonition} Démonstration
:class: important
>On prend un axe Oz vertical vers le haut et deux axe Ox et Oy horizontaux. A nouveau, la projection de l'équation fondamentale sur x et y montre que le champ de pression ne dépend ni de x, ni de y. On écrira donc bien $P(z)$ et on remplace la dérivée partielle par rapport à z par une dérivée droite.
>
>L'équation d'état établie précédemment permet de réécrire l'équation fondamentale de la statique des fluides et de la résoudre:
>
>\begin{align*}
\frac{dP}{dz} + \frac{PM}{RT}g &= 0\\
P(z) &= A e^{-\frac{Mgz}{RT}}\\
P(z) &= P(z=0) e^{-\frac{Mgz}{RT}}\\
P(z) &= P(z=0) e^{-\frac{M_P gz}{\frac{R}{N_A}T}}\\
P(z) &= P(z=0) e^{-\frac{M_P gz}{k_B T}}
\end{align*}
````

## Facteur de Boltzmann

````{topic} Profil de concentration
En utilisant les différentes relations établies précédemment, on observe que le nombre de particule par unité de volume située à une altitude z est:  $n(z) = n_0 \exp(-\frac{M_p gz}{k_B T})$.

$n(z)$ représente donc la statistiques des particules en fonction de l'altitude mais on peut aussi le comprendre comme __la statistique  des particules en fonction de leur énergie potentielle (ici de pesanteur).__

__Analyse de la statistique des particules__  
On observe que le nombre de particules décroit avec l'énergie potentielle: les hautes énergies (ici hautes altitudes) sont moins peuplées que les basses altitudes.

L'argument de l'exponentielle fait apparaître un rapport entre deux termes énergétiques. C'est la compétition entre ces deux termes qui va permettre de déterminer si le niveau d'énergie sera densément peuplé ou non:

* $M_p gz$ représente l'énergie potentielle d'une particule à l'altitude z. Plus ce terme est grand, plus le terme exponentielle est faible et plus le nombre de particule qui auront cette énergie sera faible. On retrouve le principe que les systèmes mécaniques tendent à se stabiliser au minimum d'énergie potentielle.
* $k_B T$ représente l'agitation thermique (on verra que l'énergie d'agitation thermique est proportionnelle à $k_B T$). Plus ce terme est grand, plus le terme exponentielle est grand et plus le nombre de particule qui auront une énergie donnée sera grand. On peut ainsi peupler les état d'énergie plus important (ici les hautes altitudes). L'agitation thermique tend à homogénéiser le système, ici à atteindre toutes les énergies - les altitudes.


Suivant la température, les particules vont occuper une gamme d'énergie plus ou moins grande. Pour un état d'énergie $E_p$, si $k_B T \gg E_p$, l'état énergétique sera densément peuplé et si $k_B T \ll E_p$ l'état énergétique sera faiblement peuplé.
````


````{sidebar} Interprétation
Comme on l'a dit précédemment, cette loi statistique montre que, comme le prévoit la mécanique classique, les états de plus faibles énergies sont les plus peuplées (cf. les études des systèmes conservatifs) mais que l'agitation thermique permet statistiquement d'atteindre des états d'énergie plus haut. De nombreux phénomènes peuvent s'expliquer au moyen de la statistique de Boltzmann, notamment en chimie où les systèmes sont en général en équilibre avec un thermostat (ex: la loi d'Arhénius).
````
````{important} __Généralisation (Admise): Facteur de Boltzmann__

D'une manière plus générale, si un système de $n_0$ particules par unité de volume est __en équilibre à une température T__, le nombre de particule par unité de volume $n(E_p)$ ayant l'énergie potentielle $E_p$ est:

\begin{equation}
n(E_p) = A \exp(-\frac{E_p}{k_B T})
\end{equation}
Le terme exponentielle porte le nom de __facteur de Boltzmann__. La constante A est une constante de normalisation telle que la somme du nombre de particules dans chaque état donne $n_0$.
````



