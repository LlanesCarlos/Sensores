# Sensores

El código es un programa para Arduino que utiliza varios sensores para medir y mostrar diferentes variables ambientales, como temperatura, humedad y concentración de CO2. A continuación, se explica paso a paso qué hace el código:

Inclusión de bibliotecas: El programa incluye varias bibliotecas necesarias para el uso de los diferentes sensores. Estas bibliotecas facilitan la comunicación con los sensores y permiten acceder a sus funciones.

Configuración de pines y sensores: Se definen algunas constantes y variables para configurar los pines a los que están conectados los sensores. Además, se selecciona el tipo de sensor DHT que se está utilizando (DHT11, DHT22 o DHT21).

Inicialización de los sensores DHT: Se inician los sensores DHT y se muestran detalles sobre los mismos a través del puerto serial.

Inicialización del sensor HP20x: Se inicia el sensor HP20x y se muestra un mensaje indicando si el sensor está disponible o no.

Inicialización del sensor T6615-50KF: Se inicia el sensor T6615-50KF utilizando una comunicación serial por software.

Función setup(): Esta función se ejecuta una sola vez al inicio del programa. Aquí se realiza la configuración inicial de los sensores y se muestran mensajes informativos a través del puerto serial.

Función loop(): Esta función se ejecuta en un ciclo continuo después de que se haya completado la función setup(). Aquí se toman las mediciones de temperatura, humedad, presión y altitud, y se muestra el valor de concentración de CO2 a través del puerto serial. Luego, se espera un corto tiempo antes de repetir el ciclo.

Explicación detallada de las secciones principales:

Sensor DHT (Líneas 19-68):

Se utilizan las bibliotecas necesarias para trabajar con los sensores DHT.
Se selecciona el tipo de sensor DHT utilizado (DHT11, DHT22 o DHT21) descomentando la línea correspondiente.
Se inicia el sensor DHT con el pin especificado en la constante DHTPIN.
Se imprimen detalles sobre el sensor DHT, como el tipo de sensor, versión del driver, ID único, valores máximos y mínimos, y resolución.
Sensor HP20x (Líneas 71-92):

Se utiliza la biblioteca HP20x_dev para trabajar con el sensor HP20x.
Se inicia el sensor HP20x y se verifica si está disponible.
Se realizan lecturas de temperatura, presión y altitud del sensor HP20x.
Los valores de temperatura, presión y altitud se filtran utilizando el filtro de Kalman antes de mostrarlos por el puerto serial.
Sensor T6615-50KF (Líneas 94-131):

Se utiliza la biblioteca SoftwareSerial para establecer una comunicación serial por software con el sensor T6615-50KF.
Se definen funciones para enviar una solicitud al sensor T6615-50KF y para obtener el valor de concentración de CO2 de la respuesta recibida.
Función loop() (Líneas 134-162):

En este bucle, se realizan las mediciones de temperatura y humedad utilizando el sensor DHT y se muestran por el puerto serial.
Luego, se toman las mediciones de temperatura, presión y altitud utilizando el sensor HP20x y se filtran antes de mostrarlos por el puerto serial.
A continuación, se toma la medición de concentración de CO2 utilizando el sensor T6615-50KF y se muestra por el puerto serial.
Después de completar el ciclo, se espera un tiempo antes de repetir las mediciones.
