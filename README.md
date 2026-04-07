# titanic
> **Domaine** : Data Management  
> **Objectif** : Exploration, nettoyage et visualisation du dataset Titanic avec Python & Pandas

---

## 📋 Description

Ce travail constitue une introduction pratique à la manipulation de données tabulaires en Python. Il couvre l'ensemble du pipeline d'analyse de données : chargement, exploration, nettoyage, transformation et visualisation — à travers le célèbre dataset **Titanic**.

---

## 🎯 Objectifs pédagogiques

- Comprendre la structure d'un jeu de données tabulaire
- Identifier les problèmes de qualité (valeurs manquantes, doublons, incohérences)
- Réaliser des opérations de nettoyage et de préparation des données
- Manipuler un DataFrame pandas : filtrage, tri, création de colonnes
- Produire des visualisations pour explorer les données

---

## 🗂️ Structure du projet

```
TP1/
│
├── titanic.ipynb        # Notebook Jupyter principal
└── README.md        # Ce fichier
```

---

## 📦 Dataset

Le dataset utilisé est le **Titanic**, chargé directement via la bibliothèque `seaborn` :

```python
import seaborn as sns
df = sns.load_dataset("titanic")
```

### Colonnes principales

| Colonne | Description |
|---|---|
| `survived` | 0 = décédé, 1 = survivant |
| `pclass` | Classe du billet (1 / 2 / 3) |
| `sex` | Sexe du passager |
| `age` | Âge du passager |
| `sibsp` | Nombre de frères/sœurs/époux à bord |
| `parch` | Nombre de parents/enfants à bord |
| `fare` | Tarif du billet |
| `embarked` | Port d'embarquement (S / C / Q) |
| `deck` | Pont du navire (beaucoup de valeurs manquantes) |

---

## 🔬 Contenu du TP

### Partie 1 — Découverte du dataset
Chargement des données et exploration initiale avec `df.info()`, `df.describe()`, `df.head()` et `df.tail()`.

### Partie 2 — Qualité des données
Identification des problèmes :
- **177 valeurs manquantes** dans `age` (~20% des passagers)
- **688 valeurs manquantes** dans `deck` (~75% de la colonne)
- **2 valeurs manquantes** dans `embarked`
- Vérification des doublons avec `df.duplicated().sum()`

Réponses aux questions clés :
- Nombre total de passagers : **891**
- Âge moyen : **~29.7 ans**
- Taux de survie : **~38.4%**

### Partie 3 — Nettoyage des données
| Problème | Solution appliquée |
|---|---|
| Valeurs manquantes dans `age` | Remplacement par la **médiane** |
| Valeurs manquantes dans `embarked` | Remplacement par la **valeur la plus fréquente** |
| Colonne `deck` inutilisable | **Suppression** de la colonne |
| Noms de colonnes peu lisibles | **Renommage** : `sibsp` → `Freres/Epoux`, `parch` → `Parents/Enfants` |

### Partie 4 — Manipulation des données
- Filtrage des passagers en 1ère classe
- Tri par âge décroissant
- Création d'une colonne `TailleFamille` = `Freres/Epoux` + `Parents/Enfants` + 1
- Calcul du prix moyen du billet par classe

### Partie 5 — Visualisations
- 📊 **Histogramme** : distribution des âges des passagers
- 🥧 **Diagramme circulaire** : répartition par sexe
- 📈 **Diagramme en barres** : taux de survie par classe

---

## 🧹 Problèmes de qualité détectés & transformations

### Problèmes identifiés
1. **Valeurs manquantes** dans `age`, `deck` et `embarked`
2. **Colonne inutilisable** : `deck` avec 75% de données absentes
3. **Noms de colonnes cryptiques** : `sibsp`, `parch`

### Transformations réalisées
1. Imputation de `age` par la médiane (robuste aux valeurs extrêmes)
2. Imputation de `embarked` par le mode (valeur la plus fréquente)
3. Suppression de `deck`
4. Renommage des colonnes pour plus de lisibilité
5. Création de la colonne `TailleFamille`

> 💡 En data science, le nettoyage et la préparation des données représentent environ **80% du travail** d'un projet.

---

## 🛠️ Technologies utilisées

![Python](https://img.shields.io/badge/Python-3.12-blue?logo=python)
![Pandas](https://img.shields.io/badge/Pandas-2.x-150458?logo=pandas)
![Seaborn](https://img.shields.io/badge/Seaborn-0.13-4c72b0)
![Matplotlib](https://img.shields.io/badge/Matplotlib-3.x-11557c)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange?logo=jupyter)

---

## ▶️ Lancer le projet

1. Clone le dépôt :
```bash
git clone https://github.com/TON_USERNAME/TON_REPO.git
cd TON_REPO
```

2. Installe les dépendances :
```bash
pip install pandas seaborn matplotlib jupyter
```

3. Lance le notebook :
```bash
jupyter notebook tp1.ipynb
```

---

## 👤 Auteur

**Voundi Abessolo**  
Étudiant M1 — EPSI 2026  
