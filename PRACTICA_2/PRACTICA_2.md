# PRACTICA 2: Simulación y Análisis de los Fenómenos de Canal en GNU Radio: Visualización en Osciloscopio, Analizador de Espectros y su Impacto en la Conversión de Frecuencia

---
Integrantes: 
- Didier Manuel Correa Gomez - 2212254
- Samantha Lucía Triana Toloza - 2212249

Escuela de Ingenierías Eléctrica, Electrónica y de Telecomunicaciones
Universidad Industrial de Santander

Fecha: 18 de marzo del 2025
---

## Declaración de Originalidad y Responsabilidad
Los autores de este informe certifican que el contenido aquí presentado es original y ha sido elaborado de manera independiente. Se han utilizado fuentes externas únicamente como referencia y han sido debidamente citadas.

Asimismo, los autores asumen plena responsabilidad por la información contenida en este documento. 

Se empleó el uso de IA para mejorar la redacción y sinónimos de secciones del informe, a pesar de ésto el contenido técnico fue desarrollado íntegramente por los autores.

---
## Contenido

### Resumen
La presente prática se enfoca en llevar a cabo la simulación de fenómenos de canal utilizando GNU Radio, con el objetivo de analizar los efectos que estos tienen en la transmission de señales. Así mismo, se estudian diferentes tipos de distorsiones y degradaciones que puede sufrir una señal durante su propagación, como atenuación, desvanecimiento, retardo y dispersion en el canal. Estos fenómenos se observan y analizan mediante herramientas de visualización como el osciloscopio y el analizador de espectros, lo que permite analizar el comportamiento en el tiempo y en frecuencia de las señal afectada.
Además, se evalúa el impacto de los fenómenos de canal en la conversion de frecuencia, destacando cómo las imperfecciones del canal pueden influir en el proceso de modulación y demodulación, así como en la integridad de la señal recibida. La práctica, proporciona una comprensión integral de los efectos del canal en sistemas de comunicación y la importancia de considerar estos fenómenos en el diseño y análisis de dichos sistemas.

**Palabras clave:** GNU Radio, analizador de espectos, atenuación, desvanecmiento, retardo, modulación, demodulación, radiofrecuencia

### Introducción
En los sistemas de comunicación inalámbricos, la señal transmitida se ve afectada por una variedad de fenómenos que ocurren durante su propagación a través del canal. Estos fenómenos, conocidos como fenómenos de canal, incluyen atenuación, desvanecimiento, retardo y dispersión, los cuales pueden degradar significativamente la calidad y la integridad de la señal recibida. De manera que le estudio y la comprensión de estos efectos son fundamentales para el diseño eficiente de sistemas de comunicación robustos.
Por esta razón la práctica emplea GNU Radio como una herramienta de simulación para modelar y analizar el comportamiento de una señal afectada por diferentes condiciones de canal. La observación de las señales se realiza a través de un osciloscopio y un analizador de espectros, permitiendo estudiar tanto su representación temporal como espectral. Así mismo, se examina el impacto que los fenómenos de canal tienen en la conversión de frecuencia, lo cual es un proceso clave en la modulación y demodulación de señales dentro de los sistemas de radiofrecuencia.
La finalidad de la práctica es proporcionar un entendimiento integral de cómo los fenómenos de canal influyen en el desempeño de los sistemas de comunicación y resaltar la importancia de considerar estos efectos al momento de diseñar y analizar dichos sistemas.

## Materiales y Equipos

- **USRP 2920:** Radio definido por software.
- **Osciloscopio R&S RTB2004:** Para visualización de señales en el dominio del tiempo y la frecuencia.
- **Analizador de Espectros R&S FPC1000:** Para mediciones en el dominio de la frecuencia.
- **Computador con GNU Radio:** Para simulación y generación de señales usando el USRP 2920.
- **Cables y conectores:** Para interconexión de equipos.
  
  
### Procedimiento

La presente práctica estaba compuesta de 4 actividades, en las cuáles se realizaron revisiones de especificaciones de los equipos, simulación de canal en GNU Radio, fenómenos de canal en el osciloscopio, fenómenos de canal en el analizador de espectros y efectos de los fenómenos de canal en la conversión de frecuencia. Cabe aclarar que cada sección contiene preguntas orientadoras que contribuyeron a mejorar el entendimiento de la práctica.

