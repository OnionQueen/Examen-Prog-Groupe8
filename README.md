$Lucas, Christus, Mouad, Thomas$

# Examen Programmation Avancé

**description**

[Lien vers le notebook choisi (Heart Disease)](https://www.kaggle.com/datasets/redwankarimsony/heart-disease-data)

### Contenu

#### Structure du projet

<pre>
Examen-Prog-Groupe8/
│
├── notebooks/
│ ├── eda.ipynb # Analyse exploratoire des données
│ ├── pre_processing.ipynb # Preprocessing et pipeline
│ ├── modeling.ipynb # Entraînement et comparaison des modèles
│ └── tuning.ipynb # Optimisation des hyperparamètres
│
├── dataset.csv # Jeu de données
├── requirements.txt # Dépendances Python
└── README.md # Documentation du projet
</pre>

#### Description des colones :

- `id` (id unique pour chaque patient)
- `age` (Age des patients en années)
- `origin` (Origine des patients)
- `sex` (Homme / Femme)
- `cp` (Type de douleur)
    - typical angina.
    - atypical angina.
    - non-anginal.
    - asymptomatic.
- `trestbps` (pression artérielle au repos (en mm Hg))
- `chol` (cholestérol en mg/dl)
- `fbs` (si la glycémie à jeun est supérieure à 120 mg/dl)
- `restecg` (résultats électrocardiographiques au repos)
    - normal.
    - stt abnormality.
    - lv hypertrophy.
- `thalach` (fréquence cardiaque maximale atteinte)
- `exang` (angine induite par l'effort)
- `oldpeak` (Dépression du segment ST induite par l'exercice par rapport au repos)
- `slope` (la pente du segment ST maximal à l'effort)
- `ca` (nombre de vaisseaux principaux colorés par fluoroscopie)
    - normal.
    - fixed defect.
    - reversible defect.
- `num` (l'attribut prédit)

### Problèmes rencontrés

(explication)

### Installation

#### Mac/Linux

```
python3 -m venv .venv
source .venv/bin/activate
python -m pip install --upgrade pip
python -m pip install -r requirements.txt
```

---

#### Windows

```
python -m venv .venv
.venv\Scripts\activate
python -m pip install --upgrade pip
python -m pip install -r requirements.txt
```

### Résultats

GridSearchCV a été utilisé afin d’explorer différentes configurations
d’hyperparamètres du Gradient Boosting à l’aide d’une validation croisée.
Les résultats montrent que le modèle baseline était déjà proche de l’optimum,
ce qui confirme la pertinence du choix initial des paramètres.

### Résumé

(description)

### 1. Analyse Exploratoire (EDA)

Notebook : `notebooks/eda.ipynb`

Cette étape permet :

- d’explorer la structure des données,
- d’identifier les valeurs manquantes,
- d’analyser les distributions et les valeurs extrêmes,
- d’étudier les relations entre variables et la cible,
- d’analyser les corrélations entre variables numériques.

Les conclusions de l’EDA guident les choix de preprocessing et de modélisation.

---

### 2. Preprocessing

Notebook : `notebooks/pre_processing2.0.ipynb`

Un pipeline de preprocessing est mis en place afin de :

- gérer les valeurs manquantes,
- encoder les variables catégorielles,
- standardiser les variables numériques,
- éviter toute fuite de données.

Le preprocessing est réalisé à l’aide de :

- `Pipeline`
- `ColumnTransformer`
- `SimpleImputer`
- `StandardScaler`
- `OneHotEncoder`

---

### 3. Modélisation

Notebook : `notebooks/modeling2.0.ipynb`

Plusieurs modèles de classification sont entraînés et comparés à l’aide d’un pipeline commun :

- **Régression Logistique** (baseline)
- **Random Forest**
- **Gradient Boosting**

Les performances sont évaluées à l’aide de :

- l’accuracy
- le F1-score pondéré

Le **Gradient Boosting** obtient les meilleurs résultats globaux et est retenu pour l’optimisation.

---

### 4. Optimisation des hyperparamètres

Notebook : `notebooks/tuning.ipynb`

Le modèle Gradient Boosting est optimisé à l’aide de **GridSearchCV** avec validation croisée.

Les hyperparamètres optimisés incluent :

- `n_estimators`
- `learning_rate`
- `max_depth`

Le modèle optimisé présente de meilleures performances que la version par défaut.

### Modèle final

Le **Gradient Boosting optimisé** est retenu comme modèle final pour la prédiction de maladies cardiaques.

### Limites et pistes d'amélioration

### Références

