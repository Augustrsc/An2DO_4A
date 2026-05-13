# Analyse des données Parcoursup 2025-2026

[![R](https://img.shields.io/badge/R-276DC3?logo=r&logoColor=white)](https://www.r-project.org/)
[![Python](https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white)](https://www.python.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-F37626?logo=jupyter&logoColor=white)](https://jupyter.org/)
[![Course](https://img.shields.io/badge/UE-Analyse_de_Donn%C3%A9es_(4MA--AD)-C62828)]()

> Exploration statistique, analyses factorielles et clustering des formations de l'enseignement superieur francais a partir des donnees Parcoursup.

## Vue d'ensemble
Ce depot rassemble notre projet d'analyse de donnees realise dans le cadre de la 4e annee d'ingenieur en mathematiques appliquees a l'INSA Toulouse.

Nous cherchons a mettre en evidence les structures latentes de l'offre de formation en France a partir de la session **Parcoursup 2025-2026**, en croisant plusieurs dimensions :

- l'attractivite des formations ;
- la selectivite et les taux d'acces ;
- la mixite sociale ;
- les profils de baccalaureat ;
- la repartition geographique.

## Problematique
> Comment les facteurs de **selectivite**, de **mixite sociale** et de **localisation geographique** structurent-ils l'offre de formation actuelle ?  
> Existe-t-il une coherence entre les filieres declarees et les classes statistiques obtenues par clustering ?

## Objectifs

- decrire le jeu de donnees Parcoursup et ses grands equilibres ;
- comparer plusieurs methodes factorielles pour synthetiser l'information ;
- produire des typologies de formations robustes par clustering ;
- confronter les groupes statistiques obtenus a la lecture institutionnelle des filieres.

## Stack du projet
Le travail repose sur une approche hybride :

- **R** pour la preparation des donnees, l'analyse descriptive et certaines analyses statistiques ;
- **Python** pour les visualisations, les analyses multivariees complementaires et les algorithmes de machine learning ;
- **Jupyter notebooks** pour documenter l'ensemble du pipeline de facon reproductible.

## Methodologie

### 1. Analyse exploratoire
Nous commencons par un nettoyage global de la base puis par une lecture unidimensionnelle et bidimensionnelle des variables afin d'identifier :

- les contrastes entre types de formations ;
- les liens entre attractivite, selectivite et profil social ;
- les effets de territoire et de localisation.

### 2. Analyses factorielles
Plusieurs methodes de reduction de dimension sont mobilisees selon la nature des variables :

- **ACP** pour les variables quantitatives ;
- **ACM / CA** pour les variables qualitatives ;
- **AFM / MFA** pour articuler plusieurs groupes de variables.

### 3. Clustering
Le coeur du projet consiste a comparer plusieurs approches de segmentation :

- **K-Means** ;
- **CAH / HAC** ;
- **GMM** ;
- **Spectral Clustering** ;
- **DBSCAN**.

Une attention particuliere est portee au clustering apres reduction de dimension, notamment apres **ACM**, afin d'obtenir des classes plus stables et plus interpretable.

## Structure du depot

```text
.
├── R/                        # Scripts R de preparation
├── analyses/                 # Notebooks principaux d'analyse
├── data/raw/                 # Donnees brutes et sources intermediaires
├── figures/                  # Figures exportees
├── Rendu/                    # Supports finaux et livrables
├── pyproject.toml            # Dependances Python
├── renv.lock                 # Environnement R
└── README.md
```

## Parcours de lecture recommande
Pour suivre le projet dans un ordre logique :

| Etape | Fichier | Description |
| --- | --- | --- |
| 1 | `R/shared_data.R` | Nettoyage global et preparation du dataset principal. |
| 2 | `analyses/Analyse_Uni.ipynb` | Analyse descriptive des variables. |
| 3 | `analyses/analyse_bidimensionnelle.ipynb` | Croisements et lectures comparees. |
| 4 | `data/raw/data_GPS.ipynb` | Traitement des coordonnees geographiques. |
| 5 | `analyses/visu_carte.ipynb` | Cartographie interactive des formations. |
| 6 | `analyses/ACP.ipynb` ou `analyses/1_ACP.ipynb` | Analyse en composantes principales. |
| 7 | `analyses/LDA.ipynb` | Analyse discriminante lineaire. |
| 8 | `analyses/CA_MCA_Parcoursup_python.ipynb` | Analyse des correspondances simple et multiple. |
| 9 | `analyses/AD_MFA_python.ipynb` | Analyse factorielle multiple. |
| 10 | `analyses/GMM.ipynb` et `analyses/GMM_python.ipynb` | Modeles de melanges gaussiens. |
| 11 | `analyses/3_clustering.ipynb` | Premiers essais de segmentation. |
| 12 | `analyses/clustering_acm.ipynb` | Notebook central de comparaison des clustering. |

## Livrables importants

- `Rendu/Slides_oral.ipynb` : support de presentation du projet ;
- `Rendu/Fichier_Rendu/` : version finalisee des notebooks et ressources associees ;
- `analyses/carte.html` et `analyses/carte_multi_habillages.html` : cartes interactives ;
- `figures/ACP/corrplot.png` : exemple de figure exportee.

## Installation

### Cloner le depot
```bash
git clone https://github.com/Augustrsc/An2DO_4A.git
cd An2DO_4A
```

### Environnement Python
Les dependances Python sont definies dans [`pyproject.toml`](/home/gugubre/Projet_analyse_de_donnees_vf/An2DO_4A/pyproject.toml).

```bash
python -m venv .venv
source .venv/bin/activate
pip install -e .
```

Bibliotheques principales :
`pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn`, `plotly`, `prince`, `statsmodels`, `yellowbrick`, `pyreadr`, `graspologic`, `jupyter`.

### Environnement R
Le projet reference un environnement reproductible via [`renv.lock`](/home/gugubre/Projet_analyse_de_donnees_vf/An2DO_4A/renv.lock).

```r
install.packages("renv")
renv::restore()
```

Packages R centraux :
`FactoMineR`, `MASS`, `DT` et leurs dependances.

## Resultats vises

- degager une lecture structurelle du paysage Parcoursup ;
- identifier des regroupements coherents de formations ;
- comparer plusieurs methodes de segmentation sur une meme base ;
- relier les classes obtenues aux categories institutionnelles et territoriales.

## Pour commencer rapidement
Si vous voulez voir le coeur du travail sans tout lire, commencez par :

1. `analyses/clustering_acm.ipynb`
2. `analyses/visu_carte.ipynb`
3. `Rendu/Slides_oral.ipynb`

## Cadre academique
Projet realise dans le cadre de l'UE **Analyse de Donnees (4MA-AD)** a l'**INSA Toulouse**.
