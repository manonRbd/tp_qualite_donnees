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

### Résultats

| Capitale      |     Moyenne     |  Ecar-type |  Aire      |  
| ------------- |: -------------: | ---------: | ---------: |
| Helsinki      |        1        |      1     |      1     |
| Oslo          |        2        |      1     |      1     |
| Stockholm     |        3        |      1     |      1     |
