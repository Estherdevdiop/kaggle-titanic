# Projet Kaggle Titanic – Prédiction de survie

**Nom d’utilisateur Kaggle :** ton_nom_utilisateur_01EDU_emplacement_MM_AAAA

## Introduction

Ce projet a pour objectif de prédire la survie des passagers du Titanic lors de son naufrage en 1912, en utilisant des techniques de machine learning sur les données fournies par Kaggle. Le défi consiste à construire un modèle capable d’anticiper si un passager a survécu ou non, en se basant sur des caractéristiques telles que l’âge, le sexe, la classe socio-économique, le titre, le type de cabine, etc.

## Ingénierie des fonctionnalités

Pour améliorer la performance du modèle, plusieurs nouvelles caractéristiques ont été créées à partir des données brutes :

- **Extraction du titre** (Mr, Mrs, Miss, Master…) depuis le nom du passager, pour capter des informations sociales et démographiques.
- **Traitement des cabines** : création de variables indiquant le nombre de cabines attribuées et la lettre de la cabine, pour refléter la localisation et la richesse.
- **Analyse des tickets** : distinction entre tickets numériques et alphanumériques, extraction des préfixes des tickets.
- **Imputation des valeurs manquantes** : remplacement des âges et tarifs manquants par la médiane.
- **Transformation des variables continues** : normalisation logarithmique de la variable tarif (Fare) et standardisation des variables numériques.
- **Encodage des variables catégorielles** via one-hot encoding pour les modèles.

## Modèles et performances

Plusieurs modèles ont été testés avec validation croisée 5-fold :

| Modèle                     | Score de base (%) | Score optimisé (%) |
|----------------------------|-------------------|--------------------|
| Régression logistique      | 82.1              | 82.6               |
| K-Nearest Neighbors        | 80.5              | 83.0               |
| Random Forest              | 80.6              | 83.6               |
| Support Vector Classifier  | 83.2              | 83.2               |
| XGBoost                   | 81.8              | 85.3               |

Des classificateurs en vote (soft voting) combinant plusieurs modèles ont permis d’atteindre un score final supérieur à **79,1%** sur le leaderboard Kaggle, validant ainsi le projet (seuil de validation : 78,9%).

## Résultat final

Le meilleur score obtenu sur l’ensemble de test Kaggle est de **79,186%** de précision, ce qui valide la réussite du projet.

## Structure du dépôt
project/
│   README.md
│   requirements.txt
│   username.txt
│
└───data/
│   │   train.csv
│   │   test.csv
│   │   gender_submission.csv
│
└───notebook/
│   │   main.ipynb
│
└───models/
│   │   (scripts et fichiers liés à l’entraînement des modèles)
│
└───predictions/
    │   (scripts et fichiers pour générer les prédictions)



