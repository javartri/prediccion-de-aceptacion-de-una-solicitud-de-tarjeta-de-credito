# prediccion de aceptacion de una solicitud de tarjeta de credito

Los datos utilizados provienen del repositorio de aprendizaje automático de UCI: http://archive.ics.uci.edu/ml/datasets/credit+approval

• Consta de 15 variables que representan varios atributos del cliente. Estas variables son anónimas para proteger la privacidad de los clientes. La decimosexta variable representa si los bancos aprueban o rechazan la solicitud para esa persona en forma de + o -

• Los datos también tienen algunos valores faltantes. Es posible que algunos modelos no funcionen con datos faltantes. Puede haber alguna información importante que pueda usarse para entrenar el modelo.

Datos imputados de la siguiente manera para mejorar la precisión del modelo:

• Tenemos algunos datos como '?', Los reemplazamos con NaN usando numpy

• Asignamos los datos numéricos que faltan con valores medios para esa variable.

• Asignamos los datos no numéricos faltantes con los valores más frecuentes para esa variable.

Preprocesamiento de datos:

• LabelEncoder normaliza los datos y también se puede usar para transformar datos no numéricos en etiquetas numéricas, si son comparables.

• La codificación de etiquetas es una tarea importante para este proyecto, ya que necesitamos encontrar la correlación entre las variables y luego ejecutar algoritmos de predicción en los datos.

• Verificamos la correlación y observamos que las características 4,3 y 9,10 están altamente correlacionadas, esto podría conducir a multicolinealidad

• También podemos observar que la característica 0,6,11 tiene muy poca correlación con la variable 15, que es nuestra variable dependiente. Entonces, decidimos eliminar las funciones 0,4,6,9,11

• A continuación, dividimos los datos en conjuntos de entrenamiento y prueba en una proporción de 70/30, lo que significa que el 70% de los datos se utilizarán para entrenar nuestro modelo y lo probaremos con el 30% restante.

• construimos una matriz de confusión para ver qué tan bien ha funcionado nuestro modelo. La matriz de confusión es un diseño de tabla específico que permite la visualización del rendimiento de un algoritmo. Proporciona información sobre las medidas de precisión en un modelo predictivo. Cada fila de la matriz representa las instancias en una clase predicha, mientras que cada columna representa las instancias en una clase real. Todas las predicciones correctas están en la diagonal de la tabla, es decir, verdaderos positivos y verdaderos negativos.

• Luego creamos el modelo KNN con K = 5 y verificamos la precisión

• Luego construimos nuestro segundo modelo usando Regresión logística y verificamos la precisión

• Observamos que la precisión ha mejorado significativamente

• Trazamos la curva ROC para ajustar nuestro modelo y aumentar la precisión.

• Cambiamos el valor umbral para la regresión logística a 0.4 (que es 0.5 por defecto). Esto significa que cualquier probabilidad por debajo de 0.4 se considerará 0 y cualquier cosa por encima de esto se considerará 1.

• Observamos un aumento significativo en la tasa de precisión y precisión después de cambiar el umbral.