- Actividad 1: Simulación de canal en GNU Radio, donde nos familiarizamos con la configuración del entorno de GNU Radio para transmitir señales moduladas y estudiar su comportamiento bajo distintas condiciones de canal. Se ajustaron parámetros como la frecuencia de muestreo y la ganancia de transmisión para evaluar su efecto en la relación señal-ruido (SNR).
- Actividad 2: Fenómenos de canal en el osciloscopio, se analizaron señales en el dominio del tiempo en el osciloscopio para estudiar el comportamiento de la señal al variar la frecuencia de portadora entre 50 MHz y 500 MHz, evaluando los efectos del ruido y la relación señal-ruido en comparación con las simulaciones. Se observaron los fenómenos de desviación de frecuencia, la influencia de la distancia y el medio de transmisión en la amplitud de la señal, utilizando cables coaxiales de diferentes longitudes y antenas.
- Actividad 3: Fenómenos de canal en el analizador de espectros, se configuró y utilizó el analizador de espectros para examinar la respuesta en frecuencia de las señales generadas por el USRP 2920, evaluando el impacto del ruido, la relación señal-ruido y la desviación de frecuencia. Se compararon los resultados con las simulaciones y se evidenciaron los efectos de la distancia y el medio de transmisión sobre la señal medida, utilizando cables coaxiales de distintas longitudes y antenas. Se analizaron estrategias para mitigar la degradación de la señal y mejorar su calidad en el dominio espectral. Finalmente, se identificó el modelo de canal más adecuado para describir las mediciones obtenidas, permitiendo una mejor comprensión del comportamiento de las señales en distintos entornos de transmisión.
- Actividad 4: Efectos de los fenómenos en canal de conversión de frecuencia, se analizaron los efectos del canal en la señal recibida,   evidenciando fenómenos como atenuación, ruido y desviación de frecuencia. Se comprobó que la distancia, el medio de transmisión y las interferencias afectan significativamente la calidad de la señal, modificando su amplitud y respuesta en frecuencia.

  

## **Actividad 1: Actividades de simulación de canal en GNU Radio**


1.	¿Cuál es el efecto de filtrar las frecuencias altas de una señal periódica?
Filtrar las frecuencias altas de una señal periódica permite eliminar las componentes de alta frecuencia, lo que suaviza la señal reduciendo cambios bruscos, disminuyendo el ruido. De manera que, al eliminar interferencias de alta frecuencia, se limita el ancho de banda utilizado en la transmisión.

2.	¿Qué sucede al filtrar muy cerca de la frecuencia fundamental de la señal?

El filtrado cerca de la frecuencia fundamental de la señal puede causar una atenuación significativa de su contenido esencial, reduciendo su amplitud y distorsionándola su forma original.

3.	¿Cuál es el efecto de filtrar las frecuencias bajas de una señal periódica?

Filtrar las frecuencias bajas de una señal periódica, elimina variaciones lentas y la su componente en DC, permitiendo que permanezcan oscilaciones rápidas.

4.	¿Qué ocurre al eliminar los primeros armónicos de la señal?

Eliminar los primeros armónicos de una señal reduce sus componentes de baja frecuencia y suaviza la forma, de manera que se prevalecen en la señal las frecuencias altas.

5.	¿Qué efecto tiene la desviación de frecuencia en la señal recibida? ¿Qué efecto produce el filtro cuando la señal recibida se ve afectada por desviación de frecuencia?

La desviación de frecuencia sucede cuando la frecuencia de la señal recibida no coincide exactamente con la frecuencia esperada en el receptor. Esto puede deberse a factores como inestabilidad del oscilador, efecto Doppler, errores de sintonización o dispersión en el canal de transmisión. Adicionalmente, en la práctica se visualizó que su efecto es generar más armónicos a medida que se aumenta la frecuencia, caso contrario de cuando se proporciona un filtro a la señal recibida, se suprimen los armónicos.

6.	¿Cómo cuantificar la degradación de la señal al aumentar los niveles de ruido?

La degradación de la señal debido al aumento del ruido puede cuantificarse utilizando varias métricas, en nuestro caso se realize teniendo en cuenta la relación de potencia de la señal y la potencia del ruido, empleada para determinar SNR de la señal. Ahora bien, desde el punto de vista interpretativo, un menor SNR nos indica mayor degradación de la señal.

7.	¿Cómo se puede mejorar la relación señal a ruido en una señal?

Se puede mejorar aumentando la potencia de la señal, específicamente incrementando la amplitud o potencia de la señal transmitida para que supere el nivel de ruido.

8.	¿Cómo podría cuantificar la calidad de la señal recibida? Considere el caso se señales analógicas y digitales

En el caso de las señales analógicas por medio de la relación Señal-Ruido (SNR), mide la potencia que tiene la señal comparada con el ruido y valores que permiten mejorar la calidad de la señal recibida; la relación Señal-Ruido y Distorsión (SINAD), permite considerar la distorsión además del ruido o la relación Señal a Interferencia y Ruido (SINR), que cumple la función mencionada anteriormente a cerca de la SNR, adicionando que considera las interferencias externas. 

