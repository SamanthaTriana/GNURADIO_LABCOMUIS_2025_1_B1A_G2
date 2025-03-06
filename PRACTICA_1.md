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

**Palabras clave:** GNU radio, amplitud, analizador de espectros, potencia, frecuencia.

### Introducción
El análisis y procesamiento de señales es esencial en telecomunicaciones e ingeniería. En esta práctica, se introduce el uso de GNU Radio y equipos de laboratorio para desarrollar habilidades en la medición e interpretación de señales. A través de la implementación de flujogramas, el estudiante comprenderá la importancia de la frecuencia de muestreo y su impacto en señales senoidales y reales, como audios y voz pregrabada. Además, se explorará el uso del osciloscopio y el analizador de espectros para observar señales en los dominios del tiempo y la frecuencia. Finalmente, la integración del radio definido por software (SDR) permitirá ampliar el conocimiento sobre la generación y análisis de señales en entornos prácticos.

### Procedimiento
Cabe resaltar que la presente práctica se desarrolló en tres partes, teniendo como primera parte realizar mediciones de GNU radio para el procesamiento de señales, reconocimiento de equipos y mediciones de potencia y frecuencia.
De ésta manera en la primera parte, se exploró la herramienta GNU radio con una guía realizada en la plataforma, a partir de la cual se tomaron capturas de las señales generadas para analizar su comportamiento al interpolar, diezmar y aplicar el teorema de Nyquis. Luego en la segunda parte se realizó un análisis a cerca de la amplitud medida y generada del osciloscopio, junto con medidas de atenuación de un cable coaxial. Para finalmente realizar en la tercera parte mediciones de potencia y frecuencia.

Adicionalmente en la práctica 1C se realizaron 4 actividades a lo largo de la práctica, en las cuáles se realizaron revisiones de especificaciones de los equipos, simulación de señales en GNU Radio, transmisión y medición de señales con el USRP 2920. Cabe aclarar que cada sección contiene preguntas orientadoras que contribuyeron a mejorar el entendimiento de la práctica.

## **Actividad 1: Revisión de Especificaciones de los Equipos**

1. ¿Cuál es el rango de frecuencia del USRP 2920 y cómo se compara con el del analizador de espectros?

Se obtuvo un rango de frecuencia es 68.750 – 2200MHz y un rango de frecuencia del analizador de espectros: 5KHz -1GHz. Esto nos indica que el analizador de espectros posee un mayor rango de frecuencia, facilitando que genere y reciba señales en frecuencias más bajas y más altas que del USRP 2920. 

2. ¿Qué parámetros del USRP 2920 se deben configurar para transmitir una señal en una frecuencia específica?

Rango de frecuencias, rango de ganancias, rango de ancho de banda, tipo de conexión y uso de compensación de oscilador local.

3. ¿Cómo se configura el osciloscopio para medir la amplitud y la frecuencia de una señal?
   
    1.	Primeramente, se ubica el menú principal
    2.	Luego se da clic en la opción “medida”
    3.	Se selecciona una posición al azar
    4.	Dar clic en “tipo”, seguido de esto se debe desplegar una ventana emergente
    5.	Seleccionar la casilla donde dice “vertical” y seleccionamos donde dice “amplitud”
    6.	Para medir la amplitud, nos ubicamos en la casilla que aparece como “horizontal”

4. ¿Qué diferencia hay entre medir una señal en el dominio del tiempo (osciloscopio) y en el dominio de la frecuencia (analizador de espectros)?
   
Medir una señal en el dominio del tiempo con un osciloscopio permite ver como varia su amplitud respecto al tiempo. En cambio, en el dominio de la frecuencia, un analizador de espectros muestra la distribución de la energía en distintas frecuencias, permitiendo identificar componentes espectrales. El osciloscopio revela cuando ocurre un evento en la señal, mientras que el analizador de espectros muestra qué frecuencias la componen. Ambos instrumentos son complementarios y esenciales en telecomunicaciones y electrónica.

