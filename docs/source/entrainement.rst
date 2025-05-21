Entraînement du modèle
=====================

Configuration d'entraînement
----------------------------

Le modèle est entraîné avec les paramètres suivants:

- **Optimiseur**: Adam avec un taux d'apprentissage de 1e-4
- **Fonction de perte**: Binary Crossentropy
- **Métriques**: Accuracy
- **Batch size**: 32
- **Nombre d'époques**: 50 (avec early stopping)
- **Callbacks**:
  - ModelCheckpoint pour sauvegarder le meilleur modèle
  - EarlyStopping avec une patience de 10 époques

Classe de générateur de données
-------------------------------

Pour gérer efficacement la mémoire pendant l'entraînement, une classe ``DataGeneratorHelper`` a été implémentée. Cette classe:

- Charge les données par lots (batch)
- Effectue le prétraitement à la volée
- Met en œuvre l'interface d'itérateur Python pour une intégration transparente

Méthode d'entraînement optimisée
--------------------------------

Le script utilise une méthode d'entraînement optimisée pour la mémoire:

- Entraînement par lots avec ``model.train_on_batch()``
- Nettoyage explicite de la mémoire avec ``gc.collect()``
- Sauvegarde périodique du modèle

Performance et évaluation
-------------------------

Le modèle est évalué à l'aide de:

- Perte (loss) sur l'ensemble de validation
- Précision (accuracy) sur l'ensemble de validation
- Visualisation des prédictions sur des exemples de test
