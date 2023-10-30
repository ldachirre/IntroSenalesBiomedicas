# LABORATORIO 9: Filtrado de ECG y obtención de sus características
# **Tabla de contenidos**

1. [Introducción](#id1)
2. [Objetivos](#id2)
3. [Protocolo de Procesamiento](#id3)
4. [Procesamiento y obtención de características de EMG](#id4)
5. [Conclusiones](#id5)
6. [Referencias](#id6)
   
## **Introducción** <a name="id1"></a>

El electrocardiograma, comúnmente conocido como EKG o ECG, es una herramienta fundamental en el mundo de la medicina, ofreciendo una ventana única para observar la actividad eléctrica del corazón. Esta representación gráfica de la función cardíaca no solo es crucial para el diagnóstico y seguimiento de trastornos cardíacos, sino que también desempeña un papel esencial en la comprensión de la salud cardiovascular.
En términos generales, el pico del ECG oscila en torno a 1 mV y sigue un patrón de ondas denominado PQRST, ilustrado en la Figura 1. Este patrón sigue una periodicidad que se reproduce a lo largo de las ondas características del ECG. Debido a la similitud en la forma de las ondas, los profesionales de la medicina a menudo pueden extraer información visualmente del ECG basándose en la forma de la señal. Por lo tanto, si la forma de la onda no coincide con la morfología esperada y saludable, se puede inferir que existe una enfermedad cardiovascular subyacente causando la anomalía. Esto subraya la importancia de una precisa extracción de las características de una señal ECG. Los usos comunes del ECG abarcan desde el diagnóstico de condiciones como el dolor torácico, taquicardia, bradicardia, hipertensión, hipotensión, lesiones miocárdicas, hasta enfermedades cardíacas reumáticas, y mucho más [1].
![ecg imagen x](https://github.com/ldachirre/IntroSenalesBiomedicas/assets/90112793/aeaeb658-9f72-4ea1-8234-31a8a3fb7b42)
**Figura 1.** Señal ECG que muestra los componentes PQRST

Pueden extraerse varias características de una señal de electrocardiograma (ECG), y cada una de ellas proporciona información valiosa para el análisis de la señal de ECG. A continuación se presentan algunas características comunes y lo que significan en el análisis de la señal de ECG [2], además, se muestra en la **Figura 2**:

- La **frecuencia cardíaca:** La frecuencia cardiaca representa el número de latidos por minuto y se calcula midiendo el tiempo entre los picos R en la forma de onda del ECG. La frecuencia cardíaca suele estar entre 60-90 lpm.

- El **intervalo PR:** es la distancia entre el inicio de la onda P hasta el inicio del complejo QRS y está típicamente entre 0,12-0,20 seg.

- El **complejo QRS:** mide el tiempo que tardan los ventrículos en despolarizarse. Una duración prolongada del QRS puede sugerir anomalías en la conducción, la cual debe tener una duración inferior a 0,12 seg.

- El **intervalo QT:** su duración representa el tiempo que tarda la despolarización y repolarización ventricular. Un intervalo QT prolongado puede indicar un mayor riesgo de arritmias.

- El **segmento ST:** representa el tiempo entre la despolarización ventricular y la repolarización y debe ser isoeléctrico. Es crucial en el diagnóstico de afecciones cardiacas como el infarto de miocardio.

- La **onda T:** representa la repolarización ventricular y debe ser vertical en las derivaciones I y II. Asimismo, su amplitud puede ser útil para evaluar ciertas afecciones cardíacas y desequilibrios electrolíticos.

- **Variabilidad de la frecuencia cardiaca (VFC):** mide la variación en el tiempo entre picos R sucesivos. Refleja la influencia del sistema nervioso autónomo sobre el corazón y puede ser un indicador de la salud general, el estrés y los factores de riesgo de diversas afecciones.

- **Frecuencia de la señal:** puede revelar bandas de frecuencia específicas asociadas a arritmias y otras afecciones cardiacas.

- **RMS (Root Mean Square):** El valor RMS proporciona una medida cuantitativa de la amplitud de la señal ECG y se utiliza comúnmente para describir las propiedades estadísticas de la señal de ECG y pueden ser indicativas de condiciones cardiacas específicas.


## **Objetivos** <a name="id2"></a>
1. **Obtener características estadísticas de la señal:** Incluye la extracción de características como la amplitud de la señal, el valor promedio (media), la frecuencia y el valor Root Mean Square (RMS) de la señal ECG.

2. **Realizar el análisis de las características y compararlo con valores de la literatura:** Evalúa las características extraídas y compáralas con valores de referencia disponibles en la literatura. Esto ayuda a entender cómo se comporta la señal en relación con los datos previamente documentados.

3. **Verificar el comportamiento de la señal ECG:** Asegúrate de examinar el comportamiento general de la señal EMG para identificar patrones, tendencias o anomalías que puedan ser relevantes para tu análisis o aplicación específica.

## **Protocolo de Procesamiento de la señal ECG** <a name="id3"></a>

El procesamiento de la señal ECG involucra una serie de pasos esenciales para obtener información clara y precisa de la señal. Estos pasos son los siguientes:

1. **Leer el DataSet:** En esta etapa, se accede a los datos del electrocardiograma para su posterior análisis.

2. **Analizar el ECG en frecuencia:** Se examina la señal en el dominio de la frecuencia para identificar componentes relevantes y características.

3. **Reducir los ruidos con filtro Notch:** Se utiliza un filtro Notch para eliminar ruidos específicos, como interferencias de frecuencia de la red eléctrica.

4. **Filtrar la señal con un filtro pasa banda:** Aplicar un filtro pasa banda ayuda a aislar las frecuencias de interés en la señal ECG.

5. **Filtrar la señal con un filtro pasa alto:** Este filtro permite eliminar componentes de baja frecuencia no deseados.

6. **Realizar el filtrado derivativo:** Se aplica un filtro derivativo para resaltar los cambios en la señal, como las pendientes asociadas a los complejos QRS.

7. **Elevar al cuadrado la señal:** El cuadrado de la señal puede destacar características importantes y suprimir el ruido.

8. **Emplear el operador Moving Window Integration:** Este operador se utiliza para suavizar la señal y resaltar características específicas.

9. **Marcar los picos:** Se detectan los picos R en la señal, que corresponden a la despolarización ventricular.

10. **Realizar el análisis de Threshold:** Se determina el umbral de detección de los picos R y se distingue entre estos picos y el ruido.

11. **Obtener los complejos QRS en la señal ECG inicial:** Finalmente, se identifican y extraen los complejos QRS, que representan la actividad eléctrica de los ventrículos del corazón en la señal ECG original.[2]



## **Procesamiento de ECG** <a name="id4"></a>

### 1. Lectura del Dataset
La señal ECG a utilizar en este entregable es la señal del sujeto 3 en estado activo (en ejercicio) obtenida en el entregable 4. Esta señal no se encuentra en unidades de voltaje, por lo que habrá que realizar una conversión de unidades para poseer la señal en mV. Para ello, se realizará una conversión de unidades con la fórmula de la Figura 3.

![1](https://github.com/ldachirre/IntroSenalesBiomedicas/assets/90112793/a55347a5-8a04-4ea1-9448-1799101a16de)
![2](https://github.com/ldachirre/IntroSenalesBiomedicas/assets/90112793/3cd10b0f-9450-40c4-b966-d36be5fafded)
**Figura 3.** Conversión de unidades 
Una vez realizada esta conversión, se obtiene los valores de la señal ECG en mV.

![3](https://github.com/ldachirre/IntroSenalesBiomedicas/assets/90112793/f999fa22-c9f2-4373-a211-be805ad1e9df)

### 2. Análisis en frecuencia
Se procede a realizar la FFT de la señal ECG.
Se puede apreciar en la figura. que existe ruido de frecuencias de 60 y 120 Hz, por lo que se procede a realizar un filtrado con filtro digital Notch.
![f2](https://github.com/ldachirre/IntroSenalesBiomedicas/assets/90112793/4b477854-581e-4b53-a075-3de07b08203d)

### 3. Filtro Notch

Se aprecia cómo el ruido de 60 y 180 Hz desaparece después del filtrado.
![f3](https://github.com/ldachirre/IntroSenalesBiomedicas/assets/90112793/b8677b1f-a2b0-42cc-8db7-28ee1ee6c98a)

![f333](https://github.com/ldachirre/IntroSenalesBiomedicas/assets/90112793/738a26cd-413c-42f9-8994-782e84401645)

### 4. Filtro pasa banda

Creación de filtro pasa banda.
![f4](https://github.com/ldachirre/IntroSenalesBiomedicas/assets/90112793/d3583507-45c1-48dc-8b07-8849268f2e4a)
![f44](https://github.com/ldachirre/IntroSenalesBiomedicas/assets/90112793/f3265c5a-f299-4c6e-baf1-8c15c1f1ea33)


### 5. Filtro pasa alto

Creación de filtro pasa alto.
![f5](https://github.com/ldachirre/IntroSenalesBiomedicas/assets/90112793/27bc7db4-c9be-4fa0-8e5b-c5428e2a5679)
![f55](https://github.com/ldachirre/IntroSenalesBiomedicas/assets/90112793/1e470728-e8fb-41c0-b56a-dd1f617cf419)


### 6. Filtrado derivativo

En el artículo nos dan la siguiente función que describe al operador:
En el artículo nos dan la siguiente función que describe al operador:
y[n]=(1/8)(−x[n−2]−2x[n−1]+2x[n+1]+x[n+2])
Para que esta ecuación pueda ser utilizada necesitamos encuadrarla en un rango de [0,+∞] haciendo que n=+2 entonces tenemos:
y[n]=(1/8)(−x[n]−2x[n+1]+2x[n+3]+x[n+4])
Por lo tanto:
b=[−1,−2,0,2,1]
![f6](https://github.com/ldachirre/IntroSenalesBiomedicas/assets/90112793/0c5f28d5-0d26-496e-8dd3-d78fab6cc823)
![f66](https://github.com/ldachirre/IntroSenalesBiomedicas/assets/90112793/aca200f2-7f4e-4fc0-9917-662d92bcd4e4)

### 7. Operador cuadrático

El operador cuadrático se emplea para destacar ciertas características de la señal, como la amplitud, que puede ser relevante para la detección de arritmias y otras afecciones cardíacas.
y[n]=x^2[n]
![f7](https://github.com/ldachirre/IntroSenalesBiomedicas/assets/90112793/17a34c73-1024-4169-b7bc-143412517c06)


### 8. Operador Moving Window Integration

Este operador se usa para suavizar la señal y extraer características específicas, lo que facilita la identificación de patrones en la señal EKG.
y[n]=(1/N)(x[n−(N−1)]+x[n−(N−2)]+..+x[n])
![f8](https://github.com/ldachirre/IntroSenalesBiomedicas/assets/90112793/0ed228fc-a959-4d3d-9791-bb0fe1e88a71)


### 9. Marcar picos
Marcar los picos R es esencial para identificar la actividad eléctrica ventricular y medir la frecuencia cardíaca.
![f9](https://github.com/ldachirre/IntroSenalesBiomedicas/assets/90112793/6cb43acf-b0a0-43d6-bb4f-deb747085104)



### 10. Análisis Threshold

El análisis de Threshold es fundamental para distinguir entre picos R y ruido, garantizando una detección precisa de los complejos QRS.
![f10](https://github.com/ldachirre/IntroSenalesBiomedicas/assets/90112793/1f2fc3f0-651a-4892-aaee-edeccd48c97f)
![f1010](https://github.com/ldachirre/IntroSenalesBiomedicas/assets/90112793/9a77cc6f-bc17-48b5-b854-704dd0305d93)
![f101010](https://github.com/ldachirre/IntroSenalesBiomedicas/assets/90112793/635a03e1-bb6b-4c09-9dc3-b7e0195d8e81)

### 11. Complejos QRS

En esta sección se describe el proceso de identificación y delimitación de los complejos QRS utilizando el método de Wavelet Discreta. Este método permite una representación más precisa de la actividad eléctrica ventricular en la señal ECG lo que es crucial en el diagnóstico de afecciones cardíacas y la evaluación de la salud del corazón.. El proceso se lleva a cabo en varias etapas:
![f11](https://github.com/ldachirre/IntroSenalesBiomedicas/assets/90112793/f6f29bf3-98cb-4796-9bc7-db465003e603)
1. **Identificación de los picos R:** El primer paso consiste en identificar los picos R en la señal ECG. Estos picos representan la despolarización ventricular y son fundamentales para determinar la frecuencia cardíaca y la actividad eléctrica del corazón.
![picos r](https://github.com/ldachirre/IntroSenalesBiomedicas/assets/90112793/cb1fa991-571b-4277-9563-38f81941e151)

2. **Delimitando el complejo QRS con la librería Neurokit:** Una vez que se han identificado los picos R, se utiliza la librería Neurokit para delimitar el complejo QRS en la señal. Esto implica identificar los puntos iniciales y finales de la onda QRS, lo que permite un análisis más preciso de esta importante parte del ECG.
![qrs neurokit](https://github.com/ldachirre/IntroSenalesBiomedicas/assets/90112793/285fb533-4de0-4a3c-b32b-fc2073605618)

3. **Delineación de las ondas P y T:** Después de delimitar el complejo QRS, se enfoca en la identificación de los picos P y T en la señal. Estos picos representan la despolarización de las aurículas (onda P) y la repolarización ventricular (onda T). Para una identificación precisa, se centra en el período entre -0.2 y 0.2 segundos, ya que fuera de este rango se pueden encontrar repeticiones de las mismas ondas.
![wavelet discreto](https://github.com/ldachirre/IntroSenalesBiomedicas/assets/90112793/0fcbc64d-d1b7-4d45-b6cb-2d30c93dd83f)
observamos los picos P y T
![picos P y T](https://github.com/ldachirre/IntroSenalesBiomedicas/assets/90112793/b3f0c4ac-7663-4475-81ba-4a43b90efffd)

4. **Establecimiento de los límites de cada onda:** Se definen los límites de cada onda en el ECG, incluyendo la onda T, la onda P y la onda R. Esto permite una descripción detallada de la actividad eléctrica cardíaca y es fundamental en el diagnóstico de afecciones cardíacas.
![limites de cada onda](https://github.com/ldachirre/IntroSenalesBiomedicas/assets/90112793/fb1abf59-7437-46f2-9696-c479385c657e)
![sigue limites de cada onda](https://github.com/ldachirre/IntroSenalesBiomedicas/assets/90112793/99919e38-872e-4eb5-94d7-d52189d89120)
![sigueeee](https://github.com/ldachirre/IntroSenalesBiomedicas/assets/90112793/0296f619-6454-4484-8e18-5c33283e02aa)

5. **Delineación del ECG utilizando el método wavelet con la señal previamente filtrada por un filtro FIR:** Al pasar la señal ECG a través del método de Wavelet Discreta con la señal previamente filtrada por un filtro FIR, se logra una identificación aún más precisa de los límites de las ondas en la señal. Este enfoque refinado mejora la calidad del análisis.
![wavelet fir](https://github.com/ldachirre/IntroSenalesBiomedicas/assets/90112793/334450c1-4e60-4101-a2eb-d5dba8fc9bb2)

6. **RR distance y BPM (en los primeros 5 segundos):** Finalmente, se calculan algunas métricas importantes, como el intervalo máximo R-R, el intervalo mínimo R-R, el intervalo promedio R-R y el promedio de latidos por minuto (BPM). Estas métricas proporcionan información vital sobre la variabilidad de la frecuencia cardíaca y el ritmo cardíaco en los primeros 5 segundos de la señal ECG.

**RR distance y BPM (en los primeros 5 segundos)**

El intervalo máximo R-R es: 0.43 ms
El intervalo mínimo R-R es: 0.23 ms
El intervalo promedio R-R es: 0.368 ms
El BPM promedio es: 162 latidos por minuto
![ultima](https://github.com/ldachirre/IntroSenalesBiomedicas/assets/90112793/f26293c1-4f34-4b02-afaa-9c4a22259c2d)


## **Conclusiones** <a name="id5"></a>
- Los coeficientes de wavelet en diferentes escalas y posiciones revelan información sobre la morfología de las ondas en el ECG, permitiendo identificar los complejos QRS, picos R, límites de onda P, onda T y onda R.

- Al analizar la transformada wavelet discreta de la señal ECG, se identifican las componentes de alta frecuencia que corresponden a la actividad cardíaca. Esto permite calcular la frecuencia cardíaca (beat rate) a partir de los picos R identificados.

- Es posible detectar arritmias cardíacas al analizar las irregularidades en la forma de las ondas ECG y la variabilidad de los intervalos RR.

- La aplicación de filtros Notch y pasa banda resultó eficaz para reducir el ruido en la señal ECG, mejorando la calidad de los datos y permitiendo una detección más precisa de eventos cardíacos.


## **Referencias** <a name="id6"></a>
[1] Singh, A.K., Krishnan, S. ECG signal feature extraction trends in methods and applications. BioMed Eng OnLine 22, 22 (2023). https://doi.org/10.1186/s12938-023-01075-1

[2] Sörnmo, L. (2009). Electrocardiogram (ECG) Signal Processing. En L. Sörnmo (Ed.), Electrocardiogram (ECG) Signal Processing (pp. 12-20). Wiley.

[3] Gacek, A. (2012). An Introduction to ECG Signal Processing and Analysis. In: Gacek, A., Pedrycz, W. (eds) ECG Signal Processing, Classification and Interpretation. Springer, London. https://doi.org/10.1007/978-0-85729-868-3_2

[4]“Locate P, Q, S and T waves in ECG — NeuroKit2 0.2.7 documentation”, Github.io. [En línea]. Disponible en: https://neuropsychology.github.io/NeuroKit/examples/ecg_delineate/ecg_delineate.html.

[5][10]	“hrv_parameters”, Pluxbiosignals.com. [En línea]. Disponible en: http://notebooks.pluxbiosignals.com/notebooks/Categories/Extract/hrv_parameters_rev.html. 

