Déploiement
===========

Déploiement local
-----------------

Pour déployer l'application localement:

.. code-block:: bash

   streamlit run notebooks/Stremlitapp.py

Déploiement sur serveur
-----------------------

Pour le déploiement sur un serveur:

1. Installer les dépendances:

   .. code-block:: bash

      pip install -r requirements.txt

2. Lancer l'application avec un service comme gunicorn:

   .. code-block:: bash

      gunicorn -w 4 -b 0.0.0.0:8000 streamlit_app:app

3. Configuration Nginx (exemple):

   .. code-block:: nginx

      server