Para las señales digitales su calidad se mide evaluando la precisión en la recepción mediante bits, por medio de la relación BER, que involucra el número de bits erróneos con el número total de bits transmitidos, indicando que entre menor sea BER, mejor será la calidad de la señal; la relación energía por bit a densidad de ruido (Eb/N0), la cual indica la calidad en términos de energía por bit en presencia del ruido; y MER que evalúa la precisión en la modulación de señales digitales. [1]


## **Actividad 2: Fenómenos de canal en el osciloscopio**


1.	¿Cuál es el efecto del ruido sobre la amplitud de las señales medidas en el osciloscopio? ¿Conservan las mismas relaciones que se evidencian en la simulación?

El efecto de ruido proporciona en frecuencia mayores armónicos y un aumento en la ganancia relativa. Además de aumentar el piso de ruido.

2.	¿La relación señal a ruido creada intencionalmente en el computador se amplifica o se reduce en la señal observada en el osciloscopio?

La señal a ruido amplifica la potencia de la señal en una escala de 2500Hz, lo que nos indica que mientras aumente el ruido, aumenta la potencia.

3.	Demuestre ¿Cómo se puede mejorar la relación señal a ruido en una señal?

Disminuyendo el ancho de banda, de manera que se realizó un ajuste del ancho de banda en el USRP 2920, para luego usar el medidor de espectros y observar la reducción del ruido fuera de la banda útil.

4.	¿Cómo se evidencia el fenómeno de desviación de frecuencia en el osciloscopio? evidencie al menos con dos formas de onda

Teniendo en cuenta que se modularon las señales seno y cuadrada, por medio de la modulación de la señal de offset. Se genera un fenómeno en dónde la señal portadora varía en función del offset aplicado. Este comportamiento se puede evidenciar en el osciloscopio observando cambios en la periodicidad y la forma de onda de la señal


5.	Determine la afectación de un medio de transmisión coaxial (use los cables largos) sobre una señal periódica operando a las capacidades máximas de muestreo del USRP. 


NOTA: La frecuencia de transmisión no debe superar los 500 MHz para ser observada en el osciloscopio. Para el experimento realizado se consideraron las relaciones de muestreo correspondientes como atenuación, ruido…


6.	Usando cables coaxiales de diferentes longitudes ¿Cómo afecta la distancia entre el transmisor y el receptor a la amplitud de la señal medida? 

Con cables coaxiales largos, la señal sufre mayor atenuación, reduciendo su amplitud debido a las pérdidas por absorción y dispersión en el medio. Además, puede haber un ligero retardo en la propagación de la señal. En contraste, con cables coaxiales cortos, la atenuación es menor, conservando mejor la amplitud y minimizando el retardo.

7.	Usando antenas ¿Cómo afecta la distancia entre el transmisor y el receptor a la amplitud de la señal medida? es posible compensar el fenómeno

Cuando se emplea un sistema de transmisión inalámbrico con antenas, la distancia entre transmisor y receptor afecta directamente la amplitud de la señal debido a la pérdida de propagación en el espacio libre y otros factores como interferencia. En el caso particular de la práctica cuando se tiene una pequeña distancia se amplifica la señal y cuando se tiene una larga distancia la amplitud de la señal amplifica poco. Cabe resaltar que en caso de tener una perturbación en la señal se puede evidenciar que la señal absorbe energía.


8.	¿Qué modelo de canal básico describe mejor las mediciones obtenidas en la práctica?

El modelo de pérdida en Espacio Libre (Friis)

En dónde el modelo permite describir la propagación de ondas electromagnéticas en un ambiente ideal sin obstáculos, basada en la ecuación de Friss que involucra la potencia recibida, potencia transmitida, ganancias de las antenas transmisora y receptora, longitud de onda y la distancia entre transmisor y receptor. Sin embargo, este modelo de canal básico no es adecuado para emplearlo en entorno urbanos o cerrados, reflexiones, difracciones o dispersiones. [1]



## **Actividad 3: Fenómenos de canal en el analizador de espectro**


1.	¿Cuál es el efecto del ruido sobre la respuesta en frecuencia de las señales medidas en el analizador de espectro? ¿Conservan las mismas relaciones que se evidencian en la simulación?
El ruido afecta la respuesta en frecuencia de las señales medidas en el analizador de espectro al introducir interferencias que pueden manifestarse como impulsos o variaciones a lo largo del espectro. Sin embargo, al aplicar la función Max Hold, es posible visualizar una relación similar a la observada en la simulación, ya que esta función retiene los valores máximos detectados en cada punto de frecuencia a lo largo del tiempo. De este modo, el comportamiento de los armónicos se mantiene, permitiendo comparar la señal real con la simulada, aunque con la influencia adicional del ruido. [3]

