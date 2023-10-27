# LABORATORIO 8: Filtrado de EMG y obtención de sus características
# **Tabla de contenidos**

1. [Introducción](#id1)
2. [Objetivos](#id2)
3. [Filtrado de EMG](#id3)
4. [Obtencion de Características](#id4)
6. [Conclusiones](#id5)
7. [Referencias](#id6)
   
## **Introducción** <a name="id1"></a>
La electromiografía (EMG) es una técnica utilizada para registrar la actividad eléctrica de los músculos. Una vez que se ha adquirido la señal EMG, es necesario procesarla adecuadamente para extraer información relevante que permita comprender la función muscular y diagnosticar posibles trastornos neuromusculares. La EMG es especialmente valiosa en aplicaciones como el control de prótesis, donde las señales EMG del antebrazo se utilizan para dirigir manos protésicas en lo que se conoce como 'control mioeléctrico'. Tras el procesamiento de las señales EMG, los sistemas de reconocimiento de patrones involucran segmentación de datos, extracción de características, clasificación y control. Esto implica la reducción de dimensiones de las señales y el uso de un clasificador para identificar patrones de señales y clasificarlos en categorías predefinidas, como movimientos de mano y dedos.
![EMG1](https://github.com/ldachirre/IntroSenalesBiomedicas/assets/90112793/47778e6b-1e32-4e8f-9ee0-6fa6a856073f)
![EMG2](https://github.com/ldachirre/IntroSenalesBiomedicas/assets/90112793/9abcb971-7b53-456d-a828-ee152d92e313)

Una vez que se ha eliminado el ruido y se ha obtenido una señal limpia y precisa, el siguiente paso es la extracción de características. Las características que se extraen de una señal EMG son esenciales para evaluar y analizar la actividad muscular de manera cuantitativa.

Las características de EMG pueden ser utilizadas para diagnosticar una variedad de trastornos musculares y nerviosos. Por ejemplo, la amplitud de la señal puede ser utilizada para evaluar la fuerza muscular, la frecuencia puede ser utilizada para evaluar la actividad muscular, y la duración puede ser utilizada para evaluar el estado de las unidades motoras. Se presentan estas características a continuación:

- **Amplitud de la señal:** La amplitud representa la magnitud de la señal EMG y se relaciona con la fuerza muscular. Se puede medir en términos de voltaje y proporciona información sobre la intensidad de la contracción muscular.

- **Frecuencia de la señal:** La frecuencia se refiere a la cantidad de oscilaciones por segundo en la señal EMG y puede ayudar a identificar patrones de actividad muscular. Se mide en Hertz (Hz) y puede ser útil para distinguir entre contracciones musculares normales y patológicas.

- **Duración de los eventos:** Esta característica indica el tiempo durante el cual un músculo se encuentra activo, lo que es crucial para evaluar la fatiga muscular y determinar cuánto tiempo puede mantener una contracción un músculo antes de debilitarse.

- **RMS (Root Mean Square):** El valor RMS proporciona una medida cuantitativa de la amplitud de la señal EMG y se utiliza comúnmente para cuantificar la fuerza muscular.

- **Área bajo la curva:** Esta medida proporciona información sobre la energía total en la señal EMG y puede estar relacionada con la intensidad y la duración de la actividad muscular.


## **Objetivos** <a name="id2"></a>
1. **Obtener características estadísticas de la señal:** Incluye la extracción de características como la amplitud de la señal, el valor promedio (media), la frecuencia y el valor Root Mean Square (RMS) de la señal EMG.

2. **Realizar el análisis de las características y compararlo con valores de la literatura:** Evalúa las características extraídas y compáralas con valores de referencia disponibles en la literatura. Esto ayuda a entender cómo se comporta la señal en relación con los datos previamente documentados.

3. **Verificar el comportamiento de la señal EMG:** Asegúrate de examinar el comportamiento general de la señal EMG para identificar patrones, tendencias o anomalías que puedan ser relevantes para tu análisis o aplicación específica.


## **Filtrado EMG** <a name="id3"></a>
Según los datos obtenidos en la experiencia de laboratorio pasada (Filtrado de señales) se tiene lo siguiente: Filtrado de la señal EMG mediante filtros digitales FIR e IIR. Sabemos que las frecuencias de EMG se encuentran en un rango entre 50-150 Hz es por ello que se le aplicó un filtro pasa baja con frecuencia de corte de 200 Hz. Respecto al tiempo de análisis, la ventana utilizada fue de 2 segundos. 

Se presentan los valores EMG de los sujetos (4 ejemplares) analizados en la experiencia de laboratorio 4.


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

