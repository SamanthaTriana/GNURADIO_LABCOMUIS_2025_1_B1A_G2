# PRÁCTICA 1C: Mediciones de potencia y frecuencia

---
Integrantes: 
- Didier Manuel Correa Gomez - 2212254
- Samantha Lucía Triana Toloza - 2212249

Escuela de Ingenierías Eléctrica, Electrónica y de Telecomunicaciones
Universidad Industrial de Santander

Fecha: 03 de marzo del 2025
---

### **Resumen**
La presente prática resalta la importancia de las mediciones de potencia y frecuencia para el análisis de señales, utilizando equipos como el osciloscopio, el analizador de espectros y la plataforma GNU Radio. Esta última permite diseñar flujogramas para procesar y analizar señales en tiempo real, facilitando su visualización en los dominios temporal y espectral. El osciloscopio mide parámetros como amplitud y frecuencia, mientras que el analizador de espectros identifica frecuencias dominantes y potencia. En el laboratorio, se configuran los equipos y se interpretan los resultados para evaluar el comportamiento de las señales. GNU Radio complementa estos análisis al permitir la adquisición y procesamiento flexible de datos. Finalmente se visualiza la relevancia de las herramientas de software y hardware, dado que proporcionan una metodología eficiente para la medición y análisis de señales en telecomunicaciones e ingeniería.


### **Introducción**
La medición de potencia y frecuencia es fundamental en el análisis de señales, permitiendo evaluar el comportamiento de sistemas de comunicación y radiofrecuencia. Para ello, se emplean equipos de laboratorio como el osciloscopio y el analizador de espectros, junto con herramientas de software como GNU Radio, que facilita el procesamiento y análisis digital de señales. A través de estas herramientas, es posible visualizar y medir distintos parámetros en los dominios del tiempo y la frecuencia, optimizando el diseño y desempeño de sistemas electrónicos y de telecomunicaciones.

### **Procedimiento**
    Se realizaron 4 actividades a lo largo de la práctica, en las cuáles se realizaron revisiones de especificaciones de los equipos, simulación de señales en GNU Radio, transmisión y Medición de Señales con el USRP 2920, para finalmente realizar un análisis y conclusiones a cerca de lo obtenido en el laboratorio; esto a partir de preguntas orientadoras asignadas en la guía.


## **Actividad 1: Revisión de Especificaciones de los Equipos**

1. **Revisar Manuales y Verificar Equipos**:
   - Revisar las especificaciones de los equipos de laboratorio (USRP 2920, Osciloscopio R&S RTB2004 y Analizador de Espectros R&S FPC1000).
   - Identificar las principales funciones y controles de los equipos.

2. **Seleccionar Especificaciones Relevantes**:
   - Seleccionar las **5 especificaciones** que consideren **más relevantes** de cada equipo. 

3. **Configuración de los Equipos**:
   - **USRP 2920**: Identificar el rango de frecuencia y ganancia configurable del radio. Para esto, conecte la alimentación y el cable de red al radio, y desde un terminal (Ctrl + Alt + T) ejecute el comando `uhd_usrp_probe`.
   - **Osciloscopio R&S RTB2004**: Identificar el ancho de banda máximo, resolución vertical y tipos de mediciones soportadas.
   - **Analizador de Espectros R&S FPC1000**: Identificar el rango de frecuencia, resolución y figura de ruido.

### **Preguntas Orientadoras**

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

