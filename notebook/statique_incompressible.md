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

````{note}
Un fluide est __incompressible_ si sa masse volumique est la même quelques soient les conditions de pression.
````

## Equation barométrique

````{margin}
Il s'agit de profondeur soit la coordonnée verticale pour un axe pris vers le __bas__.
````
````{important} __Equation barométrique - Champ de pression pour un fluide incompressible__

Dans un fluide incompressible de masse volumique $\rho_0$ dans un champ de pesanteur d'intensité $g$, le champ de pression ne dépend que de la profondeur. La variation de pression $\Delta P = P(h_2) - P(h_1)$ entre les __profondeurs__ $h_2$ et $h_1$ s'écrit:

$$
\Delta P = P(h_2) - P(h_1) = \rho_0 g (h_2 - h_1)
$$
````

````{admonition} Démonstration
:class: important
>On applique l'équation fondamental de la dynamique avec $\rho_0$ uniforme (on oriente l'axe z vers le bas et les axes x et y sont horizontaux):
>
>\begin{equation}
\begin{cases}
\frac{\partial P}{\partial x} &= 0\\
\frac{\partial P}{\partial y} &= 0\\
\frac{\partial P}{\partial z} &= \rho_0 g\\
\end{cases}
\end{equation}
>Les deux premières équations permette de dire que le champ de pression ne dépend que de z. On peut donc réécrire P comme une fonction d'une seule variable $P(z)$ et la dérivée partielle suivant z devient une dérivée droite. En intégrant entre $z = h_1$ et $z = h_2$, il vient l'équation demandée (on rappelle que $\rho_0$ est uniforme).
````

````{topic} Interprétation
On peut remarquer à nouveau que la variation de pression correspond à $\rho_0 g \Delta h$, soit le poids, par unité de surface de la colonne de fluide se situant au dessus sur une hauteur $\Delta h$.

On remarquera aussi que le champ de pression ne varie pas à altitude constante __quelque soit la forme du fluide.__. Il suffit que les différentes parties du fluide communiquent.
````



