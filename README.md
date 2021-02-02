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

| Mois      |      Moyenne    |  Ecart-type |   Température minimal    |  Température Maximal
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
Dans le jeu de données de SI erreur des données de type chaine de caractère. Afin de les corriger nous réalisons une moyenne avec 5 données antérieurs et postérieurs. Ensuite nous suposions que certaines données étaient érronées. Afin de les corriger nous avons réaliser une moyenne avec les valeurs des données antérieur et postérieur.

| Mois      |      Moyenne    |  Ecart-type |   Température minimal    |  Température Maximal
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


### Résultats

| Capitale      |     Différence de Moyenne avec SI_Error     |  Différence d'Ecart-type avec SI_Error |  Différence d'Aire avec SI_Error      |  Différence totale
| --------------|-----------------|------------| ---------- | ---------- |
| Helsinki      |        4.86        |      8.51     |      337     | **354.03**|
| Oslo          |        0.23        |      6.84     |      121     | **134.69**|
| Stockholm     |        22.99        |      3.85     |      940     | **947.70**|
