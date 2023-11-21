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

**Training 2 labels**

**Espectral Features**
![Imagen de WhatsApp 2023-11-20 a las 22 54 57_91ed5d5f](https://github.com/ldachirre/IntroSenalesBiomedicas/assets/56425258/48f08af5-85d5-4fab-8631-b8003fd4d8f5)
![2](https://github.com/ldachirre/IntroSenalesBiomedicas/assets/56425258/fa74f2e9-c5ce-4eda-b670-bc0e7d3d34c3)

**Classifier**
![4](https://github.com/ldachirre/IntroSenalesBiomedicas/assets/56425258/5cdeaf34-a519-48ac-a917-3700407a171d)
![3](https://github.com/ldachirre/IntroSenalesBiomedicas/assets/56425258/2eefb2b0-739f-4844-ae0a-e8f8c27f57d7)

**Training 4 labels**
**Spectral Features**
![6](https://github.com/ldachirre/IntroSenalesBiomedicas/assets/56425258/54a457b7-9971-43e9-8470-3aa7ef5b0c4b)
![5](https://github.com/ldachirre/IntroSenalesBiomedicas/assets/56425258/7184a3c8-01e2-403c-a66c-884a6720b042)

**Classifier**
![7](https://github.com/ldachirre/IntroSenalesBiomedicas/assets/56425258/b3423e4a-5502-4212-b458-01fca717810b)


## **Conclusiones** <a name="id5"></a>



## **Referencias** <a name="id6"></a>
[1] S. U. C. M. Ehrotra, Introduction To EEG- and Emotion Recognition. 2018. Accedido: 30 de septiembre de 2023. [En línea]. Disponible en: http://www.sciencedirect.com:5070/book/9780128044902/introduction-to-eeg-and-speech-based-emotion-recognition

[2] W. A. W Azlan and Y. F. Low, "Feature extraction of electroencephalogram (EEG) signal - A review," 2014 IEEE Conference on Biomedical Engineering and Sciences (IECBES), Kuala Lumpur, Malaysia, 2014, pp. 801-806, doi: 10.1109/IECBES.2014.7047620.

[3] S. Sur and V. Sinha, “Event-related potential: An overview,” vol. 18, no. 1, pp. 70–70, Jan. 2009, doi: https://doi.org/10.4103/0972-6748.57865.

[4] Graetzer, D. G., PhD. (2023). Electroencephalography (EEG). Magill’s Medical Guide (Online Edition). Disponible en: https://research-ebsco-com.ezproxybib.pucp.edu.pe/c/d6owsy/details/cdlxy7ttnv



