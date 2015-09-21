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

# Grands Principes
* Chaque vue est une application (un Activity)
    * côté vues :
        * développement des IHM statiques en XML
        * développement des IHM dynamiques en Java
    * côté métier :
        * développement essentiellement en JAVA et XML (exceptionnellement C / C++ )
* Les vues communiquent par message asynchrone (Intent)

## Cycle de vie des Activity
3 états :
* Active (affiché à l'écran)
* En pause (visible mais non accessible à l'utilisateur e.G en cas de pop up)
* Arréte (non visible, mais état maintenu tel quel)

Le système peut décider de détruire et de relancer les activités arrêtées (eg pour libére de la mémoire).

Il y a 3 cycles à prendre en compte :
* Le cycle de l'application (onCreate() - onDestroy())
* Le cycle visible (onStart() - onStop())
* le cycle actif (onResume() - onPause())


* onCreate(Bundle state) démare l'application
* onRestart() relance l'application après un arrêt
* onStart() relance l'application après un arrêt
* onResume() relance l'application
* onDestroy()
* onStop()
* onPause()

## Composant "Service"

* Pas de vue
* Processus en tache de fond qui offre des "capacities"
* Communique à partir des intent
* Dérive de "Service"

## Composant "BroadcastReceiver"

* Recoit et traite les messages broadcasté à l'ensemble des applications
* Peut émettre les messages
* Pas de vues
    * ... mais peut en démarer
    * ... ou intéragir avec le "NotificationManager"
* Dérive de "BroadcastReceiver"

## Composant "Content Providers"

* Rend disponible des données d'une application à d'autres applications (e.g carnet d'adresses)
    * données stockées dans le système de fichiers local
    * données stockées dans une base SQLite
    * ou tout autre source de données (e.g. Service web)
* déclare des points d'entrées pour les données
* s'interface avec un "ContentResolver"
* les autres applications interrogent le "ContentResolver"

## Mécanique des "Intent"
* Permet d'établir des liens en temps-réel entre les applications
    * En respectant les types des intent (broadcast intent nest transmis qu'aux broadcast receivers, ...)
    * Les "intent" peuvent viser
        * Une appli particulière (Intent Explicite)
        * Une appli non nommées (Intent Implicites)

### Activity
Une Activity se démarre en envoyant un intent avec la méthode :
* startActivity(Intent, ...)
* startActivityForResult(Intent, ...)
