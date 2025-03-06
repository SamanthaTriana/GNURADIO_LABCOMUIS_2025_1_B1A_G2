# PRÁCTICA 1: MANEJO DE HERRAMIENTAS DE SOFTWARE Y HARDWARE PARA EL PROCESAMIENTO DE SEÑALES

---
Integrantes: 
- Didier Manuel Correa Gomez - 2212254
- Samantha Lucía Triana Toloza - 2212249

Escuela de Ingenierías Eléctrica, Electrónica y de Telecomunicaciones
Universidad Industrial de Santander

Fecha: 04 de marzo del 2025
---

## Declaración de Originalidad y Responsabilidad
Los autores de este informe certifican que el contenido aquí presentado es original y ha sido elaborado de manera independiente. Se han utilizado fuentes externas únicamente como referencia y han sido debidamente citadas.

Asimismo, los autores asumen plena responsabilidad por la información contenida en este documento. 

Se empleó el uso de IA para mejorar la redacción y sinónimos de secciones del informe, a pesar de ésto el contenido técnico fue desarrollado íntegramente por los autores.

---
## Contenido

### Resumen
La presente práctica se enfoca en reconocer y aprender el manejo de la plataforma GNU Radio y los equipos de laboratorio, desarrollando habilidades para implementar flujogramas y realizar mediciones de señales. Se abordan conceptos fundamentales como la frecuencia de muestreo, iniciando con señales senoidales hasta llegar a señales reales.
Además, se integra el uso del osciloscopio y el analizador de espectros para interpretar señales en los dominios del tiempo y la frecuencia. También se explora la generación y análisis de señales mediante un radio definido por software (SDR), permitiendo una comprensión más amplia de las mediciones en telecomunicaciones.

### Introducción
El análisis y procesamiento de señales es esencial en telecomunicaciones e ingeniería. En esta práctica, se introduce el uso de GNU Radio y equipos de laboratorio para desarrollar habilidades en la medición e interpretación de señales. A través de la implementación de flujogramas, el estudiante comprenderá la importancia de la frecuencia de muestreo y su impacto en señales senoidales y reales, como audios y voz pregrabada. Además, se explorará el uso del osciloscopio y el analizador de espectros para observar señales en los dominios del tiempo y la frecuencia. Finalmente, la integración del radio definido por software (SDR) permitirá ampliar el conocimiento sobre la generación y análisis de señales en entornos prácticos.

### Procedimiento
Cabe resaltar que la presente práctica se desarrolló en tres partes, teniendo como primera parte realizar mediciones de GNU radio para el procesamiento de señales, reconocimiento de equipos y mediciones de potencia y frecuencia.
De ésta manera en la primera parte, se exploró la herramienta GNU radio con una guía realizada en la plataforma, a partir de la cual se tomaron capturas de las señales generadas para analizar su comportamiento al interpolar, diezmar y aplicar el teorema de Nyquis. Luego en la segunda parte se realizó un análisis a cerca de la amplitud medida y generada del osciloscopio, junto con medidas de atenuación de un cable coaxial. Para finalmente realizar en la tercera parte mediciones de potencia y frecuencia.


### Conclusiones
1.	La Práctica 1A, GNU Radio para el procesamiento de señales, nos permitió explorar el manejo de GNU Radio. A través del desarrollo de un sistema básico, se experimentó con el ajuste de parámetros fundamentales, como la frecuencia de operación y la frecuencia de muestreo. Además, se generaron y analizaron diferentes tipos de señales en los dominios del tiempo y frecuencia, utilizando herramientas gráficas y analíticas integradas en GNU Radio. Esta práctica nos ayudó a comprender la estructura y funcionalidad de los bloques que componen un sistema de comunicaciones digital.
   
2.	La Práctica 1B, Reconociendo equipos, nos permitió comprender el manejo de GNU Radio y la integración de equipos de laboratorio, como el SDR y el osciloscopio. Se exploró la generación y medición de señales en el dominio del tiempo y la frecuencia, ajustando parámetros clave como la frecuencia de transmisión y la amplitud. A través del análisis de los datos obtenidos, se evidenció la influencia de factores como la atenuación en el medio de transmisión, la impedancia de los cables y conectores, y la respuesta del SDR a diferentes frecuencias, destacando la importancia de una correcta configuración y conexión de los equipos para obtener mediciones precisas.
   
3.	La Práctica 1C, Mediciones de potencia y frecuencia, nos permitió familiarizarnos con GNU Radio y la herramienta SDR, así como con equipos de medición como el USRP 2920, el osciloscopio R&S RTB2004 y el analizador de espectros R&S FPC1000. A través de diversas actividades, se exploraron aspectos clave como la medición de potencia, ancho de banda, relación señal a ruido (SNR) y piso de ruido, contrastando mediciones en el dominio del tiempo y la frecuencia. Además, se evidenció cómo factores como la frecuencia de muestreo, la ganancia y la interferencia afectan la calidad de la señal.



### Referencias
- Se empleó el uso de ChatGPT para reformular secciones del texto, verificar gramática, sin embargo el contenido fue desarrollado íntegramente por los autores.
- A. Proakis and M. Salehi, Fundamentals of Communication Systems, 2nd ed. Boston, MA, USA: Pearson, 2014, ch. 6.
