# Flood Prediction – Regression Models Comparison

## Contexte du projet

Ce projet a été réalisé dans le cadre d'un **Travail Pratique (TP) en Intelligence Artificielle**.  
L'objectif principal est de comparer les performances de deux algorithmes de **régression supervisée** appliqués à un dataset réel/simulé de grande taille, conformément aux consignes pédagogiques.

Le thème retenu est la **prédiction des inondations**, un problème réel à fort impact socio-environnemental.

---

## Objectifs

- Utiliser un dataset contenant :
  - **1 117 957 observations**
  - **20 variables explicatives**
- Appliquer et comparer :
  - la **Régression Linéaire Multiple**
  - le **Random Forest Regressor**
- Évaluer les performances des modèles
- Identifier le modèle le plus adapté au dataset
- Analyser les notions de **bias, variance, underfitting et overfitting**

---

## Dataset

### Caractéristiques

- **Nombre d'observations** : 1 117 957
- **Nombre de variables explicatives** : 20
- **Variable cible** : `FloodProbability` (probabilité d'inondation)
- **Valeurs manquantes** : 0

### Variables explicatives

Le dataset contient les 20 variables suivantes :

1. `MonsoonIntensity` - Intensité de la mousson
2. `TopographyDrainage` - Drainage topographique
3. `RiverManagement` - Gestion des rivières
4. `Deforestation` - Déforestation
5. `Urbanization` - Urbanisation
6. `ClimateChange` - Changement climatique
7. `DamsQuality` - Qualité des barrages
8. `Siltation` - Envasement
9. `AgriculturalPractices` - Pratiques agricoles
10. `Encroachments` - Empiètements
11. `IneffectiveDisasterPreparedness` - Préparation inefficace aux catastrophes
12. `DrainageSystems` - Systèmes de drainage
13. `CoastalVulnerability` - Vulnérabilité côtière
14. `Landslides` - Glissements de terrain
15. `Watersheds` - Bassins versants
16. `DeterioratingInfrastructure` - Infrastructure en détérioration
17. `PopulationScore` - Score de population
18. `WetlandLoss` - Perte de zones humides
19. `InadequatePlanning` - Planification inadéquate
20. `PoliticalFactors` - Facteurs politiques

### Préparation des données

Avant l'entraînement des modèles, le dataset a fait l'objet de :
- Nettoyage des données
- Analyse exploratoire (distributions, corrélations)
- Séparation en jeux d'entraînement (80%) et de validation (20%)
- Standardisation pour les modèles linéaires

---

## Modèles utilisés

### 1. Régression Linéaire Multiple

La régression linéaire multiple est utilisée comme **modèle de référence**.  
Elle permet :
- une interprétation simple des relations entre variables
- une bonne compréhension des coefficients
- une évaluation du caractère linéaire du problème
- une rapidité d'entraînement et une faible consommation mémoire

### 2. Random Forest Regressor

Le Random Forest est un modèle basé sur un ensemble d'arbres de décision.  
Il permet :
- de capturer des relations **non linéaires**
- de gérer les interactions complexes entre variables
- de fournir l'importance des variables
- de réduire le risque d'overfitting par l'agrégation des arbres

**Hyperparamètres utilisés** :
- `n_estimators=100`
- `max_depth=20`
- `min_samples_split=10`
- `min_samples_leaf=5`

---

## Métriques d'évaluation

Les modèles sont comparés à l'aide des métriques suivantes :

- **MSE** (Mean Squared Error)
- **RMSE** (Root Mean Squared Error)
- **MAE** (Mean Absolute Error)
- **R² Score** (coefficient de détermination)

Les performances sont évaluées sur :
- le jeu d'entraînement
- le jeu de validation

---

## Résultats obtenus

### Performances des modèles

| Métrique | Régression Linéaire (Train) | Régression Linéaire (Val) | Random Forest (Train) | Random Forest (Val) |
|----------|----------------------------|---------------------------|----------------------|---------------------|
| **MSE** | 0.000404 | 0.000403 | 0.000409 | 0.000955 |
| **RMSE** | 0.020095 | 0.020080 | 0.020224 | 0.030911 |
| **MAE** | 0.015815 | 0.015792 | 0.016339 | 0.025232 |
| **R²** | 0.844968 | 0.844877 | 0.842972 | 0.632403 |

### Analyse des résultats

**Régression Linéaire Multiple** :
- R² Train : 0.8450, R² Validation : 0.8449
- Différence : 0.0001 (excellent équilibre, pas d'overfitting)
- **Diagnostic** : Bon équilibre entre bias et variance

**Random Forest** :
- R² Train : 0.8430, R² Validation : 0.6324
- Différence : 0.2106 (écart significatif)
- **Diagnostic** : Overfitting important

### Variables les plus importantes

**Régression Linéaire** (Top 5) :
1. `CoastalVulnerability`
2. `TopographyDrainage`
3. `PoliticalFactors`
4. `PopulationScore`
5. `Urbanization`

**Random Forest** (Top 5) :
1. `MonsoonIntensity`
2. `Siltation`
3. `PopulationScore`
4. `Deforestation`
5. `Landslides`

---

## Conclusion

### Modèle recommandé : Régression Linéaire Multiple

Le modèle de **Régression Linéaire Multiple** s'avère être le meilleur choix pour ce problème de prédiction d'inondation :

- **Meilleure performance** : R² de 0.8449 sur les données de validation (contre 0.6324 pour Random Forest)
- **Meilleure généralisation** : Écart minimal entre train et validation (0.0001)
- **Pas d'overfitting** : Excellent équilibre entre bias et variance
- **Interprétabilité** : Permet de comprendre l'impact de chaque variable
- **Efficacité** : Rapide à entraîner et peu coûteux en ressources

### Observations

- La **régression linéaire multiple** démontre que les relations dans ce dataset sont principalement linéaires
- Le **Random Forest** souffre d'un overfitting important, suggérant que les hyperparamètres pourraient nécessiter un réglage plus fin
- Les deux modèles identifient des variables importantes similaires, confirmant la cohérence des résultats

### Perspectives d'amélioration

- Tuning des hyperparamètres pour le Random Forest (réduction de la profondeur, augmentation de `min_samples_split`)
- Feature engineering pour créer de nouvelles variables pertinentes
- Utilisation de modèles plus avancés (XGBoost, LightGBM) avec validation croisée
- Analyse plus approfondie des interactions entre variables

---

## Installation

### Prérequis

- Python 3.8 ou supérieur

### Installation des dépendances

```bash
pip install -r requirements.txt
```

### Dépendances

- `pandas>=1.5.0` - Manipulation et analyse de données
- `numpy>=1.23.0` - Calculs numériques
- `matplotlib>=3.6.0` - Visualisation de données
- `seaborn>=0.12.0` - Visualisation de données avancée
- `scikit-learn>=1.2.0` - Machine Learning

---

## Structure du projet

```
FloodPrediction/
├── datasets/                    # Datasets du projet
│   ├── train.csv               # Dataset d'entraînement (1 117 957 observations)
│   ├── test.csv                # Dataset de test
│   ├── sample_submission.csv   # Exemple de soumission
│   └── flood.csv               # Dataset original
├── docs/                        # Documentation
│   └── CONTRIBUTING.md         # Règles de commit
├── index.ipynb                  # Notebook principal avec l'analyse complète
├── requirements.txt             # Dépendances Python
└── README.md                   # Ce fichier
```

---

## Utilisation

### Exécution du notebook

1. Ouvrir le notebook Jupyter :
```bash
jupyter notebook index.ipynb
```

2. Exécuter les cellules dans l'ordre pour :
   - Charger et explorer les données
   - Visualiser les distributions et corrélations
   - Entraîner les modèles
   - Évaluer et comparer les performances

### Workflow du projet

Le notebook suit cette structure :

1. **Présentation du dataset** - Chargement et informations générales
2. **Analyse exploratoire** - Visualisations et corrélations
3. **Préparation des données** - Partition train/validation et standardisation
4. **Entraînement des modèles** - Régression Linéaire et Random Forest
5. **Évaluation et comparaison** - Métriques et visualisations
6. **Analyse bias/variance** - Diagnostic d'overfitting/underfitting
7. **Conclusion** - Recommandation du meilleur modèle

---

## Technologies utilisées

- **Python** - Langage de programmation
- **NumPy** - Calculs numériques
- **Pandas** - Manipulation de données
- **Scikit-learn** - Machine Learning
- **Matplotlib / Seaborn** - Visualisation

---

## Équipe

Projet réalisé par le **groupe d'exposé** dans le cadre du TP d'Intelligence Artificielle.

---

## Remarques pédagogiques

Ce travail s'inscrit dans une démarche d'apprentissage visant à :
- Comprendre les modèles de régression
- Comparer leurs performances sur un dataset réel
- Appliquer des concepts théoriques à un cas concret
- Analyser les phénomènes de bias, variance, underfitting et overfitting
- Développer des compétences en data science et machine learning

---

## Contribution

Pour contribuer à ce projet, veuillez consulter les [règles de commit](docs/CONTRIBUTING.md) dans le dossier `docs/`.
