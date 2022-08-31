# flow6-NodeRed-ESP32CAM-MQTT
Este repositorio contiene los archivos para el ejercicio en cual se intercambiará información entre NodeRed y ESP32CAM con MQTT

## Introducción

Este Flow muestra el intercambio de información entre el ESP32CAM y NodeRed a través de MQTT. El objetivo es demostrar como mandar instrucciones al ESP32CAM

## Material Necesario

### Software
Para poder hacer funcionar este proyecto, es necesario contar con el siguiente software:
- [Ubuntu 20.04](https://releases.ubuntu.com/20.04/)
- [Arduino IDE](https://www.arduino.cc/en/software)
    - [Gestor de tarjetas ESP32](https://github.com/iotechbugs/esp32-arduino/blob/master/docs/arduino-ide/boards_manager.md)
    - [Configuración de la IDE de Arduino para trabajar con el ESP32CAM](https://github.com/iotechbugs/esp32-arduino)
    - [Biblioteca PubSubClient](https://github.com/knolleary/pubsubclient)
- [Mosquitto MQTT Broker](https://mosquitto.org/download/)
    - [Listener en puerto 1883 para 0.0.0.0 y conexiones no autentificadas activadas](https://mosquitto.org/man/mosquitto-conf-5.html)
- [NodeJS](https://nodejs.org/es/)
    - [NPM](https://www.npmjs.com/)
    - [NodeRed](https://nodered.org/docs/getting-started/local)
    - [Nodos Dashboard](https://flows.nodered.org/node/node-red-dashboard)
### Hardware

Para probar este ejercicio se necesitan los siguientes componentes electrónicos
- Micro controlador ESP32CAM
- Adaptador de niveles TTL FTDI32
- Cable USB-A a USB Mini
- Jumpers
- Protoboard
## Material de referencia

En los siguientes enlaces puedes encontrar cursos en la plataforma de edu.codigoiot.com que te permitirán realiar las configuraciones necesarias

- [Instalación de Virutal Box y Ubuntu 20.04](https://edu.codigoiot.com/course/view.php?id=812)
- [Configuración de Arduino IDE para ESP32CAM](https://edu.codigoiot.com/course/view.php?id=850)
- [Instalación de NodeRed](https://edu.codigoiot.com/course/view.php?id=817)
- [Introducción a NodeRed](https://edu.codigoiot.com/course/view.php?id=278)
- [Instalación de Mosquitto MQTT](https://edu.codigoiot.com/course/view.php?id=818)

## Instrucciones

### Requisitos previos

Para que este flow funcione, debes cumplir con los siguientes requisitos previos
1. Instalación de NodeJS. Se recomienda tener instalado NodeJS en alguna versión LTS. Al momento de creación de este documento, se usó la versión 16.17.0LTS. Esta instalación debe incluir las Build-Tools para hacer uso de NPM
2. Instalación de NodeRed. La instalación se realiza por NPM. Al momento de la creación de este contenido, se usó la versión 3.0.2
3. Instalar los nodos node-red-dashboard. Para ello, dirigete a la opcion "Manage Palet" de NodeRed y en la pestaña Install busca node-red-dashboard. Finalmente haz clic en instalar.
4. Instalación de Broker local Mosquitto MQTT.
5. Configurar el archivo mosquitto.conf para que el Broker Local acepte conexiones externas

### Instrucciones de preparación del entorno

Para poder configurar tu entorno y realizar este ejercicio, encesitas lo siguiente

1. Realiza el circuito. Las instrucciones se encuentran en el encabezado del código para el ESP32CAM. Deberás cambiar lo siguiente:
    - El tema de publicación y suscripción
    - Nombre de red y contraseña al que deseas conectarte
    - IP de tu broker local
    - Tiempo de espera entre envío de datos en milisegundos

2. Arrancar NodeRed con el comando `node-red`
    - Importar el flow del repositorio
    - Modifica los temas MQTT segun tus necesidades


### Instrucciones de operación

- Para observar el resutlado de este flow, abre un navegador y dirígete a [localhost:1880/ui](http://localhost:1880/ui) desde la computadora que ejecuta NodeRed
-  Energizar el ESP32CAM y asegurarse de que esta en rango de una conexión WiFi

### Notas

- Este Flow se suscribe al tema codigoIoT/flow6/mqtt
- El mensaje mqtt usado para probar este flow es `mosquitto_pub -h localhost -t codigoIoT/Mor/mqtt/flow4 -m '{"ID":"Hugo Vargas","temp":18,"hum":78}'`
- Este flow publica en el tema codigoIoT/flow6/mqttin

## Resultados

A continuación puedes ver los nodos del flow.
![](https://github.com/hugoescalpelo/flow6-NodeRed-ESP32CAM-MQTT/blob/main/Imagenes/nodos.png?raw=true)

A continuación puede ver el tablero resultante.

![](https://github.com/hugoescalpelo/flow6-NodeRed-ESP32CAM-MQTT/blob/main/Imagenes/Dashboard.png?raw=true)

Este flow enciende y apaga el led Flash del ESP32CAM cuando se activa el switch, puedes ver un video en la sección de evidencias.

## Evidencias

- [YouTube]()

# Créditos

Desarrollado por Hugo Escalpelo
- [hugoescalpelo.com](https://hugoescalpelo.com/)
- [Página en Facebook](https://www.facebook.com/Hugo-Escalpelo-Profesional-337708683840136)
- [GitHub](https://github.com/hugoescalpelo)