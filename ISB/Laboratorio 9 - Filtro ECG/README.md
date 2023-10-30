# LABORATORIO 9: Filtrado de ECG y obtención de sus características
# **Tabla de contenidos**

1. [Introducción](#id1)
2. [Objetivos](#id2)
3. [Filtrado de EMG](#id3)
4. [Protocolo de Procesamiento](#id8)
5. [Obtencion de Características](#id4)
6. [Conclusiones](#id5)
7. [Referencias](#id6)
   
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

## **Protocolo de Procesamiento de la señal ECG** <a name="id8"></a>

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



## **Procesamiento de ECG** <a name="id3"></a>

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

### 3. Filtro Notch

Se aprecia cómo el ruido de 60 y 180 Hz desaparece después del filtrado.

### 4. Filtro pasa banda

Creación de filtro pasa banda.

### 5. Filtro pasa alto

Creación de filtro pasa alto.

### 6. Filtrado derivativo

En el artículo nos dan la siguiente función que describe al operador:




| Creación de Filtros|
| :---:  |
![filtroemg](https://github.com/ldachirre/IntroSenalesBiomedicas/assets/42382614/85604920-0edc-40c1-939c-d548d78fc5b2)

| Señal |
| :---:  |
![IMG-20231023-WA0033](https://github.com/ldachirre/IntroSenalesBiomedicas/assets/56425258/2604d181-9725-4e0d-acc8-dce22b64892a)
![IMG-20231023-WA0034](https://github.com/ldachirre/IntroSenalesBiomedicas/assets/56425258/ef63c4e1-bb9c-4da6-afb9-e0a3a72c32cb)
![IMG-20231023-WA0035](https://github.com/ldachirre/IntroSenalesBiomedicas/assets/56425258/8e3de7ec-fdd7-42cc-931c-dee8cb4d08b0)
![IMG-20231023-WA0036](https://github.com/ldachirre/IntroSenalesBiomedicas/assets/56425258/4df81fd9-b71f-42eb-97ce-9befd8b932e4)


## **Obtencion de Características** <a name="id4"></a>

Respecto a las características de la señal, para este laboratorio se decidió obtener y analizar las características estadísticas de esta. Se presenta el análisis y comparación entre los 4 sujetos en:

| Mean value |
![medias](https://github.com/ldachirre/IntroSenalesBiomedicas/assets/56425258/df32664e-35ea-4390-b29f-0b829a52bb06)

| RMS |
![rms](https://github.com/ldachirre/IntroSenalesBiomedicas/assets/56425258/840099f0-9734-47a5-939b-e33347409e42)

| Pico-pico |
![pico-pico](https://github.com/ldachirre/IntroSenalesBiomedicas/assets/56425258/ef88a7df-3daf-4516-821e-f1b3d72d08f1)

| Área bajo la curva |
![areas](https://github.com/ldachirre/IntroSenalesBiomedicas/assets/56425258/1154290c-dc34-4091-8856-63d210e8ba6c)

## **Conclusiones** <a name="id5"></a>
- La evaluación de la amplitud, tendencia central y variabilidad de las señales EMG permite identificar diversas afecciones y situaciones asociadas al sistema neuromuscular. En este contexto, el análisis de señales EMG es de particular interés debido a su aplicación en el diagnóstico clínico y en diversas aplicaciones biomédicas, como se explico en la introducción, tales como miopatías, neuropatías periféricas, Esclerosis lateral amiotrófica (ELA), Síndrome del túnel carpiano, entre otros.
- En el laboratorio, se llevó a cabo un análisis de las señales de EMG utilizando un conjunto de datos previamente recopilado. El objetivo principal fue identificar la actividad muscular en función de los movimientos realizados y los músculos involucrados. Este análisis de señales EMG tiene una gran importancia en el ámbito de la biomecánica, ya que proporciona información detallada acerca de la contracción muscular, la fatiga, la coordinación y otros aspectos relacionados con el funcionamiento de los músculos y su relación con los movimientos corporales. Para obtener resultados óptimos a partir de una señal EMG, es esencial realizar una serie de etapas que incluyen el preprocesamiento, la extracción de características y la aplicación de métodos de análisis y clasificación apropiados. Estos procedimientos son cruciales para obtener datos valiosos que se emplean en el diagnóstico y tratamiento de trastornos neuromusculares, así como en otras áreas de la medicina e investigación

## **Referencias** <a name="id6"></a>
[1] A. Farina, M. C. Romano, and A. V. Masci, "Electromyography: Signal analysis and processing," IEEE Signal Processing Magazine, vol. 27, no. 5, pp. 106-121, Sep. 2010.
[2] M. A. E. El-Borgy, "Electromyography (EMG) signal processing for biomedical applications," Journal of Biomedical Engineering, vol. 32, no. 1, pp. 1-12, Jan. 2010.
[3] J. C. De Luca, "The use of surface electromyography in assessing muscle function," Journal of Electromyography and Kinesiology, vol. 18, no. 3, pp. 333-345, Jun. 2008.

