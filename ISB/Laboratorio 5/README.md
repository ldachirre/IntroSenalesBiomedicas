# **LABORATORIO 5: USO DE BITalino PARA ECG**
# **Tabla de contenidos**

1. [Introducción](#id1)
2. [Objetivos](#id2)
3. [Materiales y equipos](#id3)
4. [Características de los sujetos de prueba](#id4)
5. [Metodología](#id5)
6. [Resultados](#id6)
   - [Sujeto 1](#sujeto-1)
   - [Sujeto 2](#sujeto-2)
   - [Sujeto 3](#sujeto-3)
   - [Sujeto 4](#sujeto-4)
7. [Referencias](#id7)
   
## **Introducción** <a name="id1"></a>

La electrocardiografía (ECG) es una señal biológica que registra el proceso de latido del corazón mediante la medición del voltaje a lo largo del tiempo. Se realiza mediante la colocación de electrodos externos en la piel humana [1]. La ECG se utiliza principalmente para obtener información sobre la frecuencia cardíaca (pulso cardíaco), el ritmo y la actividad eléctrica del corazón. Esta técnica captura los puntos clave del cuerpo humano y genera una señal de voltaje cuasiperiódica no lineal y no estacionaria [2]. Asimismo, la ECG ofrece la ventaja de ser un procedimiento de bajo costo y de respuesta inmediata. Para registrar un ECG, se mide la diferencia de potencial entre los electrodos que se colocan en la piel del paciente. Esta medición permite obtener una representación gráfica de los impulsos eléctricos del corazón, lo que proporciona información valiosa sobre su funcionamiento [3].

La señal de ECG tiene una amplitud pequeña, típicamente 2.5 mV en un entorno de desplazamiento de 400 mV, y los componentes de frecuencia de una señal de ECG típica están en el rango de 0.05–150 Hz [4]. Cada señal de ECG tiene puntos fiduciales (P, Q, R, S, T, U) y varios intervalos (S-T, Q-T, P- R, R-R) [3], como se observa en la Figura 1.

- La onda P es el resultado de la despolarización de la aurícula y el ventrículo provoca el resto de picos.
- Intervalo PR representa el tiempo desde el comienzo de la despolarización auricular hasta el comienzo de la despolarización ventricular e incluye el retraso en el nodo AV.
-El complejo QRS es la despolarización de ambos ventrículos cardiacos, utilizado como punto de referencia para el análisis de señales.
- El intervalo QT es un indicador de la repolarizacíón ventricular
- El segmento ST representa el final de la despolarización ventricular y el comienzo de la repolarización ventricular
- La onda Q representa la despolarización del tabique interventricular.
- La onda R representa el estímulo eléctrico a medida que pasa por los ventrículos durante la despolarización.
- La onda S representa la despolarización final de las fibras de Purkinje.
- La onda T representa la repolarización ventricular [3].


<p align="center"><img src="/ISB/Images/ecg/ondaqt.png" width="600" height="600"></p>
Figura 1. Análisis de la señal ECG []

## **Objetivos** <a name="id2"></a>

- Adquirir señal biomédica de ECG.
- Hacer una correcta configuración de BiTalino.
- Extraer la información de la señal ECG del software OpenSignals (r)evolution
  
## **Materiales y equipos** <a name="id3"></a>

| Material   | Imagen   |
|:-------------: |:---------------:| 
| **BITalino** es un kit de herramientas de prototipado rápido para proyectos de salud y bienestar personal. Incluye sensores inalámbricos y una plataforma de software para adquirir, procesar y visualizar datos biomédicos         | ![lot](https://camo.githubusercontent.com/d4a44aa322d672288a9f7497916a86b024eaa53d3fa5c9b670ee08258c660f22/68747470733a2f2f63646e2e737061726b66756e2e636f6d2f2f6173736574732f70617274732f312f312f382f322f382f31343032322d3031612e6a7067)       |
| **Fluke ProSim 4 Vital Signs Patient Simulator** es un simulador de paciente que imita los signos vitales del paciente, como la presión arterial, la frecuencia cardiaca y la respiración, para ayudar en el entrenamiento y prueba de equipos médicos          | ![m](https://www.flukebiomedical.com/sites/default/files/styles/slideshow_image/public/prosim4front_0.png)          |
| **OpenSignals Software**: Se puede conectar mediante Bluetooth a la placa BITalino y permite adquirir y visualizar bioseñales          | ![bi](https://cdn.shopify.com/s/files/1/0595/1068/5887/t/6/assets/opensignalshorizontallogocoloralpha-1-1649366393124.png?v=1649366394)      |
***

## **Características de los sujetos de prueba** <a name="id4"></a>
## **Metodología** <a name="id5"></a>
## **Resultados** <a name="id6"></a>
## **Referencias** <a name="id7"></a>
[1]	A. Sheta et al., «Diagnosis of Obstructive Sleep Apnea from ECG Signals Using Machine Learning and Deep Learning Classifiers», Applied Sciences 2021, Vol. 11, Page 6622, vol. 11, n.o 14, p. 6622, jul. 2021, doi: 10.3390/APP11146622.

[2]	S. Chatterjee, R. S. Thakur, R. N. Yadav, L. Gupta, y D. K. Raghuvanshi, «Review of noise removal techniques in ECG signals», IET Signal Processing, vol. 14, n.o 9, pp. 569-590, dic. 2020, doi: 10.1049/IET-SPR.2020.0104.

[3]	J. Aspuru et al., «Segmentation of the ECG Signal by Means of a Linear Regression Algorithm», Sensors 2019, Vol. 19, Page 775, vol. 19, n.o 4, p. 775, feb. 2019, doi: 10.3390/S19040775.

[4]	A. : Meyer, H. A. Brochero, y C. A. Rojas, «SISTEMA PARA EL MONITOREO DE EPISODIOS DE LA APNEA DEL SUEÑO».
