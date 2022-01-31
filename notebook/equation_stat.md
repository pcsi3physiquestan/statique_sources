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
# Equation fondamental de la statique des fluides

## Particule de fluide

````{important} __Définition : Particule de fluide__

Dans un fluide, on peut isoler mentalement un volume infinitésimal $d\tau_Q$ autour d'un point Q. On appelle ce petit élément __particule de fluide__.

````

__Caractère infinitésimal__  
Le caractère infinitésimal permet d'appliquer les méthodes du calcul différentiel. Ainsi les grandeurs internes sont considérées comme homogène sur le petit volume: la masse volumique, le champ de pesanteur... 

Attention, ces grandeurs peuvent par contre varier d'une particule de fluide à l'autre.


````{dropdown} Remarque
__Système non fermé__  
A priori, une particule de fluide est un système non fermé c'est-à-dire qu'il peut échanger de la matière avec l'extérieur. Nous travaillerons ici dans le cadre de la statique des fluides. L'évolution est alors supposée stationnaire de sorte qu'on pourra considérer que la masse (et donc la masse volumique) de la particule est constante. Cette hypothèse n'est plus forcément vérifiée en dynamique des fluides.
````

## Bilan des forces

__Bilan des forces__  
Deux forces s'appliquent sur la particule de fluide:


* l'action de la pesanteur. Elle s'applique à tout le volume $d\tau_Q$. On parle de __force volumiques__. La masse volumique et le champ de pesanteur étant considéré comme homogènes, l'action de la pesanteur est modélisée par une force ponctuelle $\overrightarrow{dP} = \rho d\tau_Q \overrightarrow{g}$.
* l'action de contact fluide environnant sur la particule de fluide. Ce sont des forces __surfaciques__. Pour chaque surface de contact, cette action se décompose en deux parties
    * l'action normale qui représente les forces de pression. Elle a une expression de la forme $\overrightarrow{dF_{pression}}=P_{surface}\overrightarrow{dS}$. Nous allons voir ensuite comment réexprimer cette force.
    * l'action tangentielle. Le fluide étant au repos, on considèrera celle-ci nulle.




## Equivalent volumique des forces de pression

````{important} __Fondamental : Equivalent volumique des forces de pression__

Pour une particule de fluide en un point M dans un fluide où le champ de pression est P, la résultante des forces de pression s'appliquant sur la particule de fluide peut se réécrire sous la forme:

\begin{equation}
\overrightarrow{dF_{pression}} = - \overrightarrow{grad}P d\tau_Q
\end{equation}
On obtient ainsi une expression proportionnelle au volume donc __comme si__ l'action de la pression s'exerçait en volume. D'où le nom __d'équivalent volumique des forces de pression__.
````

__Démonstration__  
On va se placer dans un système de coordonnées cartésiennes où le point M est de coordonnées (x,y,z). La démonstration peut se généraliser aux différents systèmes de coordonnées mais l'introduction du gradient permettra cette généralisation.

On s'intéresse plus particulièrement aux actions de pression sur les deux faces inférieures et supérieures (c'est-à-dire aux côte z et z+dz).

```{figure} ./images/thermo_statique_pression.jpg
:name: fig_265
:align: center

```

