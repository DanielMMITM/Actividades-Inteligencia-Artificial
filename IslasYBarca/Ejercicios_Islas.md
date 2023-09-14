# Ejercicio Granjero y animales:
Se tienen dos islas/lados, en una isla/lado se encuentra un granjero con una lechuza, un pollo y un coyote. La idea es pasar a todos los animales del otro lado (en este caso de lado izquierdo a lado derecho), el problema está en que no podemos dejar solo al pollo con la lechuza porque se la come y no podemos dejar al coyote con el pollo porque se lo come.

## Secuencia de percepción:
A continuación se muestra en una tabla el análisis de todos los posibles estados o situaciones del ejercicio de los animales, las cuales podríamos realizar en este ejercicio para llegar al estado final o estado ideal.

|        **Estado**       |    **Cruza solo**   | **Cruza con pollo** | **Cruza con lechuza** | **Cruza con coyote** |
|:-----------------------:|:-------------------:|:-------------------:|:---------------------:|:--------------------:|
| **estado(i, i , i, i)** |       problema      | estado (d, d, i, i) |        problema       |       problema       |
|  **estado(d, d, i, i)** | estado(i, d, i, i)  |  estado(i, i, i, i) |       imposible       |       imposible      |
|  **estado(i, d, i, i)** |  estado(d, d, i, i) |      imposible      |   estado(d, d, d, i)  |  estado(d, d, i, d)  |
|  **estado(d, d, d, i)** |       problema      |  estado(i, i, d, i) |   estado(i, d, i, i)  |       imposible      |
|  **estado(d, d, i, d)** |       problema      |  estado(i, i, i, d) |       imposible       |  estado(i, d, i, i)  |
|  **estado(i, i, d, i)** |       problema      |  estado(d, d, d, i) |       imposible       |  estado(d, i, d, d)  |
|  **estado(i, i, i, d)** |       problema      |  estado(d, d, i, d) |   estado(d, i, d, d)  |       imposible      |
|  **estado(d, d, d, i)** |       problema      |  estado(i, i, d, i) |   estado(i, d, i, i)  |       imposible      |
|  **estado(d, i, d, d)** |  estado(i, i, d, d) |      imposible      |   estado(i, i, i, d)  |  estado(i, i, d, i)  |
|  **estado(i, i, d, d)** |  estado(d, i, d, d) |  estado(d, d, d, d) |       imposible       |       imposible      |
|  **estado(d, d, d, d)** |       problema      |  estado(i, i, d, d) |        problema       |       problema       |

## Medida de rendimiento:
Podemos notar que no existe un solo camino, sin embargo, ambos caminos tienen el mismo número de estados y dan un buen rendimiento. Lo ideal es cruzar al pollo y regresar solo por la lechuza o el coyote, a partir de aqui varía las decisiones hasta cierto estado, cruzamos con la lechuza y regresamos al pollo a la barca para volver al lado izquierdo, del lado izquierdo dejamos al pollo y subimos al coyote para llevarlo al lado derecho. En este punto las dos soluciones vuelven a tener los mismos estados, ahora solo falta regresar al lado izquierdo y subir al pollo para finalmente llevarlo al lado derecho y llegar al estado ideal y final. Esta medida de rendimiento se lleva a cabo en 7 pasos.


# Ejercicio Monjes y Canibales: 
Para este ejercicio de los canibales se pide, encontrar la secuencia de percepción y la medida de rendimiento. Las reglas consisten en que hay 3 monjes y 3 canibales del mismo lado y tenemos que pasar a cada uno de ellos al otro lado (en este caso de lado izquierdo a lado derecho), el problema está en que si de un lado hay más canibales que monjes, estos se comeran o pelearan con los monjes.

## Secuencia de percepción: 
A continuación se muestra en una tabla el análisis de todos los posibles estados o situaciones para el ejercicio de monjes, las cuales podríamos realizar en este ejercicio para llegar al estado final o estado ideal.

