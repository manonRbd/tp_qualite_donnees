# TP La qualité des données

## Rambaud Manon et Riwal Le Faou

Comparer deux jeux de données de climat pour déterminer la capitale européenne dont les données de
température sont fournies dans le fichier Climat.xlsx On se servira du fichier Savukoskikirkonkyla.xlsx issu de l’open data pour servir de référence.

Objectifs :

* Mettre en oeuvre un environnement de traitement graphique de données issues de sources plus ou
moins fiables.
* Corriger un jeu de données mal formé
* Proposer un candidat potentiel pour l’origine des données.

### Pour voir nos résultats détaillés vous pouvez soit :
* Aller sur le lien du <a href="https://nbviewer.jupyter.org/github/rbdManon/tp_qualite_donnees/blob/main/tp_Qualite_des_donnees.ipynb?flush_cache=True">notebook sur nbviewer</a> pour visualiser le notebook en ligne
* Télécharger le fichier <a href="https://github.com/rbdManon/tp_qualite_donnees/blob/main/tp_Qualite_des_donnees.ipynb">tp_Qualite_des_donnees.ipynb</a> et l'ouvrir sur un outil de notebook python comme Google Colab ou Jupyter

Au niveau des données utilisées pour comparer avec les capitales européennes du nord, nous avons utilisés les données présentes sur ce lien : https://www.kaggle.com/sudalairajkumar/daily-temperature-of-major-cities et qu proviennent originellement de l'université de Dayton. Après extraction des températures nous obtenons le fichier temp_north_city.xlsx avec les températures annuelles d'Oslo, de Stockholm et de Helsinki pour l'année 2018.

### Fichier de données SI

| Mois      |      Moyenne    |  Ecart-type |   Température minimale    |  Température maximale
| --------------|-----------------|------------| ---------- | ---------- |
| Janvier  |        -8.967742       |      4.490611    |      **-23.0**     | -3.0 |
| Février    |       -4.928571      |      4.561746    |     -12.0      | 5.0 |
| Mars     |        1.193548       |     3.506369     |      -8.0    | 7.0|
| Avril     |        8.000000        |    3.151354   |     2.0    | 16.0|
| Mai     |        12.903226       |      4.036127     |    5.0      | 18.0 |
| Juin     |        17.033333       |     3.011281    |      11.0     | 22.0 |
| Juillet     |       18.322581       |      3.571994     |   13.0      | **26.0**|
| Août     |         17.838710      |     2.696872    |      14.0     | 26.0 |
| Septembre     |        10.500000        |      2.330458     |     6.0    | 16.0 |
| Octobre     |        3.870968        |     1.802627    |      1.0     | 7.0 |
| Novembre     |       -0.333333        |     3.717000     |     -8.0     | 5.0 |
| Décembre     |        -7.000000       |      2.065591     |    -11.0     | -3.0 |


### Fichier de données SI erreur
Dans le jeu de données de SI erreur des données de type chaine de caractère ont été relevées. Afin de les corriger nous réalisons une moyenne avec 5 données antérieures et postérieures. Ensuite nous supposions que certaines données étaient erronées avec des valeurs trop hautes comme 45° au mois d’août. Afin de les corriger nous avons réalisé une moyenne avec les valeurs des données antérieures et postérieures. Pour trouver ces données erronées, la mise en place d'un critère de recherche a été nécessaire. Nous considérions que si la température du jour est supérieure à 15 de la température de la veille alors celle-ci est erronée. Les données corrigées sont proches des données du fichier SI.Le plus grand écart de valeur est de 3 mais varie plus autour de 0,5 et 1,5.

| Mois      |      Moyenne    |  Ecart-type |   Température minimale    |  Température maximale
| --------------|-----------------|------------| ---------- | ---------- |
| Janvier  |        -8.967742       |      4.490611    |      **-23.0**     | -3.0 |
| Février    |       -5.196429     |      4.225889    |     -12.0      | 3.0 |
| Mars     |        1.169355       |     3.496062     |      -8.0    | 7.0|
| Avril     |        8.000000        |    3.151354   |     2.0    | 16.0|
| Mai     |        12.903226       |      4.036127     |    5.0      | 18.0 |
| Juin     |        17.012500       |    3.027950  |      11.0     | 22.0 |
| Juillet     |       18.338710       |      3.552903     |   13.0      | **26.0**|
| Août     |         17.822581     |     2.703542   |      14.0     | 26.0 |
| Septembre     |        10.500000        |      2.330458     |     6.0    | 16.0 |
| Octobre     |        3.802419       |     1.798661    |      1.0     | 7.0 |
| Novembre     |       -0.333333        |     3.717000     |     -8.0     | 5.0 |
| Décembre     |        -7.129032       |      1.927726     |    -11.0     | -3.0 |

