# Marseille et ses transports en commun



## Présentation du projet



Ce projet a pour objectif d'étudier les relations entre les caractéristiques socio-démographiques de la population marseillaise et l'accessibilité au réseau de transports en commun.



L'étude combine des données carroyées de l'INSEE et des données géographiques ouvertes sur les lignes et les arrêts du réseau de transport marseillais afin de construire une nouvelle base de données spatiale.



L'objectif est d'analyser :



* la répartition spatiale de la population et du niveau de vie
* le maillage du réseau de transports en commun
* les liens entre accessibilité au réseau et niveau de vie
* les disparités observées dans ces liens entre les différents arrondissements de Marseille



### Sources des données



###### Données socio-démographiques :

Données carroyées INSEE à l'échelle de 200 m × 200 m (Ces données sont trop volumineuses et n'ont pas été incluses dans le dossier data. Pour les télécharger, la source est disponible dans le fichier source.txt du même dossier.)



###### Données de transport :

Lignes du réseau RTM

Arrêts du réseau RTM



###### Données administratives :

Contours géographiques des communes et arrondissements en France



Les différentes sources sont répertoriées dans le dossier :

data/raw/



#### 

### Structure du projet



Marseille\_transport\_analysis/

│

├── data/

│   ├── raw/

│   │   ├── insee/

│   │   ├── transport/

│   │   ├── administratif/

│   │   └── sources.txt

│   │

│   └── cleaned/

│       ├── data\_marseille\_tec\_cleaned.geojson

│       └── data\_zones\_arrets.geojson

│

├── notebooks/

│   ├── 01\_data\_cleaning.ipynb

│   └── 02\_analysis.ipynb

│

├── docs/

│   └── maps/

│	└── 10 fichiers HTML des cartes présentées dans 02\_analysis.ipynb

│

├── README.md

├── requirements.txt

└── .gitignore





## Démarche



### 1\. Construction de la base de données



Le notebook 01\_data\_cleaning.ipynb comprend :



* le nettoyage des données
* la création de nouvelles variables socio-démographiques
* la sélection des arrêts sur la base du territoire étudié
* l'association des arrêts aux lignes du réseau
* la création de zones d'arrêts regroupant les arrêts portant le même nom
* le calcul de plusieurs indicateurs d'accessibilité
* l'enrichissement des données carroyées de l'INSEE



Deux jeux de données sont ensuite exportés :



* une base de données sur les carreaux de 200 m
* une base regroupant les zones d'arrêts



### 2\. Analyse



Le notebook 02\_analysis.ipynb contient :



* une analyse exploratoire des variables
* l'étude de la structure spatiale de la ville
* l'analyse de l'accessibilité au réseau de transport
* l'étude des relations entre niveau de vie et accès au réseau
* une analyse détaillée par arrondissement



## Principaux résultats



### Ville de Marseille



* La population est principalement concentrée dans le centre-ville autour du Vieux-Port.
* Les zones les plus denses sont en moyenne plus modestes.
* Une opposition Nord/Sud apparaît dans la répartition du niveau de vie.



### Réseau de transport



* La quasi-totalité de la population réside à moins de 500 mètres d'un arrêt.
* 80 % des habitants vivent à moins de 500 mètres d'une zone desservie par au moins quatre lignes.
* La proximité du Vieux-Port est associée à une meilleure accessibilité au réseau.



### Niveau de vie et accessibilité



À l'échelle de la ville, les zones les plus aisées apparaissent en moyenne plus éloignées du réseau.



Cependant, cette relation n'est pas uniforme :



* dans les arrondissements périphériques, elle est généralement négative
* dans plusieurs arrondissements du centre-ville, elle devient plus ambiguë



## Limites de l'étude



Plusieurs limites doivent être prises en compte :



* certaines associations entre arrêts et lignes reposent uniquement sur la proximité géographique
* les zones d'arrêts sont construites à partir du nom des arrêts et non de leur proximité spatiale
* l'accessibilité est mesurée uniquement à travers les infrastructures et le nombre de lignes
* les distances calculées correspondent à des distances à vol d'oiseau
* les données utilisées ne permettent pas d'étudier l'évolution du réseau dans le temps
* certains arrondissements disposent d'un faible nombre d'observations



## Recommandations



* Favoriser la mise à disposition de données plus exhaustives sur le réseau de transports en commun.
* Mener une analyse longitudinale pour mettre en avant les dynamiques de l'évolution du réseau et de l'organisation de la ville.
* Affiner l'analyse à l'échelle locale pour déterminer les spécificités de l'accès au réseau par arrondissement.



## Bibliothèques utilisées



pandas

numpy

geopandas

shapely

pyproj

folium

matplotlib

seaborn

scipy

branca



## Compétences mobilisées



* Nettoyage et préparation des données
* Construction d'une base de données
* Manipulation de données géographiques
* Analyse exploratoire
* Statistiques descriptives
* Corrélations et analyse spatiale
* Data visualisation
* Interprétation et communication des résultats
* Formulation de recommandations

