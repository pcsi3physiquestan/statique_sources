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

````{topic} Rappel : Relation pression force
Pour un corps subissant l'action d'un fluide dont le champ de pression est P, si on note $\Sigma$ la surface de contact entre le fluide et le corps étudié, la résulante des forces de pression du fluide sur le corps s'écrit:

\begin{equation}
\iint_{M \in \Sigma} P \overrightarrow{d^2 S}
\end{equation}
Si la surface de contact est une surface fermée, on note l'intégrale avec un cercle. On a aussi orienté le vecteur surface dans les conventions précisées précédemment (ce devrait être une intégrale double):

\begin{equation}
\oint_{M \in \Sigma}  - P \overrightarrow{d^2 S_{ext}}
\end{equation}


Pour connaître la résultante des forces, il faut donc:

1. Calculer/connaître le champ de pression dans le fluide. Dans l'hypothèse d'un fluide au repos, on utilisera l'équation fondamentale de la statique des fluides et les types d'études vus précédemment.
1. Calculer l'intégrale. La méthode de calcul sera présentée par la suite.
````

## Théorème d'Archimède

````{margin} Corps en mouvement
Il arrive qu'on utilise la poussée d'Archimède alors que si le corps se déplace, le fluide n'est plus au repos. Ceci n'est vrai que si l'on suppose que le fluide est peu perturbé par le mouvement du solide.
````
````{important} __Théorème d'Archimède__

Tout corps entièrement immergé au repos subit de la part du fluide une force opposée à celle du poids du volume de fluide déplacé. On appelle cette force la poussée d'Archimède. D'une manière plus générale, elle est définie comme la résultante des forces de pression du fluide (ce devrait être une intégrale double):

\begin{equation}
\overrightarrow{\Pi_A} = \oint_{\Sigma}-P(M) \overrightarrow{d^2 S(M)} = - m _{\textrm{fluide déplacé}} \overrightarrow{g}
\end{equation}

````

````{topic} Démonstration
Si le fluide est au repos, alors la relation fondamentale de la statique des fluides implique que le champ de pression ne dépend que de l'altitude. Ainsi, les forces de pression s'exerçant à la frontière du corps immergée sont les mêmes que le corps soit présent ou non. On peut donc mentalement remplacé le corps immergé par le fluide environnant. La force exercée sera la même.

Or le fluide étant au repos, cette masse de fluide est équilibrée par la force de pression $\overrightarrow{\Pi_A}$ et son propre poids. Il vient que $\overrightarrow{\Pi_A} = - \overrightarrow{P_{fluide deplace}}$
````

````{topic} Centre de poussée
N'oublions que les corps étudiée ne sont pas des points matériels mais des solides. Il faudrait donc définir la résultante des forces de pression ET le moment résultant de ces forces. En pratique, on définit plutôt un point de moment nul appelé __centre de poussée.__

La démonstration précédente permet de comprendre que le centre de poussée C correspond au centre d'inertie du volume de fluide déplacé. Dans le cas des fluides homogènes, le placement d'un tel point peut se faire qualitativement.

Si la répartition de masse du corps considéré et du fluide déplacé est différente, C et G le centre d'inertie du corps ne sont pas confondu. __On s'entraînera à montrer__ que les positions d'équilibre correspondent alors aux cas où C et G sont à la verticale l'un de l'autre et que la seule position stable au cas où le centre d'inertie est sous le centre de poussée. Cela explique qu'on a tendance à placer les marchandises lourdes au fond des bateaux.

```{figure} ./images/thermo_centre_pousse.jpg
:name: fig_267
:align: center
```
````

````{topic} Corps immergé dans deux fluides
* __Horizontalité de l'interface__ : Pour deux fluides en contact, l'étude de l'interface permet de montrer que la surface de contact est nécessaire horizontale et que le fluide le plus de dense est au dessous.
* On notera aussi que l'interface étant au repos, il y a __nécessairement continuité du champ de pression à l'interface entre les deux fluides.__.
    * Ces observations seront nuancées par la notion de tension de surface en deuxième année. Pour les systèmes étudiés en première année, on considérera cet effet comme négligeable.
* Le théorème d'Archimède nécessite que le corps soit __entièrement immergé__. Mais le théorème s'applique si plusieurs fluides (au repos) différents entourent le corps.
> C'est le cas d'un objet flottant: il est entouré par l'eau ET l'air. Le théorème d'Archimède s'applique alors en divisant en deux le corps: on distinguera la partie immergée dans l'eau et la partie immergée dans l'air. Comme nous le verrons, la masse volumique de l'air étant très faible devant celle de l'eau, on néglige souvent la poussée d'Archimède sur la partie dans l'air mais en toute rigueur, elle doit être comptabilisée.
````

## Non application du théorème d'Archimède

````{admonition} Cas de non application
:class: tip

Le théorème d'Archimède ne s'applique que si le corps est entièrement immergé dans les fluide, c'est-à-dire qu'il n'y pas de contact solide en certains points.

Sinon, il ne s'applique pas. Par exemple un corps posé au fond de l'eau ou un système dont seule une aprtie est en contact avec le fluide (barrage).
````

Si le théorème d'Archimède ne s'applique pas, la résultat des forces de pression ne peut se calculer qu'au moyen de l'intégrale:

\begin{equation}
\iint_{M \in \Sigma} P \overrightarrow{d^2 S}
\end{equation}

````{margin} Bases locales

Lorsqu'on utilise des coordonnées cylidnriques ou sphériques, il arrive fréquemment que le vecteur unitaire portant $\overrightarrow{d^2 S}$ __varie quand la variable d'intégration varie__. Il est donc important de projeter de tels vecteurs dans une base globale (cartésienne).
````
````{hint} __Calcul de la résultante des forces__  

Calculer la résultante des forces nécessite de choisir un système de coordonnées adapté puis d'exprimer chaque élément de l'intégrale dans ce système. Les étapes sont  donc:

1. Choisir un système de coordonnées adapté aux symétries du problème. Normalement, le vecteur surface doit s'exprimer simplement suivant un seul vecteur.
1. Exprimer le vecteur surface dans le système de coordonnées. On rappelle qu'on distingue le calul de dS comme un produit des déplacements élémentaires et l'expression du vecteur unitaire portant $\overrightarrow{dS}$.
1. Exprimer le champ de pression dans le système de coordonnées. En général, on utilise l'équation fondamentale de la statique des fluides ou ses corollaires (comme l'équation barométrique).
1. Réécrire alors l'intégrale et en déduire les variables d'intégration. On déterminer alors les bornes d'intégration de chaque intégrale en fonction de la surface d'intégration.
1. Dans le cadre du programme, l'intégrale de surface à calculer est une intégrale à variable séparable. On calcule donc séparément deux intégrales qu'on multiplie.
````

