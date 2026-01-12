# 🌊 Flood Prediction – Regression Models Comparison

## 📌 Contexte du projet

Ce projet a été réalisé dans le cadre d’un **Travail Pratique (TP) en Intelligence Artificielle**.  
L’objectif principal est de comparer les performances de deux algorithmes de **régression supervisée** appliqués à un dataset réel/simulé de grande taille, conformément aux consignes pédagogiques.

Le thème retenu est la **prédiction des inondations**, un problème réel à fort impact socio-environnemental.

---

## 🎯 Objectifs

- Utiliser un dataset contenant :
  - plus de **1 000 lignes**
  - plus de **10 variables explicatives**
- Appliquer et comparer :
  - la **Régression Linéaire Multiple**
  - le **Random Forest Regressor**
- Évaluer les performances des modèles
- Identifier le modèle le plus adapté au dataset
- Analyser les notions de **bias, variance, underfitting et overfitting**

---

## 📊 Dataset

Le dataset utilisé regroupe plusieurs facteurs influençant le risque d’inondation, notamment :

- précipitations
- humidité du sol
- niveau des cours d’eau
- température
- pression atmosphérique
- pente du terrain
- couverture végétale
- autres variables climatiques et environnementales

Avant l’entraînement des modèles, le dataset a fait l’objet de :
- nettoyage des données
- traitement des valeurs manquantes
- mise à l’échelle si nécessaire
- séparation en jeux d’entraînement et de test

---

## 🧠 Modèles utilisés

### 1️⃣ Régression Linéaire Multiple

La régression linéaire multiple est utilisée comme **modèle de référence**.  
Elle permet :
- une interprétation simple des relations entre variables
- une bonne compréhension des coefficients
- une évaluation du caractère linéaire du problème

---

### 2️⃣ Random Forest Regressor

Le Random Forest est un modèle basé sur un ensemble d’arbres de décision.  
Il permet :
- de capturer des relations **non linéaires**
- de gérer les interactions complexes entre variables
- de réduire le risque d’overfitting par l’agrégation des arbres

---

## 📈 Métriques d’évaluation

Les modèles sont comparés à l’aide des métriques suivantes :

- **MSE** (Mean Squared Error)
- **RMSE** (Root Mean Squared Error)
- **R² Score**

Les performances sont évaluées sur :
- le jeu d’entraînement
- le jeu de test

---

## 🔍 Analyse des résultats

Les résultats obtenus permettent de :
- comparer la capacité de généralisation des deux modèles
- analyser le compromis **bias / variance**
- détecter les phénomènes d’underfitting ou d’overfitting
- justifier le choix du modèle le plus adapté au problème étudié

---

## ✅ Conclusion

Ce projet montre que :
- la **régression linéaire multiple** est utile pour l’interprétation et comme baseline
- le **Random Forest Regressor** offre généralement de meilleures performances sur des données complexes et non linéaires

Le modèle Random Forest s’avère plus adapté pour la prédiction des inondations dans ce contexte, tout en nécessitant une attention particulière sur le réglage des hyperparamètres.

---

## 🛠️ Technologies utilisées

- Python
- NumPy
- Pandas
- Scikit-learn
- Matplotlib / Seaborn (visualisation)

---

## 👥 Équipe

Projet réalisé par le **groupe d’exposé** dans le cadre du TP d’Intelligence Artificielle.

---

## 📚 Remarques pédagogiques

Ce travail s’inscrit dans une démarche d’apprentissage visant à :
- comprendre les modèles de régression
- comparer leurs performances
- appliquer des concepts théoriques à un cas réel

