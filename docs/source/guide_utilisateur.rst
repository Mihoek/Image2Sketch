User Guide / Guide Utilisateur
=============================

Installation
-----------

1. Clonez le dépôt:

   .. code-block:: bash

      git clone https://github.com/Mihoek/Image2Sketch.git
      cd Image2Sketch

2. Installez les dépendances:

   .. code-block:: bash

      pip install -r requirements.txt

Utilisation de l'Application
--------------------------

Démarrage
~~~~~~~~~

1. Lancez l'application:

   .. code-block:: bash

      streamlit run notebooks/Stremlitapp.py

2. Ouvrez votre navigateur à l'adresse: http://localhost:8501

Transformer une Image
~~~~~~~~~~~~~~~~~~~

1. Choisissez une méthode d'entrée:
   * Cliquez sur "Télécharger une image" pour utiliser une image existante
   * Ou utilisez "Utiliser la caméra" pour prendre une photo

2. Sélectionnez un effet:
   * Normal: rendu standard
   * Contraste élevé: pour plus de détails
   * Adouci: pour un rendu plus doux
   * Net: pour des traits précis

3. Cliquez sur "Générer le croquis"

4. Téléchargez le résultat avec le bouton "Télécharger le croquis"

Dépannage
---------

Si l'application ne démarre pas:

1. Vérifiez que toutes les dépendances sont installées:

   .. code-block:: bash

      pip install -r requirements.txt

2. Assurez-vous que le modèle est présent:
   * Le fichier `models/image_to_sketch_model.h5` doit exister
   * Si absent, téléchargez-le depuis les releases du projet

3. Port déjà utilisé:
   * Fermez les autres applications utilisant le port 8501
   * Ou changez le port: `streamlit run notebooks/Stremlitapp.py --port 8502`