La pression sur la surface supérieure est $P(x,y,z+dz)$ (les variations suivant x et y feraient apparaître des termes d'ordre 2 et sont donc négligés) donc la force exercée sur la partie s'écrit: $\overrightarrow{F_{P,z+dz}} = - P(x,y,z+dz) dxdy \overrightarrow{e_z}$.

La pression sur la surface inférieure est $P(x,y,z)$ (les variations suivant x et y feraient apparaître des termes d'ordre 2 et sont donc négligés) donc la force exercée sur la partie s'écrit: $\overrightarrow{F_{P,z}} = P(x,y,z) dxdy \overrightarrow{e_z}$.

La résultante des deux forces considérées ci-dessus est donc:

\begin{align*}
\overrightarrow{dF_{P,1}} &= \left(P(x,y,z) - P(x,y,z+dz)\right)dxdy \overrightarrow{e_z}\\
&= -\frac{\partial P}{\partial z}dx dy dz\overrightarrow{e_z}\\
&= -\frac{\partial P}{\partial z} d\tau_Q \overrightarrow{e_z}
\end{align*}
On a utilisé ici la définition du taux de variation (on rappelle qu'en notation différentielle, le passsage à la limite est implicite): $\frac{\rm{d}f}{\rm{dx}} = \frac{f(x+dx)-f(x)}{dx}$. La différence est qu'ici, la fonction P dépend aussi de x et de y, donc c'est une dérivée partielle.

Remarquons que le raisonnement précédent s'applique aussi aux actions sur les faces perpendiculaires aux axes $\overrightarrow{e_x}$ et $\overrightarrow{e_y}$. Donc la résultante totale des forces s'écrit:

\begin{align*}
\overrightarrow{dF_{pression}} &= -\left(\frac{\partial P}{\partial z}  \overrightarrow{e_z} + \frac{\partial P}{\partial y}  \overrightarrow{e_y} + \frac{\partial P}{\partial x}  \overrightarrow{e_x}\right) d\tau_Q\\
\overrightarrow{dF_{pression}} &= - \overrightarrow{grad}P d\tau_Q
\end{align*}

````{dropdown} Remarque
__Interprétation__  
L'équivalent volumique de la résultante des forces de pression est fondamental pour la mise en équation. Mais il permet aussi de mieux comprendre l'influence de va avoir la pression d'un fluide sur un système (que ce soit le fluide lui-même ou un corps étranger).

En effet, on observe que la résultante des forces est opposée au gradient des forces de pression. Ainsi, la force s'effectue en direction des dépressions (zones de pression plus faibles) locales. Nous énoncerons par la suite le théorème d'Archimède mais on peut déjà remarquer qu'il en est la conséquence. Sous l'effet de la pesanteur la pression a tendance a diminuer avec l'altitude (ce sera prouvé par la suite) et donc l'action des forces de pression d'un fluide où le solide est immergé est vers le "haut".
````

## Equation fondamentale de la statique des fluides

````{important} __Fondamental : Equation fondamentale de la statique des fluides__

Dans un fluide __au repos__ soumis à la seule action extérieure du champ de pesanteur $\overrightarrow{g}$, le champ de pression P est donné par l'équation:

\begin{equation}
\rho \overrightarrow{g} - \overrightarrow{grad}P = 0
\end{equation}
````

__Démonstration__  
On va travailler sur une particule de fluide et appliquer le principe fondamental de la dynamique dans le référentiel terrestre qu'on suppose galiléen. Le bilan des forces a déjà été fait. Leurs somme est égale à 0 puisque le fluide est supposé au repos (donc la particule de fluide aussi). Il vient:

\begin{align*}
\overrightarrow{0} = \rho \overrightarrow{g} d\tau_Q - \overrightarrow{grad}P d\tau_Q\\
\overrightarrow{0} = \rho \overrightarrow{g} - \overrightarrow{grad}P
\end{align*}

````{dropdown} Remarque
__Interprétation__  
Comme on l'a déjà dit précédemment, il apparaît que le gradient du champ de pression est colinéaire au champ de pesanteur et dans le même sens. Cela signifie que la pression va diminuer quand on prend de l'altitude.

On peut remarquer aussi qu'en intégrant sur un chemin entre deux altitude $z_1$ et $z_2$, il vient la différence (on a multiplier par une section constante S):

\begin{align*}
\int \overrightarrow{grad}P \overrightarrow{dl} &= \int \rho \overrightarrow{g}\overrightarrow{dl}\\
P(z_2) - P(z_1) &= \frac{\overrightarrow{P_{colonne}}}{S} \cdot \overrightarrow{e_z}
\end{align*}
où $\overrightarrow{P_{colonne}}$ correspond au poids de la colonne comprise entre$z_1$ et $z_2$ dans un cylindre verticale de section S. La pression en un point correspond donc au poids (surfacique) de la colonne de fluide situé au dessus du point considéré.
````

````{attention}
__Besoin d'une équation supplémentaire__


L'équation fondamental de la statique des fluides relie trois grandeurs: le champ de pesanteur (dont il faut connaître l'expression - dans le cadre du cours, il sera supposé uniforme), la masse volumique et la pression. Mais __on ne peut intégrer directement cette équation__ car on a priori aucune information sur la dépendance de la masse volumique vis-à-vis des coordonnées ou de la pression.

Il va donc falloir une équation qui donne une information sur $\rho$ ou qui relie $\rho$ à la pression P. C'est __l'équation d'état du fluide__, c'est-à-dire l'équation qui relie les différenes variables qui caractérise le fluide à l'échelle macroscopique (pression, température, masse volumique... ).

````

