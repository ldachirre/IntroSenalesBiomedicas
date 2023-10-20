# LABORATORIO 7: Filtrado de Señales Biológicas
# **Tabla de contenidos**

1. [Introducción](#id1)
2. [Objetivos](#id2)
3. [Filtrado de ECG](#id3)
4. [Filtrado de EMG](#id4)
5. [Filtrado de EEG](#id5)
6. [Conclusiones](#id6)
7. [Referencias](#id7)
   
## **Introducción** <a name="id1"></a>
En los sistemas eléctricos y electrónicos, en ciertas ocasiones, se necesita manejar información a ciertas frecuencias; es por esto que solo se deja pasar a ciertos grupos de frecuencias y las demás se eliminan. Esta función la realizan los filtros que son sistemas electrónicos que presentan características selectivas de frecuencias. Un filtro se define como un sistema que discrimina una señal de entrada y produce cambios en su salida, siendo estos cambios determinados por ciertos parámetros. Los filtros operan tomando una señal de entrada y generan una señal de salida, asimismo existen dos tipos de filtros: analógicos y digitales. Esta señal de salida experimenta modificaciones en términos de su amplitud, frecuencia o fase, dependiendo de las características específicas del filtro [1]. En comparación con los filtros analógicos, los filtros digitales tienen una amplia aplicación en la actualidad, debido en parte a la facilidad de acceso a las computadoras, y a su capacidad de almacenamiento y registro.

### **Filtros FIR (Finite Impulse Response)**
Se diferencia por su respuesta al impulso de duración finita, lo que significa que su salida se calcula como una suma ponderada de un número limitado de muestras de entrada y coeficientes del filtro, como se muestra en la Figura 1. Son predecibles y fáciles de analizar, y se ajustan según las necesidades de filtrado. Los filtros FIR son útiles para filtrar señales, reducir ruido y procesar audio e imágenes. Su ventaja clave es que proporcionan una respuesta de fase lineal, es decir, tiene un retardo de tiempo puro como respuesta de fase, y que es estable, por lo que siempre que la entrada del filtro esté acotada, la salida de este también lo estará. Estas propiedades ayudan al diseño de filtros FIR para que cumplan con ciertas especificaciones necesarias lo que es esencial en aplicaciones donde la precisión de la fase es crucial, como en sistemas de comunicación y audio de alta calidad [2].

![image](https://github.com/ldachirre/IntroSenalesBiomedicas/assets/67986101/fe76f0f7-cc84-4a57-bcd1-e0bf438f78dd)                     
Figura 1. Filtro FIR [2]

Uno de los métodos de diseño de filtros FIR es el uso de ventanas ("windowing"). Este se basa en acortar la respuesta en impulsos de la señal, mediante la multiplicación de la señal con la ventana, como se observa en la Figura 2 [3]. 
![image](https://github.com/ldachirre/IntroSenalesBiomedicas/assets/67986101/5da3795e-183d-429a-8f3a-056678011e44)                        
Figura 2. Funciones de "windowing" [3]

Existen diversos tipos de ventanas, entre las más usadas tenemos [2]: 
- Rectangular: Los valores de estas ventanas sólo varían entre 1 y 0, este filtro logra que la señal no cambie en 1 y se elimine en 0.
- Barlett: se puede observar que tiene una forma triangular, se suele usar para suavizar señales.
- Hanning: Usa transformada de Fourier para su filtrado y busca casi eliminar los lados laterales de la señal.
- Hamming: Busca reducir las discontinuidades de los laterales.
  
![image](https://github.com/ldachirre/IntroSenalesBiomedicas/assets/67986101/6d6f90c1-1f6b-4d85-9f6f-34f68d5743ba)                                            
Figura 3. Ventanas de filtro FIR [3]


### **Filtros IIR (Infinite Impulse Response)**
La característica distintiva de un filtro IIR es que su respuesta al impulso es de duración infinita, lo que significa que su respuesta a una ntrada puede persistir indefinidamente en el tiempo. En otras palabras, la salida de un filtro IIR se calcula como una combinación ponderada de muestras actuales y anteriores de la señal de entrada, así como de las salidas anteriores del filtro. Además, son conocidos por su eficiencia en términos de recursos computacionales y por su capacidad para proporcionar una respuesta en frecuencia más nítida en comparación con los filtros FIR de igual longitud. Sin embargo, suelen introducir una fase no lineal en la señal filtrada, lo que puede ser problemático en algunas aplicaciones que requieren una respuesta de fase lineal, como se observa en la Figura 4 [4].

![image](https://github.com/ldachirre/IntroSenalesBiomedicas/assets/67986101/c3bf4378-68a8-4270-8506-f644b7ecaf5c)                            
Figura 4. Filtro IIR [4]

- Butterworth: proporciona una respuesta suave y uniforme en la banda se paso, sin picos ni caídas pronunciadas. Este tipo de filtro se utiliza comúnmente cuando se requiere una respuesta en frecuencia plana en la banda de paso, sin importar la atenuación en la banda de rechazo.
- Bessel: diseñados para tener una fase lineal en las bandas pasantes, por lo que no distorsionan las señales; por el contrario tienen una mayor zona de transición entre las bandas pasantes y no pasantes.
- Elíptico: se consigue estrechar la zona de transición entre bandas y también acota el rizado en estas bandas.
- Chebyshev: se consigue una caída de la respuesta en frecuencia más pronunciada en frecuencias bajas debido a que permiten rizado en alguna de sus bandas (paso o rechazo). Existen 2 tipos de filtro de chebyshev: los de tipo I, que solo tienen polos; y los de tipo II, que tienen ceros y polos [4].
- 
![image](https://github.com/ldachirre/IntroSenalesBiomedicas/assets/67986101/d6b7e13a-aa95-4d7c-8373-188394d0097d)                                            
Figura 5. Tipos de filtros IIR [4]

### **Transformada Wavelet**
Descompone una señal en función de funciones llamadas wavelets, que son pequeñas funciones con una forma particular. La principal característica de la transformada wavelet es que las wavelets son localizadas en el tiempo y la frecuencia, lo que significa que pueden capturar detalles tanto en el dominio del tiempo como en el dominio de la frecuencia en una señal. Esto la hace especialmente adecuada para analizar señales que contienen características que cambian con el tiempo, como se  muestra en la Figura 6 [5]. 

![image](https://github.com/ldachirre/IntroSenalesBiomedicas/assets/67986101/edfc34ed-f507-468e-b687-f201a1b1ada2)                   
Figura 6. Transformada Wavelet [5]

## **Objetivos** <a name="id2"></a>
- Diseñar un 3 tipos de filtros diferentes IIR , FIR y Wavelet
- Filtrar las señales de ECG, EMG y EEG obtenidas en laboratorios pasados
- Analizar la capacidad de cada filtro para limpiar la señal de interés

## **Filtrado ECG** <a name="id3"></a>
En el código proporcionado, se llevó a cabo un proceso de filtrado de la señal de electrocardiograma (ECG) del "sujeto 3 activo" del laboratorio de electrocardiografía. El objetivo del filtrado es mejorar la calidad de la señal ECG y reducir el ruido no deseado.
| Creación de Filtros|
| :---:  |
![ECG FILTRADO](https://github.com/ldachirre/IntroSenalesBiomedicas/assets/90112793/d4b6d196-c8c2-4486-9435-c4cd81e859f1)


| Señal |
| :---:  |
![WhatsApp Image 2023-10-19 at 4 21 42 PM (1)](https://github.com/ldachirre/IntroSenalesBiomedicas/assets/90112793/6bdbb4fd-9a10-4940-bbcf-946ea9d9bc71)

En base a la observación de las señales resultantes y las respuestas en frecuencia presentadas en el código,se observa que la señal resultante del filtro wavelet parece mostrar un escalado peculiar, y es evidente que persiste cierto nivel de ruido o distorsión en la señal. Sin embargo,tanto el filtro FIR como el filtro IIR tienden a preservar mejor la forma de onda de la señal original. Por lo que se puede concluir que para esta señal de electrocardiograma (ECG) específica, los filtros FIR e IIR (Butterworth) parecen ser más adecuados en comparación con el filtro wavelet.

## **Filtrado EMG** <a name="id4"></a>
| Señal |
| :---:  |

## **Filtrado EEG** <a name="id5"></a>
| Señal |
| :---:  |
  

## **Conclusiones** <a name="id6"></a>
- Se comprobó que el filtrado con el filtro IIR son menos eficientes que con el filtro FIR, ya que estos ultimos son más estables, lo que los hace más adecuados para esta aplicación.
- Después de aplicar el proceso de filtrado a las señales, se notaron mejoras significativas, incluyendo la reducción del ruido y la amplitud no deseada, lo que resultó en una señal más clara y con los componentes de interés de manera más destacada.

## **Referencias** <a name="id7"></a>
[1]    	J. Cedillo et al., “IMPLEMENTATION OF DIGITAL FILTERS OF FIR TYPE IN FPGA Implementación de Filtros Digitales Tipo FIR en FPGA,” vol. 37, 2008, Available: https://www.scielo.org.mx/pdf/poli/n37/n37a12.pdf

[2]    	JuanS, “IIR vs FIR: Entendiendo realmente sus diferencias,” JuanSaudio, Apr. 23, 2020. https://www.juansaudio.com/post/iir-vs-fir-entendiendo-realmente-sus-diferencias (accessed May 04, 2023).

[3] 	   “Window function - figure of merits - GaussianWaves”. Accedido: 14 de octubre de 2023. [En línea]. Disponible en: https://www.gaussianwaves.com/2020/09/window-function-figure-of-merits/

[4] 	   JuanS, “IIR vs FIR: Entendiendo realmente sus diferencias,” JuanSaudio, Apr. 23, 2020. https://www.juansaudio.com/post/iir-vs-fir-entendiendo-realmente-sus-diferencias (accessed May 04, 2023).

[5]      I. J. Rubén y A. Montoya, “LA TRANSFORMADA WAVELET”.
