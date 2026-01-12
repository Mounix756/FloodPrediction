# Règles de Commit

Ce document décrit les conventions de commit à suivre pour ce projet.

## Format des messages de commit

Nous utilisons le format **Conventional Commits** pour standardiser les messages de commit.

### Structure générale

```
<type>(<scope>): <description>

[corps optionnel]

[footer optionnel]
```

### Types de commit

| Type | Description | Exemple |
|------|-------------|---------|
| `feat` | Ajout d'une nouvelle fonctionnalité | `feat: ajout du modèle Random Forest` |
| `fix` | Correction d'un bug | `fix: correction du calcul du RMSE` |
| `docs` | Modification de la documentation | `docs: mise à jour du README` |
| `style` | Changements de formatage (pas de changement de code) | `style: reformatage du code` |
| `refactor` | Refactorisation du code (pas de bug fix ni de nouvelle fonctionnalité) | `refactor: simplification de la fonction de preprocessing` |
| `perf` | Amélioration des performances | `perf: optimisation du chargement des données` |
| `test` | Ajout ou modification de tests | `test: ajout de tests unitaires pour le modèle` |
| `chore` | Tâches de maintenance (dépendances, configuration, etc.) | `chore: mise à jour des dépendances` |
| `build` | Changements liés au système de build | `build: configuration de l'environnement virtuel` |

### Scope (optionnel)

Le scope indique la partie du projet affectée :

- `model` : Modèles de machine learning
- `data` : Traitement des données
- `notebook` : Notebooks Jupyter
- `config` : Configuration
- `deps` : Dépendances

### Exemples de messages de commit

#### Commit simple
```
feat: ajout du modèle de régression linéaire
```

#### Commit avec scope
```
fix(model): correction de l'overfitting dans Random Forest
```

#### Commit avec description détaillée
```
feat(data): ajout du preprocessing des données

- Gestion des valeurs manquantes
- Normalisation des features
- Séparation train/test
```

#### Commit avec breaking change
```
feat(model)!: changement de l'API d'entraînement

BREAKING CHANGE: La méthode train() nécessite maintenant un paramètre validation_split
```

## Bonnes pratiques

### 1. Messages clairs et concis
- Utiliser l'impératif présent ("ajoute" plutôt que "ajouté" ou "ajoute")
- Limiter la première ligne à 50-72 caractères
- Décrire **quoi** et **pourquoi**, pas **comment**

### 2. Un commit = une modification logique
- Éviter de mélanger plusieurs modifications non liées
- Utiliser `git add -p` pour commiter par parties si nécessaire

### 3. Corps du message (optionnel mais recommandé)
Pour les commits complexes, ajouter un corps détaillé :
```
feat(model): implémentation de la validation croisée

- Ajout de la fonction cross_validate()
- Support de k=5 et k=10 folds
- Calcul automatique des métriques
```

### 4. Footer (optionnel)
Pour référencer des issues ou des breaking changes :
```
fix(data): correction du chargement CSV

Fixes #42
```

## À éviter

- Messages vagues : `fix bug`, `update`, `changes`
- Messages trop longs en première ligne
- Mélanger plusieurs modifications non liées
- Commits avec des fichiers de debug ou temporaires

## Checklist avant de commiter

- [ ] Le message suit le format Conventional Commits
- [ ] Le code fonctionne et passe les tests
- [ ] Les fichiers temporaires/debug sont exclus
- [ ] Un seul changement logique par commit
- [ ] Le message est clair et descriptif

## Ressources

- [Conventional Commits](https://www.conventionalcommits.org/)
- [Git Commit Best Practices](https://cbea.ms/git-commit/)

---

**Note** : Ces règles s'appliquent à tous les contributeurs du projet. En cas de doute, n'hésitez pas à consulter les commits précédents pour maintenir la cohérence.
