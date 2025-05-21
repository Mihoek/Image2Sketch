Préparation des données
=======================

Sources de données
------------------

Le modèle a été entraîné sur le dataset ``edge2real`` qui contient des paires d'images réelles et leurs correspondances en croquis. La structure du dataset est organisée comme suit:

.. code-block:: text

   dataset/edge2real/
   ├── train/
   ├── test/
   └── val/

Chaque image dans le dataset est une combinaison d'une image réelle et d'un croquis côte à côte.

Prétraitement
-------------

Le script ``Preprocesing_training.py`` effectue les opérations suivantes:

1. **Division des images combinées**: Sépare chaque image en deux moitiés, l'image réelle et le croquis correspondant
2. **Redimensionnement**: Toutes les images sont redimensionnées à 256×256 pixels
3. **Normalisation**: Les valeurs des pixels sont normalisées entre 0 et 1
4. **Augmentation des données**: Non implémentée dans la version actuelle, mais pourrait inclure des rotations, des flips, etc.

Structure des données prétraitées
---------------------------------

Après le prétraitement, les données sont organisées comme suit:

.. code-block:: text

   data/
   ├── images_combinees/
   │   ├── train/
   │   ├── test/
   │   └── val/
   ├── images_reelles/
   │   ├── train/
   │   ├── test/
   │   └── val/
   └── images_sketch/
       ├── train/
       ├── test/
       └── val/
