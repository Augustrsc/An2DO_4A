Analyse des données Parcoursup (2025-2026)


Ce projet s'inscrit dans le cadre de l'unité d'enseignement Analyse de Données (4MA-AD). L'objectif est d'étudier les structures latentes et les typologies de formations dans l'enseignement supérieur français à partir des données Parcoursup. 

Problématique: Comment les facteurs de sélectivité, de mixité sociale et de localisation géographique structurent-ils l'offre de formation actuelle ? Existe-t-il une cohérence entre les filières déclarées et les classes statistiques obtenues par clustering ?


Organisation du dépôt:

Le projet est divisé en deux environnements pour tirer profit des meilleures bibliothèques de chaque langage.

Dans le fichier Rendu (et ordre exécution des fichiers en (.)):
    -un fichier R avec:
            -shared_data.R (nettoyage des données) (1)
            -Analyse Unidimensionnelle (2)
            -data_GPS (nettoyage des données spécifiquement pour exploiter les données GPS) (4)
            -ACP (qu'on réutilise ensuite) (6)
            -LDA (7)
    -un fichi Python avec:
            -analyse bidimensionnelle (3)
            -visu_carte (5)
            -CA_MCA (8)


Groupe: Romain Deleris, Corentin Brandam, Augustin Traissac, 2026
