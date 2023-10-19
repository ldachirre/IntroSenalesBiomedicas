# **LABORATORIO 3: – USO DE BITalino PARA EMG y ECG**
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

## **Introducción** <a name="id1"></a>
El presente laboratorio busca analizar la actividad eléctrica de los músculos del brazo mediante señales EMG a través de electrodos de superficie. Se compararán las señales del músculo en reposos y en conrtacción para comprobar la diferencia en la actividad muscular en estos casos.

## **Objetivos** <a name="id2"></a>
* Adquirir señales biomédicas de EMG y ECG.
* Hacer una correcta configuración de BiTalino.
* Extraer la información de las señales EMG y ECG del software OpenSignals (r)evolution

## **Materiales y equipos** <a name="id3"></a>

<div align="center">

|  **Modelo**  | **Descripción** | **Cantidad** |
|:------------:|:---------------:|:------------:|
| (R)EVOLUTION |   Kit BITalino  |       1      |
|       -      |      Laptop     |       1      |

</div>

<p align="justify">

## **Características de los sujetos de prueba** <a name="id4"></a>
<div align="center">

|          | **Edad** | **Sexo** | **Frec. act. física** | **Intensidad act.** | **Condición Física** | **IMC** |
|:--------:|:--------:|:--------:|:---------------------:|:-------------------:|:--------------------:|:-------:|
| Sujeto 1 |    22    |     F    |           3           |        Media        |         Sano         |   21.9  |
| Sujeto 2 |    21    |     M    |           2           |        Fuerte        |         Sano        |    27   |
| Sujeto 3 |    21    |     M    |           2           |        Media        |         Asma         |    25   |
| Sujeto 4 |    21    |     M    |           3           |        Media        |         Sano         |    28   |

</div>

<p align="justify">

## **Metodología** <a name="id5"></a>
Se tomó los datos de los participantes en las pruebas de EMG del presente laboratorio, posteriormente se midió su actividad muscular del brazo en reposo y en contracción y posteriormente mostrarlas en gráficas en Python.

1. Toma de las señales en reposo
<p align="center"><img src="/ISB/Images/sujetoreposo.jpg" width="600" height="400"></p>


https://github.com/ldachirre/IntroSenalesBiomedicas/assets/56425258/9bade6f9-01c4-4ec4-b59a-020df3f3c808





2. Toma de las señales en contracción
<p align="center"><img src="/ISB/Images/sujetocontraccion.jpg" width="600" height="400"></p>



https://github.com/ldachirre/IntroSenalesBiomedicas/assets/56425258/8f6fdf56-915a-4c6e-a60d-f375c078741a



3. Código del plot de señales en python

```
#Luis Contraido

import numpy as np
import matplotlib.pyplot as plt

# Nombre de tu archivo TXT
archivo_txt = "Luiscontraido.txt"

# Cargar los datos desde el archivo TXT
datos_emg = np.loadtxt(archivo_txt)

# Extraer la sexta columna de datos_emg
# recordamos que el archivo txt me da informacion de todas las entradas del bitalino pero 
# la única que nos interesa es la que se encuentra en el encabezado A1
columna_sexta = datos_emg[:, 5]  # El índice 5 representa la sexta columna (0-indexed)

# Crear un arreglo de tiempo en segundos
frecuencia_muestreo = 1000  # Frecuencia de muestreo en Hz
tiempo = np.arange(len(columna_sexta)) / frecuencia_muestreo

# Definir el intervalo de tiempo que deseas graficar (segundos 6 al 7)
inicio_segundo = 6
fin_segundo = 7
inicio_muestra = int(inicio_segundo * frecuencia_muestreo)
fin_muestra = int(fin_segundo * frecuencia_muestreo)

# Extraer los datos del intervalo de tiempo especificado
tiempo_intervalo = tiempo[inicio_muestra:fin_muestra]
columna_intervalo = columna_sexta[inicio_muestra:fin_muestra]

# Crear el gráfico
plt.figure(figsize=(10, 4))  # Ajusta el tamaño del gráfico según tus necesidades
plt.plot(tiempo, columna_sexta, lw=1, color='blue')
plt.xlabel('Tiempo (s)')
plt.ylabel('Valor EMG ')
plt.title('Datos de EMG (Luis Contraído)')
plt.grid(True)

# Mostrar el gráfico
plt.show()


# Crear el gráfico para los datos del intervalo de tiempo especificado
plt.figure(figsize=(10, 4))  # Ajusta el tamaño del gráfico según tus necesidades
plt.plot(tiempo_intervalo, columna_intervalo, lw=1, color='blue')
plt.xlabel('Tiempo (s)')
plt.ylabel('Valor EMG (Sexta Columna)')
plt.title('Datos de EMG Contracción Muscular (Segundos 6 al 7)')
plt.grid(True)

# Mostrar el gráfico
plt.show()

```
## **Resultados** <a name="id6"></a>
* Sujeto 1: Katherine <a id="sujeto-1"></a>
<p align="center"><img src="/ISB/Images/kathrelajado.jpg" width="600" height="300"></p>
<p align="center"><img src="/ISB/Images/kathcontraido.jpg" width="600" height="300"></p>

* Sujeto 2: Luis <a id="sujeto-2"></a>
<p align="center"><img src="/ISB/Images/luisrelajado.jpg" width="600" height="300"></p>
<p align="center"><img src="/ISB/Images/luiscontraido.jpg" width="600" height="300"></p>

* Sujeto 3: Italo <a id="sujeto-3"></a>
<p align="center"><img src="/ISB/Images/paezrelajado.jpg" width="600" height="300"></p>
<p align="center"><img src="/ISB/Images/paezcontraido.jpg" width="600" height="300"></p>

* Sujeto 4:  Dante <a id="sujeto-4"></a>
<p align="center"><img src="/ISB/Images/danterelajado.jpg" width="600" height="300"></p>
<p align="center"><img src="/ISB/Images/dantecontraido.jpg" width="600" height="300"></p>
