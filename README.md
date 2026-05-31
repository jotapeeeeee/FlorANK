# FlorANK
Mi proyecto de Inteligencia artificial que busca solucionar un problema de mi novia. Ella no sabe mucho de flores y siempre que ve una se pregunta que flor es, este modelo busca satisfacer su curiosidad y aunque es complicado contemplar todas las flores que existen, con unas cuantas se puede empezar.

----

# Primera entrega
Para esta etapa del proyecto he de obtener un set de datos, haber separado los datos en prueba y en entrenamiento, debí haber aplicado las técnicas de escalamiento y hacer el preprocesado pertinente.

## Obtención del set de datos
Acudí a la página de kaggle.com e hice una búsqueda por datasets de clasificación de flores, en mi búsqueda encontré el dataset de [Marquis03](https://www.kaggle.com/datasets/marquis03/flower-classification). Este set ofrece 13 mil registros de imágenes de tamaño 256x256 en RGB, además de estar etiquetados.

## Separación de datos de prueba y de entrenamiento
Marquis03 ya había separado las imagenes en train y val. Lo que hice yo fue utilizar val como mis datos de prueba ya que se encuentran aisladas en carpetas y subcarpetas distintas, aún así creé una subdivisión para la etapa de validación real en los datos de train, esto me permitirá verificar que el modelo no aprenda del ruido, sino de las características de cada flor.
Las carpetas se encuentran en mi [Drive](https://drive.google.com/drive/folders/14JBFmcF31-db9eyofANAiShgmEpXoXDn?usp=drive_link).

## Técnicas de escalamiento
La técnica de escalamiento que utilicé es la única que conozco ahora que es simplemente convertir el intervalo de 0 -> 255 que tienen las imagenes a uno de 0 -> 1, esto facilitará el entrenamiento por el uso de números menores en los cálculos.

## Preprocesamiento de datos
De las misma manera que el escalamiento, solo se aplicó el método que ví en clase, al reducir los canales de la imagen es que se simplifica el entrenamiento del modelo puesto que solo se basa en la forma de la imagen y no tiene un enfoque en los colores (que para las próximas entregas deberé utilizar el color puesto que para la identificación de flores es crucial el color de los pétalos, tallos, etc).

-----Data Augmentation TODO-----

# Segunda entrega
Para la segunda entrega Seleccionar un modelo respaldado por un artículo del estado del arte, Implementar el modelo usando un framework seleccionado, Seleccionar métricas adecuadas respaldadas por un artículo del estado del arte, Reportar resultados obtenidos e interpretarlos. 

## Seleccionar un modelo
Inicié con la búsqueda de un artículo en Scopus, utilicé las palabras clave: "Flower", "Classification" y "CNN" para agilizar la búsqueda, y tras unos minutos de búsqueda me encontre el paper: [Comparative analysis of CNN-based approaches for flower classification](https://www.sciencedirect.com/science/article/pii/S2772375526004338?fr=RR-2&rr=a04786110b9e219c), este paper me pareció muy interesante puesto que se implementaron y compararon 5 modelos distintos para así determinar cual es el mejor modelo para determinar la etapa de floración y la especie de una flor, el paper solo utiliza dos especies, rosas y girasoles, pero identifica 4 etapas de floración. Este paper concluye que un VGG16 es el modelo adecuado para la problemática.

## Implementación del modelo
Tengo entendido que esta segunda entrega debía ser un modelo no tan funcional para que en la siguiente entrega, el refinamiento, se pueda obtener un modelo capaz de hacer predicciones correctas con mayor constancia, evidentemente, si implemento el VGG16, es muy probable que la mejora que se presente en ese momento sea nula, pero al basarme en las guías como "Cats&Dogs" y "Callbacks for saving models" que me compartió el profesor, generé un modelo mediocre, que tiene un accuracy del 38%. El paper había determinado que el accuracy de su modelo VGG16 era de 0.9995 en train y de 1 en validación, cifras muy impactantes.

## Seleccionar métricas adecuadas
El mismo artículo utilizó cuatro métricas, Accuracy, Precision, Recall y F1 Score, esto para evaluar cada uno de sus modelos y así determinar cual satisfacia la necesidad de una manera más integra. El estudio utilizó la misma metodología de validación y test para identificar la posibilidad de overfit dentro de los modelos.

## Reportar resultados 
Para el reporte de resultados, utilicé lo que aprendí en clase, una matriz de confusión, que aunque se ve un poco saturado por la distribución (son 14 clases), se puede utilizar para observar el desempeño del modelo. El modelo inicial sobresale en la detección de tulipanes, y presenta buenos resultados con girasoles, iris, dientes de leon y corepsis. Aunque sí confunde flores que tienen algunos rasgos parecidos, justamente confunde algunos coreopsis con dientes de leon, puesto que ambos comparten el color y la forma, pero si mis steps fueran más grandes, considero que podría determinar que el coreopsis tiene pétalos más largos.
También utilicé sklearn para crear un reporte de clasificación, en el que calcula algunas métricas como precision, recall y f1 para medir estos valores por clase.


