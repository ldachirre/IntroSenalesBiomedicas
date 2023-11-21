# LABORATORIO 11: Edge Impulse
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
   - Seguidamente, exportamos la data en formato .txt (el mismo formato que guarda el programa OpenSignals) a un archivo .csv para que pueda ser leído por Edge Impulse. Es necesario recalcar que el dataset a ser subido debe tener por lo menos 2 columnas una con los valores (características) a evaluar y el otro con el timestamp (no será evaluado pero genera un error si no hay por lo menos 2 columnas). [1]

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



---
## **Resultados** <a name="id4"></a>

Link de edge-impulse: https://studio.edgeimpulse.com/studio/311698/learning/keras/7

### **Training 2 labels**

Se subieron los modelos analizados por el laboratorio 4 donde se evaluaron los siguientes ejercicios de EMG: relajado y evaluado. Para esto nuestro modelo de ML fue inicialmente entrenado con un dataset un sujeto de prueba en 2 condiciones de ejercicio “relajado” y “contraído”.

**Espectral Features**
![Imagen de WhatsApp 2023-11-20 a las 22 54 57_91ed5d5f](https://github.com/ldachirre/IntroSenalesBiomedicas/assets/56425258/48f08af5-85d5-4fab-8631-b8003fd4d8f5)
> Figura 2. Características Espectrales, generación de características

![2](https://github.com/ldachirre/IntroSenalesBiomedicas/assets/56425258/fa74f2e9-c5ce-4eda-b670-bc0e7d3d34c3)
> Figura 3. Características Espectrales, importancia
**Classifier**

![4](https://github.com/ldachirre/IntroSenalesBiomedicas/assets/56425258/5cdeaf34-a519-48ac-a917-3700407a171d)
![3](https://github.com/ldachirre/IntroSenalesBiomedicas/assets/56425258/2eefb2b0-739f-4844-ae0a-e8f8c27f57d7)
---
### **Training 4 labels**

**Spectral Features**

![5](https://github.com/ldachirre/IntroSenalesBiomedicas/assets/56425258/7184a3c8-01e2-403c-a66c-884a6720b042)
![6](https://github.com/ldachirre/IntroSenalesBiomedicas/assets/56425258/54a457b7-9971-43e9-8470-3aa7ef5b0c4b)

**Classifier**

![7](https://github.com/ldachirre/IntroSenalesBiomedicas/assets/56425258/b3423e4a-5502-4212-b458-01fca717810b)
---
### Retraining
![8](https://github.com/ldachirre/IntroSenalesBiomedicas/assets/56425258/c4171648-2ff6-4324-a389-7dd5fce4d370)
![9](https://github.com/ldachirre/IntroSenalesBiomedicas/assets/56425258/103b8d8b-a108-44be-bdb2-40e44161a0e9)
![10](https://github.com/ldachirre/IntroSenalesBiomedicas/assets/56425258/dcbd78a9-b83e-4340-b2fe-f5b465a35259)

Se reentreno el modelo con la función "Retrain Model" donde se observa como aumenta la precision a 80% con una mejoria deo 0.6% con respecto a la primera vez y tambien se redujo la perdida de datos, en la gráfica creada se pueden diferenciar mejor los valores para cada label.

## **Conclusiones** <a name="id5"></a>
- A pesar del tamaño limitado del dataset, el modelo demostró una precisión notable en la diferenciación entre "músculo contraído" y "músculo relajado". Esto sugiere un potencial prometedor para aplicar el modelo en un conjunto de datos más grande y variado.
- Es importante señalar que los resultados se basan en un dataset pequeño con muestras de solo 2 sujetos. Esto limita la generalización de los resultados y puede haber cierto sesgo debido a la variabilidad interindividual. Por ello es recomendable ampliar la muestra para obtener resultados menos sesgados.


## **Referencias** <a name="id6"></a>
[1] Edge impulse (2021) Edge AI and Vision Alliance. Available at: https://www.edge-ai-vision.com/companies/edge-impulse/
[2] Abdalrahman (2022) Dataset from from 2 channels of the EMG sensor/unable to upload due to timestamp, Edge Impulse. Available at: https://forum.edgeimpulse.com/t/dataset-from-from-2-channels-of-the-emg-sensor-unable-to-upload-due-to-timestamp/4693
[3] Zachary / classification of EMG SIGINAL (no date) Classification of EMG siginal - Dashboard - Edge Impulse. Available at: https://studio.edgeimpulse.com/public/107747/latest




