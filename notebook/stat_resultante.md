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
# Expression de la résultante des forces de pression

## Relation pression-force: Rappel

_Rappel : Relation pression force_
Pour un corps subissant l'action d'un fluide dont le champ de pression est P, si on note $\Sigma$ la surface de contact entre le fluide et le corps étudié, la résulante des forces de pression du fluide sur le corps s'écrit:

\begin{equation}
\iint_{M \in \Sigma} P \overrightarrow{dS}
\end{equation}
Si la surface de contact est une surface fermée, on note l'intégrale avec un cercle. On a aussi orienté le vecteur surface dans les conventions précisées précédemment (ce devrait être une intégrale double):

\begin{equation}
\oint_{M \in \Sigma}  - P \overrightarrow{dS_{ext}}
\end{equation}


Pour connaître la résultante des forces, il faut donc:

1. Calculer/connaître le champ de pression dans le fluide. Dans l'hypothèse d'un fluide au repos, on utilisera l'équation fondamentale de la statique des fluides et les types d'études vus précédemment.
1. Calculer l'intégrale. La méthode de calcul sera présentée par la suite.


Avant d'apprendre à calculer une telle intégrale, nous allons voir un cas particulier où ce calcul n'est pas nécessaire: le cas d'application du théorème d'Archimède.


## Théorème d'Archimède

````{admonition} Fondamental : Théorème d'Archimède
:class: attention

Tout corps entièrement immergé au repos subit de la part du fluide une force opposée à celle du poids du volume de fluide déplacé. On appelle cette force la poussée d'Archimède. D'une manière plus générale, elle est définie comme la résultante des forces de pression du fluide:

\begin{equation}
\overrightarrow{\Pi_A} = \oint_{\Sigma}-P(M) \overrightarrow{dS(M)} = - m _{\textrm{fluide déplacé}} \overrightarrow{g}
\end{equation}

````

__Démonstration__  
Si le fluide est au repos, alors la relation fondamentale de la statique des fluides implique que le champ de pression ne dépend que de l'altitude. Ainsi, les forces de pression s'exerçant à la frontière du corps immergée sont les mêmes que le corps soit présent ou non. On peut donc mentalement remplacé le corps immergé par le fluide environnant. La force exercée sera la même.

Or le fluide étant au repos, cette masse de fluide est équilibrée par la force de pression $\overrightarrow{\Pi_A}$ et son propre poids. Il vient que $\overrightarrow{\Pi_A} = - \overrightarrow{P_{fluide deplace}}$


````{dropdown} Remarque
__Corps en mouvement__  
Il arrive qu'on écrive un PFD en utilise la poussée d'Archimède alors que si le corps se déplace, le fluide n'est plus au repos. Ceci n'est vrai (en première approximation) que si l'on néglige les frottements du fluide et que l'on suppose que le fluide est peu perturbé par le solide. Cela implique que le mouvement du corps est relativement lent (on rappelle que le frottement fluide est proportionnel à la vitesse).

Si le corps est moins dense que l'eau, il va remonter, s'il est plus dense, il va tomber au fond.
````

__Centre de poussée__  
N'oublions que les corps étudiée ne sont pas des points matériels mais des solides. Il faudrait donc définir la résultante des forces de pression ET le moment résultant de ces forces. En pratique, on définit plutôt un point de moment nul appelé __centre de poussée.__

La démonstration précédente permet de comprendre que le centre de poussée C correspond au centre d'inertie du volume de fluide déplacé. Dans le cas des fluides homogènes, le placement d'un tel point peut se faire qualitativement.

Si la répartition de masse du corps considéré et du fluide déplacé est différente, C et G le centre d'inertie du corps ne sont pas confondu. __On s'entraînera à montrer__ que les positions d'équilibre correspondent alors aux cas où C et G sont à la verticale l'un de l'autre et que la seule position stable au cas où le centre d'inertie est sous le centre de poussée. Cela explique qu'on a tendance à placer les marchandises lourdes au fond des bateaux.

```{figure} ./images/thermo_centre_pousse.jpg
:name: fig_267
:align: center

```


## Corps immergé dans deux fluides

__Horizontalité de l'interface__  
Pour deux fluides en contact, l'étude de l'interface permet de montrer que la surface de contact est nécessaire horizontale et que le fluide le plus de dense est au dessous.

On notera aussi que l'interface étant au repos, il y a __nécessairement continuité du champ de pression à l'interface entre les deux fluides.__.

Ces observations seront nuancées par la notion de tension de surface en deuxième année. Pour les systèmes étudiés en première année, on considérera cet effet comme négligeable.


````{dropdown} Remarque : Théorème d'Archimède et multiples fluides
Le théorème d'Archimède nécessite que le corps soit __entièrement immergé__. Mais le théorème s'applique si plusieurs fluides (au repos) différents entourent le corps.

