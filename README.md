# Documentation du Workflow dans ce Fichier Jupyter Notebook

## Importation des Bibliothèques
- Importation des bibliothèques nécessaires comme `pandas`, `numpy`, `matplotlib`, `seaborn`, et des modules de `sklearn`.

## Chargement des Données
- Chargement des fichiers CSV `listings_lyon.csv` et `listings_paris.csv` dans des DataFrames `df_lyon` et `df_paris`.

## Préparation des Données
1. **Ajout de la colonne `city`** :
    - Ajout de la colonne `city` pour identifier les données de Lyon et Paris.
2. **Suppression des colonnes non pertinentes** :
    - Suppression des colonnes inutiles pour la prédiction du prix, comme `id`, `listing_url`, `description`, etc.
3. **Concaténation des DataFrames** :
    - Fusion des DataFrames `df_lyon` et `df_paris` en un seul DataFrame `df`.

## Analyse des Données Manquantes
1. **Calcul des pourcentages de valeurs manquantes** :
    - Identification des colonnes avec des valeurs manquantes.
2. **Imputation des valeurs manquantes** :
    - Remplissage des valeurs manquantes avec la médiane pour les colonnes numériques et la mode pour les colonnes catégoriques.
3. **Suppression des lignes restantes avec des valeurs manquantes** :
    - Suppression des lignes contenant encore des valeurs manquantes après l'imputation.

## Nettoyage des Données
1. **Conversion des colonnes** :
    - Extraction du symbole de la colonne `price` et conversion en type numérique.
2. **Suppression des doublons** :
    - Identification et suppression des doublons dans le DataFrame.

## Analyse Exploratoire des Données (EDA)
1. **Analyse des corrélations** :
    - Calcul des corrélations entre les colonnes numériques et visualisation avec un heatmap.
2. **Analyse bivariée** :
    - Visualisation des relations entre différentes colonnes (`price` vs `room_type`, `property_type`, etc.) à l'aide de graphiques comme boxplots, scatterplots, et violin plots.

## Encodage des Données Catégoriques
1. **Encodage manuel** :
    - Mapping des colonnes comme `room_type` en valeurs numériques.
2. **Encodage avec `LabelEncoder`** :
    - Utilisation de `LabelEncoder` pour encoder plusieurs colonnes catégoriques.
3. **Encodage avec `OneHotEncoder`** :
    - Transformation des colonnes catégoriques en variables indicatrices.

## Modélisation
1. **Régression Linéaire** :
    - Sélection des colonnes pertinentes pour la prédiction (`features`) et entraînement d'un modèle de régression linéaire.
    - Évaluation du modèle avec le MSE (Mean Squared Error) et le R² Score.
2. **Recherche d'Hyperparamètres** :
    - Utilisation de `GridSearchCV` pour optimiser les hyperparamètres d'un modèle Ridge Regression.

## Visualisation des Résultats
1. **Comparaison des valeurs réelles et prédites** :
    - Visualisation des prédictions du modèle sur les ensembles d'entraînement et de test.
2. **Analyse des erreurs** :
    - Calcul de la racine carrée de l'erreur quadratique moyenne (RMSE).

## Résumé des Données
- Affichage des types de données, des dimensions, et des statistiques descriptives pour les colonnes importantes.

---

Ce fichier Jupyter Notebook combine des étapes de nettoyage, d'analyse exploratoire, d'encodage, et de modélisation pour prédire les prix des logements à partir des données d'Airbnb pour Lyon et Paris.