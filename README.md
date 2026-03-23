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