5. ¿Cómo se mide el piso de ruido en el analizador de espectros? ¿Cómo afecta la frecuencia central, SPAN y RBW la medida de piso de ruido? ¿Por qué?
   
Según el valor de RBW dado por nosotros en el analizador de espectros vamos a tener un valor de piso de ruido, observada en la pantalla del analizador en una medida de dB.
El piso de ruido en un analizador de espectro depende de la frecuencia central, SPAN y RBW. La frecuencia central no afecta directamente el piso de ruido, pero en frecuencias altas, el ruido del sistema puede aumentar. Un SPAN amplio suele requerir un RBW mayor, lo que eleva el piso de ruido porque se integra más ruido dentro del ancho de banda de resolución. El RBW es el factor más importante, un RBW mayor sube el piso de ruido, mientras que uno menor lo reduce, ya que se promedia el ruido en un ancho de banda más estrecho. 

### **Evidencia**
  - Lista con las 5 especificaciones más relevantes de cada equipo:

USRP 2920

•	Rango de frecuencia: 50 MHz a 2.2 GHz 
•	Ancho de banda instantáneo máximo:
      16-bit: 20 MHz
      8-bit: 40 MHz
•	Tasa máxima de muestreo I/Q:
      16-bit: 25 MS/s
      8-bit: 50 MS/s
•	Convertidores de señal:
      DAC: 2 canales, 400 MS/s, 16-bit.
      ADC: 2 canales, 100 MS/s, 14-bit.
•	Potencia de salida máxima:
      50 MHz a 1.2 GHz: 50 mW a 100 mW (17 dBm a 20 dBm).
      1.2 GHz a 2.2 GHz: 30 mW a 70 mW (15 dBm a 18 dBm)


Osciloscopio R&S RTB2004

•	Número de canales: 4 canales.
•	Frecuencia de muestreo máxima: Hasta 2.5 GS/s en tiempo real.
•	Ancho de banda: 200 MHz.
•	Resolución del ADC: 10 bits.
•	Frecuencia de muestreo máxima: 2.5 GS/s


Analizador de Espectros R&S FPC1000

•	Rango de frecuencia: 5 kHz hasta 1 GHz.
•	Ancho de banda de resolución (RBW): 1 Hz hasta 3 MHz.
•	Nivel de ruido de fase: < -100 dBc/Hz
•	DANL (Nivel de Ruido de Fondo de Referencia): -150 dBm
•	Pantalla táctil de alta resolución: 10.1 pulgadas con interfaz táctil intuitiva para facilitar la manipulación de señales.



## **Actividad 2: Simulación de Señales en GNU Radio**

1. ¿Cómo se puede explicar matemáticamente la diferencia entre una fuente de tipo flotante y una de tipo complejo?
   
Matemáticamente, una fuente flotante se representa con un número real. La diferencia clave es que la fuente flotante solo tiene una magnitud real, mientras que la fuente compleja permite representar tanto amplitud como fase, lo que es útil en análisis fesoria.

2. ¿Cómo afecta la forma de onda a la distribución de energía (potencia) en el dominio de la frecuencia?
   
En las diferentes formas de ondas podemos observar diferentes armónicos: Seno 2 armónicos, constante 1 armónico, etc.

3. ¿Qué sucede con la señal en el dominio del tiempo y la frecuencia si se modifican los diferentes parámetros de la fuente? ¿Lo observado corresponde a lo esperado teóricamente?

Cabe resaltar que, para las variaciones de amplitud, frecuencia en Hz, offset y fase en radianes se empleó la función seno.
De manera práctica se observa que al manipular la amplitud se me modificada la señal en el tiempo de manera significativa, pero en       frecuencia se mantienen sus armónicos.
Al manipular la frecuencia en Hz, se ve afectado el periodo en el tiempo y la frecuencia se mantiene mostrando sus dos armónicos.
La modifcación del offset, desplaza la señal en el tiempo en amplitud, por otro lado, en frecuencia aparece un nuevo armónico.
Para finalizar cuando se manipula la fase en radianes, a pesar de que se trabaja con una señal seno, se tiene en el tiempo una gráfica constante y en frecuencia permanece el armónico adicional y existente anteriormente en la señal cuando se le aplicaba el offset, es decir, la señal cuenta con 3 armónicos. Cabe resaltar que offset es 0, en este caso.

