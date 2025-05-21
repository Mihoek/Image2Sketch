API et intégration
=================

Utiliser le modèle dans d'autres applications
---------------------------------------------

Pour intégrer le modèle dans d'autres applications Python:

.. code-block:: python

   from tensorflow.keras.models import load_model
   import numpy as np
   from PIL import Image

   # Charger le modèle
   model = load_model('path/to/image_to_sketch_model.h5')

   # Préparer l'image
   def preprocess_image(img_path, target_size=(256, 256)):
       img = Image.open(img_path).convert('RGB').resize(target_size)
       img_array = np.array(img) / 255.0
       return np.expand_dims(img_array, axis=0)
       
   # Générer le croquis
   def generate_sketch(model, img_path):
       preprocessed_img = preprocess_image(img_path)
       sketch = model.predict(preprocessed_img)[0]
       return sketch.reshape(sketch.shape[0], sketch.shape[1])

   # Utilisation
   sketch = generate_sketch(model, 'path/to/image.jpg')

Exposition via API REST
-----------------------

Pour créer une API REST avec Flask (non implémentée dans le code actuel):

.. code-block:: python

   from flask import Flask, request, jsonify
   import base64
   import io
   from PIL import Image

   app = Flask(__name__)

   @app.route('/generate-sketch', methods=['POST'])
   def api_generate_sketch():
       if 'image' not in request.files:
           return jsonify({'error': 'No image provided'}), 400
           
       file = request.files['image']
       img = Image.open(io.BytesIO(file.read()))
       
       # Prétraitement et génération
       preprocessed = preprocess_image(img)
       sketch = model.predict(preprocessed)[0]
       
       # Conversion en base64 pour la réponse
       img_io = io.BytesIO()
       Image.fromarray((sketch * 255).astype('uint8')).save(img_io, 'PNG')
       img_io.seek(0)
       img_data = base64.b64encode(img_io.getvalue()).decode()
       
       return jsonify({'sketch': img_data})

   if __name__ == '__main__':
       app.run(debug=True)
