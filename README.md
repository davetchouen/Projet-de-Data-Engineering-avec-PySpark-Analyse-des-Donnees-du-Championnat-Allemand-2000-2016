# Projet de Data Engineering avec PySpark : Analyse des Données du Championnat Allemand (2000-2016)
## Problématique
Dans le cadre de ce projet, nous cherchons à analyser les performances des équipes de football du championnat allemand (Bundesliga) entre 2000 et 2016. Les données disponibles contiennent des informations sur les matchs, telles que les équipes, les scores, les résultats, et les saisons. Cependant, ces données brutes ne sont pas directement exploitables pour une analyse approfondie. Plusieurs défis se posent

## Problèmes Rencontrés et Solutions

### Chargement des Données

Problème : Les données sont stockées dans un fichier CSV, et il faut les importer dans un format utilisable pour l'analyse.

Solution : Nous avons utilisé PySpark pour charger les données dans un DataFrame, ce qui permet de manipuler facilement les données.

### Renommage des Colonnes

Problème : Les noms des colonnes dans le fichier CSV ne sont pas très clairs (par exemple, FTHG, FTAG, FTR).

Solution : Nous avons renommé ces colonnes avec des noms plus explicites, comme HomeTeamGoals, AwayTeamGoals, et FinalResult, pour faciliter la compréhension.

### Suppression des Colonnes Inutiles

Problème : Après avoir renommé les colonnes, certaines d'entre elles ne sont plus nécessaires.

Solution : Nous avons supprimé ces colonnes pour simplifier le DataFrame.

### Création de Colonnes Binaires pour les Résultats

Problème : Les résultats des matchs sont représentés par des lettres (H pour une victoire à domicile, A pour une victoire à l'extérieur, D pour un match nul), ce qui n'est pas pratique pour l'analyse.

Solution : Nous avons créé de nouvelles colonnes binaires (HomeTeamWin, AwayTeamWin, GameTie) pour indiquer si l'équipe à domicile a gagné, perdu, ou si le match s'est terminé par un match nul.

### Filtrage des Données pour la Bundesliga

Problème : Les données contiennent des matchs de plusieurs divisions et saisons, mais nous ne sommes intéressés que par les matchs de la Bundesliga (division D1) entre 2000 et 2016.

Solution : Nous avons filtré les données pour ne garder que les matchs de la Bundesliga dans la plage de saisons spécifiée.

### Agrégation des Statistiques par Équipe et Saison

Problème : Nous voulons calculer des statistiques agrégées pour chaque équipe et chaque saison, comme le nombre de victoires, de défaites, de matchs nuls, et les buts marqués et encaissés à domicile et à l'extérieur.

Solution : Nous avons regroupé les données par équipe et saison, puis calculé les statistiques nécessaires pour les matchs à domicile et à l'extérieur.

### Fusion des Données Domicile et Extérieur

Problème : Les statistiques des matchs à domicile et à l'extérieur sont dans deux DataFrames distincts.

Solution : Nous avons fusionné ces deux DataFrames pour avoir une vue complète des performances de chaque équipe.

### Calcul des Totaux

Problème : Nous voulons calculer les totaux des buts marqués et encaissés, ainsi que les totaux des victoires, défaites et matchs nuls pour chaque équipe et saison.

Solution : Nous avons créé de nouvelles colonnes contenant ces totaux pour chaque équipe et saison.

## Conclusion
Ce projet montre comment utiliser PySpark pour manipuler et analyser des données de football. Les étapes clés incluent le chargement des données, le nettoyage, la transformation, l'agrégation et la fusion des données pour obtenir des insights sur les performances des équipes dans le championnat allemand. Ces techniques peuvent être appliquées à d'autres ensembles de données pour des analyses similaires.

N'hésitez pas à explorer le notebook pour plus de détails sur chaque étape du processus !
