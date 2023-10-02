# LABORATORIO 5: Procedimiento de registro EEG*
# **Tabla de contenidos**

1. [Introducción](#id1)
2. [Objetivos](#id2)
3. [Materiales y equipos](#id3)
4. [Procedimiento](#id4)\
4.1 [Medición y Adquisición por electrodos](#id5)\
4.2 [Protocolo de adquisición](#id6)
5. [Resultados](#id7)\
5.1 [Fotos de conexión usada](#id8)\
5.2 [Señal con MarckOpenBCI4](#id9)\
    5.2.1 [Gráficas del OpenBCI](#id10)\
5.3 [Señal con Bitalino](#id11)\
    5.3.1 [Videos utilizando el Bitalino](#id12)\
    5.3.2 [Análisis de gráficas](#id13)
6. [Conclusiones](#id14)
7. [Referencias](#id15)
   
## **Introducción** <a name="id1"></a>

El cerebro humano está formado por alrededor de 85.000 millones de neuronas que desempeñan un papel fundamental en la comunicación a través de conexiones llamadas sinapsis que se encuentran en los extremos de los axones. Estas neuronas transmiten información mediante la liberación de neurotransmisores, lo que provoca cambios en el voltaje en la membrana celular. Esto da lugar a la generación de un campo eléctrico que dura solo unos cientos de milisegundos, conocido como potencial postsináptico. [1]

El sistema nervioso es una compleja red de estructuras especializadas que regula el funcionamiento de los órganos y sistemas del cuerpo, así como la interacción del organismo con el entorno. Este sistema está diseñado para generar respuestas a cambios tanto internos como externos, evaluando la información que recibe. [2]

El cerebro humano se divide en cuatro áreas principales conocidas como lóbulos: el frontal (en naranja), el temporal (en verde), el parietal (en azul) y el occipital (en amarillo), como se muestra en la Figura 1. Cada uno de estos lóbulos se ha subdividido y se asocia con funciones cerebrales específicas. Nos centraremos en el lóbulo frontal en este laboratorio, ya que es responsable de controlar los movimientos voluntarios, tomar decisiones, llevar a cabo procesos cognitivos como la planificación y la atención, y se considera el centro de nuestra personalidad. [3]

![cerebro3](https://github.com/ldachirre/IntroSenalesBiomedicas/assets/67986101/9b5bad24-51b3-472c-90a7-c169ae1ecd13)
Figura 1. El cerebro y sus lóbulos superficiales [3]

Un electroencefalograma (EEG) es un procedimiento médico que registra la actividad eléctrica en el cerebro utilizando electrodos colocados en el cuero cabelludo o cerca de la parte superior de la cabeza. Las neuronas en el cerebro se comunican entre sí mediante impulsos eléctricos que están en constante actividad. Esta actividad se representa como patrones de ondas en el registro del EEG. [4]
El sistema de colocación de electrodos denominado "internacional 10-20" se utiliza para posicionar los electrodos en lugares estandarizados identificados por las letras F (frontal), C (central), P (parietal), T (temporal) y O (occipital) en el cuero cabelludo. El EEG se emplea para diagnosticar diversos trastornos, como convulsiones, problemas en el tronco encefálico, lesiones cerebrales y alteraciones en el estado de conciencia. Las señales eléctricas generadas por la actividad cerebral normal presentan amplitudes atípicas en el rango de 30 a 100 milivoltios y exhiben variaciones irregulares en el tiempo. El EEG permite medir cinco sub-bandas de frecuencia que definen las frecuencias de las señales cerebrales, desde las más rápidas, conocidas como gamma, hasta las más lentas, denominadas delta, como se ilustra en la Figura 2. [5]

![Captura de pantalla 2023-10-01 200816](https://github.com/ldachirre/IntroSenalesBiomedicas/assets/67986101/3491545d-f923-4ba3-9c86-8a0a17b9562d)
Figura 2. EEG bandas de frecuencia, ocurrencia y tareas para activar la potencia de banda [3]
