# Convnet-MNIST-simple
Red neuronal

# 1. Descripción del dataset:
Fashion-MNIST es un conjunto de datos que consiste en imágenes en escala de grises de prendas de vestir pertenecientes a 10 categorías diferentes. Cada imagen tiene una resolución de 28x28 píxeles. El conjunto de datos se compone de 60,000 imágenes de entrenamiento y 10,000 imágenes de prueba. Está diseñado para reemplazar el conjunto de datos clásico MNIST para probar algoritmos de aprendizaje automático y visión por computadora.
Las categorías en Fashion-MNIST son:
0: Camiseta/top
1: Pantalón
2: Suéter
3: Vestido
4: Abrigo
5: Sandalia
6: Camisa
7: Zapatilla
8: Bolso
9: Bota

# 2. Problema a resolver:
El problema a resolver es la clasificación de prendas de vestir en una de las 10 categorías mencionadas anteriormente, basándose en las imágenes proporcionadas en el conjunto de datos.

# 3. Descripción del procedimiento y capas de la red neuronal:
- Carga de datos: El conjunto de datos Fashion-MNIST se carga utilizando la función fashion_mnist.load_data() proporcionada por Keras.
  
- Preprocesamiento de datos: Las imágenes se normalizan dividiendo los valores de píxeles por 255 para escalarlos en el rango [0, 1].
  
- Construcción de la red neuronal: Se construye una ConvNet simple utilizando capas de convolución, capas de agrupación (pooling), y capas totalmente conectadas.
La primera capa es una capa de convolución con 32 filtros de tamaño 3x3 y activación ReLU.
Se sigue con una capa de agrupación (max pooling) con tamaño de ventana 2x2.
Se añade otra capa de convolución con 64 filtros de tamaño 3x3 y activación ReLU, seguida de otra capa de agrupación.
Se añade una tercera capa de convolución similar.
Luego, se aplanan los mapas de características y se conectan a dos capas densas con activación ReLU.
La capa de salida tiene 10 neuronas con activación softmax para la clasificación de las 10 clases.

- Compilación del modelo: El modelo se compila con el optimizador Adam y la función de pérdida sparse_categorical_crossentropy.
  
- Entrenamiento del modelo: El modelo se entrena durante 5 épocas utilizando los datos de entrenamiento.
  
- Evaluación del modelo: Se evalúa la precisión del modelo en los conjuntos de datos de entrenamiento y prueba.
  
- Visualización de la precisión: Se traza la precisión de entrenamiento y validación a lo largo del tiempo (épocas).

# 4. Resultado:
El resultado muestra que el modelo alcanzó una precisión (accuracy) del 89.67% en el conjunto de datos de prueba. Esto significa que, de todas las imágenes de prendas de vestir en el conjunto de prueba, el modelo clasificó correctamente el 89.67% de ellas en la categoría correcta.

# 5. Matrices de confusión y su interpretación:
Una matriz de confusión es una tabla que se utiliza para describir el rendimiento de un modelo de clasificación en un conjunto de datos. En el contexto de este problema, las matrices de confusión muestran cuántas imágenes de cada clase se clasificaron correctamente y cuántas se clasificaron incorrectamente.
