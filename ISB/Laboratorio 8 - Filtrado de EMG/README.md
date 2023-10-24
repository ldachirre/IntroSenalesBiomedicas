# LABORATORIO 8: Filtrado de EMG y obtención de sus características
# **Tabla de contenidos**

1. [Introducción](#id1)
2. [Objetivos](#id2)
3. [Filtrado de EMG](#id3)
4. [Obtencion de Características](#id4)
5. [Discusión](#id5)
6. [Conclusiones](#id6)
7. [Referencias](#id7)
   
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
| Creación de Filtros|
| :---:  |
![filtroemg](https://github.com/ldachirre/IntroSenalesBiomedicas/assets/42382614/85604920-0edc-40c1-939c-d548d78fc5b2)

| Señal |
| :---:  |
![filtradoemg](https://github.com/ldachirre/IntroSenalesBiomedicas/assets/42382614/52173e1d-6fae-47d0-b178-1050bf7084ea)
Para el filtrado de esta señal se uso una frecuencia de corte de 50hz

## **Obtencion de Características** <a name="id4"></a>

## **Discusión ** <a name="id5"></a>

## **Conclusiones** <a name="id6"></a>
- Se comprobó que el filtrado con el filtro IIR son menos eficientes que con el filtro FIR, ya que estos ultimos son más estables, lo que los hace más adecuados para esta aplicación.
- Después de aplicar el proceso de filtrado a las señales, se notaron mejoras significativas, incluyendo la reducción del ruido y la amplitud no deseada, lo que resultó en una señal más clara y con los componentes de interés de manera más destacada.

## **Referencias** <a name="id7"></a>
[1] A. Farina, M. C. Romano, and A. V. Masci, "Electromyography: Signal analysis and processing," IEEE Signal Processing Magazine, vol. 27, no. 5, pp. 106-121, Sep. 2010.
[2] M. A. E. El-Borgy, "Electromyography (EMG) signal processing for biomedical applications," Journal of Biomedical Engineering, vol. 32, no. 1, pp. 1-12, Jan. 2010.
[3] J. C. De Luca, "The use of surface electromyography in assessing muscle function," Journal of Electromyography and Kinesiology, vol. 18, no. 3, pp. 333-345, Jun. 2008.

