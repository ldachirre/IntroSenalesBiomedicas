# LABORATORIO 11: Edge Impulse.
# **Tabla de contenidos**

1. [Introducción](#id1)
2. [Objetivos](#id2)
3. [Metodología](#id3)
4. [Resultados](#id4)
5. [Conclusiones](#id5)
6. [Referencias](#id6)
   
## **Introducción** <a name="id1"></a>

### **¿Qué es Edge Impulse ?**
Edge Impulse es una plataforma integral de desarrollo de aprendizaje automático que se especializa en la creación e implementación de modelos de inteligencia artificial (IA) en dispositivos con recursos limitados, como microcontroladores y dispositivos IoT (Internet de las cosas). La plataforma facilita la recopilación, el procesamiento y el entrenamiento de datos para construir modelos de aprendizaje automático personalizados, centrándose en la inferencia en el "borde" (edge), es decir, directamente en el dispositivo en lugar de depender de recursos en la nube.

Edge Impulse ofrece una interfaz amigable que permite a los desarrolladores, incluso aquellos sin una experiencia extensa en aprendizaje automático, diseñar y desplegar modelos de forma eficiente. Facilita la integración de la IA en una variedad de aplicaciones prácticas, como sistemas de monitoreo, dispositivos médicos, wearables y otros dispositivos conectados.  [1]

![ei_cycle_d_e59c64ebeda3ccc80fa9a298cd0835f2_944901ad41](https://github.com/ldachirre/IntroSenalesBiomedicas/assets/90112793/8ae14947-01e1-41e3-9a97-ff6f1c258101)


> Figura 1. "Getting Started with Edge Impulse." Evan Rust. TINYML. 

En este entregable se analizarán las señales obtenidas



## **Objetivos** <a name="id2"></a>


1. **Desarrollar un modelo** que pueda reconocer y clasificar la contracción muscular en el bíceps basados en patrones de actividad EMG.

2. **Analizar la duración de la contracción muscular** en el bíceps y desarrollar un modelo que pueda reconocer patrones temporales.


## **Metodología** <a name="id3"></a>
## Metodología

1. **Adquisición de Datos:**
   - Utilizamos sensores de EMG para recopilar datos durante contracciones del bíceps en un laboratorio de prototipado. Los datos recopilados en este laboratorio son los utilizados en este modelo.

2. **Exportación de Datos:**
   - Seguidamente, exportamos la data en formato .txt (el mismo formato que guarda el programa OpenSignals) a un archivo .csv para que pueda ser leído por Edge Impulse.

3. **Etiquetado de Datos:**
   - Asignamos etiquetas a cada grabación, indicando la intensidad de la contracción y la duración correspondiente. Esto facilita el entrenamiento supervisado del modelo.

4. **Preprocesamiento de Datos:**
   - Aplicamos técnicas de preprocesamiento, como filtrado, normalización y extracción de características, para preparar los datos para el entrenamiento del modelo.

5. **Desarrollo del Modelo:**
   - Seleccionamos un modelo de aprendizaje automático apropiado y ajustamos sus parámetros utilizando el conjunto de datos de entrenamiento.

6. **Evaluación del Modelo:**
   - Evaluamos el rendimiento del modelo utilizando el conjunto de datos de prueba para asegurarnos de que generalice bien a datos no vistos durante el entrenamiento.

7. **Documentación:**
   - Documentamos todos los aspectos del proceso, desde la adquisición de datos hasta la configuración del modelo, para facilitar la comprensión y replicación de nuestro trabajo.




## **Resultados** <a name="id4"></a>





## **Conclusiones** <a name="id5"></a>
- El filtrado de señales EEG permitió eliminar el ruido de las señales EEG. Esto facilitó la identificación de patrones de actividad cerebral asociados a los diferentes escenarios en los que se registraron las señales EEG.
- En este caso, la detección de ERP permitió identificar diferencias en la actividad cerebral entre los diferentes escenarios. En particular, se observaron diferencias significativas en los ERP asociados a la presentación de preguntas matemáticas difíciles y fáciles.
- La extracción de ondas alfa mostró que la amplitud de las ondas alfa es mayor en estado de reposo que en los otros escenarios. Esto es consistente con la literatura científica, que muestra que las ondas alfa están asociadas a un estado de relajación y atención relajada.


## **Referencias** <a name="id6"></a>
[1] S. U. C. M. Ehrotra, Introduction To EEG- and Emotion Recognition. 2018. Accedido: 30 de septiembre de 2023. [En línea]. Disponible en: http://www.sciencedirect.com:5070/book/9780128044902/introduction-to-eeg-and-speech-based-emotion-recognition

[2] W. A. W Azlan and Y. F. Low, "Feature extraction of electroencephalogram (EEG) signal - A review," 2014 IEEE Conference on Biomedical Engineering and Sciences (IECBES), Kuala Lumpur, Malaysia, 2014, pp. 801-806, doi: 10.1109/IECBES.2014.7047620.

[3] S. Sur and V. Sinha, “Event-related potential: An overview,” vol. 18, no. 1, pp. 70–70, Jan. 2009, doi: https://doi.org/10.4103/0972-6748.57865.

[4] Graetzer, D. G., PhD. (2023). Electroencephalography (EEG). Magill’s Medical Guide (Online Edition). Disponible en: https://research-ebsco-com.ezproxybib.pucp.edu.pe/c/d6owsy/details/cdlxy7ttnv



