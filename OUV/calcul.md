# Projet d'ouverture
> Anne-Sophie Balestra, Manal Afif et Jérémy Viallatte

## Budget matériel
* Location serveur (environ 15€/mois)
* Achat nom de domaine (entre 5 et 10€/an)

## Technologies prévues
* Application Web PHP (avec évolution vers une application mobile dans le future)
* Git pour le versionning
* Framework Symphony 2 pour la structure
* Doctrine pour insertion dans une base relationnelle
* Base NoSQL pour lecture rapide des données
* Framework Bootstrap Twitter pour l'interface graphisme et le dynamisme JavaScript
* Google Graph (ou autres outils de graphiques) pour l'affichage de statistiques
* Système de gestion de l'intégration continue

## Définition du projet
### But
Développer une application web qui permette à des associations de gérer l'interne (membres, dons, statistiques...).  
Mais, beaucoup de types d'associations différentes (protection animale, sportive, parents d'élèves...) donc beaucoup de besoins différents.  
Il faut donc développer une application suffisamment générique pour répondre aux différents types d'associations et suffisamment spécifique pour avoir une application qui réponde uniquement aux besoins de l'association.

### Méthode
Développer un tronc commun puis des templates/modèles pour différents types d'associations. De cette façon, chaque association pourra choisir le template qui lui correspond le plus et le personnaliser ensuite (de façon limitée) afin de répondre au mieux aux attentes.

### Activités hors développement
* Etude de marché auprès des associations
* Définition des différents types d'associations que nous voulons traiter (protection animale, sportive...)
* Demande des besoins à des membres d'associations en fonction de leur type
* Recoupement des besoins pour un tronc commum dans l'application
* Estimation du temps de développement
* Rédaction de documents (cahier des charges, document de spécifications techniques...)
* Documentation du code
* Tutoriels pour les utlisateurs (vidéos explicatives, documents texte...)

### Fonctionnalités à mettre en place
L'application sera de type CRUDL. Les fonctionnalités plus approfondies seront détaillées une fois les étude de marché et les demandes des besoins auprès des associations faites.

## Temps de travail
Dans le cadre de la formation, le temps disponible pour ce projet sera de 10h/homme par semaine en moyenne (il pourra varier après la formation).  

## Budget Humain
Nous nous basons sur une base à 16€/heure en brut pour chaque membre de l'équipe.
Sachant que nous prévoyons un travail de 10h/homme par semaine sur 16 semaines (cadre de la formation), notre budget humain serait de 640€ par mois (4 semaines/mois) .

## Rentabilité
Deux modes pour rentabiliser le projet :
* Mode **Premium** : 5 à 10€/mois (Le prix pourra varier en fonction du nombre de membres dans les associations) par association pour l'application complète et sans publicité
* Mode **Gratuit** : application limitée avec publicités

### Tests en fonction des utilisateurs
>*1 utilisateur = 1 association*

Sur une base de 100 utilisateurs (Premium à 7€, Rentabilité d'environ 3€/mois par association grâce aux publicités) :  

||Premium|Gratuit|TOTAL|
|---|---|---|---|
|Nombre d'utilisateurs|65|35|100|
|Prix/Mois|7|0|-|
|Rentabilité Publicités|0|3|-|
|Total/Mois|455|105|**560**|

## Point de rentabilité du projet
Nous serons donc en déficit sur les mois de développement et plusieurs mois qui suivent, puis le temps de travail sera diminuer (uniquement des maintenances) et donc le projet devrait devenir rentable dans les mois qui suivent la fin du développement.

En effet, sur notre base de 640€/mois pendant 4 mois minimum, (avant de pouvoir commencer à commercialiser notre projet), soit 2560€, nous pourrons commencer à être rentable au bout de 6 mois de commercialisation (sur notre base de 100 utilisateurs), en comptant des heures pour la maintenance.