4. ¿Cómo se relaciona la amplitud de la señal con la potencia observada en el dominio de la frecuencia?
   
La amplitud de una señal está directamente relacionada con la potencia observada en el dominio de la frecuencia. En términos generales, la potencia de una señal es proporcional al cuadrado de su amplitud, lo que significa que, al aumentar la amplitud en el dominio del tiempo, se incrementa la energía distribuida en sus componentes frecuenciales.

5. ¿Qué diferencias se observan entre una señal senoidal y una señal cuadrada en el dominio de la frecuencia?
   
La señal senoidal contiene una frecuencia fundamental sin armónicos, lo que indica que su espectro de frecuencia es de una sola línea en la frecuencia fundamental. Por otro lado, la señal cuadrada es periódica y posee armónicos a lo largo de su espectro.



## **Actividad 3: Transmisión y Medición de Señales con el USRP 2920**

1. ¿Cómo se configura el USRP 2920 para transmitir una señal en una frecuencia específica?
   
Para configurar el USRP 2920, primero se debe conectar a una fuente de alimentación de 6V a 3A. Luego, se conecta el cable Ethernet para establecer la comunicación entre GNU Radio y el USRP. Finalmente, se conecta el cable desde la terminal TX1 del USRP al analizador de espectro para visualizar la señal.

2. ¿Qué parámetros del flujograma afectan la potencia de la señal transmitida?
   
El QT GUI Range te afecta porque permite variar la amplitud en tiempo real, lo que cambia la potencia de transmisión y cómo se visualiza la señal en el analizador de espectro. Si no quieres que influya, usa un valor fijo en su lugar

3. ¿Cómo se mide el ancho de banda de la señal transmitida en el analizador de espectros?
   
Se utilizan dos markers para medir el ancho de banda, colocándolos a una diferencia de 20 dB en la respuesta de la señal. Esto permite determinar el ancho de banda a -20 dB respecto al nivel máximo.

4. ¿Cómo se calcula la relación señal a ruido (SNR) a partir de las mediciones de potencia y piso de ruido?
   
Se utilizan markers en el analizador de espectro para medir la potencia de la señal y la del ruido. Con estos valores, el SNR se calcula como la diferencia entre la potencia de la señal y la del piso de ruido en dB

5. ¿Qué diferencias se observan en las mediciones de potencia cuando se varía la ganancia del USRP?
   
No se logran ver ganancias significativas en las potencias de la señal por el radio y el cable.

6. ¿Es posible medir o estimar la potencia de la señal observada en el osciloscopio? ¿Por qué?

Sí, es posible medir o estimar la potencia de la señal observada en el osciloscopio. Esto se debe a que el osciloscopio permite visualizar la amplitud de la señal en el dominio del tiempo, a partir de la cual se puede calcular la potencia.



## **Actividad 4: Análisis de Resultados y Conclusiones**

1. ¿Qué conclusiones se pueden obtener sobre la relación entre la potencia de la señal y la calidad de la comunicación?
   
La potencia es un factor crucial en la calidad de la comunicación, pero no es el único ni el más eficiente. Una comunicación eficaz se logra con un balance entre potencia, técnicas de modulación, reducción de ruido e interferencia, y optimización del ancho de banda.

2. ¿Cómo afecta el piso de ruido a la capacidad de detectar señales débiles?

El piso de ruido permite establecer el límite inferior de detección de señales. Esto con el fin de mejorar la capacidad de detectar señales débiles, es clave reducir el ruido, mejorar la sensibilidad del receptor y optimizar las técnicas de transmisión.

3. ¿Qué limitaciones tienen los equipos utilizados en términos de ancho de banda y precisión en las mediciones?

