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
# Cas des fluides incompressibles

_Nous allons commencer par traiter un premier exemple de fluide: les fluides incompressibles (ou peu compressibles). Un fluide peu compressible est un fluide pour lequel la masse volumique varie peu lorsque la pression varie. On fera ici l'hypothèse qu'il est incompressible, c'est-à-dire que sa masse volumique est la même quelques soient les conditions._

## Equation barométrique

````{important} __Fondamental : Equation barométrique - Champ de pression pour un fluide incompressible__

Dans un fluide incompressible de masse volumique $\rho_0$ dans un champ de pesanteur d'intensité $g$, le champ de pression ne dépend que de la profondeur. La variation de pression $\Delta P = P(h_2) - P(h_1)$ entre les __profondeurs__ $h_2$ et $h_1$ s'écrit:

\begin{equation}
\Delta P = P(h_2) - P(h_1) = \rho_0 g (h_2 - h_1)
\end{equation}
````

````{attention}

Il s'agit de profondeur soit la coordonnée verticale pour un axe pris vers le __bas__.

````

__Démonstration__  
On applique l'équation fondamental de la dynamique avec $\rho_0$ uniforme (on oriente l'axe z vers le bas et les axes x et y sont horizontaux):

\begin{equation}
\begin{cases}
\frac{\partial P}{\partial x} &= 0\\
\frac{\partial P}{\partial y} &= 0\\
\frac{\partial P}{\partial z} &= \rho_0 g\\
\end{cases}
\end{equation}
Les deux premières équations permette de dire que le champ de pression ne dépend que de z. On peut donc réécrire P comme une fonction d'une seule variable $P(z)$ et la dérivée partielle suivant z devient une dérivée droite. En intégrant entre $z = h_1$ et $z = h_2$, il vient l'équation demandée (on rappelle que $\rho_0$ est uniforme).


## Equation barométrique: Interprétation

__Interprétation__  
On peut remarquer à nouveau que la variation de pression correspond à $\rho_0 g \Delta h$, soit le poids, par unité de surface de la colonne de fluide se situant au dessus sur une hauteur $\Delta h$.

On remarquera aussi que le champ de pression ne varie pas à altitude constante __quelque soit la forme du fluide.__. Il suffit que les différentes parties du fluide communiquent.


## Validité du modèle incompressible

````{admonition} Exercice 
:class: attention

Dans le cas de l'eau, on peut donner le coefficient de compressibilité isotherme:

\begin{equation}
\chi_{T} = \frac{1}{\rho}\left(\frac{\partial \rho}{\partial P}\right)_{T} = 5 \times 10^{-10} \rm{Pa^{-1}}
\end{equation}
où l'indice T signifie que la température est maintenue constante.

1. Rappeler la valeur numérique de la masse volumique de l'eau
1. Déduire du coefficient $\chi_T$ une relation entre la variation $d\rho$ et la variation $dP$.
1. En déduire une estimation de la variation relative $\frac{\Delta \rho}{\rho_0}$ pour une variation d'altitude $\Delta z$ en considérant que le champ de pression suit le modèle d'un fluide incompressible.
1. Estimer la variation d'altitude nécessaire pour observer une variation de 1\% de la masse volumique. Commenter l'hyptohèse de fluide incompressible dans le cas de l'eau.

````

````{dropdown} Démonstration
_Rappel : La masse volumique de l'eau (à connaître) est $\rho_0 = 10^3 \rm{kg.m^{_3}}$._

\begin{align*}
\frac{1}{\rho}\frac{\partial \rho}{\partial P} &= \chi_T\\
\frac{d\rho}{\rho} &= \chi_T dP\\
\rho &= \rho_0 e^{\chi_T \Delta P}\\
\rho &= \rho_0 e^{\chi_T \rho_0 g \Delta z}\\
\frac{\rho - \rho_0}{\rho_0} &= e^{\chi_T \rho_0 g \Delta z} - 1\\
\frac{\rho - \rho_0}{\rho_0} &\approx \chi_T \rho_0 g \Delta z\\
\Delta z &\approx \frac{1}{\chi_T\rho_0 g} \frac{\Delta \rho}{\rho_0}\\
\Delta z & \approx 10^4 \rm{m}
\end{align*}

Dans ce calcul, on a remplacer la dérivée partielle par une dérivée droite en supposant que la température était uniforme, donc la masse volumique ne peut plus dépendre que de P. On linéarise ensuite l'exponentielle en considérant que son argument est faible (validé puisqu'on veut une variation de 1\%

La profondeur nécessaire est énorme et on peut donc largement faire l'hypothèse d'u fluide incompressible pour l'eau.

On pourra retenir que les fluides incompressibles possèdent un coefficient de compressibilité isotherme très faible.

````

## Baromètre

````{admonition} Exercice 
:class: attention

Le baromètre le plus courant est le baromètre de Torricelli. Il s'agit d'un tube en U fermé à une extrémité et l'autre extrémité est ouverte et à l'air libre. Du côté fermé, le mercure est surmonté par du vide en première approximation (P=0).

1. Exprimer la différence de hauteur h entre les deux surfaces libres du mercure.
1. On donne la masse volumique du mercure $\rho_{Hg} = 13,5 \times 10^3 \rm{kg.m^{-3}}$. Justifier l'utilisation du mercure plutôt que de l'eau pour faire un baromètre.
1. Expliquer la définition de l'unité de pression mmHg (millimètre de mercure): $1\rm{mmHg}=133,3\rm{Pa}$
````

````{dropdown} Démonstration
On retiendra de cet exercice l'utilisation du fait que la pression est la même en tout point isoaltitude.


__Résolution__  

A la surface libre en contact avec l'atmosphère règne une pression $P_0 = 1 \rm{atm} \approx 10^5 \rm{Pa}$. De l'autre côté, on assimile la pression à une pression nulle $P= 0$. Le fluide étant au repos, on peut appliquer l'équation de la statique des fluides et puisqu'on fait l'hypothèse d'un fluide incompressible, on applique l'équation barométrique (on a orienté z vers le bas et pris la profondeur nulle à la hauteur de la surface de pression nulle):

\begin{align*}
&P(z=h) - P(z=0) = \rho g h\\
& \Longrightarrow h = \frac{P_0}{\rho g}\\
& \Longrightarrow h_{mercure} = 760 mm\\
& \Longrightarrow h_{mercure} = 10 m
\end{align*}
On observe que la taille du barométre sera beaucoup plus faible grâce sa plus forte masse volumique.

On remarquera aussi que la différence de pression correspondant à une hauteur de mercure de 1mm est 133Pa, ce qui permet de définir l'unité de pression mmHg.
````

