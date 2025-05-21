Dépannage et FAQ
================

Q: Comment installer les dépendances ?
--------------------------------------

R: Utilisez la commande suivante dans votre terminal:

.. code-block:: bash

   pip install -r requirements.txt

Q: Que faire si le modèle ne charge pas ?
-----------------------------------------

- Vérifiez le chemin vers le fichier `.h5`
- Assurez-vous que la version de TensorFlow est compatible
- Essayez de re-télécharger ou ré-entraîner le modèle

Q: L’interface Streamlit ne s’affiche pas
-----------------------------------------

- Vérifiez que le port 8501 est libre
- Assurez-vous d’avoir lancé la commande `streamlit run notebooks/Stremlitapp.py`
- Vérifiez la version de Streamlit
