# Développement de Logiciel Durable

une présentation sur la maintenabilité des applications

## Synopsis

* parler des différents défis pour le développeur : métier, ergonomie très fonctionnels, architecture et performance plus technique. Et en venir à la maintenabilité. Des difficultés très spécifiques (pas pollueur-payeur, pas évident, même pas vraiment de nom !) Une manière intéressante de faire ça pourrait être de décrire un scenario catastrophe.
* définition de la maintenabilité. Parler d'adaptation au contexte (il faut choisir l'investissement en fonction du besoin). Mentionner la dette technique. Présenter un diagramme _araignée_ avec les 4 axes d'un projet (coût, délai, fonctionnalités, qualité) et leurs interactions. Parler de ce qui est possible ou pas : certains prétendent qu'il ne faut pas jouer sur la qualité, expliquer que pas possible trop jouer sur les délais grâce aux coûts, expliquer que client pas souvent d'accord pour jouer sur les fonctionnalités, ...
* bonnes pratiques : convention over configuration, maven, frameworks, comprendre ce qui se passe vraiment sous le capot. supprimer le code obsolète au fur et à mesure. [clean code](http://blog.octo.com/les-artisans-codeurs-chez-octo/)
* se concentrer sur le coeur de métier : le moins de code possible, utilisation de bibliothèques (code déporté, pas de responsabilité). Attention à ce qu'il soit propre et à ne pas prendre trop d'inutile. Parler aussi de lombok
* la documentation : your code is your documentation, pas de documents énormes word mais plutôt des fichiers en gestion de version avec editeur en ligne (cf [readme un fichier nommé désir](http://www.paris-web.fr/2012/conferences/readme-un-fichier-nomme-plaisir.php)) ou des wikis. L'important est la facilité de mise à jour et la taille.
* tests automatisés : unitaires, intégration, fonctionnels (graphique pour montrer le flou entre les définitions). Parler des difficultés et contraintes. Evoquer les mocks et le TD
* intégration/[déploiement](http://blog.octo.com/continuous-deployment/)/... continu
* usine de développement (jenkins, sonar) avec nexus en bonus. Évoquer les critères de choix des outils et la vigilance à ne pas s'enfermer
* parler de stratégie de mise en place du suivi qualité (pour une application existante, lien avec d'autres systèmes qualité comme opquast par exemple). Les indicateurs pour les indicateurs sont inefficaces : prendre du recul, parler de l'expérience vécue. C'est une aide pour le développeur seulement. Evoquer les erreurs sonars liés au code Lombok et le fait de faire des commentaires vides ou nuls.
* exemples de règles java sur du vrai code avec sonar
 * possibilité de devoir à partir d'un projet antérieur
 * ou alors moi je prends des projets étudiants et je montre ce qui pourrait être amélioré 
* conclure sur le [software craftmanship](http://training.xebia.fr/formations-java-jee/formation-tdd-software-craftsmanship.html)


## Préparation de la présentation
### Outils

* [Reveal.js](https://github.com/hakimel/reveal.js)
* [Sozi](http://sozi.baierouge.fr/wiki/fr:bienvenue) pour naviguer dans du SVG

Ce qu'on n'utilisera pas [fathom.js](http://markdalgleish.com/projects/fathom/), [Deck.js](http://imakewebthings.com/deck.js/) (avec des [extensions](http://home.heeere.com/tech-deckjs-ext.html)) et [Shower](https://github.com/pepelsbey/shower) (avec les [notes](http://christianheilmann.com/2012/08/15/browsers-have-a-presenter-mode-console-info/))

### Astuces et aide pour la présentation
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