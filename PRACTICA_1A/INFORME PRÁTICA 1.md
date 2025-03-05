#PRÁCTICA 1A: GNU radio para el procesamiento de señales

---
Integrantes: 
- Didier Manuel Correa Gomez - 2212254
- Samantha Lucía Triana Toloza - 2212249

Escuela de Ingenierías Eléctrica, Electrónica y de Telecomunicaciones
Universidad Industrial de Santander

Fecha: 17 de febrero del 2025
---

### Resumen
En esta práctica de laboratorio, se exploró el uso de GNU Radio como herramienta para el procesamiento de señales digitales. Se implementaron diversos bloques para la generación, muestreo, filtrado y visualización de señales, evaluando el impacto de la frecuencia de muestreo en la calidad de la señal procesada.
Además, se confirmó la importancia del teorema de Nyquist, pues una frecuencia de muestreo inadecuada que genera aliasing, afectando la reconstrucción de la señal original. También se comprobó que la interpolación y la decimación son técnicas clave para modificar la tasa de muestreo sin distorsionar la señal, siempre que se utilicen filtros adecuados. Finalmente, se destacó la versatilidad de GNU Radio para diseñar y simular sistemas de comunicación en tiempo real, facilitando el análisis sin necesidad de hardware costoso. Esta práctica permitió afianzar conocimientos sobre muestreo y procesamiento digital de señales en un entorno experimental.

### Introducción
El procesamiento de señales es una disciplina clave en ingeniería, donde la teoría de muestreo juega un papel esencial para convertir señales analógicas en digitales sin pérdida de información. La frecuencia de muestreo es crucial para evitar el aliasing, un fenómeno que distorsiona la señal cuando no se cumple el criterio de Nyquist. Herramientas como GNU Radio facilitan la experimentación en laboratorios de comunicaciones, permitiendo el análisis y diseño de sistemas sin necesidad de hardware especializado.
Además, técnicas como la interpolación y la decimación permiten ajustar la tasa de muestreo según las necesidades del procesamiento, optimizando el almacenamiento y la transmisión de señales. Sin embargo, una frecuencia de muestreo inadecuada puede causar distorsiones y pérdida de información, afectando la calidad del análisis y la interpretación de los datos. Este documento explora estos conceptos fundamentales y sus aplicaciones en el procesamiento digital de señales.

### Procedimiento
•	Se abrió el entorno de GNU Radio y se guardó el proyecto con extensión. grc, diferenciándolo del archivo .py generado automáticamente. 
•	Se añadieron los bloques Signal Source, Throttle, QT GUI Frequency Sink y QT GUI Time Sink para generar, visualizar y controlar señales. 
•	Se conectaron los bloques asegurando su correcta comunicación, verificando que los textos cambiaran de rojo a negro. 
•	Se usaron bloques Variable y QT GUI Range para ajustar frecuencia, amplitud y forma de onda. 
•	Se asignaron las variables creadas a las propiedades del bloque Signal Source para modificar su comportamiento.
•	Se añadió el bloque QT GUI Chooser para cambiar entre distintos tipos de onda de forma interactiva. 
•	Se ejecutó el diagrama de flujo, observando las señales en los dominios de tiempo y frecuencia al modificar parámetros. 
•	Durante el experimento, se tomaron capturas de las señales generadas para analizar su comportamiento al interpolar, diezmar y aplicar el teorema de Nyquis


### Conclusiones
En la primera práctica, titulada "Introducción al Laboratorio de Comunicaciones 1", se exploró el manejo de GNU Radio, una herramienta de simulación ampliamente utilizada en sistemas de comunicaciones. El objetivo principal de esta práctica fue familiarizarse con los conceptos básicos y la funcionalidad de los bloques que componen un sistema de comunicaciones digital, así como desarrollar habilidades prácticas en su implementación y ajuste.
Durante el desarrollo de la actividad, se construyó un sistema básico que permitió experimentar con el ajuste de parámetros fundamentales, como la frecuencia de operación y la frecuencia de muestreo de las señales. Además, se generaron diferentes tipos de señales, las cuales fueron analizadas tanto en el dominio del tiempo como en el dominio de la frecuencia, utilizando herramientas gráficas y analíticas integradas en GNU Radio.

### Referencias
- Se empleó el uso de ChatGPT para reformular secciones del texto, verificar gramática, sin embargo el contenido fue desarrollado íntegramente por los autores.
