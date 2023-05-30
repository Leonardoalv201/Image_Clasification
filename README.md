# Image_Clasification

## Muffins vs Chihuahuas

Leonardo Alvarado Menéndez A01705998

En este repositorio, se encuentra el codigo para la creación de un modelo que resuelva el ya conocido problema de muffins vs chihuahuas, usando herramietas de inteligencia artificial para clasificacion de imagenes en python.

El dataset se obtuvo de: https://www.kaggle.com/datasets/samuelcortinhas/muffin-vs-chihuahua-image-classification

## Pasos de la creación del modelo:

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

Nota: 
* En loss se uso binary crossentropy, ya que queremos clasificar 0 o 1: https://keras.io/api/metrics/probabilistic_metrics/#binarycrossentropy-class
* En optimizer adam, ya que el método es "computacionalmente eficiente, tiene pocos requisitos de memoria, es invariable al cambio de escala diagonal de gradientes y es muy adecuado para problemas que son grandes en términos de datos/parámetros": https://keras.io/api/optimizers/adam/
* En metrics accuracy, ya que de igual forma queremos saber si el modelo acerto a su prediccion o no, y el procentaje de predicciones correctas que hay: https://keras.io/api/metrics/accuracy_metrics/#accuracy-class


5- Testeo del modelo base

6- Creación y entrenamiento del modelo mejorado con las siguientes caractaristicas:

### Modelo mejorado

Para la mejora del modelo, se cambio la primer capa de un simple Conv2D a un modelo preentrenado VGG16, eliminando sus capas densas finales, se eligio este modelo previo, debido a su facilidad de uso, y gran efectividad. 

Para saber mas al respecto, se puede ver en: https://medium.com/@mygreatlearning/everything-you-need-to-know-about-vgg16-7315defb5918#:~:text=VGG16%20is%20object%20detection%20and,to%20use%20with%20transfer%20learning.

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

8- Comparación de los modelos

|Metricas  |Modelo base  |Modelo mejorado  |
|:--------:|:-----------:|:---------------:|
|loss train|0.4438       |0.1198           |
|acc train |0.8014       |0.9519           |
|loss test |0.4008       |0.0561           |
|acc test  |0.8250       |0.9800           |

Los modelos ya entrenados se enceuntran en:
* Modelo base: https://drive.google.com/file/d/1-1wzrfwG1w6FnsCR7QJKfuiAuul5jIfk/view?usp=sharing
* Modelo final: https://drive.google.com/file/d/19lIzKs4XEpnYLHMeHuwY1NsVi8LRIBuH/view?usp=sharing

Drive con imagenes, codigo y modelos:

* https://drive.google.com/drive/folders/19LfJWtZVNsLxX24-CBW7eWa_c18EMYc4?usp=sharing

Nota1: Algunos comentarios sobre como correr el codigo se encuentran en el doc Untilted0.ipynb
