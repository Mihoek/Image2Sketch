Architecture du modèle
======================

Vue d'ensemble
--------------

Le projet utilise une architecture U-Net, qui est particulièrement adaptée aux tâches de segmentation d'image et de génération de contenu visuel. Cette architecture se caractérise par:

- Une partie encodeur qui capture le contexte
- Une partie décodeur qui permet une localisation précise
- Des connexions de type "skip" entre l'encodeur et le décodeur

Structure détaillée
-------------------

.. code-block:: text

   Inputs (256×256×3)
   │
   ├── Encoder
   │   ├── Conv1 (64 filtres)
   │   │   └── MaxPool1
   │   ├── Conv2 (128 filtres)
   │   │   └── MaxPool2
   │   └── Conv3 (256 filtres)
   │       └── MaxPool3
   │
   ├── Bridge
   │   ├── Conv4 (512 filtres)
   │   └── Dropout (0.5)
   │
   └── Decoder
       ├── UpSample1 + Concat avec Conv3
       │   └── Conv5 (256 filtres)
       ├── UpSample2 + Concat avec Conv2
       │   └── Conv6 (128 filtres)
       ├── UpSample3 + Concat avec Conv1
       │   └── Conv7 (64 filtres)
       └── Output (1 filtre, activation sigmoid)