### Graphiques
Ci-dessous le graphique des courbes mois par mois pour le fichier SI, le graphe est retrouvable à cette [adresse](https://nbviewer.jupyter.org/github/rbdManon/tp_qualite_donnees/blob/main/tp_Qualite_des_donnees.ipynb?flush_cache=True#Affichage-des-courbes-de-temp%C3%A9ratures-mensuelles)
![alt text](https://github.com/rbdManon/tp_qualite_donnees/blob/main/images/diagramme1.PNG?raw=true)

Voici ensuite le graphe à l'année du fichier SI le graphe est retrouvable à cette [adresse](https://nbviewer.jupyter.org/github/rbdManon/tp_qualite_donnees/blob/main/tp_Qualite_des_donnees.ipynb?flush_cache=True#Assemblage-des-courbes-sur-une-ann%C3%A9e)
![alt text](https://github.com/rbdManon/tp_qualite_donnees/blob/main/images/diagramme2.PNG?raw=true)


### Comparaison avec la station Savukoski kirkonkyla
Savukoski est une ville en Finlande d'où ont étées tirées des données de température au même format que nos fichiers SI et Si-Erreur précédents. Nous voulons comparer les deux courbes pour se rendre compte si elles sont proches. Voici le graphe de comparaison (retrouvable à cette [adresse](https://nbviewer.jupyter.org/github/rbdManon/tp_qualite_donnees/blob/main/tp_Qualite_des_donnees.ipynb?flush_cache=True#Comparaison-des-donn%C3%A9es-%C3%A0-l'ann%C3%A9e-pour-le-fichier-SI-error-et-le-fichier-de-Savukoski-kirkonkyla)) :
![alt text](https://github.com/rbdManon/tp_qualite_donnees/blob/main/images/diagramme3.PNG?raw=true)

Nous pouvons voir certaines différences notables entre les deux courbes notamment en début d'année vers le mois de mars ou les courbes s'éloignent significativement. Ce n'est probablement pas dans cette ville que les mesures de température du fichier SI ont étées réalisées.

### Comparaison graphique avec divers capitales du nord de l'Europe
Comme savukoski n'est probablement pas la ville recherchée nous allons comparer les courbes de températures du fichier avec les relevés de températures de diverses autres capitales d'Europe, nous avons restreints notre choix aux métropoles nordiques car les températures peuvent atteindre la barre des -20 ce qui est assez rare dans le centre et le sud de l'europe. Nous avons donc choisis Oslo, Helsinki, Stockholm ainsi que Kiev.

#### Comparaison avec Oslo
Voici le graphe de comparaison avec Oslo (retrouvable à cette [adresse](https://nbviewer.jupyter.org/github/rbdManon/tp_qualite_donnees/blob/main/tp_Qualite_des_donnees.ipynb?flush_cache=True#Comparaison-avec-Oslo)) :
![alt text](https://github.com/rbdManon/tp_qualite_donnees/blob/main/images/diagramme5.PNG?raw=true)

#### Comparaison avec Stockholm
Voici le graphe de comparaison avec Stockholm (retrouvable à cette [adresse](https://nbviewer.jupyter.org/github/rbdManon/tp_qualite_donnees/blob/main/tp_Qualite_des_donnees.ipynb?flush_cache=True#Comparaison-avec-Stockholm)) :
![alt text](https://github.com/rbdManon/tp_qualite_donnees/blob/main/images/diagramme4.PNG?raw=true)


#### Problème de la comparaison graphique
Bien que ces comparaisons graphiques soient esthétiquement agréable à l'oeil, elles n'en restent pas moins compliquées à interpréter. En effet il est complexe d'analyser la différence entre ces deux courbes à l'oeil nu, il est donc nécessaire de réaliser des comparaisons mathématiques entre les deux courbes.

### Comparaison numérique entre les températures des villes
Pour comparer les données du fichier SI-Error et celles des capitales européennes nous avons réalisés une comparaison en 3 étapes :
* Tout d'abord nous avons comparé la différence de moyenne de température mois par mois
* Ensuite nous avons fait la même chose mais pour l'écart-type
* Enfin nous avons calculé l'aire entre les deux courbes pour compléter notre calcul

Nous additionnons ensuite ces 3 valeurs qui sont censés tendre vers 0 à mesure que les données se rapprochent du lieu exacte où a été réalisé les mesures du fichier SI-Error et nous obtenons un score global.

Dans la partie suivante nous vous présentons les résultats pour les 4 villes que nous avons sélectionnés.

### Résultats

| Capitale      |     Différence de Moyenne avec SI_Error     |  Différence d'Ecart-type avec SI_Error |  Différence d'Aire avec SI_Error      |  Différence totale
| --------------|-----------------|------------| ---------- | ---------- |
| Helsinki      |        4.86        |      8.51     |      337     | **354.03**|
| Oslo          |        0.23        |      6.84     |      121     | **134.69**|
| Stockholm     |        22.99        |      3.85     |      940     | **947.70**|
| Kiev          |       36.49         |     4.31  |  1069 | **1077.62**
| Savukoski     |       51.69         |   12.98   | 1587 | **1613.77**

### Conclusion
Au vu de ces résultats, il a été conclus que le fichier SI représente probablement les températures de la capitale de la Norvège c'est-à-dire Oslo.
