Interface utilisateur
====================

L'interface utilisateur est construite avec Streamlit, offrant une expérience web interactive et réactive.

Fonctionnalités de l'interface
------------------------------

- **Téléchargement d'image**: Les utilisateurs peuvent télécharger une image depuis leur appareil
- **Capture webcam**: Prise de photo en direct via la caméra
- **Effets**: Plusieurs options de post-traitement sont disponibles
  - Normal: Croquis standard
  - Contraste élevé: Utilise CLAHE pour améliorer le contraste
  - Adouci: Applique un flou gaussien pour des lignes plus douces
  - Net: Applique un filtre de netteté pour des détails plus précis
- **Téléchargement**: Les utilisateurs peuvent télécharger le croquis généré

Structure du code
-----------------

Le script Streamlit (``Stremlitapp.py``) est organisé selon le flux suivant:

1. Configuration et mise en page
2. Chargement du modèle
3. Fonctions de prétraitement et de génération
4. Interface d'upload et de capture
5. Traitement et génération du croquis
6. Options de téléchargement
7. Informations supplémentaires
