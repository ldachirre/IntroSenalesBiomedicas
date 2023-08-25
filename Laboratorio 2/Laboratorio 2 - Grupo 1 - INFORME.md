
**Introducción a señales biomédicas**
![UPCH - UNIVERSIDAD PERUANA CAYETANO HEREDIA - PORTAL INSTITUCIONAL](Aspose.Words.d9afab2e-0b38-426f-bd70-e3cee72174d5.001.png)	![](Aspose.Words.d9afab2e-0b38-426f-bd70-e3cee72174d5.002.png)

# **LABORATORIO 2 – ADQUISICIÓN DE SEÑALES Y GRAFICACIÓN EN ARDUINO**

1. # **Integrantes del GRUPO 1**
   * Katherine Zorrilla - kpzorrilla@pucp.edu.pe
   * Dante Rodriguez - a20203483@pucp.edu.pe
   * Luis Chirre - luis.chirre@upch.pe
   * Diego Palacios - <d.palaciose@pucp.edu.pe>

1. # **Entregables**

0. Plotear al menos 3 señales en Arduino IDE provenientes del generador de señales.
0. Comparar las señales graficadas del Arduino IDE con las gráficas obtenidas del osciloscopio.
0. Graficar en Arduino cloud.

**Configuración inicial del Osciloscopio**

![](Aspose.Words.d9afab2e-0b38-426f-bd70-e3cee72174d5.003.png)

![](Aspose.Words.d9afab2e-0b38-426f-bd70-e3cee72174d5.004.png)

**Configuración inicial del generador de señales**

![](Aspose.Words.d9afab2e-0b38-426f-bd70-e3cee72174d5.005.png)



**Señales generadas**

Onda sinusoidal generada:

![](Aspose.Words.d9afab2e-0b38-426f-bd70-e3cee72174d5.006.png)

Onda sinusoidal a 500Hz En el Serial Plotter de Arduino IDE:

![](Aspose.Words.d9afab2e-0b38-426f-bd70-e3cee72174d5.007.png)



Onda cuadrada generada:

![](Aspose.Words.d9afab2e-0b38-426f-bd70-e3cee72174d5.008.png)

Onda cuadrada a 500Hz En el Serial Plotter de Arduino IDE:




Onda triangular generada:

![](Aspose.Words.d9afab2e-0b38-426f-bd70-e3cee72174d5.009.png)

Onda triangular a 500Hz En el Serial Plotter de Arduino IDE:


Código utilizado  de Arduino :

const int analogPin = A0;    // Analog input pin

const int numSamples = 100;  // Number of samples to collect

const int sampleInterval = 500; // Time between samples in milliseconds

void setup() {

`  `Serial.begin(9600);

}

void loop() {

`  `for (int i = 0; i < numSamples; i++) {

`    `int sensorValue = analogRead(analogPin);

`    `float voltage = sensorValue \* (5.0 / 1023.0); // Convert to voltage (5V reference, 10-bit ADC)

`    `Serial.println(voltage, 4); // Print voltage value with 4 decimal places

`    `delay(sampleInterval);

`  `}

`  `Serial.println(); // Separate readings from different sweeps

`  `delay(1000);      // Delay between sweeps

}













Moises Meza | Lewis De La Cruz Versión 01 | 2023

Página  PAGE 1 de 7
![](Aspose.Words.d9afab2e-0b38-426f-bd70-e3cee72174d5.010.png)![](Aspose.Words.d9afab2e-0b38-426f-bd70-e3cee72174d5.011.png)
