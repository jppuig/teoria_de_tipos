#clase7

Estudiamos dos tipos: proposicional clásica y primer orden clásica.

# <mark style="background-color: rgba(255, 131, 195, 0.31); color: rgb(255, 134, 226); text-decoration: underline;">Lógica</mark>

Por alguna razón en la época las investigaciones lógicas se basaban en reducción a la mínima cantidad de operadores posibles que, en ese momento no tenía utilidad pero, más tarde iba a ser útil.

## <mark style="background-color: rgba(115, 239, 97, 0.31); color: rgb(0, 190, 79);">Lógica proposicional:</mark>
Lograron reducir a dos operadores lógicos:
![[Pasted image 20250524184804.png]]
## <mark style="background-color: rgba(115, 239, 97, 0.31); color: rgb(0, 190, 79);">Lógica de primer orden:</mark>
Pero en la lógica de primer orden se tenía que un solo cuantificador alcanzaba ya que el existe es igual al not para todo not.
![[Pasted image 20250524185014.png]]
Schönfinkel propone que una sola constante lógica también es suficiente tomando de la lógica proposicional la incompatibilidad:
![[Pasted image 20250524185031.png]]
Pero le hace una modificación diciendo que es incompatible en x (una variable aleatoria). Sin embargo, al agregar la x en la constante debe eliminar las variables ligadas ya que complican la sustitución:
![[Pasted image 20250524185310.png]]
La captura se produce de dos maneras:
1. Mismos símbolos son utilizados con dos propósitos distintos: quedan las variables libres ("reales") y las ligadas ("aparentes").
2. Sustitución de una expresión con x libre dentro del alcance de (Qx).

Con Church en 1932 surge el cálculo lambda con la sustitución parcial, pero fue Curry-Feys en el 58' que permiten la sustitución total que evita la captura.

En un caso de la teoría de funciones (acá me perdí):
![[Pasted image 20250524190727.png]]

El algoritmo para abstraer la x planteado por Schönfinkel es el siguiente:
![[Pasted image 20250524190604.png]]Usando este algoritmo pudo formar a las funciones a partir de otras ya que fue abstrayendo la variable en cada caso.
![[Pasted image 20250524190952.png]]

# <mark style="background-color: rgba(255, 131, 195, 0.31); color: rgb(255, 134, 226); text-decoration: underline;">Cálculo lambda</mark>
![[Pasted image 20250524191121.png]]
![[Pasted image 20250524191156.png]]

3 formas de solucionar esto:
1. ![[Pasted image 20250524191243.png]]
2. ![[Pasted image 20250524191258.png]]
3. ![[Pasted image 20250524191325.png]]
