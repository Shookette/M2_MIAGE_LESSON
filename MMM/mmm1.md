# Android - Un système d'exploiration pour appareils mobiles

## I - Présentation
### Contexte

* Convergence des technologies matérielles, du réseau et du logiciel a mener à une évolution majeure dans le monde informatique
* Marché en forte croissance des terminaux mobiles
* De gros acteurs viennent promouvoir le développement d'applications mobile

### Révolution des usages

* Les technologies mobiles ont transformé radicalement notre façon d'intéragir avec le monde.
* Depuis 8 ans les évolutions des possibilités et des demandes ont explosé.
* Nouvelles intéractions créées (réseaux sociaux, jeux, gps, etc ...)

### Impacts

* Communication vs services :
    * Les acteurs se mettent tous au mobiles (effet de mode)
    * Valeur ajoutée pour le client (nouvelle façon de récupérer ces données)

### Industries du logiciel

* Besoins de développement sur terminaux mobiles
    * Portage d'applications existantes
    * Accès à distance a nos données
    * Nouveaux besoins (réseaux sociaux, jeux, etc ...)
* Problèmatique du portage d'application entre terminaux (Blackberry, Iphone, WPhone, Android)
    * Développement constant de nouveaux OS constructeur (samsung, bada, etc)

## Architecture
### Noyau Android

* Binder
    * Communication spécifique interprocessus (IPC) pour renforcer la sécurité
    * Chaque application est lancée dans un processus différent, une application A ne peut pas accéder aux informations d'une application B car lancé sur des processus différents.
    * Prise en charge du partage de données et les accés concurrents
* Webkit
* MediaFormat permet la gestion des medias

## Android Runtime

>JVM Dalvik : Machine virtuelle Java spécifique pour les appli Android

* Une nouvelle instance de la JVM est lancée pour chaque process ce qui permet l'indépendance des application
* Le code est compilé dans des fichiers (Dalvik Executables)
* Dalvik core class library est basé sur java SE 5
* JVM Dalvik :
    * Basé sur une architecture basée sur une machine à registre (machine de turing) plutôt qu'une machine à pile.
        * Machine à pile nécessitent des instructions particulières pour charger les arguments
        * Marchine à registre ont des "pocode" plus complexes (spécification des registres source et destrination)
    * La JVM possède une empreinte mémoire réduite
    * La JVM est optimisée pour faire tourner plusieurs JVM simultané et en parallèle
    * Les perf sont tout de même en déca d'un java EMBEDDED

## Framework application

* Les vues qui permettent de construire une application (widget + layout)
* Les content Providers autorisent l'application à accéder à des données d'autre applications