C'est le cas d'un objet flottant: il est entouré par l'eau ET l'air. Le théorème d'Archimède s'applique alors en divisant en deux le corps: on distinguera la partie immergée dans l'eau et la partie immergée dans l'air. Comme nous le verrons, la masse volumique de l'air étant très faible devant celle de l'eau, on néglige souvent la poussée d'Archimède sur la partie dans l'air mais en toute rigueur, elle doit être comptabilisée.

Une justification sera donnée en classe.
````

## Iceberg

````{admonition} Exercice 
:class: attention

On veut calculer le volume émergé de l'iceberg qu'on suppose de masse m répartie uniformément et de volume V. On suppose de plus que l'air et l'eau sont pour les dimensions considérées des fluides homogènes.

On donne: $\rho_{glace} = 0,9 \rho_{eau}$ et $\rho_{air} \ll \rho_{glace}$.
````

````{dropdown} Démonstration
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

## Ballon ascensionnel

````{admonition} Exercice 
:class: attention

On s'intéresse à un ballon de volume V constant gonflé avec un gaz plus léger que l'air atmosphérique. Dans ce modèle, nous supposerons que le volume V est suffisamment petit pour qu'on puisse considérer que la masse volumique de l'air qui entoure le ballon est constante. On la note: $\rho_{air}$ On note m la masse totale du ballon et ($\rho$ sa masse volumique moyenne, c'est-à-dire que  $\rho = \frac{m}{V}$, il faut compter dans m la masse du gaz ET de l'enceinte).

1. Etablir l'équation différentielle du mouvement du ballon en supposant le théorème d'Archimède applicable.
1. On suppose qu'à une altitude $z_0$, le ballon est à l'équilibre. Faut-il augmenter ou diminuer la masse volumique du ballon pour monter? Justifier qu'on chauffe alors le gaz à l'intérieur pour s'élever.
1. Pour descendre, on ouvre en général une soupape qui libère du gaz. Justifier la manoeuvre.

````

````{dropdown} Réponses

1. On est dans le cas où l'on assimile le champ de l'air à celui qu'il aurait au repos ce qui permet d'appliquer le théorème d'Archimède.

\begin{equation}
m \ddot z = \left(\rho_{air} - \rho\right) g V
\end{equation}
2. Il faut évidemment diminuer la masse volumique du ballon pour qu'il monte. En considérant le volume du ballon comme fixe (le ballon est tendu) et sa pression comme fixe (elle es imposée par la pression extérieure, la loi des gaz parfait montre qu'une diminution de la masse est associée à une augmentation de température.

3. Cette fois-ci, la diminution de matière entraîne une diminution du volume (T et P constants) donc une augmentation de la masse volumique (à cause de la masse de la nacelle), ce qui permet de faire redescendre le ballon.
\end{meth}
````

## Non application du théorème d'Archimède

````{admonition} Exemple : Exemple de cas de non application
:class: tip, dropdown

Le théorème d'Archimède ne s'applique que si le corps est entièrement immergé dans les fluide, c'est-à-dire qu'il n'y pas de contact solide en certains points.

Sinon, il ne s'applique pas. Par exemple un corps posé au fond de l'eau ou un système dont seule une aprtie est en contact avec le fluide (barrage).
````


Si le théorème d'Archimède ne s'applique pas, la résultat des forces de pression ne peut se calculer qu'au moyen de l'intégrale:

\begin{equation}
\iint_{M \in \Sigma} P \overrightarrow{dS}
\end{equation}

__Calcul de la résultante des forces__  

Calculer la résultante des forces nécessite de choisir un système de coordonnées adapté puis d'exprimer chaque élément de l'intégrale dans ce système. Les étapes sont  donc:

1. Choisir un système de coordonnées adapté aux symétries du problème. Normalement, le vecteur surface doit s'exprimer simplement suivant un seul vecteur.
1. Exprimer le vecteur surface dans le système de coordonnées. On rappelle qu'on distingue le calul de dS comme un produit des déplacements élémentaires et l'expression du vecteur unitaire portant $\overrightarrow{dS}$.
1. Exprimer le champ de pression dans le système de coordonnées. En général, on utilise l'équation fondamentale de la statique des fluides ou ses corollaires (comme l'équation barométrique).
1. Réécrire alors l'intégrale et en déduire les variables d'intégration. On déterminer alors les bornes d'intégration de chaque intégrale en fonction de la surface d'intégration.
1. Dans le cadre du programme, l'intégrale de surface à calculer est une intégrale à variable séparable. On calcule donc séparément deux intégrales qu'on multiplie.

````{admonition} Attention : Bases locales
:class: note