1. **Iniciar GNU Radio**:
   - Ejecute GNU Radio Companion (GRC) (`gnuradio-companion`).
   - Cargue el flujograma [`simple_flowgraph.grc`](https://github.com/omreyes/LabComUIS/blob/develop/guides/practice1/simple_flowgraph.grc).
   - Identifique los bloques principales: `Signal Source`, `Throttle`, `QT GUI Time Sink` y `QT GUI Frequency Sink`.
   - Configure la frecuencia de muestreo (samp_rate) en 20 kHz.

2. **Ejecutar el Flujograma**:
   - Ejecute el flujograma y observe los diferentes controles (Source Controls, Channel Controls, USRP Controls), así como las señales generadas en las ventanas de tiempo (`Time Sink`) y frecuencia (`Frequency Sink`).
   - Identifique y relacione los bloques presentes en el flujograma con lo observado en la ventana de ejecución.
  
3. **Análisis de Señales** 
   - Analice y valide los resultados en el dominio del tiempo y de frecuencia si se modifica:
     - el tipo de dato de la fuente (compleja o flotante)
     - la forma de onda 
     - la frecuencia y fase de la señal
     - la amplitud de la señal generada.
   - Modifique el nivel de ruido del modelo de canal y analice el efecto en tiempo y frecuencia.

### **Preguntas Orientadoras**

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

1. **Configurar el USRP 2920**:
   - Configure el flujograma en GNU Radio para transmitir una señal a través del USRP. Habilite o deshabilite los bloques correspondientes (Channel Model, Throttle, UHD: USRP Sink, Virtual Sink). Para esto seleccione el bloque deseado y presionando `E` (enable) o `D` (disable), respectivamente.
   - Identifique el bloque de frecuencia de muestreo (samp_rate) y observe el efecto de cambiar su valor (e.g. 10 kHz).
   - Configure la frecuencia de muestreo (samp_rate) en 1 MHz.
   - Verifique el efecto de modificar la frecuencia y ganancia del USRP. 

2. **Medición con el Analizador de Espectros**:
   - Conecte la salida del USRP al analizador de espectros.
   - Mida el piso de ruido normalizado a la frecuencia de portadora que va a utilizar.
   - Compare el espectro de la señal observada en el analizador de espectros con la observada en la pantalla de simulación. Tenga en cuenta que el radio (USRP) equivale al diagrama de bloques mostrado en la figura.

<img src="qam_modulator.png" alt="QAM Modulator" width="400">
     
   - Analice y valide los resultados en el dominio de la frecuencia si se modifica:
     - el tipo de dato de la fuente (compleja o flotante)
     - la forma de onda 
     - la frecuencia y fase de la señal
     - la amplitud de la señal generada.
   - Mida potencia de la señal transmitida y ancho de banda de diferentes señales generadas.
   - Conecte una antena apropiada a la entrada del analizador de espectros y observe el espectro de una señal FM (las estaciones FM se sitúan entre los 88 MHz y 108 MHz). Mida su ancho de banda y relación señal a ruido. 
   - Determinar la máxima potencia de transmisión.
   - Evalúe la respuesta en frecuencia del canal midiendo los cambios de ganancia del sistema cuando varía la frecuencia de portadora.
   - Compare los resultados de transmitir usando un cable y usando antenas.

4. **Medición con el Osciloscopio**:
   - Analice y valide los resultados en el dominio del tiempo si se modifica:
     - el tipo de dato de la fuente (compleja o flotante)
     - la forma de onda 
     - la frecuencia y fase de la señal
     - la amplitud de la señal generada.
  - Contraste estos resultados con los obtenidos con el analizador de espectros.

5. **Cálculo de la Relación Señal a Ruido (SNR)**:
   - Usar las mediciones de potencia y piso de ruido para calcular la SNR de algunas de las señales generadas.
   - Anotar el valor de la SNR en dB.

### **Preguntas Orientadoras**

1. ¿Cómo se configura el USRP 2920 para transmitir una señal en una frecuencia específica?
    Para configurar el USRP 2920, primero se debe conectar a una fuente de alimentación de 6V a 3A. Luego, se conecta el cable Ethernet para establecer la comunicación entre GNU Radio y el USRP. Finalmente, se conecta el cable desde la terminal TX1 del USRP al analizador de espectro para visualizar la señal.

2. ¿Qué parámetros del flujograma afectan la potencia de la señal transmitida?
    el QT GUI Range te afecta porque permite variar la amplitud en tiempo real, lo que cambia la potencia de transmisión y cómo se visualiza la señal en el analizador de espectro. Si no quieres que influya, usa un valor fijo en su lugar

3. ¿Cómo se mide el ancho de banda de la señal transmitida en el analizador de espectros?
    Se utilizan dos markers para medir el ancho de banda, colocándolos a una diferencia de 20 dB en la respuesta de la señal. Esto permite determinar el ancho de banda a -20 dB respecto al nivel máximo.

4. ¿Cómo se calcula la relación señal a ruido (SNR) a partir de las mediciones de potencia y piso de ruido?
    Se utilizan markers en el analizador de espectro para medir la potencia de la señal y la del ruido. Con estos valores, el SNR se calcula como la diferencia entre la potencia de la señal y la del piso de ruido en dB

5. ¿Qué diferencias se observan en las mediciones de potencia cuando se varía la ganancia del USRP?
    No se logran ver ganancias significativas en las potencias de la señal por el radio y el cable.

6. ¿Es posible medir o estimar la potencia de la señal observada en el osciloscopio? ¿Por qué?

    Sí, es posible medir o estimar la potencia de la señal observada en el osciloscopio. Esto se debe a que el osciloscopio permite visualizar la amplitud de la señal en el dominio del tiempo, a partir de la cual se puede calcular la potencia.

## **Actividad 4: Análisis de Resultados y Conclusiones**

### **Para la Elaboración del Informe**
1. **Comparar Resultados**:
   - Compare los resultados obtenidos en las simulaciones y las transmisiones reales.
   - Discuta las diferencias entre las mediciones realizadas con el osciloscopio y el analizador de espectros.

2. **Reflexionar sobre la SNR**:
   - Analice la importancia de la relación señal a ruido (SNR) en las comunicaciones inalámbricas.
   - Discuta cómo el piso de ruido afecta la capacidad de detectar señales débiles.

3. **Conclusiones Finales**:
   - Escriba conclusiones basadas en los resultados obtenidos.
   - Reflexe sobre las limitaciones de los equipos y cómo se podrían mejorar las mediciones.


### **Preguntas Orientadoras**

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


### Referencias
- Se empleó el uso de ChatGPT para reformular secciones del texto, verificar gramática, sin embargo el contenido fue desarrollado íntegramente por los autores.
