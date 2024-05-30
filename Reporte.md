Juan David Bahamon  
Samuel Hernández  
David Peñaranda  

## 1. Introducción  
La clasificación de objetos en imágenes es un desafío clave en el campo de la visión por computadora con aplicaciones en diversas áreas, como reconocimiento de objetos, sistemas de seguridad y diagnóstico médico. En este contexto, la agrupación de objetos en clases similares es un paso fundamental para desarrollar sistemas de clasificación robustos y precisos. Este informe presenta el proceso utilizado para agrupar imágenes de perros, gatos y gallinas en clases similares utilizando técnicas de aprendizaje no supervisado.  

El objetivo principal de este proyecto es desarrollar un sistema capaz de reconocer y clasificar automáticamente diferentes tipos de objetos en imágenes. Para lograr este objetivo, se exploraron y aplicaron técnicas de preprocesamiento de imágenes, extracción de características y algoritmos de agrupación no supervisada.  

## 2. Comprensión del Problema  
El conjunto de datos utilizado en este proyecto consta de imágenes de tres clases diferentes de objetos: perros, gatos y gallinas. Cada clase contiene un conjunto significativo de imágenes capturadas con una cámara web. El objetivo es agrupar estas imágenes en clases distintas, sin la necesidad de etiquetas previas, mediante técnicas de agrupación no supervisada. Esto implica encontrar patrones y similitudes intrínsecas en los datos que permitan agrupar los objetos de manera significativa y representativa.  

Para ello se deben seleccionar cuidadosamente las técnicas de preprocesamiento de datos, extracción de características y algoritmos de agrupación para garantizar que se capturen las características distintivas de los objetos y se generen agrupaciones significativas y precisas.  

## 3. Preprocesamiento de Datos  
En el preprocesamiento de datos se implementaron una serie de técnicas de preprocesamiento de imágenes para garantizar que los datos estén limpios, uniformes y preparados para el análisis posterior:  

**Eliminación de Ruido:**  
Se aplicó el filtro Gaussiano para eliminar el ruido presente en las imágenes. Esto ayudó a suavizar las imágenes y a mejorar la calidad de los datos para el análisis subsiguiente.  

**Normalización del Tamaño:**  
Todas las imágenes se redimensionan a un tamaño uniforme utilizando la técnica de redimensionamiento. Esto aseguró que todas las imágenes tuvieran las mismas dimensiones, lo que facilitó el procesamiento y la comparación entre ellas.  

**Ajuste de Contraste:**  
Se utilizó la ecualización del histograma para ajustar el contraste de las imágenes. Esto ayudó a mejorar la visibilidad de los detalles en las imágenes y a resaltar las características relevantes para la agrupación de objetos.  

## 4. Preparación de los Datos  
La preparación de los datos se centró en la extracción de características relevantes de las imágenes preprocesadas para representar adecuadamente los objetos y facilitar la agrupación:  

**Extracción de Características:**  
Se utilizó el método de Histograma de Gradientes Orientados (HOG) para extraer características distintivas de cada imagen. El HOG es una técnica ampliamente utilizada en visión por computadora para describir la forma y la textura de los objetos en una imagen. Esta captura la distribución de los gradientes de intensidad en regiones de la imagen, proporcionando una representación efectiva de los objetos.  

**Selección de Características:**  
Las características extraídas mediante HOG fueron seleccionadas para capturar las características relevantes de los objetos en las imágenes y minimizar la dimensionalidad de los datos.  

## 5. Modelado  
El modelado se centró en la aplicación de algoritmos de aprendizaje no supervisado para agrupar los objetos en clases similares:  

**Selección de Algoritmos:**  
Se seleccionó el algoritmo de K-means como el método principal para la agrupación de objetos. Este asigna puntos de datos a clusters basándose en la similitud de sus características.  

**Reducción de Dimensionalidad:**  
Antes de aplicar K-means, se realizó una reducción de dimensionalidad utilizando el análisis de componentes principales (PCA). Permitiendo reducir la dimensionalidad de los datos y conservando la mayor cantidad posible de información. La cantidad de componentes principales se seleccionó utilizando la varianza explicada acumulada para garantizar una representación efectiva de los datos con una dimensionalidad reducida.  

