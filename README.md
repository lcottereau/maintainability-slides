# Développement de Logiciel Durable

une présentation sur la [maintenabilité](http://en.wikipedia.org/wiki/Maintainability) des applications

## Synopsis

* PRESENTATION
    * expérience professionnelle dans le développement
    * insister sur le fait que ce condensé est lié à mon expérience et *doit* être analysé, questionné et remis en cause régulièrement
    + qu'est-ce que la maintenabilité pour vous ?
* SCENARIO CATASTROPHE
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
        * des points particulièrement importants (métier complexe, ergonomie, nombreux projets en parallèle)
        * des points parfois moins critiques (architectures classiques, performance moins importante)
    * Problématiques de la maintenabilité (on le garde ou pas cf maintenabilité)
        * la maintenance est parfois mal considérée
            * par les développeurs
            * par les manageurs
            * par l'organisation
        * c'est compliqué à expliquer (cf la durée de l'introduction) et à chiffrer
        * MAIS ça s'améliore
            * dette technique
        * côté développement
            * Code _legacy_ peut être vraiment ancien, compliqué et lourd
            * une forme d'arrogance et de paresse fait que de nombreux développeurs n'aiment pas _rentrer_ dans du code produit par quelqu'un d'autre
            * manque d'implication des développeurs projet qui savent qu'ils ne maintiendront pas
            * MAIS il y a systématiquement des améliorations à apporter, un intérêt à trouver, beaucoup à apprendre (attention à l'empathie)
            * l'adrénaline et la complexité de la résolution des bugs de production apporte autre chose
        * Parler de la problématique du pollueur-payeur (rarement maintenu par celui qui a développé). 
            * Indiquer qu'il est important pour bien développer de maintenir aussi du code.
            * appliquer ces techniques en début de récupération de maintenance est positif (meilleure maintenabilité et montée en connaissance)
            * le karma : il faut bien commencer quelque part dans la situation difficile actuelle
            * c'est utile aussi pour soi (oubli car nombreuses maintenances et projets en parallèle)
        * Politiquement, pour les managers, un projet est plus porteur que la maintenance
        * La gestion financière (largement répandue en entreprise) sépare schématiquement
            * budget d'investissements - projet - BON
            * budget d'exploitation - maintenance - MAUVAIS
        * maintenance et développement en interne limitent ces difficultés (projet et maintenance peut être avec même dev)
    * Conclure
        * c'est parfois mal considéré
        * c'est compliqué à expliquer (cf la durée de l'introduction)
        * à tel point qu'il n'y a même pas de vrai nom !
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
            * une fois le choix fait, approfondir la connaissance pour une efficacité optimale.
        * petite pépite : Lombok
            * expliquer le principe (parler des beans en injection de dépendance Spring/J2EE CDI)
            * une démo avec du code (avant après sur le site, peut-être aussi avec des beans métier)
            * évoquer les difficultés (éditeurs, debug, ...) comme avec les techniques AOP
        * convention over configuration (allusion à maven, documentation, choix des bibliothèques et frameworks exactement adaptés)
        * "your code is your documentation" (citation de quelqu'un ?). Y compris les tests
            * ne pas oublier que c'est le code le patrimoine et la valeur de l'entreprise qui fait du développement
            * pas de documents word énormes. 
            * plutôt des choses faciles à mettre à jour, simples et petites
                * éditeur en ligne de github
                * wikis dans les forges logicielles
                * évoquer [readme un fichier nommé désir](http://www.paris-web.fr/2012/conferences/readme-un-fichier-nomme-plaisir.php)
            * les sources d'information existantes _automatiques_
                * historique des problèmes, incidents, évolutions fonctionnelles, choix d'architecture
                * javadoc dans code source et tests
                * description et commentaires dans gestionnaire de tickets
                * commentaires de commit dans gestionnaire de source
                * idéalement, des liens entre ces infrastructures
            * noter les TODO
                * dans le gestionnaire de tickets
                * éventuellement dans le code (mais pas trop)
            * Ce qu'il est bon d'avoir
                * un point d'entrée pour un nouveau participant (dev, utilisateur, management)
                * description fonctionnelle haut niveau (à adapter en fonction de la cible et du besoin)
                * description technique haut niveau
                * changelog ou historique (plus de détails si souhaité car informations pérennes)
                * ce qui ne rentre pas ailleurs
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
    * Utiliser toutes les informations disponibles
        * message du compilateur 
        * certains éditeurs (exemple pour les variables non utilisées)
        * logs (serveurs, framework, bibliothèques, applicatifs)
        * plateformes de suivi 
            * suivi d'un certain nombre d'indicateurs qualité
                * complexité (cyclomatique?) : utile globalement mais il peut être normal d'avoir du code complexe
                * taux de couverture des tests : normal de ne pas être à 100%TODO les plus importants
                * couverture javadoc sur les API publiques (attention, cela ne vérifie pas la pertinence)
                * ...
            * pour le développeur, pour l'équipe, pour le management
            * attention à ne l'utiliser que comme aide à contextualiser. 100% cache un projet extrêmement simple ou alors des mauvais choix
                * commentaire _ceci est un commentaire_
                * pas d'accesseurs lorsque l'on utilise lombok : normal
                * lorsque l'on étend des classes de bibliothèques, des erreurs sur les signatures originelles ne peuvent pas être corrigées.
                * désactiver les règles peut parfois être utiles, mais seulement si jamais nécessaire
            * un point plus utile que la note instantanée est l'évolution. 
                * Certaines entreprises comme la RATP contractualisent parfois cette évolution pour la maintenance.
        * ne rien laisser passer sans comprendre : "ce qui est facile en informatique, c'est qu'il y a __toujours__ une explication rationnelle"
        * traiter au fur et à mesure au risque de se faire dépasser (cf la théorie de la fenêtre brisée à NY), quel que soit l'environnement
        * Si message compris et accepté, essayer de le faire disparaître (sans empêcher les nouveaux messages)
        * Si pas possible, documenter pour les prochains mainteneurs ou pour soi dans quelques mois.
* ENVIRONNEMENTS
    * Viser une portabilité complète du binaire
        * un package identique qui marche partout sans modification
        * des fichiers de configuration, par exemple à des emplacements "connus"
        * limiter les risques pour le passage en production
        * partage complet et simple pour toute l'entreprise
    * environnement de production
    * environnement local
        * maximum doit être fait dessus si c'est possible (suivant l'infrastructure)
    * environnement d'intégration 
        * identique à la production 
        * pour des tests en conditions réelles,  reproduction d'incidents de production, tests de charge pertinents (mais pas idéaux)
        * faire plus de tests sur cet environnement si le contexte infra est très différent entre produciton et local
    * à adapter évidemment au contexte
* USINE LOGICIELLE
    * préambule : critères de choix généraux
        * fonctionnalités. Attention à ne prêter attention qu'à ce qui est nécessaire
        * interconnexion entre les briques de l'usine
        * communauté et implantation en entreprise
        * connaissance en interne (par les administrateurs système, par les utilisateurs)
        * facilité d'utilisation et documentation
        * ne pas oublier la capacité à changer d'outil. Pour certains outils, il faut pouvoir garder l'historique
    * stratégie de mise en place
        * peut-être lourd à gérer et à maintenir
        * utile uniquement si c'est vraiment utilisé
        * sauf si stratégie d'entreprise, mieux vaut y aller graduellement
        * certaines applications tout compris ou dans le nuage peuvent aider
            * avantage : moins de maintenance, intégration entre briques plus poussée
                1. exemple d'un commentaire de commit sur github contenant _fixes #12 /cc @toto_) TODO
                1. le ticket 12 a un commentaire de plus avec le message et un lien vers la page du commit
                1. le ticket 12 est résolu
                1. le développeur @toto est prévenu par mail
                1. le message de commit sur le site a un lien direct vers le ticket
            * désavantages : utilisation partielle compliquée, interopérabilité souvent plus complexe
            * quelques exemples d'[usines en ligne](http://deors.wordpress.com/2012/10/03/developer-day/) : github, jira studio, trac
            * attention à la localisation du code source et à la sécurité
    1. Un nouveau bug à gérer : **Suivi des tickets**
        * sert à la fois pour les bugs et les évolutions
        * pas de documentation énorme donc nécessité de tout suivre, même petits bugs rapides à corriger
        * réfléchir à qui saisit, administre et voit les tickets (problèmatiques d'efficacité, de conservation de l'historique, de compréhension _téléphone arabe_)
        * suggestions
            * bugzilla (compliqué mais complet et pérenne)
            * mantis (plus apprécié des utilisateurs et grosse communauté)
            * suivi des tickets intégrés (en général très simples) : github, gitlab, trac, jira
    1. Développement : **Poste utilisateur**
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
            * ne sera jamais plus utile que la maîtrise que le développeur en a. il est nécessaire d'apprendre à bien s'en servir
                * capacités
                * raccourcis clavier
        * Maven
            * gestionnaire de dépendances
            * ensemble de bonnes pratiques _gratuites_ : convention over configuration
                * organisation des répertoires
                * TODO
            * gestionnaire de construction
                * prépackagé pour jar et war et extensible
                * différenciation entre les version SNAPSHOT et finales
    1. Echange avec les autres développeurs ou membres projet : **Site web du code source**
        * pas d'authentification ou alors facile pour tous (SSO d'entreprise par exemple)
        * suggestions : webgit inclus avec git
    1. Sauvegarde et partage des changements du code : **Gestion des sources**
        * sauvegarde, historique, partage
        * TODO parler des branches et des tags
        * TODO parler des hookups git
        * suggestions
            * ce qui est en place par défaut (pas le premier truc à faire évoluer)
            * CVS était chouette mais maintenant complètement dépassé
            * Subversion mieux que CVS (support, changements atomiques) mais pas terrible
            * Les gestionnaires distribués sont à privilégier
            * histoire rapide de git : pas mal de support aujourd'hui, github, pérennité
    1. __Revue de code__
        * parfois a priori (par exemple Google, avec un nombre de validations dépendant de la criticité du projet)
        * parfois a posteriori (suivi d'un développeur junior ou d'un stagiaire par un senior à moindre coût)
        * objectifs assez similaire au pair programming mais plus facile à mettre en place et différemment efficace
            * moins de communication et de partage
            * meilleure validation effective de la maintenabilité long terme
    1. Pour documenter ce qui n'est pas documentable dans le code : __Documentation__
        * suggestions :
            * wiki autonome : le wiki d'entreprise (habitude pour les utilisateurs)
            * wiki intégré : github, trac, gitlab
    1. Vérifier en permanence la compilation et l'ensemble des tests : **Intégration continue**
        * différentes stratégies de lancement (au commit, régulier)
            * en fonction du besoin de réactivité, du nombre de commits, des durées de compilation et de tests
            * stratégies mixtes possibles si build trop long
                * tests de montée en charge une fois par semaine
                * packaging des binaires que sur les versions non SNAPSHOT
        * penser à exécuter le maximum de tests en local (unitaires au minimum)
        * suggestions
            * hudson/jenkins : opensource et largement utilisé mais pas très user-friendly
            * cruise control
            * celui de atlassian
    1. __Dépôt de binaires__
        * pour rendre disponible des packages binaires projet à tous
            * pas besoin d'avoir les sources pour installer en production
            * partage des bibliothèques utilitaires développées de manière centralisée
        * mirroir pour économiser la bande passante externe
        * pour les dépendances qui ne sont pas disponibles publiquement (Drivers Oracle par exemple)
        * suggestions
            * apache nexus : open source, grosse communauté, simple
            * un autre TODO ?
    1. __Tests d'intégration et mise en production__
        * intégration/[déploiement](http://blog.octo.com/continuous-deployment/)/... continu : TODO
        * évoquer le mouvement DevOps, récent mais appelé à un grand avenir
        * profite grandement des préceptes décrits ici : automatisation, indépendance aux environnements
    1. __Suivi de la qualité__ de l'ensemble du patrimoine applicatif
        * suggestions
            * Sonar est globalement seul sur le marché et très simple d'utilisation avec un serveur d'intégration continue et maven
            * évoquer des produits comme CAST mais fermé, très cher et complexe à utiliser
            * évoquer des outils comme Opquast qui valident la qualité du produit final et pas du code permettant de l'obtenir
* MISE EN PRATIQUE (différentes possibilités)
    * expliquer les premières étapes de reprise en maintenance
        1. lister et récupérer l'ensemble des contenus : code source, documentation, URLs, ...
        1. lire la documentation de démarrage si elle existe
        1. lire ou parcourir l'ensemble de la documentation
        1. installation d'un environnement de dev complet (compiltation, packaging, infrastructure, ne pas oublier les données)
            * Tout devrait être disponible
        1. Effectuer toutes les corrections ou oublis nécessaires pour que l'installation soit effectivement possible pour un nouvel arrivant
        1. Prévoir un plan d'action à plus ou moins long terme pour suivre l'ensemble des bonnes pratiques évoquées
            * intégration plus ou moins poussée à une usine de développement
                * penser aux coûts globaux (si l'on veut sonar, il faut probablement utiliser maven par exemple)
            * rationalisation des environnements
            * packaging indépendant de l'environnement
            * mise en place d'un processus d'amélioration continue de la qualité
        1. Point d'étape avec le management et les utilisateurs
            * Formalisation orale ou contractuelle du mode de fonctionnement 
        1. Prise en charge du premier ticket
        * Lors de l'ensemble de ces étapes, il faut noter toutes les questions qui viennent à l'esprit
            * cette étape est très utile car c'est un tests grandeur nature. Elle doit être répétée à chaque arrivée dans l'équipe
    * faire utiliser Sonar aux élèves sur une plateforme en ligne sur un projet précedent.
        * le livrable est le code mis à jour avec l'explication des choix des points améliorés ou non
        * cinq point sonar doivent être améliorés
        * la note tiendra compte de la criticité de la correction, du coût de la correction : une meilleure note pour les corrections utiles et pas chères
    * récupération d'un projet précédent (plutôt en groupe)
        * je le passe dans Sonar
        * je fais un compte-rendu du résultat
        * je propose des améliorations et expliquant comment choisir les plus efficaces et les moins chères
* CONCLUSION TODO
    * Rappel sur les points les plus importants
        * Less is More : pour cela, comprendre toujours dans le détail le code écrit ou maintenu
            * normalement, devriez avoir peur de la quantité de choses à connaître à fond
            * bien de savoir ce qui est attendu de vous
            * c'est cette diversité qui fait que le boulot reste intéressant après de nombreuses années
        * Remettre en cause sans craindre mais sans ignorer ou minimiser les impacts.
            * le code source
            * l'architecture technique et les choix de bibliothèques
            * les outils de développement
        * Ne pas se baser sur les modes mais plutôt sur des besoins précis que l'on peut exprimer
    * Ce qui commencê à être généralisé
        * bonnes pratiques de dev
        * le concept d'usine de développement, outillage qualité
    * Les axes qui doivent encore être améliorés en entreprise
        * le concept de patrimoine de code
        * du coup, l'intérêt d'investir sur la qualité du code, que ce soit en investissement ou en exploitation
        * le développement de la culture des [artisans codeur](http://training.xebia.fr/formations-java-jee/formation-tdd-software-craftsmanship.html)

A caser :
* l'objectif de la présentation (évoquer sans trop de détails, donner des pistes de réflexion et de travail, ...)
* la métaphore de l'écologie
* des petits sondages (qu'est-ce que la maintenabilité, qui a fait de la maintenance en stage/apprentissage, ...) avec idéalement des statistiques réelles pour les résultats
* [clean code](http://blog.octo.com/les-artisans-codeurs-chez-octo/).
* note sur les choix de carrière, exigez un ordinateur puissant, cela coûte beaucoup moins cher que votre temps perdu. Faut-il forcément travailler à un endroit où une usine de développement est en place ?
* parler de la gestion des postes clients (IE 6 par exemple quand dev sous Linux) : dans la section sur les environnements de dev ?
* où parler de l'intérêt des liens URL entre les différents contenus de l'usine de dev ?
* penser à mettre un slide sur les coûts de maintenance sur la durée de vie d'un projet.
* mode de fonctionnement flickr avec activation des fonctionnalités ou non
* parler de budgets d'investissement et d'exploitation
* penser aux crédits logiciels et photo

Ne sera probablement pas décrit :
* les différences entre outils par projet et outils centralisés pour l'usine de développement

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
* Lang H.
* Eric L.