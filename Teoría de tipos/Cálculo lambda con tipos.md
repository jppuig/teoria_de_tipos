#clase8

A partir de la dos anteriores, [[Expresiones aritméticas y booleanas]] y [[Lógica y surgimiento del Cálculo Lambda]]. En esta clase implementamos cálculo lambda con tipos.

![[Pasted image 20250524191540.png]]

Ground son los tipos de los valores.

# <mark style="background-color: rgba(255, 131, 195, 0.31); color: rgb(255, 134, 226); text-decoration: underline;">A la Church</mark>
Comenzamos definiendo la implementación monomórfica, o sea a la Church:![[Pasted image 20250524191730.png]]

Siguiendo las 3 reglas de búsqueda de una variable, aplicación y abstracción (que actualiza el contexto de declaración) (hoy llamadas funciones lambda).

Posee esas propiedades esta implementación:
- El monomorfismo, en el caso de la identidad debemos definir la identidad para cada uno de los casos que los queramos usar ya que aunque la definición sea igual, el uso cambia por los tipos.
- La autoaplicación está prohibida, dado el ejemplo visto.
- Normalización fuerte dice que una función en la que se ingresan correctos los tipos siempre retornará el tipo de la función.![[Pasted image 20250524192214.png]]

El type-checking de la implementación de Church es decidible con un type-inference que retorna Maybe alpha:
![[Pasted image 20250524192336.png]]

# <mark style="background-color: rgba(255, 131, 195, 0.31); color: rgb(255, 134, 226); text-decoration: underline;">A la Curry</mark>
Curry implementa el cálculo lambda de forma polimórfica:
![[Pasted image 20250524192737.png]]

Vemos que Curry va a trabajar sobre esta implementación casi idéntica a la de Church y sobre esta le agrega tipos paramétricos:
![[Pasted image 20250524193537.png]]

Vemos que las mismas reglas se mantienen pero asignando tipos paramétricos en todos los lugares posibles. Además del contexto de declaración las reglas mantienen constraints en los que van llevando las variables aparecidas y sus tipos. La flecha para arriba significa "es de tipo".

Este sería un ejemplo de ejecución del type-inference sobre un caso mal formado:
![[Pasted image 20250524193716.png]]

El type-checker es el que tira el error al ver que un tipo está definido circularmente:
![[Pasted image 20250524193827.png]]

Esta sería la resolución de constraints que realiza el type-checker de Curry:
![[Pasted image 20250524193915.png]]