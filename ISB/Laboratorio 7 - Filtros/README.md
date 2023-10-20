# LABORATORIO 7: Filtrado de Señales Biológicas
# **Tabla de contenidos**

1. [Introducción](#id1)
2. [Objetivos](#id2)
3. [Procedimiento](#id3)
4. [Resultados](#id4)
5. [Conclusiones](#id5)
6. [Referencias](#id6)
   
## **Introducción** <a name="id1"></a>
En los sistemas eléctricos y electrónicos, en ciertas ocasiones, se necesita manejar información a ciertas frecuencias; es por esto que solo se deja pasar a ciertos grupos de frecuencias y las demás se eliminan. Esta función la realizan los filtros que son sistemas electrónicos que presentan características selectivas de frecuencias. Un filtro se define como un sistema que discrimina una señal de entrada y produce cambios en su salida, siendo estos cambios determinados por ciertos parámetros. Los filtros operan tomando una señal de entrada y generan una señal de salida, asimismo existen dos tipos de filtros: analógicos y digitales. Esta señal de salida experimenta modificaciones en términos de su amplitud, frecuencia o fase, dependiendo de las características específicas del filtro [1]. En comparación con los filtros analógicos, los filtros digitales tienen una amplia aplicación en la actualidad, debido en parte a la facilidad de acceso a las computadoras, y a su capacidad de almacenamiento y registro.

### **Filtros FIR (Finite Impulse Response)**
Se diferencia por su respuesta al impulso de duración finita, lo que significa que su salida se calcula como una suma ponderada de un número limitado de muestras de entrada y coeficientes del filtro, como se muestra en la Figura 1. Son predecibles y fáciles de analizar, y se ajustan según las necesidades de filtrado. Los filtros FIR son útiles para filtrar señales, reducir ruido y procesar audio e imágenes. Su ventaja clave es que proporcionan una respuesta de fase lineal, es decir, tiene un retardo de tiempo puro como respuesta de fase, y que es estable, por lo que siempre que la entrada del filtro esté acotada, la salida de este también lo estará. Estas propiedades ayudan al diseño de filtros FIR para que cumplan con ciertas especificaciones necesarias lo que es esencial en aplicaciones donde la precisión de la fase es crucial, como en sistemas de comunicación y audio de alta calidad [2].

![image](https://github.com/ldachirre/IntroSenalesBiomedicas/assets/67986101/fe76f0f7-cc84-4a57-bcd1-e0bf438f78dd)
Figura 1. Filtro FIR [2]

Uno de los métodos de diseño de filtros FIR es el uso de ventanas ("windowing"). Este se basa en acortar la respuesta en impulsos de la señal, mediante la multiplicación de la señal con la ventana. Existen diferentes tipos de ventanas, entre las más conocidas tenemos: Barthann, Barlett, Blackman y Blackmanharris, como se observa en la Figura 2 y 3 [3]. 
![image](https://github.com/ldachirre/IntroSenalesBiomedicas/assets/67986101/5da3795e-183d-429a-8f3a-056678011e44)
Figura 2. Funciones de "windowing" [3]

![image](https://github.com/ldachirre/IntroSenalesBiomedicas/assets/67986101/ed0246fb-8227-4ea9-9ef4-02e303967279)
Figura 3. Ventanas de filtro FIR [3]

### **Filtros IIR**



## **Objetivos** <a name="id2"></a>
- Diseñar un IIR eligiendo si es Bessel, Butterworth, Chebyshev o Eliptico.
- Elegir 2 métodos de ventana para diseñar un filtro FIR.
- Filtrar el Dataset de las señales ECG realizado en el laboratorio anterior.

## **Procedimiento** <a name="id3"></a>

### **Medición y Adquisición por electrodos** <a name="id5"></a>



#### ULTRACORTEX:



## **Resultados** <a name="id4"></a>



## **Conclusiones** <a name="id15"></a>


## **Referencias** <a name="id6"></a>
[1]    	J. Cedillo et al., “IMPLEMENTATION OF DIGITAL FILTERS OF FIR TYPE IN FPGA Implementación de Filtros Digitales Tipo FIR en FPGA,” vol. 37, 2008, Available: https://www.scielo.org.mx/pdf/poli/n37/n37a12.pdf

[2]    	JuanS, “IIR vs FIR: Entendiendo realmente sus diferencias,” JuanSaudio, Apr. 23, 2020. https://www.juansaudio.com/post/iir-vs-fir-entendiendo-realmente-sus-diferencias (accessed May 04, 2023).

[3] 	   “Window function - figure of merits - GaussianWaves”. Accedido: 14 de octubre de 2023. [En línea]. Disponible en: https://www.gaussianwaves.com/2020/09/window-function-figure-of-merits/

[4] 	
Accedido: 30 de septiembre de 2023. [En línea]. Disponible en:
https://search-ebscohost-com.ezproxybib.pucp.edu.pe/login.aspx?direct=true&db=ers&AN=87690502&lang=es&site=eds-live&scope=site

[5]    	S. U. C. M. Ehrotra, Introduction To EEG- and Emotion Recognition. 2018. Accedido: 30 de septiembre de 2023. [En línea]. Disponible en: http://www.sciencedirect.com:5070/book/9780128044902/introduction-to-eeg-and-speech-based-emotion-recognition
