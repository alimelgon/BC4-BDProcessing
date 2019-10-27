# BC4-BDProcessing
Scala/Spark/Kafka/Cloacalandia

Este repositorio cuenta con:
-mensajes.txt: fichero fuente de datos, que sigue el siguiente esquema (ID_Mensaje, Contenido_Mensaje, ID_Usuario). Nota: el fichero de texto no puede contener tildes para no perjudicar el conteo de palabras.
-Paquete Cloacalandia con dos Scala Object:
    -Cloacalandia_Streaming: para leer de kafka los datos que injecta el fichero "mensajes.txt". Saca por pantalla un DF con el conteo de palabras en 24 ventanas de 60 minutos cada una. No he sabido extraer ese DF para limpiarlo y quedarme con la palabra más numerosa por cada hora y cruzarlo con la Lista Negra.
    -Cloacalandia_ListaNegra: como no he podido extraer los datos del DF a un fichero, he simulado lo que deberia haber quedado: hago una lectura del fichero de origen "mensajes.txt" y hago una limpieza de esos datos con map y filter. Me quedo con las 10 palabras más repetidas y las imprimo por pantalla. Por último, cruzo la palabra más repetida con la lista "listaNegra" y si está contenida en esta lista, imprimo n mensaje de aviso por pantalla.
