#clase4

![[Pasted image 20250404182019.png]]

### <mark style="background-color: rgba(115, 239, 97, 0.31); color: rgb(0, 190, 79);">2 formas de expresión:</mark>
- <mark style="background-color: rgba(2, 214, 234, 0.31); color: #2ab7de;">Concreta:</mark> cómo se escriben las expresiones del lenguaje (usualmente en strings).![[Pasted image 20250404182628.png]]
- <mark style="background-color: rgba(2, 214, 234, 0.31); color: #2ab7de;">Abstracta:</mark> cómo se estructuran las expresiones del lenguaje (usualmente en árboles).

## <mark style="background-color: rgba(255, 131, 195, 0.31); color: rgb(255, 134, 226); text-decoration: underline;">Estratificación de operadores</mark>

Primero se define una sintaxis concreta que permite definir un orden de precedencia. Si dejamos únicamente a esta, estaríamos permitiendo que se pueda hacer una multiplicación entre booleanos.

![[Pasted image 20250404182959.png]]

Por lo que invocamos a un parser (analizador sintáctico), el cual tiene dentro un lexer (analizador lexicográfico), que convierte de la sintaxis concreta a la abstracta. El segundo de estos se encarga de analizar la línea a evaluar y dándole sentido a las palabras (tokens) que toma para luego pasarle al parser para que dicha línea sea analizada sintácticamente (si está siendo bien escrita en cuanto al sentido de la expresión).

![[Pasted image 20250404183423.png]]

De esta sintaxis, se pasa al pretty printer, el cual es el que se ejecuta cada vez que se ejecuta el programa.

Sin embargo, el type checker, ejecutado luego del parser, es el que nos va a permitir hacer ciertas operaciones o no (por ejemplo, tener una multiplicación de booleanos).