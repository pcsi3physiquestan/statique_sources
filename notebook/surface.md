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
# Préambule: Surfaces orientées

## Vecteur surface

````{important} __Définition : Vecteur surface élémentaire__

Soit une surface infinitésimale de surface dS, on peut orienté la surface, c'està-dire choisir un sens dans lequel la traversée de la surface est positif. On définit alors le vecteur surface $\overrightarrow{dS}$ comme le vecteur de norme $dS$ orienté perpencidulairement à la surface et dirigé dans le sens d'orientation choisi de la surface.

```{figure} ./images/mathematiques_surface_contour.jpg
:name: fig_263
:align: center
```
````

````{admonition} Exemple : Expression d'un vecteur surface.
:class: tip, dropdown

Dans le cadre du programme, l'expression d'un vecteur surface élémentaire s'établira toujours simplement si l'on choisit correctement le système de coordonnées.

Par exemple, si l'on considère un plan et une petite portion infinitésimale dS du plan, on va choisir de paramétrer ce plan avec un système de coordonnées cartésiennes (en choisissant par exemple l'axe Oz perpendiculaire au plan). Un élément de surface infinitésimal est alors un carré dont les côté sont les variations infinitésimales de x et y soit dx et dy. La surface vaut alors $dS = dx dy$.

De la même manière, l'orientation du vecteur s'établira, dans le cadre du programme, suivant un seul vecteur de la base. Ici, il le vecteur normal au plan est le vecteur $\pm \overrightarrow{e_z}$. Nous reviendrons plus tard sur les convention d'orientation des surfaces. Ici, on peut choisir arbitrairement l'orientation. On écrira par exemple le vecteur surface $\overrightarrow{dS} = dx dy \overrightarrow{e_z}$.
````

__Notation infinitésimale__  
Normalement, il faudrait noter $d^2S$ car il s'agit d'un double infinitésimale (produit de deux infinitésimaux comme on peut le voir sur l'exemple précédent). Par souci de simpification, on notera simplement dS. On retiendra que le fait que ce soit un double infinitésimal signifie que des surfaces infinitésimales, il faudra les sommer sur deux coordonnées: il s'agira d'une __intégrale double__. La méthode permettant de calculer une telle intégrale sera exposée plus tard.


````{important} __Définition : Vecteur surface__

Si l'on considère une surface d'extension finie, on peut la découper en une multitude de surface infinitésimale $\overrightarrow{dS}$. Le vecteur surface $\overrightarrow{S}$ est alors la somme des vecteurs surfaces infinitésimaux:

\begin{equation}
\overrightarrow{S} = \iint_{M \in S} \overrightarrow{dS}
\end{equation}
Comme dit précédemment, il s'agit d'une intégrale double sur une surface. Nous verrons plus tard comment la calculer.

````

## Vecteur surface: Orientation

````{important} __Définition : Surface fermée et non fermée.__

Une surface fermée est une surface qui divise l'espace en deux parties et où il est impossible de passer d'une partie à l'autre sans traverser la surface. On définit alors un intérieur et un extérieur.

````

__Convention d'orientation pour les surfaces fermées.__  
Pour une surface fermée, on oriente par convention le vecteur surface vers l'extérieur.


__Convention d'orientation d'une surface non fermée.__  
Pour une surface non fermée, l'orientation de la surface est arbitraire sauf si l'on oriente le contour sur lequel s'appuie la surface. Ce cas ne sera traité qu'en fin d'année. Pour l'instant , on choisira arbitrairement (c'est-à-dire intelligement) l'orientation de la surface.


