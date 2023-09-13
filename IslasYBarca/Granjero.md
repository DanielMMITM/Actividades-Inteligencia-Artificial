# Ejercicio Granjero y animales:
Se tienen dos islas/lados, en una isla/lado se encuentra un granjero con una lechuga, un pollo y un coyote. La idea es pasar 

## Secuencia de percepción
Primeramente, podemos pasar al pollo, de esa manera el coyote no se come la lechuga. Una vez que pasamos con el pollo lo podemos regresar o podemos dejarlo del otro lado pero no tendría sentido regresarlo 
porque estaríamos en el estado inicial, regresamos al lado izquierdo y podemos llevar la lechuga o el coyote realmente se llega al mismo estado, llevamos la lechuga del lado izquierdo al lado derecho y podríamos
dejar la lechuga y volvemos a subir al pollo para que éste no se la coma, regresamos con el pollo al lado izquierdo y lo dejamos para subir al coyote, si no, el coyote se comería al pollo, ahora, cruzamos con el
coyote y lo dejamos en el lado derecho junto con la lechuga, de esa manera no se come nadie a nadie y finalmente regresamos al lado izquierdo por el pollo y lo cruzamos al lado derecho.

| **Estado**              | **Cruza solo**      | **Cruza con pollo** | **Cruza con lechuga** | **Cruza con coyote** |
|-------------------------|---------------------|---------------------|-----------------------|----------------------|
| **estado(i, i , i, i)** |       problema      | estado (d, d, i, i) |        problema       |       problema       |
| **estado(d, d, i, i)**  | estado(i, d, i, i)  |  estado(i, i, i, i) |       imposible       |       imposible      |
| estado(i, i             |                     |                     |                       |                      |
|                         |                     |                     |                       |                      |
|                         |                     |                     |                       |                      |
|                         |                     |                     |                       |                      |
|                         |                     |                     |                       |                      |
|                         |                     |                     |                       |                      |

## Medida de rendimiento



# Ejercicio Monjes y Canibales: 

## Secuencia de percepción: 

## Medida de rendimiento