**Entrenamiento del Modelo:**  
Una vez que se redujo la dimensionalidad de los datos, se aplicó el algoritmo de K-means a los datos preparados para agrupar los objetos en clases.  

## 6. Evaluación
En la evaluación del proceso de agrupación de objetos mediante aprendizaje no supervisado, se obtuvo una precisión general del 98.55%. El informe de clasificación reveló que las clases de objetos se clasificaron con alta precisión, con valores de precisión, recall y f1-score cercanos a 1 para cada clase. Específicamente, la clase 0 (perros) tuvo una precisión, recall y f1-score del 98%, mientras que las clases 1 (gatos) y 2 (gallinas) tuvieron valores similares, con una precisión y f1-score del 99% y un recall del 98%. Además, la matriz de confusión mostró que la mayoría de las clasificaciones fueron correctas, con un bajo número de falsos positivos y falsos negativos en general. Estos resultados indican que el modelo de agrupación no supervisada logró una alta precisión en la clasificación de los objetos en las imágenes, validando la efectividad del proceso de agrupación implementado.

### Demo

A continuación se adjunta una demostración del funcionamiento del prototipo. Debido a que se eligieron como categorías a tres especies de animales, se optó por emplear una cámara virtual para obtener muestras más rápidamente. La cámara virtual es provista por un programa como OBS y se presenta al computador como si fuera una cámara real (periférico del PC). La diferencia esencial es que esta puede ser controlada a gusto y simular así el comportamiento de una cámara física. En este caso particular se usó como fuente una pestaña de windows correspondiente a un reproductor multimedia. Así, el contenido reproducido en este será recibido por opencv como si fuera contenido grabado directamente por una cámara. Para emplear la cámara normal y tomar muestras libremente se debe cambiar el source de 1 a 0 en el código del prototipo.

Siguiendo este método se preparó un conjunto de videos exponiendo las tres clases a segmentar. Los videos elegidos fueron tomados de Pexels y están libres de derechos para el propósito empleado, además no fueron capturados en condiciones especiales o ambientes controlados. Así, se puede tener una idea del desempeño en las condiciones reales, con fondos, iluminaciones y poses diferentes, además de la distorsión natural que genera el movimiento en los videos (varía de video a video según cómo se capture).  

Finalmente, se observa tres ventanas. De izquierda a derecha están:
- La fuente original (esta es la es la que tiene el resultado del clasificador, en texto azul arriba a la izquierda).
- La fuente tras la mayoría de filtros preparatorios (está escalada porque la imagen original tiene un tamaño mucho menor).
- Las características extraídas fotograma a fotograma (también escaladas para facilitar su visaulización).

[Demo IA Lab 3](https://youtu.be/S6qUu1eacEw)


## 7. Conclusiones
El proyecto de agrupación de objetos mediante aprendizaje no supervisado logra resultados prometedores en la clasificación de imágenes de perros, gatos y gallinas. Con una precisión general del 98.55%, el modelo demostró una capacidad significativa para reconocer y agrupar objetos en clases similares. Los resultados del informe de clasificación revelaron una alta precisión, recall y f1-score para cada clase de objeto, indicando una clasificación precisa y consistente. Además, la matriz de confusión mostró un bajo número de falsos positivos y falsos negativos, lo que respalda la efectividad del modelo en la clasificación de objetos.

Estos resultados sugieren que las técnicas de preprocesamiento de datos, extracción de características y agrupación no supervisada implementadas fueron adecuadas y efectivas para el problema específico de clasificar objetos en imágenes. Sin embargo, también se identificaron áreas de mejora potencial, como la optimización de parámetros y la exploración de otras técnicas de agrupación no supervisada para mejorar aún más la precisión y robustez del modelo.


## Bibliografía:
Alessio Corrado. (2022). "Animals10". Recuperado de [https://www.kaggle.com/datasets/alessiocorrado99/animals10](https://www.kaggle.com/datasets/alessiocorrado99/animals10)
