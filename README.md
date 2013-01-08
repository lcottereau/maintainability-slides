# Développement de Logiciel Durable

une présentation sur la [maintenabilité](http://en.wikipedia.org/wiki/Maintainability) des applications

## Synopsis

* SCENARIO CATASTROPHE (ou alors en deuxième position ?)
    * correction d'un bug bloquant simple et livraison (rappel qu'il y a des coûts associés)
    * arrivée d'un autre bug lié à une duplication du code précedent -> correction de tout et relivraison (ou batterie de tests quand on a cette phase)
    * régression fonctionnelle lié à une toute petite modif dans le code dupliqué pour un cas, non vu
    * Conclure sur le fait que c'est la vraie vie de développeur
        * ici à mon arrivée dans une entreprise
        * mais aussi partout où je suis allé
        * et partout où vous irez
* INTRODUCTION A LA MAINTENABILITE
    * parler de la théorie des [3 contraintes d'un projet informatique](http://www.projectsmart.co.uk/project-management-scope-triangle.html)
    * Bien montrer qu'en fait la qualité n'est pas fixe (plutôt un carré donc) avec une histoire où l'on parle des commerciaux (pas de décalage, moins cher) ou des utilisateurs (pas de décalage, moins cher, plus de fonctionnalités).
    * Transition de la qualité à la maintenabilité. Définition. 
    * Donner [quelques exemples](https://www.inria.fr/centre/grenoble/actualites/la-fiabilite-des-systemes-devient-un-defi-majeur)
    * Déjà indiquer que certains points sont faciles, mais que d'autres ont des coûts.
    * Parler d'adaptation au contexte en différenciant 
        * le projet pilote
        * peut-être trouver un moyen de déjà montrer que cela pourrait être différent pour un projet avec beaucoup besoin de performance ou de sécurité
        * le projet avec beaucoup de métier
    * Accentuer sur le métier de dév en informatique de gestion
        + leur demander de le définir
        * des points particulièrement importants (métier complexe, ergonomie)
        * des points parfois moins critiques (architectures classiques, performance moins importante)
    * Parler de la problématique du pollueur-payeur (rarement le mainteneur qui a développé). 
        * Indiquer qu'il est important pour bien développer de maintenir aussi du code.
        * appliquer ces techniques en début de récupération de maintenance est positif (meilleure maintenabilité et montée en connaissance)
        * le karma : il faut bien commencer quelque part dans la situation difficile actuelle
    * Conclure
        * en indiquant que c'est compliqué à expliquer (cf la durée de l'introduction)
        * en indiquant qu'il n'y a même pas vraiment de nom !
        * en évoquant la dette technique
* BONNES PRATIQUES ET TECHNIQUES DE DEV
    * [KISS](http://www.redaction-technique.org/redacteur-technique/redacteur-technique/principe-de-simplicite-kiss/)
        * dans l'archi technique globale
        * dans le code (architecture logicielle). Evoquer l'Agile.
        * une des raisons de la réussite d'UNIX est la séparation des tâches en des programmes indépendants (chacun est plus facilement maintenable)
        * dans les choix progiciels (plus compliqué de ne pas prévoir à long terme)
    * code "expressif" (trouver une meilleure expression)
        * comparaison entre 3 codes (1 tout un bloc incompréhensible, 1 avec des noms parlants, 1 avec une fonction et une variable en plus)
        * évoquer la pratique de la métaphore en XP
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
        * "your code is your documentation" (citation de quelqu'un ?). Y compris les tests
            * pas de documents word énormes
            * plutôt des choses faciles à mettre à jour, simples et petites
                * éditeur en ligne de github
                * wikis dans les forges logicielles
                * évoquer [readme un fichier nommé désir](http://www.paris-web.fr/2012/conferences/readme-un-fichier-nomme-plaisir.php)
            * gestionnaire de sources
                * historique des problèmes, incidents, choix d'architecture
                * changelog automatisé
                * liens avec le gestionnaire de tickets
            * noter les TODO
                * dans le gestionnaire de tickets
                * éventuellement dans le code (mais pas trop)
        * tempérer le discours 
    * Refactoring et nettoyage permanent
        * évoquer la difficulté (rappel au scenario catastrophe ?)
        * Tests automatisés
            * définition générale des tests automatisés
            * Plusieurs types de tests : unitaires, intégration, fonctionnels (graphique pour montrer les chevauchements)
            * Facilité de refactoring en limitant les risques de régression fonctionnelle
            * Permet de détecter le code inutile : suppression des tests inutiles et couverture des tests
            * la pratique du TDD aide à n'écrire que le code nécessaire
            * Bonnes pratiques
                * limiter les recouvrements entre les différents types de tests
                * tout ce que l'on a évoqué pour le code source (lisibilité, KISS, Less is More, ...)
                * donc pas besoin de tout tester (exemple des getters et setters)
                * parler des mocks
                * utiliser les frameworks (JUnit, Mockito)
        * si on ne sait pas à quoi sert un bout de code
            * creuser, creuser
            * tester la suppression si possible
            * très peu de cas où il est pertinent sur le long terme de garder le code non compris : le supprimer (avec éventuellement des communications, des avertissements)
    * utiliser les fonctionnalités de son éditeur (exemple pour les variables non utilisées)
        * il est nécessaire de les traiter au fur et à mesure au risque de se faire dépasser (cf la théorie de la fenêtre brisée à NY)
* USINE LOGICIELLE
    1. Un nouveau bug à gérer : **Suivi des tickets**
        * sert à la fois pour les bugs et les évolutions
        * pas de documentation énorme donc nécessité de tout suivre, même petits bugs rapides à corriger
        * réfléchir à qui saisit, administre et voit les tickets (problèmatiques d'efficacité, de conservation de l'historique, de compréhension _téléphone arabe_)
    1. Poste client
        * Editeur de code source
            * ce que vous pouvez rechercher
                * compilation automatique
                * des tests et vérifications intégrées et lancées en tâche de fond
                * des raccourcis pour le refactoring et les tests unitaires sont utiles
            * suggestions : 
                * Eclipse (très lourd mais versatile), 
                * IntelliJ (excellent mais non open source et payant), 
                * NetBeans (moche mais maintenant semble intéressant)
                * mais pourquoi pas vi ou emacs avec les bons plugins
                * un projet pérenne ne devrait pas être lié à un IDE ou à une version
            * note sur les choix de carrière
                * exigez un ordinateur puissant, cela coûte beaucoup moins cher que votre temps perdu.
                * apprenez à vous servir de votre IDE, investissement nécessaire 
                * remettez-vous en cause régulièrement en (re)testant d'autres IDEs
        * Maven
            * gestionnaire de dépendances
            * ensemble de bonnes pratiques
            * 
    * Site web du code source
    * Intégration continue
    * Gestion des sources
        * parler des hookups git
    * Dépôt de binaires
    * Documentation projet
    * Suivi de la qualité
    * Note sur les environnements de développement
        * Viser une portabilité maximale
            * limiter les risques pour le passage en production
            * un package identique qui marche partout sans modification
            * des fichiers de configuration, par exemple à des emplacements "connus"
        * environnement de production
        * environnement local
            * maximum doit être fait dessus si c'est possible (suivant l'infrastructure)
        * environnement d'intégration 
            * identique à la production 
            * pour des tests en conditions réelles,  reproduction d'incidents de production, tests de charge pertinents (mais pas idéaux)
            * faire plus de tests sur cet environnement si le contexte infra est très différent entre produciton et local
* PROJET ?
* CONCLUSION
    * Rappel sur les points les plus importants
        * Comprendre toujours dans le détail le code écrit ou maintenu
        * Remettre en cause sans craindre mais sans ignorer les impacts
    * Parler des [artisans codeur](http://training.xebia.fr/formations-java-jee/formation-tdd-software-craftsmanship.html)

A caser :
* l'objectif de la présentation (évoquer sans trop de détails, donner des pistes de réflexion et de travail, ...)
* la métaphore de l'écologie
* des petits sondages (qu'est-ce que la maintenabilité, qui a fait de la maintenance en stage/apprentissage, ...)
* [clean code](http://blog.octo.com/les-artisans-codeurs-chez-octo/).
* intégration/[déploiement](http://blog.octo.com/continuous-deployment/)/... continu
* voire comment on indique les différences entre les infrastructures "par projet" et les infrastructures mutualisées. Est-ce pertinent d'en parler ?
* usine de développement (jenkins, sonar) avec nexus en bonus. Évoquer les critères de choix des outils et la vigilance à ne pas s'enfermer. Donner quelques liens pour des [usines en ligne](http://deors.wordpress.com/2012/10/03/developer-day/)
* parler de stratégie de mise en place du suivi qualité (pour une application existante, lien avec d'autres systèmes qualité comme opquast par exemple). Les indicateurs pour les indicateurs sont inefficaces : prendre du recul, parler de l'expérience vécue. C'est une aide pour le développeur seulement. Evoquer les erreurs sonars liés au code Lombok et le fait de faire des commentaires vides ou nuls.
* exemples de règles java sur du vrai code avec sonar
 * possibilité de devoir à partir d'un projet antérieur
 * ou alors moi je prends des projets étudiants et je montre ce qui pourrait être amélioré
 * parler des usines logicielles intégrées (github voire jira studio). avantages et inconvénients par rapport à des produuits séparés

## Contexte

Il faut poser des questions sur
* taille de la classe
* niveau (en particulier maturité en java)
* connaissance sur les différentes briques de l'usine de dév pour savoir où insister
* projets existants sur lesquels travailler concrètement
* quelles parties ont déjà été vues dans un autre cours

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

### Relectures
* Florent M.
* Michael S.
* Marie C.
* Ludovic P.
* Sébastien D.
* autres collègues