|           **Estado**           |    **Cruza Canibal solo**   |     **Cruza Monje Solo**     |     **Cruzan 2 Canibales**    |     **Cruzan 2 Monjes**     | **Cruza 1 Monje y 1 Canibal** |
|:------------------------------:|:---------------------------:|:----------------------------:|:-----------------------------:|:---------------------------:|:-----------------------------:|
| **I (3 mI, 3 cI, 0 mD, 0 cD)** | I-D(3 mI, 2 cI, 0 mD, 1 cD) |  I-D(2 mI, 3 cI, 1 mD, 0 cD) |  I-D(3 mI, 1 cI, 0 mD, 2 cD)  |           problema          |  I-D(2 mI, 2 cI, 1 mD, 1 cD)  |
| **D (3 mI, 2 cI, 0 mD, 1 cD)** | D-I(3 mI, 3 cI, 0 mD, 0 cD) |           imposible          |           imposible           |          imposible          |           imposible           |
| **D (2 mI, 3 cI, 1 mD, 0 cD)** |          imposible          |  D-I(3 mI, 3 cI, 0 mD, 0 cD) |           imposible           |          imposible          |           imposible           |
| **D (3 mI, 1 cI, 0 mD, 2 cD)** | D-I(3 mI, 2 cI, 0 mD, 1 cD) |           imposible          |  D-I(3 mI, 3 cI, 0 mD, 0 cD)  |          imposible          |           imposible           |
| **I (3 mI, 2 cI, 0 mD, 1 cD)** |           problema          |  I-D(2 mI, 2 cI, 1 mD, 1 mD) |  I-D(3 mI, 0 cI, 0 mD, 3 cD)  |           problema          |            problema           |
| **D (3 mI, 0 cI, 0 mD, 3 cD)** | D-I(3 mI, 1 cI, 0 mD, 2 cD) |           imposible          |  D-I(3 mI, 2 cI, 0 mD, 1 cD)  |          imposible          |           imposible           |
| **D (2 mI, 2 cI, 1 mD, 1 cD)** |           problema          | D-I (3 mI, 2 cI, 0 mD, 1 cD) |           imposible           |          imposible          |  D-I(3 mI, 3 cI, 0 mD, 0 cD)  |
| **I (3 mI, 1 cI, 0 mD, 2 cD)** | I-D(3 mI, 2 cI, 0 mD, 1 cD) |           problema           |           imposible           | I-D(1 mI, 1 cI, 2 mD, 2 cD) |            problema           |
| **D (1 mI, 1 cI, 2 mD, 2 cD)** |           problema          |           problema           |            problema           | D-I(3 mI, 1 cI, 0 mD, 2 cD) |  D-I(2 mI, 2 cI, 1 mD, 1 cD)  |
| **I (2 mI, 2 cI, 1 mD, 1 cD)** |           problema          |           problema           |            problema           | I-D(0 mI, 2 cI, 3 mD, 1 cD) |  I-D(1 mI, 1 cI, 2 mD, 2 cD)  |
| **D (0 mI, 2 cI, 3 mD, 1 cD)** | D-I(0 mI, 3 cI, 3 mD, 0 cD) |           problema           |           imposible           | D-I(2 mI, 2 cI, 1 mD, 1 cD) |            problema           |
| **I (0 mI, 3 cI, 3 mD, 0 cD)** | I-D(0 mI, 2 cI, 3 mD, 1 cD) |           imposible          |  I-D(0 mI, 1 cI, 3 mD, 2 cD)  |          imposible          |           imposible           |
| **D (0 mI, 1 cI, 3 mD, 2 cD)** | D-I(0 mI, 2 cI, 3 mD, 1 cD) |  D-I(1 mI, 1 cI, 2 mD, 2 cD) |  D-I(0 mI, 3 cI, 3 mD, 0 cD)  |           problema          |            problema           |
| **I (0 mI, 2 cI, 3 mD, 1 cD)** | I-D(0 mI, 1 cI, 3 mD, 2 cD) |           imposible          |   I-D(0 mI, 0 cI, 3 mD, 3 cD) |          imposible          |           imposible           |
| **I (1 mI, 1 cI, 2 mD, 2 cD)** |           problema          |  I-D(0 mI, 1 cI, 3 mD, 2 cD) |           imposible           |          imposible          |  I-D(0 mI, 0 cI, 3 mD, 3 cD)  |
| **D (0 mI, 0 cI, 3 mD, 3 cD)** | D-I(0 mI, 1 cI, 3 mD, 2 cD) |           problema           |  D-I(0 mI, 2 cI, 3 mD, 1 cD)  |           problema          |  D-I(1 mI, 1 cI, 2 mD, 2 cD)  |
| **I (0 mI, 1 cI, 3 mD, 2 cD)** | I-D(0 mI, 0 cI, 3 mD, 3 cD) |           imposible          |           imposible           |          imposible          |           imposible           |

## Medida de rendimiento:
La medida de rendimiento que yo encontré fue de 11 pasos, iniciando por cruzar un monje y un canibal al lado derecho (2m, 2c, 1m, 1c), el monje regresa solo al lado izquierdo (3m, 2c, 0m, 1c), luego cruzan dos canibales del lado izquierdo al lado derecho (3m, 0c, 0m, 3c), ahora cruza un canibal solo del lado derecho al lado izquierdo (3m, 1c, 0m, 2c), cruzamos dos monjes del lado izquierdo al lado derecho (1m, 1c, 2m, 2c), luego cruzan 1 monje y un canibal del lado derecho al lado izquierdo (2m, 2c, 1m , 1c), ahora cruzan dos monjes del lado izquierdo al lado derecho y ya tenemos 3 monjes del lado derecho con un canibal y del lado izquierdo 2 canibales solamente. Después de esto, el canibal del lado derecho cruza al lado izquierdo (0m, 3c, 3m, 0c), y cruzan 2 canibales del lado izquierdo al lado derecho (0m, 1c, 3m, 2c), finalmente el canibal del lado derecho regresa al lado izquierdo por el tercer canibal y juntos regresan al lado derecho. De esta manera, llegamos de la manera más optima al estado final
