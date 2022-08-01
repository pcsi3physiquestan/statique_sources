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
# Forces de pression et pression

## Pression et forces de pression: Définitions

_Rappel : Actions de contact: Contrainte normale et tangentielle_
Dans une action de contact, on distingue au niveau des actions ponctuelles la composante normale à la surface de contact et la composante tangentielle à la surface de contact. La composante tangentielle correspond aux frottements et la composante normale aux __forces de pression__.

Dans le cadre de l'étude de l'action d'un fluide, on va séparer l'étude de l'action tangentielle et de l'action normale.

Le but de cette séquence est d'étudier les forces de pression dans le cadre de la __statique des fluides__, c'est-à-dire que l'on va supposer que le fluide est __au repos__.

````{sidebar} Signe de la relation force-pression
Attention, la relation précédente est donnée en orientant le vecteur surface vers l'extérieur du système qui exerce la force. Il arrive que pour des raisons de commodité ou de convention, le vecteur surface soit orienté dans l'autre sens. Il faut alors faire attention au signe dans la relation force-pression (il apparaît un signe "-").

````
````{important} __Pression__

A l'échelle macroscopique (notre échelle), on définit la __pression__ comme une grandeur scalaire positive correspondant à l'intensité de la force normale exercée __par unité de surface__.

Pour une surface infinitésimale $d^2S$, on relie la force de pression à la pression:

$$
\overrightarrow{d^2F} = P \overrightarrow{d^2S}
$$
```{figure} ./images/thermo_pression_def.jpg
:name: fig_264
:align: center
```
où le vecteur $\overrightarrow{d^2S}$ est orienté vers l'extérieur du système qui __exerce__ la force de pression.
````

__Relation force pression. Cas fini.__  
Dans le cas d'une action globale d'un fluide sur le système mécanique étudié, la force de pression résultante s'écrit comme la somme de la force ponctuelle sur toute la surface de contact:

$$
\overrightarrow{F} = \iint_{M\in \Sigma_{contact}} P(M) \overrightarrow{d^2S}(M)
$$

````{topic} Contexte
Dans ce chapitre, nous allons étudier deux aspects importants:

* la détermination de la pression en chaque point d'un fluide. On parlera de champ de pression. Nous verrons que l'équation principale permettant d'établir cette caractéristique est appelée __équation fondamentale de la statique des fluides__. Nous traiterons les cas particuliers des fluides dits incompressibles et des gaz parfaits. Comme nous le verrons en thermodynamique, la connaissance de ce champ de pression ne sert pas qu'à calculer une force de pression.
* Dans un second temps, nous supposerons le champ de pression dans un fluide établi et nous apprendrons à calculer la force de pression par calcul de l'intégrale donnée précédemment ou par application du théorème d'Archimède.
````

## Remarques sur la composante tangentielle (en ligne)

````{topic} Composante tangentielle et fluide au repos
Dans l'étude des fluides, on sépare en général en deux actions séparées la composante normale (force de pression) et la composante tangentielle (force de frottement fluides).

Ici, on étudie des fluides au repos, de sorte qu'on considèrera que la force de frottements fluides est nulle (on rappelle qu'elle est proportionnelle à la vitesse relative du système par rapport au fluide).

Dans le cas de mouvements faibles du système subissant l'action du fluide, on sera amené réintroduire une force de frottements fluides tout en considérant que l'action normale du fluide sur le système est assimilable à celle du fluide au repos. C'est une approximation plus ou moins valable suivant les cas mais nous ne discuterons pas de sa validité dans le cadre du programme.
````

## Origine microscopique de la pression (en ligne)

````{topic} Origine microscopique
A l'échelle microscopique, on peut traduire la pression comme un __flux__ de quantité de mouvement à travers la surface dS, c'est-à-dire un échange, par unité de temps de quantité de mouvement perpendiculairement à la surface et par unité de surface (l'échange de quantité de mouvement tangentiel correspond à la composante...  tangentielle).

* Exemple : Pression sur une paroi
>
>Le cas de la pression sur une paroi est le cas le plus utile pour nous. Lorsque les particules du fluide arrivent sur la paroi, elles ont une vitesse $\overrightarrow{v} = V_{\perp,1}\overrightarrow{e_{\perp}} + V_{//,1} \overrightarrow{e_{//}}$ où les symboles $\perp$ et $//$ traduisent les composantes de vitesse parallèles et perpendiculaires à la paroi. Si $\overrightarrow{e_{\perp}}$ est dirigé du fluide vers la paroi, alors $V_{\perp,1}$ est nécessairement positive sinon la particule ne heurterait pas la paroi.
>
>Après avoir "rebondi" sur la paroi, la particule possède une vitesse $\overrightarrow{v} = V_{\perp,2}\overrightarrow{e_{\perp}} + V_{//,2} \overrightarrow{e_{//}}$ avec $V_{\perp,2}$ négatif.
>
>La quantité de mouvement transférée par la particule perpendiculairement à la surface est alors $\overrightarrow{\Delta p} \cdot \overrightarrow{e_{\perp}}= m (v_{\perp,2} - v_{\perp,1})$. En la ramenant par unité de temps, on trouve bien une force. Il reste encore à faire une étude statistique de l'ensemble des particules qui viennent heurter la paroi pendant un temps dt pour remonter à un calcul de pression. On parle de __pression cinétique__.
>
>Un tel calcul sera réalisé en cours de thermodynamique. A l'heure actuelle, l'origine microscopique de la pression sera affirmé sans être utilisé.

* Exemple : Pression interne d'un fluide
>
>Cette appréciation de la pression est moins utile à connaître en première année. Lorsqu'on étudie un fluide, on peut parler de la pression en un point du fluide même s'il n'est pas en contact avec la paroi. Il s'agit alors du transfert de quantité de mouvement par unité de temps et de surface entre une petite portion du fluide (on parlera de particule de fluide, cf. suite) et le reste du fluide.
>
>Cette fois, il y a très peu de "choc" qui se produisent exactement à la surface de la portion de fluide (théoriquement, ce nombre est nul !). Le transfert de quantité de mouvement se fait alors par transfert de matière car le système est alors ouvert.
````
