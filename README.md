# Image_Clasification

## Muffins vs Chihuahuas

Leonardo Alvarado Menéndez A01705998

En este repositorio, se encuentra el codigo para la creación de un modelo que resuelva el ya conocido problema de muffins vs chihuahuas, usando herramietas de inteligencia artificial para clasificacion de imagenes en python.

El dataset se obtuvo de: https://www.kaggle.com/datasets/samuelcortinhas/muffin-vs-chihuahua-image-classification

Pasos de la creación del modelo:

1- Obtencion del dataset en el sitio ya mencionado

2- Separacion de las imagenes en train y test en relacion 80 - 20

- Las imagenes del dataset vienen por defecto separadas en train y test, pero para realizar la practica de separacion de un dataset en train y test, estas se deben juntar en una sola carpara imagenes 

3- Geeracion de nuevas imagenes

3.1- Para la generación de imagenes nuevas, en base a las originales, se usaron las siguientes modificaciones:
* rescale
* rotation_range
* width_shift_range
* height_shift_range 
* zoom_range 
* horizontal_flip 

Se usan estas modificaciones, ya que no afectan a la distinción de la imagen, esta se puede rotar, voltear, hacer zoom y alargar sin que se deje de entender que es cada imagen.

4- Creación y entrenamiento del primer modelo con las siguientes caractaristicas:

### Modelo base

Capas:

*   Con2D
*   Flatten
*   Densa de 256 nodos y act relu
*   Densa de 1 nodo y act sigmord

Metricas:

*   Loss = binary_crossentropy
*   Optimizer = adam
*   Metrics = accuracy

5- Testeo del modelo base

6- Creación y entrenamiento del modelo mejorado con las siguientes caractaristicas:

### Modelo mejorado

Para la mejora del modelo, se cambio la primer capa de un simple Conv2D a un modelo preentrenado VGG16, eliminando sus capas densas finales 

Capas:

*   VGG16
*   Flatten
*   Densa de 256 nodos y act relu
*   Densa de 1 nodo y act sigmord

Metricas:

*   Loss = binary_crossentropy
*   Optimizer = adam
*   Metrics = accuracy

7- Testeo del modelo final

Los modelos ya entrenados se enceuntran en:
* Modelo base: https://drive.google.com/file/d/1-1wzrfwG1w6FnsCR7QJKfuiAuul5jIfk/view?usp=sharing
* Modelo final: https://drive.google.com/file/d/19lIzKs4XEpnYLHMeHuwY1NsVi8LRIBuH/view?usp=sharing

Nota1: Algunos comentarios sobre como correr el codigo se encuentran en el doc Untilted0.ipynb
