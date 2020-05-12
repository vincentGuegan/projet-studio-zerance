# projet-studio-zerance

Bonjour,

Vous pouvez mettre la main sur le projet via le lien suivant:

[https://vincentguegan.github.io/projet-studio-zerance/](https://vincentguegan.github.io/projet-studio-zerance/)

Je vais vous expliquer les avancées sur la création de cette page section par section:

De base j'ai crée une page html classique en me servant du snippet boilerplate qui crée une page doctype classique.

## Section header

Dans le header se trouve mon logo et mon menu de navigation.
J'ai donc créé une section plutôt classique incluant une balise nav classique incorporant un `ul` et 3 `li` pour aller vers chacune des prochaines sections.

Chacun des li inclus une redirection vers les sections suivantes grâce au `a href` et `#le nom de la section`

L'image du logo étant incluse dans le header, on peut la récupérer dans son dossier via un `img src`.

La classe d-flex du header me permet de transformer les enfants en flex items.

### Difficultés:

Ce qui m'a pris du temps sur cette partie correspond à:

Un problème de mise en page de la barre de navigation avant que je trouve la classe à utiliser `d-flex` sur [https://o7planning.org/fr/12023/tutoriel-bootstrap-flex](https://o7planning.org/fr/12023/tutoriel-bootstrap-flex)

Concernant le souligné jaune des boutons du menu, j'ai cherché comment obtenir un effet de transition d'un noir non souligné vers un jaune souligné progressif. J'ai trouvé la transition progressif sur xul.fr et je l'ai adapté à mon `nav__links li > a` dans mon css et j'ai ajouté la couleur jaune disponible pour mon `nav__links li > a` via un `:hover`
[https://www.xul.fr/css/transition.php](https://www.xul.fr/css/transition.php)
Je n'ai cependant pas trouvé comment avec un effet de souligné gauche-droite dynamique.

Une mauvaise utilisation du fichier fourni Karla-Regular avec `@font-face` en css (car j'étais parti sur l'utilisation de Karla via `google font`, ce qui n'était pas la consigne).

La partie responsive avec `@media` pour faire disparaître la navbar à un `max-width` de 800px que j'ai compris via un lien vers alsacreation et son explication:
[https://www.alsacreations.com/article/lire/930-css3-media-queries.html](https://www.alsacreations.com/article/lire/930-css3-media-queries.html)

### Temps:

Je pense avoir passé entre 2-3h sur cette section.

## Section Shopify

Pour cette section, il m'a fallu prendre en compte 4 points:

1: La date et le texte doivent être en balise h1 mais faire chacun une taille spécifique et s'adapter à plusieurs tailles d'écran dynamiquement

Pour cela, j'ai utilisé les recommandations de css-tricks en utilisant viewport-weight `vw`pour adapter mon font-size à la taille de l'écran.
[https://css-tricks.com/viewport-sized-typography/](https://css-tricks.com/viewport-sized-typography/)

2: Le mot Shopify doit être souligné, j'ai utilisé également une explication de css-tricks avec l'adaptation de la propriété css `background-repeat` pour mon souligné jaune `.underline-yellow` sous le mot Shopify.
[https://css-tricks.com/almanac/properties/b/background-repeat/](https://css-tricks.com/almanac/properties/b/background-repeat/)

Sa taille est rendu responsive via l'utilisation ici aussi de la propriété `vw`.

3: Il faut inclure `<`et `/>`qui posent problème lorsqu'on souhaite les écrire en simple texte.
Pour cela, j'ai utilisé les pseudos éléments `::before` et `::after` en css en cherchant et trouvant l'explication css-tricks suivantes:
[https://css-tricks.com/almanac/selectors/a/after-and-before/](https://css-tricks.com/almanac/selectors/a/after-and-before/)


### Difficultés:

Concernant `.underline-yellow`, je n'ai pas trouvé tout de suite comment le rendre proprement responsive; j'y suis revenu après avoir travaillé sur une autre section, et j'ai trouvé qu'il fallait rajouter `background-size: 100%`.

Je n'ai pas trouvé comment ajouté, et ce quelque soit la taille de l'écran, le mot "amazing" sur la 2eme ligne de manière continue avec le mot Shopify.

### Temps:

En revenant plusieurs fois dessus, je pense avoir passé entre 2-3h sur cette section.

## section Portfolio


Concernant cette section, je suis parti sur une explication via le tuto grid of squares pour effectuer ma grill css [https://www.youtube.com/watch?time_continue=159&v=8bhKjoowr4c&feature=emb_logo](https://www.youtube.com/watch?time_continue=159&v=8bhKjoowr4c&feature=emb_logo)
Je me suis aperçu plus tard que cela n'effectuais pas le rendu que je voulais dès lors que je rajoutais le lien yokoshop dans ma `div` liée à mon lien vers ce site. Cet ajout dénaturait l'intégralité de la grille.
J'ai recommencé, supprimé mes `div` liées à mes logos et je les ai remplacé directement par des `a href`.

L'ajout des propriétés `d-flex` et `flex-wrap` que j'ai trouvé sur le site [https://css-tricks.com/almanac/properties/f/flex-wrap/](https://css-tricks.com/almanac/properties/f/flex-wrap/)
à ma section gridLogos m'a permis de contrôler le passage à la ligne des logos de manière plus élégante et responsive.

### Difficultés:

J'ai perdu du temps en changeant le système de grid et en voulant limiter le nombre de logos à max 5 et min 3 en fonction de la taille d'écran, je n'ai pas ici cette fonctionnalité.

J'ai également perdu du temps pour récupérer les photos de logos, je pensais pouvoir les avoir en simple fichier chacun mais il a fallu que je les exporte en les sauvegardant un par un; je pensais pouvoir adapter la couleur de texte des logos en blanc directement en css, mais ayant effectué des tests et n'ayant pas trouvé une solution appropriée, j'ai contourné le problème en modifiant directement la colorisation dans Affinity Designer.

### Temps:

En revenant plusieurs fois dessus, je pense avoir passé entre 3-4h sur cette section.


## Section Slider

Cette section m'a en 1er lieu amener à rechercher une librairie adaptée qui reprend la fonctionnalité de Flickity concernant la possibilité de voir un morceau de l'image suivante en étant sur une image.

J'ai cherché quelques temps plusieurs librairies qui ne m'ont pas proposé ce que je cherchais; j'en ai trouvé une s'appelant [https://owlcarousel2.github.io/OwlCarousel2/](https://owlcarousel2.github.io/OwlCarousel2/)
En l'installant, je n'ai pas réussi à effectuer cet effet, et après plusieurs recherches non fructueuse, j'ai décidé de la retirer et de passer sur un système de carousel bootstrap en installant son cdn et en choisissant un système plus classique.

J'ai essayé de contourner le problème via un `padding-right` à 10% mais hormis un décalage stylisé, je n'ai pas obtenu l'effet escompté.

Flèche carousel: de base blanche, j'ai inversé la couleur avec un filter: invert(1) dont j'ai trouvé l'explication ici:
[https://www.w3schools.com/cssref/css3_pr_filter.asp](https://www.w3schools.com/cssref/css3_pr_filter.asp)

Le contenu texte des 2 sliders au sein d'un carré a été compliqué à effectuer correctement.
Au sein de `.caption-one` représentant mon contenu:

J'ai utilisé un display-block pour le type d'affichage et une valeur de 400px en max-width pour obtenir la taille escompté.
Pour sa position dans l'espace, j'ai travaillé sur le % right et top ainsi que le padding.
La police utilisée est toujours Karla via  l'utilisation de`font-family:"Karla", serif;`

Concernant le bouton `<voir plus/>`, j'ai utilisé la même logique que pour le bouton Shopify pour le underline-yellow et également concernant l'utilisation de `::before``::after`. L'italique est visible grâce à l'utilisation en `a:hover` du `font-style: italic`.

### Temps:

Avec les recherches de librairies et l'essai non fructueux d'une librairie m'amenant à revenir sur un carousel bootstrap plus simple, je pense avoir passé entre 3-4h sur cette section.


## Section Text Infinite

Après une courte recherche, j'ai pu observé qu'une simple balise `marquee` permettait de créer l'effet désiré.
Lien: [http://ateliercss2.free.fr/PagesExercices/2011/Marquee/Marquee.html](http://ateliercss2.free.fr/PagesExercices/2011/Marquee/Marquee.html)


### Temps:

Environ 15-20 minutes.