Las limitaciones en ancho de banda afectan la capacidad del equipo para captar señales de alta frecuencia, mientras que las restricciones en precisión pueden comprometer la exactitud de las mediciones. Para superar estas limitaciones, es clave seleccionar el equipo adecuado según la aplicación, optimización su configuración y realizar calibraciones periódicas.

4. ¿Cómo se pueden mejorar las mediciones de señal en un entorno con alto nivel de ruido?

Mejorar la medición de señales entornos ruidosos requiere una combinación de filtrado, técnica de promediado, apantallamiento, equipo adecuados y optimización del entorno. La elección de la estrategia dependerá del tipo de ruido presente las características de la señal de interés.

5. ¿Qué aplicaciones prácticas tienen las mediciones de potencia y ancho de banda en sistemas de comunicaciones reales?
   
Las mediciones de potencia y ancho de banda son clave para garantizar rendimiento, eficiencia y calidad en sistemas de comunicación. Se aplican en redes móviles, sistemas satelitales, radiocomunicaciones, pruebas de equipos, seguridad y eficiencia energética.

6. ¿Cómo se puede medir la respuesta en frecuencia de un canal alámbrico?
   
Para medir la respuesta en frecuencia de un canal alámbrico, los métodos más utilizados incluyen analizadores de red (VNA), osciloscopios con generadores de señal, análisis FFT y TDR. La elección del método depende del tipo de canal y la precisión requerida.

7. ¿Cómo se puede obtener un modelo sencillo de las pérdidas (_pathloss_) en un canal inalámbrico?

Para obtener un modelo sencillo de pathloss:
•	Usa el modelo de espacio libre si no hay obstáculos
•	Aplica el modelo con exponente de desvanecimiento para entornos generales
•	Usa Okumura-Hata para modelar redes móviles en ciudades.
Estas opciones se seleccionaron teniendo en cuenta las variaciones que se pueden presentar en el entorno y la precisión deseada.



### Conclusiones
1.	La Práctica 1A, GNU Radio para el procesamiento de señales, nos permitió explorar el manejo de GNU Radio. A través del desarrollo de un sistema básico, se experimentó con el ajuste de parámetros fundamentales, como la frecuencia de operación y la frecuencia de muestreo. Además, se generaron y analizaron diferentes tipos de señales en los dominios del tiempo y frecuencia, utilizando herramientas gráficas y analíticas integradas en GNU Radio. Esta práctica nos ayudó a comprender la estructura y funcionalidad de los bloques que componen un sistema de comunicaciones digital.
   
2.	La Práctica 1B, Reconociendo equipos, nos permitió comprender el manejo de GNU Radio y la integración de equipos de laboratorio, como el SDR y el osciloscopio. Se exploró la generación y medición de señales en el dominio del tiempo y la frecuencia, ajustando parámetros clave como la frecuencia de transmisión y la amplitud. A través del análisis de los datos obtenidos, se evidenció la influencia de factores como la atenuación en el medio de transmisión, la impedancia de los cables y conectores, y la respuesta del SDR a diferentes frecuencias, destacando la importancia de una correcta configuración y conexión de los equipos para obtener mediciones precisas.
   
3.	La Práctica 1C, Mediciones de potencia y frecuencia, nos permitió familiarizarnos con GNU Radio y la herramienta SDR, así como con equipos de medición como el USRP 2920, el osciloscopio R&S RTB2004 y el analizador de espectros R&S FPC1000. A través de diversas actividades, se exploraron aspectos clave como la medición de potencia, ancho de banda, relación señal a ruido (SNR) y piso de ruido, contrastando mediciones en el dominio del tiempo y la frecuencia. Además, se evidenció cómo factores como la frecuencia de muestreo, la ganancia y la interferencia afectan la calidad de la señal.



### Referencias
- Se empleó el uso de ChatGPT para reformular secciones del texto, verificar gramática, sin embargo el contenido fue desarrollado íntegramente por los autores.
- A. Proakis and M. Salehi, Fundamentals of Communication Systems, 2nd ed. Boston, MA, USA: Pearson, 2014, ch. 6.
