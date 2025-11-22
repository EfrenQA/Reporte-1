# Reporte-1
En esta practica se documentara el uso de un sensor de temperatura y humedad DHT22.
## Descripción
A modo de introducción, se genera el código de un sensor ```DHT22``` y el control se logrará por medio de un ```ESP32``` por medio del similudor ![](https://wokwi.com/projects/new/esp32)
## Materiales
1. Simulador WOKWI, dentro del simulador:
- Cableado
- Tarjeta ```ESP32```
- Sensor ```DHT22```
- Libreria ```DHT sensor library for ESPx```
## Instrucciones
1. Abrir el simulador WOKWI en el navegador ![](https://wokwi.com/projects/new/esp32)

![](https://github.com/EfrenQA/Reporte-1/blob/main/wokwi.png?raw=true)

3. Elegir la tarjeta ```ESP32```

 ![](https://github.com/EfrenQA/Reporte-1/blob/main/ESP32.png?raw=true)

4. Selección del sketch

![](https://github.com/EfrenQA/Reporte-1/blob/main/ESP32-2.png?raw=true)

5. Al seleccionar el skecth se mostrara una interfas como se muestra en la imagen

![](https://github.com/EfrenQA/Reporte-1/blob/main/INTERFAS.png?raw=true)

6. Se hará la selección de la libreria para el sensor ```DHT22```, para esto se tiene que dirigir Library Manager

![](https://github.com/EfrenQA/Reporte-1/blob/main/AGREGAR%20LIBRERIA.png?raw=true)

7. Una ves en la pestaña de librerias, se tiene que clickear sobre el pictograma de "+", seguido de esto se abrira un cuadro de busqueda donde se buscara la libreria "DHT sensor library for ESPX"

![](https://github.com/EfrenQA/Reporte-1/blob/main/BUSQUEDA%20DE%20LIBRERIA%20.png?raw=true)

8. Para colocar el sensor en espacio de simulación se tiene que clickear en el pictograma de "+" que esta en el cuadro de simuación.

![](https://github.com/EfrenQA/Reporte-1/blob/main/AGREGAR%20COMPONENTES.png?raw=true)

9. Para la selección del sensor, podemos escribir su nombre en la barra de buscador o desplazarnos en las opciones.

![](https://github.com/EfrenQA/Reporte-1/blob/main/BUSCAR%20COMPONENTE.png?raw=true)

10. Una vez que se tengan ambos componentes seleccionados, se procede a la conección entre ambos de la siguiente forma:
"nota: para hacer conecciones solo se tiene que dar click en los pines y dirigir la linea al pin que se desde conectar"
- Primer pin del sensor se conecta al pin GND de la tarjeta.
- Segundo pin del sensor se conecta al pin 15 de la tarjeta.
- Cuarto pin del sensor se conecta al pin de 5V de la tarjeta.
![](https://github.com/EfrenQA/Reporte-1/blob/main/LAYOUT.png?raw=true)
10. En el lado de "SKETCH" se debe colocar el siguiente código:
```
#include "DHTesp.h"

const int DHT_PIN = 15;
DHTesp dhtSensor;


void setup() {

  Serial.begin(115200);
  dhtSensor.setup(DHT_PIN, DHTesp::DHT22);
}

void loop() {

  TempAndHumidity  data = dhtSensor.getTempAndHumidity();
  Serial.println("Temp: " + String(data.temperature, 1) + "°C");
  Serial.println("Humidity: " + String(data.humidity, 1) + "%");
  Serial.println("---");
  delay(1000);
}
```
11. como último paso se inicia el simulador con el botón de "play" y se podra visualizar las lecturas del sensor.
![](https://github.com/EfrenQA/Reporte-1/blob/main/SIMULACI%C3%93N.png?raw=true)
## Instrucciones de operación
1. Iniciar simulación con el botón de "PLAY"
2. Visualizar los datos
3. Descargar valores
## Resultados
Al finalizar cada paso se podrá obtener datos del simulador
![](https://github.com/EfrenQA/Reporte-1/blob/main/SIMULACI%C3%93N.png?raw=true)
## Créditos
Autor Ing. Efren David Quiroz Ayala 
