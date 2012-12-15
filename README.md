# Développement de Logiciel Durable

une présentation sur la [maintenabilité](http://en.wikipedia.org/wiki/Maintainability) des applications

## Synopsis

* SCENARIO CATASTROPHE (ou alors en deuxième position ?)
    * correction d'un bug bloquant simple et livraison (rappel qu'il y a des coûts associés)
    * arrivée d'un autre bug lié à une duplication du code précedent -> correction de tout et relivraison (ou batterie de tests quand on a cette phase)
    * régression fonctionnelle lié à une toute petite modif dans le code dupliqué pour un cas, non vu
* INTRODUCTION A LA MAINTENABILITE
    * parler de la théorie des [3 contraintes d'un projet informatique](http://www.projectsmart.co.uk/project-management-scope-triangle.html)
    * Bien montrer qu'en fait la qualité n'est pas fixe (plutôt un carré donc) avec une histoire où l'on parle des commerciaux (pas de décalage, moins cher) ou des utilisateurs (pas de décalage, moins cher, plus de fonctionnalités).
    * Transition de la qualité à la maintenabilité. Définition. 
    * Donner [quelques exemples](https://www.inria.fr/centre/grenoble/actualites/la-fiabilite-des-systemes-devient-un-defi-majeur)
    * Déjà indiquer que certains point sont faciles, mais que d'autres ont des coûts.
    * Parler d'adaptation au contexte en différenciant 
        * le projet pilote
        * peut-être trouver un moyen de déjà montrer que cela pourrait être différent pour un projet avec beaucoup besoin de performance ou de sécurité
        * le projet avec beaucoup de métier
    * Accentuer sur le métier de dév en informatique de gestion
        + leur demander de le définir
        * des points particulièrement importants (métier complexe, ergonomie)
        * des points parfois moins critiques (architectures classiques, performance moins importante)
    * Conclure
        * en parlant de la problématique du pollueur-payeur (rarement le mainteneur qui a développé)
        * en indiquant que c'est compliqué à expliquer (cf la durée de l'introduction)
        * en indiquant qu'il n'y a même pas vraiment de nom !
* BONNES PRATIQUES ET TECHNIQUES DE DEV
    * Less is More
        * __le moins de code possible, le moins de doc possible__
        * /!\ meilleur conseil à des dev : comprendre chaque bout de code écrit ou maintenu
            * pas de code en trop, pas de bugs techniques (inadmissibles)
            * c'est ce qui différencie un bon développeur d'un mauvais développeur
            * veille techniques, lecture des specs techniques, curiosité permanente, pas de pré-suppositions
        * vérifier systématiquement avant de commiter quelque chose
        * utiliser des frameworks et bibliothèques
            + demander qui connait la différence entre frameworks et bibliothèques : si pas clair, raccord sur la curiosité permanente
            * code est déporté, mieux testé (en général)
            * permet de se concentrer sur la valeur ajoutée. Exemples :
                * pour l'info de gestion, c'est le métier qui est la valeur, pas l'affichage des pages. Donc utilisation de frameworks et bibliothèques pour l'affichage (Play 2, Spring MVC, JSF)
                * pour une application de blog, c'est la gestion des articles qui est la valeur. Donc externaliser la connexion, l'infra d'exploitation.
                * autres ?
                * Des choses sont à la marge (ergo sur info de gestion, commentaires pour blog). Dans ce cas-là, c'est un choix. Pages auto ou Pages spécifiques. Code pour les commentaires ou externalisation.
            * attention malgré tout à ce qu'il soit propre, documenté, testé avec une communauté afin qu'il n'amène pas plus de problème qu'il n'en résoud.
            * éviter d'écraser une mouche avec une enclume et un marteau. Pas trop d'inutile, pas d'usine pour des choses simples. 
            * jugement qui vient avec l'expérience. Il faut sans arrêt se poser la question (cf bon développeur)
        * petite pépite : Lombok
            * expliquer le principe (parler des beans en injection de dépendance Spring/J2EE CDI)
            * une démo avec du code (avant après sur le site, peut-être aussi avec des beans métier)
            * évoquer les difficultés (éditeurs, debug, ...) comme avec les techniques AOP
        * convention over configuration (allusion à maven, documentation, choix des bibliothèques et frameworks exactement adaptés)
        * "your code is your documentation" (citation de quelqu'un ?)
            * pas de documents word énormes
            * plutôt des choses faciles à mettre à jour, simples et petites
                * éditeur en ligne de github
                * wikis dans les forges logicielles
                * évoquer [readme un fichier nommé désir](http://www.paris-web.fr/2012/conferences/readme-un-fichier-nomme-plaisir.php)
        * tempérer le discours 
    * code "expressif" (trouver une meilleure expression)
        * comparaison entre 3 codes (1 tout un bloc incompréhensible, 1 avec des noms parlants, 1 avec une fonction et une variable en plus) qui montre 
    * KISS
        * dans l'archi technique globale
        * dans le code (architecture logicielle). Evoquer l'Agile.
        * dans les choix progiciels (plus compliqué de ne pas prévoir à long terme)
    * Refactoring et nettoyage permanent
        * évoquer la difficulté
        * Tests automatisés
            * Facilité de refactoring 
            * Permet de détecter le code inutile : suppression des tests inutiles et couverture des tests
            * 
    * 
* USINE LOGICIELLE
* PROJET
* CONCLUSION

A caser :
* l'objectif de la présentation (évoquer sans trop de détails, donner des pistes de réflexion et de travail, ...)
* la métaphore de l'écologie
* des petits sondages (qu'est-ce que la maintenabilité, qui a fait de la maintenance en stage/apprentissage, ...)
* Mentionner la dette technique. 
* [clean code](http://blog.octo.com/les-artisans-codeurs-chez-octo/).
* utiliser les fonctionnalités de son éditeur (par exemple eclipse avec les variables non utilisées) : du coup obligation de purger les erreurs et warnings
* tests automatisés : unitaires, intégration, fonctionnels (graphique pour montrer le flou entre les définitions). Parler des difficultés et contraintes. Evoquer les mocks et le TD
* intégration/[déploiement](http://blog.octo.com/continuous-deployment/)/... continu
* usine de développement (jenkins, sonar) avec nexus en bonus. Évoquer les critères de choix des outils et la vigilance à ne pas s'enfermer. Donner quelques liens pour des [usines en ligne](http://deors.wordpress.com/2012/10/03/developer-day/)
* parler de stratégie de mise en place du suivi qualité (pour une application existante, lien avec d'autres systèmes qualité comme opquast par exemple). Les indicateurs pour les indicateurs sont inefficaces : prendre du recul, parler de l'expérience vécue. C'est une aide pour le développeur seulement. Evoquer les erreurs sonars liés au code Lombok et le fait de faire des commentaires vides ou nuls.
* exemples de règles java sur du vrai code avec sonar
 * possibilité de devoir à partir d'un projet antérieur
 * ou alors moi je prends des projets étudiants et je montre ce qui pourrait être amélioré 
* conclure sur le [software craftmanship](http://training.xebia.fr/formations-java-jee/formation-tdd-software-craftsmanship.html)

## Contexte

Il faut poser des questions sur
* taille de la classe
* niveau (en particulier maturité en java)
* projets existants sur lesquels travailler concrètement

## Préparation de la présentation
### Outils

* [Reveal.js](https://github.com/hakimel/reveal.js)
* [Diagram.ly](http://www.diagram.ly/), [Inkscape](http://inkscape.org/?lang=fr) et [Sozi](http://sozi.baierouge.fr/wiki/fr:bienvenue) pour le schéma de l'usine de dev. Etudier [Prezi](http://prezi.com/) mais pas sûr de pouvoir exporter à un format ouvert...
* [Delicious](http://www.delicious.com) pour partager l'ensemble des liens

Ce qu'on n'utilisera pas [fathom.js](http://markdalgleish.com/projects/fathom/), [Deck.js](http://imakewebthings.com/deck.js/) (avec des [extensions](http://home.heeere.com/tech-deckjs-ext.html)) et [Shower](https://github.com/pepelsbey/shower) (avec les [notes](http://christianheilmann.com/2012/08/15/browsers-have-a-presenter-mode-console-info/))

### Astuces et aide pour la présentation
* [Tell a Story !](http://fr.slideshare.net/andywhitlock/how-to-do-presentations-that-dont-induce-suicide)
* [Developer Evangelism](http://developer-evangelism.com/slides.php)
* [Evangelism Reps](https://wiki.mozilla.org/ReMo/SIGs/Evangelism_Reps/Evangelism_Reps_Toolkit) dont [Great Talks](https://wiki.mozilla.org/Evangelism_Reps_Training_Program/GreatTalks)
* Ateliers orateurs [2011](http://www.paris-web.fr/actualites/2011/05/compte-rendu-atelier-orateurs.php) et [2012](http://www.paris-web.fr/actualites/2012/05/compte-rendu-de-latelier-orateurs-2012.php)

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
