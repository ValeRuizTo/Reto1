# Reto1
## Miembros: Samuel Rodriguez, Valentina Ruiz Torres y Darek Aljuri Martínez

## 1. Introducción
### 1.1 Resumen General
El presente documento describe el desarrollo de un sistema IoT para la detección temprana de incendios en los cerros orientales de Bogotá. Se detallan las etapas de diseño, desarrollo, implementación y validación de la solución, asegurando que el prototipo sea funcional y eficiente en la identificación de riesgos de incendio mediante sensores de temperatura, gas y llama. La solución utiliza un microcontrolador Arduino Uno junto con una pantalla LCD y un buzzer para proporcionar alertas locales.

### 1.2 Motivación
Los incendios forestales en los cerros orientales de Bogotá representan una amenaza ambiental y social. La detección oportuna de incendios puede mitigar los daños y facilitar una respuesta rápida por parte de las autoridades. El uso de tecnología IoT permite un monitoreo en tiempo real, mejorando la capacidad de reacción ante incendios y minimizando sus consecuencias.

### 1.3 Justificación
El desarrollo de este sistema responde a la necesidad de implementar una solución de bajo costo y fácil implementación que pueda alertar sobre incendios forestales en zonas vulnerables. Mediante sensores especializados, el sistema puede detectar la presencia de gases y variaciones anómalas de temperatura, proporcionando información en tiempo real para la toma de decisiones.

### 1.4 Estructura de la Documentación
Este documento se divide en las siguientes secciones:

- Introducción: Contextualización del problema, motivación y justificación del sistema.
- Solución Propuesta: Descripción detallada del diseño, restricciones y arquitectura del sistema.
- Configuración Experimental y Resultados: Evaluación del sistema en diferentes condiciones.
- Autoevaluación del Protocolo de Pruebas: Validación de la efectividad del prototipo.
- Conclusiones y Trabajo Futuro: Reflexión sobre los logros alcanzados y posibles mejoras.
- Anexos: Código fuente, esquemáticos y material complementario.

## 2. Solución Propuesta
### 2.1 Restricciones de Diseño

***Técnicas***
- Uso de un Arduino Uno como microcontrolador central.
- Sensores de temperatura, gas (MQ-2) y llama (KY-026).
- Pantalla LCD para visualización de datos en tiempo real.
- Buzzer para alertas sonoras en caso de detección de incendio.
  
***Económicas***
- Implementación con componentes de bajo costo y accesibles.
- Uso de software de arduino para minimizar costos de desarrollo.
  
***Espacio y Escalabilidad***
- Diseño compacto para facilitar su instalación en zonas estratégicas.
- Posibilidad de ampliar el sistema mediante comunicación con otros dispositivos IoT.
- Adaptabilidad para futuras mejoras con nuevos sensores o algoritmos de detección.
  
***Temporales***
- Desarrollo del prototipo en un plazo limitado, asegurando funcionalidad básica.
- Posibilidad de mejoras futuras en algoritmos y hardware para mayor precisión.

### 2.2 Arquitectura Propuesta

***Arquitectura IoT del Sistema***
La arquitectura IoT del sistema de detección de incendios en los cerros orientales de Bogotá se basa en una estructura distribuida compuesta por sensores, procesamiento local y comunicación de datos para la notificación de alertas. Se organiza en tres capas principales:

1. Capa de Percepción (Sensores y Adquisición de Datos)
Es la capa encargada de capturar la información del entorno mediante sensores físicos. Los dispositivos utilizados incluyen:

- Sensor de temperatura (): Mide la temperatura del aire en la zona monitoreada.
- Sensor de gas (): Detecta concentraciones de gases como CO y CO₂, indicativos de combustión.
- Sensor de llama (): Detecta la presencia de llamas en el área monitoreada.
Los sensores están conectados a un Arduino Uno, que procesa la información en tiempo real.

2. Capa de Procesamiento y Control
El Arduino Uno actúa como la unidad central de procesamiento (CPU), encargada de:

- Leer y analizar los datos recibidos de los sensores.
- Determinar si las condiciones indican un posible incendio.
- Activar mecanismos de alerta local (buzzer, LED y pantalla LCD).

3. Capa de Comunicación y Notificación
En la versión básica del prototipo, las alertas se generan localmente mediante:

- Pantalla LCD: Muestra valores en tiempo real y advertencias.
- LEDs indicadores: Señalización visual de estados normales y de alerta.
- Buzzer: Alarma sonora para advertir de situaciones críticas.
![.](imagenesWiki/arqui.jpg)



2.3 Desarrollo Teórico Modular
Criterios de Diseño
Fiabilidad: Uso de sensores calibrados para evitar falsas alarmas.
Bajo Consumo Energético: Optimización del código para minimizar consumo.
Interfaz Intuitiva: Uso de LCD y alertas sonoras para notificaciones claras.
Escalabilidad: Posibilidad de agregar conectividad remota en versiones futuras.
Diagramas UML de la Solución y Módulos de Software
Se incluyen los diagramas UML para representar la lógica del software desarrollado, incluyendo:

Diagrama de Clases: Estructura del código y relación entre módulos.


Diagrama de Secuencia: Flujo de datos entre sensores, Arduino y salidas.
                  
                  Usuario          SistemaIoT        SensorTemp      SensorGas       SensorLlama       LCD        Alarma
                    |                  |                  |               |                |            |           |
                    |----setup()-----> |                  |               |                |            |           |
                    |                  |----requestTemp()->|               |                |            |           |
                    |                  |<---(temp)---------|               |                |            |           |
                    |                  |----readGasLevel()->|--------------|                |            |           |
                    |                  |<---(gas)-----------|              |                |            |           |
                    |                  |----detectarFuego()->|-------------|                |            |           |
                    |                  |<---(fuego)----------|             |                |            |           |
                    |                  |----updateLCD()------------------------------------->|            |           |
                    |                  |----activarAlarma()------------------------------------------------>|
                    |                  |----desactivarAlarma()--------------------------------------------->|




Diagrama de Estados: Estados del sistema según las condiciones detectadas.
(Aquí se deben agregar los diagramas UML correspondientes.)

Esquemático de Hardware
El diseño del hardware incluye la interconexión entre los sensores, el Arduino Uno, la pantalla LCD, el buzzer y los LEDs.

(Aquí se debe incluir el esquemático del circuito.)

Estándares de Diseño Aplicados
Normas de seguridad electrónica para evitar riesgos eléctricos.
Buenas prácticas de programación en Arduino (uso eficiente de memoria y procesamiento).
Normas de comunicación de sensores para asegurar compatibilidad y precisión.