Lorsqu'on utilise des coordonnées cylidnriques ou sphériques, il arrive fréquemment que le vecteur unitaire portant $\overrightarrow{dS}$ __varie quand la variable d'intégration varie__. Il est donc important de projeter de tels vecteurs dans une base globale (cartésienne). Nous verrons cela sur l'exemple du barrage.

````

````{dropdown} Remarque
__Symétrie__  
L'intégrand est un vecteur ($P \overrightarrow{dS}$) et on peut donc avoir à intégrer deux ou trois composantes séparément. Dans de nombreux cas l'intégration de toutes les composantes n'est pas nécessaire car certaines composantes sont nulles et ce résultat peut être déduit de l'étude des symétries du problème.
````

__Moment résultant__  
Cette méthode de calcul permettrait aussi de calcul un moment résultant.


## Méthode: Barrage

````{admonition} Exercice 
:class: attention

On considère un barrage assimilable à un demi-cylindre de hauteur H et de rayon R. L'eau est retenue à "l'intérieur" du demi-cylindre. Calculer la résultante des forces de pression exercée sur le barrage. On prendra l'origine des __profondeur__ z à la surface de l'eau où l'atmosphère supérieur y impose une pression $P_0$. Faire l'application numérique pour un barrage de 10m de haut de rayon 30m.
````

````{dropdown} Démonstration

__Choix du système de coordonnées__  

La surface de contact étant un cylindre, on va utiliser un système de coordonnées cylindriques d'axe Oz l'axe du cylindre.

__Détermination du champ de pression__  

On utilise l'équation barométrique. $P(z) - P(z=0) = P(z) - P_0 = \rho g z$ d'où $P(z) = P_0 + \rho g z$

__Vecteur surface.__  

Sur un petit élément de surface du barrage, les coordonnées qui varient sont l'angle $\theta$ (dont le déplacement élémentaire correspondant est $R d\theta$) et la hauteur z (dont le déplacement élémentaire correspondant est $dz$).

La surface vaut donc $dS = R dz d\theta$.

Le vecteur normale est $\overrightarrow{e_r}$. On l'oriente positivement $\overrightarrow{dS} = R dz d\theta \overrightarrow{e_r}$ de sorte que la force de pression élémentaire est: $\overrightarrow{dF} = P R dz d\theta \overrightarrow{e_r}$.

__Expression del'intégrale__  

L'intégrale s'écrit donc:

\begin{align*}
\overrightarrow{F} = \iint_{M\in surface} P R dz d\theta \overrightarrow{e_r}\\
\overrightarrow{F} = \int_{z=0}^{z=H} \int_{\theta = 0}^{\theta = \pi} P R dz d\theta \overrightarrow{e_r}\\
\overrightarrow{F} = \int_{z=0}^{z=H} \int_{\theta = 0}^{\theta = \pi} P R \left(\cos \theta \overrightarrow{e_x} + \sin \theta \overrightarrow{e_y}\right) dz d\theta
\end{align*}
On observe que les variables d'intégration sont z et $\theta$. On définit les bornes en fonction de la forme du barrage. Il est important de remarquer que le choix du paramétrage influe sur les bornes (ici l'origine des angles $\theta$ qui correspond à l'axe Ox est pris sur un des bords du demi-cercle.

On remarque que le vecteur $\overrightarrow{e_r}$ va varier durant l'intégration (il dépend de $\theta$), on l'a donc projeté sur une base cartésienne.

__Calcul de l'intégrale__  

Avant de se lancer dans le calcul, on va utiliser les symétries. Ici la surface de contact est symétrique par rapport à au plan xOy de sorte qu'on attend que la composante suivant $\overrightarrow{e_x}$ sera nulle (on pourra s'en convaincre en la calculant). On va donc projeter la résultante suivant $\overrightarrow{e_y}$ et ne calculer que cette composante.

L'intégrale est à variable séparable, c'est-à-dire que la fonction peut être écrite comme un produit de deux fonctions d'une variable z et $\theta$ de sorte que l'intégrale double se réécrit comme le produit de deux intégrales simples:

\begin{align*}
\overrightarrow{F} \cdot \overrightarrow{e_y} = \int_{z=0}^{z=H} \int_{\theta = 0}^{\theta = \pi} \left(P_0 + \rho g z\right) R \sin \theta  dz d\theta \\
\overrightarrow{F} \cdot \overrightarrow{e_y} = R \left(\int_{z=0}^{z=H} \left(P_0 + \rho g z\right) dz\right) \left(\int_{\theta = 0}^{\theta = \pi} \sin \theta d\theta\right) \\
\overrightarrow{F} \cdot \overrightarrow{e_y} = R \left(P_0 H + \frac{\rho g H^2}{2}\right) \left(2\right) \\
\overrightarrow{F} \cdot \overrightarrow{e_y} = R \left(2 P_0 H + \rho g H^2\right)
\end{align*}
````

