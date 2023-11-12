# LABORATORIO 10: Filtrado de ECG y obtención de sus características
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
**Figura 1.** EEG bandas de frecuencia, ocurrencia y tareas para activar la potencia de banda

El análisis de una señal se ve 

La extracción de características es un proceso por el cual a una señal le son extraídas información relevante (características) las cuales son más sencillas de interpretar que la señal original. Dicha información extraída refleja la fisiología y anatomía de la actividad ocurrida en el cerebro donde se puede observar el comportamiento que responde a cierta actividad y/o estímulo. Este proceso requiere un gran número de dataset donde se utilizan algoritmos para su extracción y análisis, por ejemplo Hilbert-Huang Transform (HHT), Principal Component Analysis (PCA), Independent Component Analysis (ICA), etc. [2]

En este entregable se analizarán las señales obtenidas previamente las cuales se les serán extraídas principalmente mediante:



## **Objetivos** <a name="id2"></a>
1. **Obtener características estadísticas de la señal:** Incluye la extracción de características como la amplitud de la señal, el valor promedio (media), la frecuencia y el valor Root Mean Square (RMS) de la señal EEG.

2. **Realizar el análisis de las características y compararlo con valores de la literatura:** Evaluación y comparación de las características extraídas con valores de referencia disponibles en la literatura. Esto ayuda a entender cómo se comporta la señal en relación con los datos previamente documentados.

3. **Verificar el comportamiento de la señal ECG:** Comportamiento general de la señal EMG para identificar patrones, tendencias o anomalías que puedan ser relevantes para tu análisis o aplicación específica.

## **Metodología** <a name="id3"></a>

El procesamiento de la señal EEG involucra una serie de pasos esenciales para obtener información clara y precisa de la señal. Estos pasos son los siguientes:

1. **Leer el DataSet:** En esta etapa, se accede a los datos del electrocardiograma para su posterior análisis.

2. **Analizar el EEG en frecuencia:** Se examina la señal en el dominio de la frecuencia para identificar componentes relevantes y características.

3. **Reducir los ruidos con filtro Notch:** Se utiliza un filtro Notch para eliminar ruidos específicos, como interferencias de frecuencia de la red eléctrica.

4. **Filtrar la señal con un filtro pasa banda:** Aplicar un filtro pasa banda ayuda a aislar las frecuencias de interés en la señal EEG.

5. **Filtrar la señal con un filtro pasa alto:** Este filtro permite eliminar componentes de baja frecuencia no deseados.

6. **Realizar el filtrado derivativo:** Se aplica un filtro derivativo para resaltar los cambios en la señal, XXX

7. **Elevar al cuadrado la señal:** El cuadrado de la señal puede destacar características importantes y suprimir el ruido.

8. **Emplear el operador Moving Window Integration:** Este operador se utiliza para suavizar la señal y resaltar características específicas.

9. **Marcar los picos:** Se detectan los picos R en la señal, que corresponden a la despolarización ventricular.

10. **Realizar el análisis de Threshold:** Se determina el umbral de detección de los picos R y se distingue entre estos picos y el ruido.


## **Procesamiento y obtención de características de EEG** <a name="id4"></a>

### 1. Lectura del Dataset

### 2. Análisis en frecuencia

### 3. Filtro Notch

### 4. Filtro pasa banda

### 5. Filtro pasa alto

### 6. Filtrado derivativo

### 7. Operador cuadrático

### 8. Operador Moving Window Integration

### 9. Marcar picos

### 10. Análisis Threshold

## **Conclusiones** <a name="id5"></a>

## **Referencias** <a name="id6"></a>
[1] S. U. C. M. Ehrotra, Introduction To EEG- and Emotion Recognition. 2018. Accedido: 30 de septiembre de 2023. [En línea]. Disponible en: http://www.sciencedirect.com:5070/book/9780128044902/introduction-to-eeg-and-speech-based-emotion-recognition

[2] W. A. W Azlan and Y. F. Low, "Feature extraction of electroencephalogram (EEG) signal - A review," 2014 IEEE Conference on Biomedical Engineering and Sciences (IECBES), Kuala Lumpur, Malaysia, 2014, pp. 801-806, doi: 10.1109/IECBES.2014.7047620.


