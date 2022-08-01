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
# Méthodes
## Fluides incompressibles

````{admonition} Validité du modèle incompressible 
:class: attention

Dans le cas de l'eau, on peut donner le coefficient de compressibilité isotherme:

$$
\chi_{T} = \frac{1}{\rho}\left(\frac{\partial \rho}{\partial P}\right)_{T} = 5 \times 10^{-10} \rm{Pa^{-1}}
$$
où l'indice T signifie que la température est maintenue constante.

1. Rappeler la valeur numérique de la masse volumique de l'eau
1. Déduire du coefficient $\chi_T$ une relation entre la variation $d\rho$ et la variation $dP$.
1. En déduire une estimation de la variation relative $\frac{\Delta \rho}{\rho_0}$ pour une variation d'altitude $\Delta z$ en considérant que le champ de pression suit le modèle d'un fluide incompressible.
1. Estimer la variation d'altitude nécessaire pour observer une variation de 1\% de la masse volumique. Commenter l'hyptohèse de fluide incompressible dans le cas de l'eau.

````

````{topic} Correction
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

````{admonition} Baromètre 
:class: attention

Le baromètre le plus courant est le baromètre de Torricelli. Il s'agit d'un tube en U fermé à une extrémité et l'autre extrémité est ouverte et à l'air libre. Du côté fermé, le mercure est surmonté par du vide en première approximation (P=0).

1. Exprimer la différence de hauteur h entre les deux surfaces libres du mercure.
1. On donne la masse volumique du mercure $\rho_{Hg} = 13,5 \times 10^3 \rm{kg.m^{-3}}$. Justifier l'utilisation du mercure plutôt que de l'eau pour faire un baromètre.
1. Expliquer la définition de l'unité de pression mmHg (millimètre de mercure): $1\rm{mmHg}=133,3\rm{Pa}$
````

````{topic} Correction
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

## Gaz parfait
````{admonition} Ordres de grandeurs 
:class: attention

On considère une atmosphère isotherme d'un gaz parfait.

1. Donner une expression d'une altitude caractéristique H qui gouverne l'échelle sur laquelle la pression varie notablement.
1. Estimer H pour de l'air à la température $T = 273 \rm{K}$. Quelle hypothèse pourra être fait pour des gaz enfermée dans une enceinte de taille "normale"?
1. Déterminer le champ de masse volumique. En déduire par intégration la masse totale de l'atmosphère (on supposera pour simplifier le calcul que la terre est plate !).
1. On donne ci-dessous le profil de température et le profil de la masse d'atmosphère contenue sous l'altitude z. Commenter la validité du modèle isotherme.


```{figure} ./images/thermo_statique_complement_fluide.jpg
:name: fig_266
:align: center
```
````

````{topic} Démonstration
* __Altitude caractéristique__  
On observe que la pression décroit suivant une exponentielle décroissante. On va considérer que la pression a varier sur quelques H où H est la hauteur caractéristique associées à l'exponentielle, soit $H = \frac{RT}{Mg}$.

On a $H \sim 7800 \rm{m}$. Pour des enceintes de tailles normales (au maximum quelques mètres), on peut considérer que que la __pression au sein d'un gaz est uniforme__.

* __Masse de l'atmosphère__  
La relation des gaz parfaits donne une expression de la masse volumique. On intégrera entre 0 et l'infini pour obtenir une estimation de la masse de l'atmosphère.

* __Pertinence de la modélisation__  
On observe que le profil de mass volumique semble être cohérent mais les valeurs numériques ne le sont pas.

Quant au profil de température, le caractère constant est largement criticable. On utilise souvent un profil de température linéaire.

````

## Théorème d'Archimède
````{admonition} Iceberg 
:class: attention

On veut calculer le volume émergé de l'iceberg qu'on suppose de masse m répartie uniformément et de volume V. On suppose de plus que l'air et l'eau sont pour les dimensions considérées des fluides homogènes.

On donne: $\rho_{glace} = 0,9 \rho_{eau}$ et $\rho_{air} \ll \rho_{glace}$.
````

````{topic} Démonstration
Notons $V_i$ le volume immergé dans l'eau et $V_e$ le voume émergé (donc immergé dans l'air). Les forces qui s'appliquent sur l'iceberg sont (on a pris un axe Oz vertical vers le haut):

* son poids: $\overrightarrow{P} = - \rho_{glace} (V_i + V_e) g \overrightarrow{e_z}$
* la poussée d'Archimède associée à l'eau: $\overrightarrow{\Pi_{A,eau}} = \rho_{eau} V_i g \overrightarrow{e_z}$
* la poussée d'Archimède associée à l'air: $\overrightarrow{\Pi_{A,air}} = \rho_{air} V_e g \overrightarrow{e_z}$


Le bilan statique s'écrit: $\overrightarrow{P} + \overrightarrow{\Pi_{A,eau}} + \overrightarrow{\Pi_{A,air}} = \overrightarrow{0}$ soit:

\begin{align*}
& (\rho_{eau} V_i +\rho_{air}V_e - \rho_{glace} (V_i + V_e))g = 0\\
& \Longrightarrow\frac{V_i}{V_e} = \frac{\rho_{glace} - \rho_{air}}{\rho_{eau} - \rho_{glace}} \approx 9
\end{align*}\end{meth}
````

````{admonition} Ballon ascensionnel 
:class: attention

