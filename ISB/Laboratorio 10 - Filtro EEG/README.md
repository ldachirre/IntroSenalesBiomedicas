# LABORATORIO 10: Filtrado de EEG y obtención de sus características
# **Tabla de contenidos**

1. [Introducción](#id1)
2. [Objetivos](#id2)
3. [Metodología](#id3)
4. [Procesamiento y obtención de características de EEG](#id4)
5. [Conclusiones](#id5)
6. [Referencias](#id6)
   
## **Introducción** <a name="id1"></a>

Como se ha discutido anteriormente, el EEG es un procedimiento valioso para registrar la actividad eléctrica en el cerebro. Esto debido a que nos permite ver dicha actividad en forma de ondas a diferentes frecuencias, proporcionando una visión detallada de la actividad cerebral en distintos estados. Durante el análisis de los datos de EEG, se examinaron varias bandas de frecuencia que reflejan patrones específicos de actividad neuronal. [1]

A continuación se presenta una figura resumen con las diferentes señales obtenidas y su representación en la actividad cerebral. Para mayor información revisar el entregable pasado sobre señales EEG [aquí](https://github.com/ldachirre/IntroSenalesBiomedicas/tree/8d0f69448327d5be9a3340be16b55933ab11a1d4/ISB/Laboratorio%206%20-%20EEG).

![Captura de pantalla 2023-10-01 200816](https://github.com/ldachirre/IntroSenalesBiomedicas/assets/67986101/3491545d-f923-4ba3-9c86-8a0a17b9562d) 
> Figura 1. EEG bandas de frecuencia, ocurrencia y tareas para activar la potencia de banda

La extracción de características es un proceso por el cual a una señal le son extraídas información relevante (características) las cuales son más sencillas de interpretar que la señal original. Dicha información extraída refleja la fisiología y anatomía de la actividad ocurrida en el cerebro donde se puede observar el comportamiento que responde a cierta actividad y/o estímulo. Este proceso requiere un gran número de dataset donde se utilizan algoritmos para su extracción y análisis, por ejemplo Hilbert-Huang Transform (HHT), Principal Component Analysis (PCA), Independent Component Analysis (ICA), etc. [2]

En este entregable se analizarán las señales obtenidas previamente las cuales se les serán extraídas principalmente mediante:



## **Objetivos** <a name="id2"></a>
1. **Obtener características estadísticas de la señal:** Incluye la extracción de características como la amplitud de la señal, el valor promedio (media), la frecuencia y el valor Root Mean Square (RMS) de la señal EEG.

2. **Realizar el análisis de las características y compararlo con valores de la literatura:** Evaluación y comparación de las características extraídas con valores de referencia disponibles en la literatura. Esto ayuda a entender cómo se comporta la señal en relación con los datos previamente documentados.

3. **Verificar el comportamiento de la señal EEG:** Comportamiento general de la señal EEG para identificar patrones, tendencias o anomalías que puedan ser relevantes para tu análisis o aplicación específica.

## **Metodología** <a name="id3"></a>

El procesamiento de la señal EEG involucra una serie de pasos esenciales para obtener información clara y precisa de la señal. Estos pasos son los siguientes:

1. **Leer el DataSet:** En esta etapa, se accede a los datos del electrocardiograma para su posterior análisis.

2. **Analizar el EEG en frecuencia:** Se examina la señal en el dominio de la frecuencia para identificar componentes relevantes y características.

3. **Filtrar la señal con un filtro pasa banda:** Aplicar un filtro pasa banda ayuda a aislar las frecuencias de interés en la señal EEG.

4. **Detección de ERP:** Se detectan potenciales relacionados con eventos (ERP), los cuales pueden desencadenarse por estímulos auditivos, visuales o somatosensoriales. Un ejemplo es el P300 , que es una desviación positiva unos 300 ms después de un evento impar. La sincronización del EEG con el momento preciso del inicio de los estímulos es importante debido a la aparición de potenciales evocados entre 100 y 900 ms después del inicio de los estímulos.

5. **Detección de la banda Alfa:** Se extraen las oscilaciones de la banda alfa oscilan en frecuencias de 8-12 Hz, las cuales se originan en el lóbulo occipital. Las ondas alfa están asociadas a un proceso específico y están presentes principalmente cuando los ojos están cerrados y bloqueadas principalmente cuando los ojos están abiertos.

 
Para extraer las ondas alfa de las señales EEG, se utilizó el método de Welch. Este método divide la señal EEG en ventanas de tiempo y calcula la transformada de Fourier de cada ventana. La transformada de Fourier de una señal es una representación de la señal en el dominio de la frecuencia. En este caso, se utilizó una ventana de tiempo de 4 segundos. Esto dio como resultado una resolución de frecuencia de 0.25 Hz.

Una vez que se calcularon las transformadas de Fourier, se seleccionaron las frecuencias entre 8 Hz y 12 Hz. Estas frecuencias corresponden a la banda alfa.

Los resultados de la extracción de ondas alfa se muestran en los cuatro subplots de la figura. Cada subplot muestra el espectro de frecuencia de las ondas alfa para un escenario diferente: en estado de reposo, parpadeando, preguntas difíciles y preguntas fáciles.


## **Procesamiento y obtención de características de EEG** <a name="id4"></a>

### Código en Google Colab
El tratamiento de la señal EEG fue realizado en Google Colab. En el siguiente enlace, podrá visualizar los resultados y el código utilizado.

`<link>` : https://colab.research.google.com/drive/1vgRHCh9aj3bNEJZHtLRCnnZxudpAYNSe?usp=sharing

### 1. Leer el DataSet
Las señales EEG a utilizar en este entregable son en los 4 escenarios obtenidos en el entregable 6:
En reposo, Parpadeando, Resolviendo preguntas díficiles y Resolviendo preguntas fáciles.

Se plotea las señales, luego de haber realizo la conversión a uV.

![image](https://github.com/ldachirre/IntroSenalesBiomedicas/assets/67986101/9e792e1f-8c75-49a3-8006-301ff7d95363)
> Fig 2. Señales EEG en uV

### 2. Señal EEG en el Dominio de la Frecuencia
Se procede a graficar la señal EEG en el Dominio de la Frecuencia. Plotear la señal de EEG en el dominio de la frecuencia FFT nos permite visualizar la distribución de la energía de la señal en diferentes frecuencias. Esto es útil para identificar diferentes patrones de actividad cerebral, que pueden estar asociados a diferentes estados mentales o procesos cognitivos. Por ejemplo, las ondas alfa, que tienen frecuencias de 8 a 12 Hz, están asociadas a un estado de relajación y atención relajada. Las ondas beta, que tienen frecuencias de 13 a 30 Hz, están asociadas a un estado de alerta y atención concentrada. Las ondas gamma, que tienen frecuencias de 30 a 100 Hz, están asociadas a procesos cognitivos complejos, como el aprendizaje y la memoria.

Además, plotear la señal de EEG en el dominio de la frecuencia FFT nos permite identificar la presencia de ruido. El ruido puede ser causado por una variedad de factores, como el movimiento del paciente, la interferencia electromagnética o la mala calidad del equipo de EEG. Presentamos las ffts de la señal a continuación 
![image](https://github.com/ldachirre/IntroSenalesBiomedicas/assets/67986101/eb552874-dd0e-43bc-b039-244708c3bd7e)
> Fig 3. Señales EEG en el Dominio de la Frecuencia

### 3. Señal EEG Filtrada
Se procede a filtrar la señal EEG. Las señales de EEG fueron filtradas utilizando un filtro pasabanda. Este filtro permitió que solo las frecuencias entre 3 Hz y 30 Hz pasaran a través del filtro. El filtro pasabanda fue implementado utilizando una función de la biblioteca bsnb. 
En este caso, se utilizó un orden de filtro de 2. Esto significa que las frecuencias fuera de la banda de paso fueron atenuadas en un factor de 4.Una vez que las señales EEG fueron filtradas, se graficaron utilizando la biblioteca Matplotlib de Python. Los gráficos muestran las señales EEG en el dominio del tiempo.
![image](https://github.com/ldachirre/IntroSenalesBiomedicas/assets/67986101/485ff6a0-ad78-4bdb-920a-09ae5057929e)
> Fig 4. Señales EEG filtrada

### 4. Detección de ERP
El ERP, o potencial relacionado con eventos, representa la actividad bloqueada en el tiempo del EEG, generando voltajes mínimos en respuesta a estímulos específicos. Estos potenciales reflejan la actividad de potenciales postsinápticos durante la sincronización de la activación de numerosas neuronas piramidales, permitiendo capturar la actividad neuronal relacionada con procesos cognitivos y sensoriales. Se dividen en dos categorías según su tiempo de aparición en relación con el estímulo: aquellos que alcanzan su máximo en los primeros 100 milisegundos y los generados en fases posteriores. La detección de ERP es una técnica que se utiliza para identificar patrones de actividad cerebral asociados a eventos específicos. En este caso, los eventos específicos fueron la presentación de preguntas matemáticas difíciles y fáciles.

Para detectar ERP, se utilizó un procedimiento llamado promediación. En este procedimiento, se promedian las señales EEG registradas en respuesta a un evento específico. El promedio ayuda a eliminar el ruido de la señal y a resaltar los patrones de actividad cerebral asociados al evento. En este caso, se utilizó una ventana de tiempo de 100 milisegundos (ms). La ventana de tiempo pre-estímulo fue de 50 ms y la ventana de tiempo post-estímulo fue de 50 ms. [3]

![image](https://github.com/ldachirre/IntroSenalesBiomedicas/assets/67986101/eb6f176e-fb67-467a-b042-5cadb1e0d6a9)
![image](https://github.com/ldachirre/IntroSenalesBiomedicas/assets/67986101/b2250edb-7686-4fc4-8f8f-b0c63cca75b6)
![image](https://github.com/ldachirre/IntroSenalesBiomedicas/assets/67986101/658a2f35-7255-447e-b850-06d73ba15406)
![image](https://github.com/ldachirre/IntroSenalesBiomedicas/assets/67986101/6914c851-719f-4964-b368-c7b8d1ed50be)
> Fig 5. Detección de ERP
#### Discusión de Resultados de ERP
Los resultados de la detección de ERP mostraron que los ERP asociados a la presentación de preguntas matemáticas difíciles y fáciles eran diferentes. En particular, los ERP asociados a las preguntas matemáticas difíciles eran más grandes y tenían una latencia más temprana que los ERP asociados a las preguntas matemáticas fáciles. Estas diferencias pueden indicar que la presentación de preguntas matemáticas difíciles activa diferentes regiones del cerebro que la presentación de preguntas matemáticas fáciles.

Una posibilidad es que las preguntas matemáticas difíciles requieran una mayor cantidad de procesamiento cognitivo que las preguntas matemáticas fáciles. Esto podría conducir a una activación más temprana y más intensa de las regiones del cerebro involucradas en el procesamiento cognitivo.

Sin embargo otra posibilidad es que las preguntas matemáticas difíciles sean más emocionalmente desafiantes que las preguntas matemáticas fáciles debido a que se está frente a varias personas y debido a que la probabilidad de fallar en la respuesta es mayor. Esto podría conducir a una activación de las regiones del cerebro involucradas en la emoción.



### 5.1 Extracción de la Banda Alfa
Las ondas alfa, con una frecuencia de 8 a 13 Hz, son observadas durante los 4 escenarios: En reposo, Parpadeando, Resolviendo preguntas díficiles y Resolviendo preguntas fáciles. Se caracterizan por ser lentas y menos intensas que las ondas beta y theta, con mayor amplitud en las regiones occipital y frontal, y ocasional presencia en las zonas parietales y temporales. Conocer estas ondas es crucial para el diagnóstico y tratamiento de trastornos neurológicos, ya que las diferencias topográficas en su distribución han demostrado ser específicas para distintos tipos de patologías. [4]

![image](https://github.com/ldachirre/IntroSenalesBiomedicas/assets/67986101/348dbe20-34c1-4e59-851e-2c2720d42c8d)
> Fig 6. Extracción de la Banda Alfa


### 5.2 Extracción de la Banda Beta
Las ondas beta, de frecuencia 13 a 30 Hz, se observan en los 4 escenarios.

![download](https://github.com/ldachirre/IntroSenalesBiomedicas/assets/42382614/676e0320-0b95-411e-905c-9ab314d5d310)
> Fig 7. Extracción de la Banda Beta


### 5.3 Extracción de la Banda Gamma
Las ondas beta, de frecuencia 30 a 100 Hz, se observan en los 4 escenarios.

> Fig 8. Extracción de la Banda Gamma
![download](https://github.com/ldachirre/IntroSenalesBiomedicas/assets/42382614/c035000a-a2c3-4f3e-912c-a8d2839a4a73)




## **Conclusiones** <a name="id5"></a>
- El filtrado de señales EEG permitió eliminar el ruido de las señales EEG. Esto facilitó la identificación de patrones de actividad cerebral asociados a los diferentes escenarios en los que se registraron las señales EEG.
- En este caso, la detección de ERP permitió identificar diferencias en la actividad cerebral entre los diferentes escenarios. En particular, se observaron diferencias significativas en los ERP asociados a la presentación de preguntas matemáticas difíciles y fáciles.
- La extracción de ondas alfa mostró que la amplitud de las ondas alfa es mayor en estado de reposo que en los otros escenarios. Esto es consistente con la literatura científica, que muestra que las ondas alfa están asociadas a un estado de relajación y atención relajada.


## **Referencias** <a name="id6"></a>
[1] S. U. C. M. Ehrotra, Introduction To EEG- and Emotion Recognition. 2018. Accedido: 30 de septiembre de 2023. [En línea]. Disponible en: http://www.sciencedirect.com:5070/book/9780128044902/introduction-to-eeg-and-speech-based-emotion-recognition

[2] W. A. W Azlan and Y. F. Low, "Feature extraction of electroencephalogram (EEG) signal - A review," 2014 IEEE Conference on Biomedical Engineering and Sciences (IECBES), Kuala Lumpur, Malaysia, 2014, pp. 801-806, doi: 10.1109/IECBES.2014.7047620.

[3] S. Sur and V. Sinha, “Event-related potential: An overview,” vol. 18, no. 1, pp. 70–70, Jan. 2009, doi: https://doi.org/10.4103/0972-6748.57865.

[4] Graetzer, D. G., PhD. (2023). Electroencephalography (EEG). Magill’s Medical Guide (Online Edition). Disponible en: https://research-ebsco-com.ezproxybib.pucp.edu.pe/c/d6owsy/details/cdlxy7ttnv



