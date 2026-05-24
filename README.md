# FlorANK
Mi proyecto de Inteligencia artificial que busca solucionar un problema de mi novia. Ella no sabe mucho de flores y siempre que ve una se pregunta que flor es, este modelo busca satisfacer su curiosidad y aunque es complicado contemplar todas las flores que existen, con unas cuantas se puede empezar.

----

# Primera entrega
Para esta etapa del proyecto he de obtener un set de datos, haber separado los datos en prueba y en entrenamiento, debí haber aplicado las técnicas de escalamiento y hacer el preprocesado pertinente.

## Obtención del set de datos
Acudí a la página de kaggle.com e hice una búsqueda por datasets de clasificación de flores, en mi búsqueda encontré el dataset de [Marquis03](https://www.kaggle.com/datasets/marquis03/flower-classification). Este set ofrece 13 mil registros de imágenes de tamaño 256x256 en RGB, además de estar etiquetados.

## Separación de datos de prueba y de entrenamiento
Marquis03 ya había separado las imagenes en train y val. Lo que hice yo fue utilizar val como mis datos de prueba ya que se encuentran aisladas en carpetas y subcarpetas distintas, aún así creé una subdivisión para la etapa de validación real en los datos de train, esto me permitirá verificar que el modelo no aprenda del ruido, sino de las características de cada flor.

## Técnicas de escalamiento
La técnica de escalamiento que utilicé es la única que conozco ahora que es simplemente convertir el intervalo de 0 -> 255 que tienen las imagenes a uno de 0 -> 1, esto facilitará el entrenamiento por el uso de números menores en estos valores

## Preprocesamiento de datos