On s'intéresse à un ballon de volume V constant gonflé avec un gaz plus léger que l'air atmosphérique. Dans ce modèle, nous supposerons que le volume V est suffisamment petit pour qu'on puisse considérer que la masse volumique de l'air qui entoure le ballon est constante. On la note: $\rho_{air}$ On note m la masse totale du ballon et ($\rho$ sa masse volumique moyenne, c'est-à-dire que  $\rho = \frac{m}{V}$, il faut compter dans m la masse du gaz ET de l'enceinte).

1. Etablir l'équation différentielle du mouvement du ballon en supposant le théorème d'Archimède applicable.
1. On suppose qu'à une altitude $z_0$, le ballon est à l'équilibre. Faut-il augmenter ou diminuer la masse volumique du ballon pour monter? Justifier qu'on chauffe alors le gaz à l'intérieur pour s'élever.
1. Pour descendre, on ouvre en général une soupape qui libère du gaz. Justifier la manoeuvre.

````

````{topic} Réponses

1. On est dans le cas où l'on assimile le champ de l'air à celui qu'il aurait au repos ce qui permet d'appliquer le théorème d'Archimède.

$$
m \ddot z = \left(\rho_{air} - \rho\right) g V
$$
2. Il faut évidemment diminuer la masse volumique du ballon pour qu'il monte. En considérant le volume du ballon comme fixe (le ballon est tendu) et sa pression comme fixe (elle es imposée par la pression extérieure, la loi des gaz parfait montre qu'une diminution de la masse est associée à une augmentation de température.

3. Cette fois-ci, la diminution de matière entraîne une diminution du volume (T et P constants) donc une augmentation de la masse volumique (à cause de la masse de la nacelle), ce qui permet de faire redescendre le ballon.
\end{meth}
````

## Calcul de force de pression
````{admonition} Barrage 
:class: attention

On considère un barrage assimilable à un demi-cylindre de hauteur H et de rayon R. L'eau est retenue à "l'intérieur" du demi-cylindre. Calculer la résultante des forces de pression exercée sur le barrage. On prendra l'origine des __profondeur__ z à la surface de l'eau où l'atmosphère supérieur y impose une pression $P_0$. Faire l'application numérique pour un barrage de 10m de haut de rayon 30m.
````

````{topic} Démonstration

* __Choix du système de coordonnées__  

La surface de contact étant un cylindre, on va utiliser un système de coordonnées cylindriques d'axe Oz l'axe du cylindre.

* __Détermination du champ de pression__  

On utilise l'équation barométrique. $P(z) - P(z=0) = P(z) - P_0 = \rho g z$ d'où $P(z) = P_0 + \rho g z$

* __Vecteur surface.__  

Sur un petit élément de surface du barrage, les coordonnées qui varient sont l'angle $\theta$ (dont le déplacement élémentaire correspondant est $R d\theta$) et la hauteur z (dont le déplacement élémentaire correspondant est $dz$).

La surface vaut donc $dS = R dz d\theta$.

Le vecteur normale est $\overrightarrow{e_r}$. On l'oriente positivement $\overrightarrow{dS} = R dz d\theta \overrightarrow{e_r}$ de sorte que la force de pression élémentaire est: $\overrightarrow{dF} = P R dz d\theta \overrightarrow{e_r}$.

* __Expression de l'intégrale__  

L'intégrale s'écrit donc:

\begin{align*}
\overrightarrow{F} = \iint_{M\in surface} P R dz d\theta \overrightarrow{e_r}\\
\overrightarrow{F} = \int_{z=0}^{z=H} \int_{\theta = 0}^{\theta = \pi} P R dz d\theta \overrightarrow{e_r}\\
\overrightarrow{F} = \int_{z=0}^{z=H} \int_{\theta = 0}^{\theta = \pi} P R \left(\cos \theta \overrightarrow{e_x} + \sin \theta \overrightarrow{e_y}\right) dz d\theta
\end{align*}
On observe que les variables d'intégration sont z et $\theta$. On définit les bornes en fonction de la forme du barrage. Il est important de remarquer que le choix du paramétrage influe sur les bornes (ici l'origine des angles $\theta$ qui correspond à l'axe Ox est pris sur un des bords du demi-cercle.

On remarque que le vecteur $\overrightarrow{e_r}$ va varier durant l'intégration (il dépend de $\theta$), on l'a donc projeté sur une base cartésienne.

* __Calcul de l'intégrale__  

Avant de se lancer dans le calcul, on va utiliser les symétries. Ici la surface de contact est symétrique par rapport à au plan xOy de sorte qu'on attend que la composante suivant $\overrightarrow{e_x}$ sera nulle (on pourra s'en convaincre en la calculant). On va donc projeter la résultante suivant $\overrightarrow{e_y}$ et ne calculer que cette composante.

L'intégrale est à variable séparable, c'est-à-dire que la fonction peut être écrite comme un produit de deux fonctions d'une variable z et $\theta$ de sorte que l'intégrale double se réécrit comme le produit de deux intégrales simples:

\begin{align*}
\overrightarrow{F} \cdot \overrightarrow{e_y} = \int_{z=0}^{z=H} \int_{\theta = 0}^{\theta = \pi} \left(P_0 + \rho g z\right) R \sin \theta  dz d\theta \\
\overrightarrow{F} \cdot \overrightarrow{e_y} = R \left(\int_{z=0}^{z=H} \left(P_0 + \rho g z\right) dz\right) \left(\int_{\theta = 0}^{\theta = \pi} \sin \theta d\theta\right) \\
\overrightarrow{F} \cdot \overrightarrow{e_y} = R \left(P_0 H + \frac{\rho g H^2}{2}\right) \left(2\right) \\
\overrightarrow{F} \cdot \overrightarrow{e_y} = R \left(2 P_0 H + \rho g H^2\right)
\end{align*}
````