2.	¿La relación señal a ruido creada intencionalmente desde el computador se amplifica o se reduce en la señal observada en el analizador de espectro?

En la señal observada en el analizador de espectro, se mantiene similar a la generada en el computador, no ha cambiado considerablemente, indicando una transmisión y medición adecuadas.

3.	Adjunte la evidencia de la medición de la relación señal a ruido de dos formas de onda distinta
La evidencia se encuentra en la figura 3.3 que se encuentra en la carpeta de la práctica 2.

4.	¿Cómo se evidencia el fenómeno de desviación de frecuencia en el analizador de espectro? Evidenciar al menos con dos formas de onda.
La desviación de frecuencia en el analizador de espectro se evidencia por el aumento del número de armónicos, visibles como picos adicionales, donde la señal ocupa un mayor ancho de banda en lugar de un solo pico definido, lo cual sucedió con las dos forma analizadas.

5.	Determine la afectación de un medio de transmisión coaxial (usar cables largos) sobre una señal periódica operando a las capacidades máximas de muestreo del USRP.
NOTA: La frecuencia de transmisión no debe superar los 1000 MHz para ser observada en el analizador. Para el experimento, se considera la atenuación, dispersion y demás para evidenciar las diversas degradaciones que pueden llegar afectar a la señal estudiada directa o indirectamente.
Así mismo, afecta la señal periódica al atenuarla en el espectro, genera una señal más definida, pero con una pérdida de potencia progresiva a medida que aumenta la longitud del cable.

6.	Usando cables coaxiales de diferentes longitudes, ¿cómo afecta la distancia entre el transmisor y el receptor a la amplitud de la señal medida?
Con cables largos, la señal sufre mayor atenuación, reduciendo su amplitud y generando una variación muy pequeña en la frecuencia central, además de un ligero retardo en la transmisión. Caso contrario con cables cortos, en donde la atenuación es menor, manteniendo una mejor amplitud y la fidelidad de la señal sin afectar significativamente su frecuencia ni introducir retardos perceptibles

7.	Usando antenas, ¿cómo afecta la distancia entre el transmisor y el receptor a la amplitud de la señal medida? ¿Es posible compensar el fenómeno?
Cuando la distancia entre el transmisor y el receptor es corta, la señal se amplifica debido a una menor dispersión y atenuación. En distancias largas, la amplitud de la señal disminuye, ya que la propagación en el espacio libre y las pérdidas afectan su intensidad. Además, si hay una perturbación en el medio, como una mano cerca de la antena, parte de la energía se absorbe, afectando la señal. Este fenómeno puede compensarse ajustando la potencia de transmisión, usando antenas direccionales o amplificadores de señal.



## **Actividad 4: Efectos de los fenómenos de canal en la conversión de frecuencia**


1.	¿Cómo se evidencian los diferentes fenómenos de canal en la señal recibida?

Los fenómenos de canal se evidencian en la señal recibida como atenuación, reduciendo su amplitud por pérdidas en el medio; desvanecimiento, con fluctuaciones en la potencia debido a interferencias, ruido, afectando la claridad con componentes no deseados.

2.	¿Cómo se pueden mitigar los efectos del canal en la señal recibida?
Se pueden mitigar usando filtros pasa banda o pasa bajos para reducir ruido, amplificadores para contrarrestar la atenuación. Aunque actualmente existen sistemas modernos como WIFI o 5G, permiten ajustar dinámicamente la transmisión para optimizar el rendimiento en distintos entornos.



### Conclusiones

La práctica 2 permitió un análisis detallado de la transmisión inalámbrica. A través de las diferentes actividades, se evidenció la importancia de la configuración de los parámetros de transmisión, como la frecuencia de portadora, la ganancia y el ancho de banda, para garantizar una correcta recepción de la señal y minimizar la degradación causada por el canal.
El estudio de los fenómenos de canal mediante herramientas como el osciloscopio y el analizador de espectros permitió comprender cómo la distancia, el medio de transmisión y la interferencia afectan la calidad de la señal.



### Referencias

[1] A. Proakis and M. Salehi, Fundamentals of Communication Systems, 2nd ed. Boston, MA, USA: Pearson, 2014, ch. 6.

[2] Se empleó el uso de ChatGPT para reformular secciones del texto, verificar gramática, sin embargo el contenido fue desarrollado íntegramente por los autores.

[3] O. Reyes, Sistemas de Comunicaciones, Universidad Industrial de Santander, diapositivas de clase, 2025.
