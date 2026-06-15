**Diplomatura en Ciencia de Datos, Aprendizaje Automático y sus Aplicaciones**

**Introducción al Aprendizaje profundo**

*Edición 2023*

----
# Trabajo práctico entregable - Parte 2

## Redes recurrentes

----

## Consignas
Dado el dataset que busca [detectar si una oración es sarcástica o no](https://www.kaggle.com/datasets/saurabhbagchi/sarcasm-detection-through-nlp?select=Sarcasm_Headlines_Dataset.json). Se pide:

### Ejercicio 1 - Preprocesamiento de los Datos: [Notebook 1](./ejercicio_1_preproc.ipynb)

Pre-procesar los datos de texto teniendo en cuenta como baseline lo que se hizo en esta [notebook](https://colab.research.google.com/drive/1jRT2MBvOO36t3lBcV2roI1NVkzP7Cjyo?usp=sharing).
Para cargar los datos pueden guiarse de esta [notebook introductoria](https://colab.research.google.com/drive/1ZxvMQhja1fZIfbcF7u1G1LN3MfpWlBSs?usp=sharing). Tengan cuenta evaluar cuál 
es la longitud máxima de sus sentencias o qué les conviene agregar/sacar para procesar el dataset
de sarcasmo.

### Ejercicio 2 - Implementar modelo básico: [Notebook 2](./ejercicio_2_baseline.ipynb)

Implementar una red neuronal RNN simple con capas lstm (este será su baseline). Pueden guiarse de la [Notebook 8](https://colab.research.google.com/drive/1jRT2MBvOO36t3lBcV2roI1NVkzP7Cjyo?usp=sharing).

### Ejercicio 3 - Implementar modelo con ajuste de hiperparámetros e interpretar resultados: [Notebook 3](./ejercicio_3_finetuning.ipynb)

En una siguiente instancia realizar una búsqueda de hiperparámetros buscando mejorar el baseline.
Traten de centrarse en probar 2, como mucho 3, hiperparámetros y ver los cambios con base a esos
hiperparámetros porque las pruebas se hacen infinitas. La idea es que prueben:

* Diferentes tamaños de épocas.
* Tamaño de batch.
* Cantidad de capas lstm.
* Valor de dropout, etc. 

Mostrar e Interpretar los resultados.

### Opcional:

* Probar otros tipos de capas como GRU o RNN.
* Agregar embeddings preentrenados