Environnement Jupyter R du projet

Le projet utilise `renv` pour figer les packages R et un kernel Jupyter dédié nommé `R (An2DO_4A)`.

Commandes utiles depuis la racine du projet :

```bash
Rscript -e 'source("renv/activate.R"); renv::status()'
jupyter lab
```

Dans Jupyter, choisir le kernel `R (An2DO_4A)` si ce n'est pas déjà sélectionné automatiquement.

Packages principaux installés pour le TP :

- `tidyverse`
- `corrplot`
- `FactoMineR`
- `factoextra`
- `ca`
- `IRkernel`

Partage des données entre notebooks

Pour éviter de copier le contenu de `data/raw/data.ipynb` dans chaque notebook, on a ajouté un script commun : [R/shared_data.R](/home/gugubre/Projet_analyse_de_donnees_vf/An2DO_4A/R/shared_data.R)

Exemple dans un notebook d'analyse :

```r
source("../R/shared_data.R")

# Charge le fichier déjà préparé s'il existe, sinon le reconstruit depuis le CSV
data_features_core <- load_analysis_data()

# Si vous voulez forcer une reconstruction après modification du prétraitement :
data_features_core <- load_analysis_data(rebuild = TRUE)
```

Workflow conseillé :

- `data/raw/Parcoursup.csv` reste la source brute.
- Toute la logique de préparation commune vit dans `R/shared_data.R`.
- Les notebooks `analyses/1_ACP.ipynb`, `analyses/2_ACM.ipynb`, etc. chargent `data_features_core` via `load_analysis_data()`.
- Le fichier généré est sauvegardé automatiquement dans `data/processed/data_features_core.rds`.
