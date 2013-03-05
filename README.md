# Développement de Logiciel Durable

Une présentation sur la [maintenabilité](http://en.wikipedia.org/wiki/Maintainability) des applications. 
Pour plus d'information, voir le [Synopsis](https://github.com/lcottereau/maintainability-slides/wiki/Synopsis)

## TODO

1. récupérer doc des 2 projets si c'est possible
1. Réfléchir à un questionnaire de satisfaction

## Installation

Installer [reveal.js](https://github.com/hakimel/reveal.js) dans un répertoire `reveal` à la racine du projet. 
Ouvrir le fichier `index.html` dans votre navigateur. Il vaut mieux le faire via http pour avoir toutes les 
fonctionnalités de reveal, en particulier les notes du présentateur (touche `s`).


## Contexte

Il faut poser des questions sur
* taille de la classe
* niveau (en particulier maturité en java)
* connaissance sur les différentes briques de l'usine de dév pour savoir où insister
* projets existants sur lesquels travailler concrètement
* quelles parties ont déjà été vues dans un autre cours
    * niveau de connaissance sur git ou autre gestionnaire de version en particulier
* est-ce qu'un environnement satisfaisant pour la projection existe 
    * prise VGA
    * Firefox dernière version (ou Chrome si Sozi marche)
    * résolution du projecteur

## Préparation de la présentation
### Outils

* [Reveal.js](https://github.com/hakimel/reveal.js) 
* [Diagram.ly](http://www.diagram.ly/), [Inkscape](http://inkscape.org/?lang=fr) et [Sozi](http://sozi.baierouge.fr/wiki/fr:bienvenue) pour le schéma de l'usine de dev. Etudier [Prezi](http://prezi.com/) mais pas sûr de pouvoir exporter à un format ouvert...
* [Delicious](http://www.delicious.com) pour partager l'ensemble des liens

Ce qu'on n'utilisera pas :
* [Power Poligon](https://hacks.mozilla.org/2013/01/power-polygon-html5-slides-with-theming-and-much-more/) est très complet (langues et profils sont intéressants) mais trop moche de base.
* [fathom.js](http://markdalgleish.com/projects/fathom/)
* [Deck.js](http://imakewebthings.com/deck.js/) (avec des [extensions](http://home.heeere.com/tech-deckjs-ext.html)) et [Shower](https://github.com/pepelsbey/shower) (avec les [notes](http://christianheilmann.com/2012/08/15/browsers-have-a-presenter-mode-console-info/))

### Astuces et aide pour la présentation
* [Tell a Story !](http://fr.slideshare.net/andywhitlock/how-to-do-presentations-that-dont-induce-suicide)
* [Developer Evangelism](http://developer-evangelism.com/slides.php)
* [Evangelism Reps](https://wiki.mozilla.org/ReMo/SIGs/Evangelism_Reps/Evangelism_Reps_Toolkit) dont [Great Talks](https://wiki.mozilla.org/Evangelism_Reps_Training_Program/GreatTalks)
* Ateliers orateurs [2011](http://www.paris-web.fr/actualites/2011/05/compte-rendu-atelier-orateurs.php) et [2012](http://www.paris-web.fr/actualites/2012/05/compte-rendu-de-latelier-orateurs-2012.php)
* [3 tricks to better public speaking](http://neiljoglekar.com/what-i-learned-from-our-guest-lecture-at-cmu)

### Citations
* Les pollueurs (dév crades) ne sont pas les payeurs (mainteneurs)
* <http://t37.net/13-citations-droles-l-histoire-programmation.html>
    * _Il y existe deux manières de concevoir un logiciel. La première, c’est de le faire si simple qu’il est évident qu’il ne présente aucun problème. La seconde, c’est de le faire si compliqué qu’il ne présente aucun problème évident. La première méthode est de loin la plus complexe_ - C.A.R. Hoare
    * _Si les ouvriers construisaient les bâtiments comme les développeurs écrivent leurs programmes, le premier pivert venu aurait détruit toute civilisation_ - Gerald Weinberg
    * _Si debugger, c’est supprimer des bugs, alors programmer ne peut être que les ajouter_ - Edsger Dijkstra
    * _Mesurer la progression du développement d’un logiciel à l’aune de ses lignes de code revient à mesurer la progression de la construction d’un avion à l’aune de son poids_ - Bill Gates
    * _Neuf femmes ne peuvent pas faire un bébé en un mois_ - Fred Brooks
    * _Avant de vouloir qu’un logiciel soit réutilisable, il faudrait d’abord qu’il ait été utilisable_ - Ralph Johnson
* <http://www.evene.fr/celebre/biographie/antoine-de-saint-exupery-279.php?citations>
    * _La perfection est atteinte, non pas lorsqu'il n'y a plus rien à ajouter, mais lorsqu'il n'y a plus rien à retirer_ - Antoine de Saint-Exupéry
* <http://marxsoftware.blogspot.fr/2013/02/five-favorite-software-development.html>
    * couplage trop fort et part de pizzas
    * Maintenabilité et Jenga
    * Neuf femmes n'accouchent pas d'un bébé en un mois
    * balayer la poussière sous le tapis et les warnings
    * commentaires sont le déodorant du code qui sent mauvais
