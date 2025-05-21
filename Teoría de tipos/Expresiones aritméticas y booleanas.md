#clase5

Las definimos de la siguiente manera (manera que vimos anteriormente en [[Expresiones aritméticas]]):
![[Pasted image 20250426172623.png]]

## <mark style="background-color: rgba(255, 131, 195, 0.31); color: rgb(255, 134, 226); text-decoration: underline;">Semántica</mark>

Vemos dos opciones. Estas pueden coexistir, no se trata de elegir una única.
### <mark style="background-color: rgba(115, 239, 97, 0.31); color: rgb(0, 190, 79);">Denotacional (matemática):</mark>
Se trata de asociar un objeto ya conocido a un término o expresión matemática.
La definimos de la siguiente manera:
![[Pasted image 20250426173045.png]]

### <mark style="background-color: rgba(115, 239, 97, 0.31); color: rgb(0, 190, 79);">Operacional:</mark>
0. <mark style="background-color: rgba(2, 214, 234, 0.31); color: #2ab7de;">Para empezar definimos nuestra noción de valor.</mark> Esta no puede ser todo del mismo nivel ya que estaríamos permitiendo que S v pueda ser S false, por ejemplo. Por lo que hay que subdividirlos:
![[Pasted image 20250426173538.png]]

1. <mark style="background-color: rgba(2, 214, 234, 0.31); color: #2ab7de;">Pasamos a los Redexes (viene de reducible expressions)</mark>, las cuales definimos como:
![[Pasted image 20250426173807.png]]
Y acá tenemos variabilidad en nuestra elección con respecto a pred ya que podemos atrasar la evaluación o no. En el libro de Pierce, pred O es O (pred es total), pero no es muy adecuado para la función. Además de que podemos chequear si pred de S de algo es de tipo nv (eager). La otra forma es atrasar la evaluación ya que no es nuestra responsabilidad y permitir un pred de S de cualquier t (lazy), este es el camino que vamos a tomar nosotros.

2. <mark style="background-color: rgba(2, 214, 234, 0.31); color: #2ab7de;">Ahora pasamos a la reducción (la computación en un paso)</mark>, definida de la siguiente manera:
![[Pasted image 20250426174645.png]]
El if es siempre lazy ya que, si no lo fuera el lenguaje permitiría escribir fácilmente un loop infinito al necesitar evaluar t2 y t3 en todos los casos incluso cuando no se vayan a ejecutar. Además en el caso eager, deberíamos agregar la siguiente regla de reducción:![[Pasted image 20250510154538.png]]
Ya que evalúa los términos dentro del constructor en el momento y no lo atrasa como en el lazy.

Acá definimos las reglas de reducción, pero para que estos funcionen debemos definir valores intermedios que no sean los valores finales, volvemos a la noción de valores. Los llamamos valores débiles:
![[Pasted image 20250426174751.png]]
El problema original es con S t, ya que el usuario podría definir un S true. Sin embargo, al estar S t dentro de la definición de valores finales debemos agregar todos los otros valores finales como intermedios previo a confirmarlos como finales. Ya que no vamos a chequear a t hasta la evaluación (runtime).

3. Las dos partes anteriores son las partes más importantes de la semántica operacional ya que las que vienen son una consecuencia de ellas. En esta tercera parte definimos los <mark style="background-color: rgba(2, 214, 234, 0.31); color: #2ab7de;">irreducibles</mark>:
![[Pasted image 20250426175222.png]]
Cuando se llega a alguno de estos utilizando las reglas de reducción, entonces no se pueden reducir más.

4. <mark style="background-color: rgba(2, 214, 234, 0.31); color: #2ab7de;">Para la computación en muchos pasos es necesario definir la computación en 0 o más pasos</mark>, la definimos con una flecha y un asterisco encima de ella. Se define de la siguiente manera:
 ![[Pasted image 20250426175407.png]]
Existen dos formas de escribirlo: Ro (p griega) es la reflectividad, cuando se utilizan 0 pasos ya que se alcanzo un irreducible. Esta se encuentra en ambas formas.
Luego, por un lado se encuentra gamma que es la computación en más de un paso. Mientras que por el otro definimos dos reglas como análogas de gamma: la flecha que es la computación en un paso y la de abajo que es en más de un paso. Igualmente utilizamos la primera.

La forma anterior de escribir la semántica operacional es la de "small step" ya que va en 1 o algunos pasos, existe una manera distinta llamada "big step": ![[Pasted image 20250510153622.png]]
Se le llama de esta manera ya que es la computación final. Esta es menos descriptiva en cómo es que llega a esa computación final, pero a la vez permite asegurar de que llega a un valor. En la semántica operacional "small step", podemos no llegar a darnos cuenta de que una computación puede no terminar nunca.

5. <mark style="background-color: rgba(2, 214, 234, 0.31); color: #2ab7de;">Por último definimos la computación final total:</mark>
![[Pasted image 20250426175940.png]]
Pasamos de los valores débiles a los finales. En los primeros tres casos quedan iguales, mientras que en el S t, debemos verificar que t' sea un nv haciendo recursión hasta encontrar el O.

A la vez, la evaluación eager al realizar todo el trabajo antes, no tiene valores débiles ni computación final total, ya que solo puede dar los siguiente resultados en caso de que termine: un valor o un error, mientras que la lazy (descrita anteriormente) da un valor intermedio o un error por lo que necesitamos la computación final total.
## <mark style="background-color: rgba(255, 131, 195, 0.31); color: rgb(255, 134, 226); text-decoration: underline;">Sistema de tipos</mark>

Definimos un tipo alpha que puede ser nat o bool:
![[Pasted image 20250426191416.png]]
Los casos a destacar son: el if que pierde generalización, en el sentido que tanto t2 como t3 deben ser el mismo alpha (nat ambos o bool ambos) y no nos conviene tener un alpha1 y alpha2 porque sino tengo que evaluarlos hasta el final para saber de qué tipo es el if, lo que demoraría mucho en el caso de lenguajes grandes y quiero que el sistema de tipos sea rápido. El otro caso a destacar es el pred, que por el contrario, tiene poca especificación ya que no distingue entre S t u O. En un caso se especifica mucho y en el otro poco.

La evaluación nos entrega distintos enunciados sobre el sistema de tipos:
![[Pasted image 20250426192527.png]]
Lo que nos permite distinguir los enunciados de la siguiente manera:
![[Pasted image 20250426192655.png]]
El primer caso es el que plantea pierce ya que él incluye en su redexes el pred O > O, establece que dado un t de tipo alpha entonces este va a evaluar completamente a un valor de tipo alpha, se mantiene, no se rompe. El caso débil plantea que dado un t de tipo alpha y si este t es evaluado completamente retornando un valor entonces este valor es de tipo alpha. Esto no nos garantiza nada ya que puede fallar en la mitad.
Podemos mejorar este enunciado para que sea mejor:
![[Pasted image 20250426194108.png]]
Si únicamente tuviésemos booleanos podríamos tener el enunciado ideal. Sin embargo, no lo tenemos por lo que podemos definirnos un tipo de enunciados erróneos para que cuando falle obtener un poco más de información, los llamamos wrong-pred y los definimos como los casos en los que sabemos que este lenguaje falla. Además, obtenemos un enunciado más fuerte que el débil que dice dado un t de tipo alpha entonces en muchos pasos vamos a obtener un valor débil de tipo alpha o un wrong-pred, ya que si realizamos la evaluación completa no podemos afirmar nada.

Se puede demostrar esta última afirmación a través de progreso:
![[Pasted image 20250426194630.png]]
O a través de preservación (preservando el tipo):
![[Pasted image 20250426194651.png]]
Lo demostramos a través de preservación realizando inducción en muchos pasos.

#clase6

En el caso eager del sistema de tipos debemos agregar esta regla de asignación de tipos a términos:
![[Pasted image 20250510155116.png]]

<mark style="background-color: rgba(115, 239, 97, 0.31); color: rgb(0, 190, 79);">Debe cumplir ciertas propiedades:</mark>
- <mark style="background-color: rgba(2, 214, 234, 0.31); color: #2ab7de;">Unicidad/monomorfismo de la asignación de tipos:</mark>
![[Pasted image 20250510155535.png]]

Para el caso bool, por ejemplo, se demuestra ya que únicamente encontramos las respectivas reglas para true y false en cada caso. Por otro lado, para el caso if demostramos por inducción: ![[Pasted image 20250510155805.png]]
(Supone que if es de tipo beta por lo que en ese caso la única regla que encontramos es la del if, por lo tanto por hipótesis if es de tipo beta para t2 y t3).

- <mark style="background-color: rgba(2, 214, 234, 0.31); color: #2ab7de;">Decidibilidad:</mark>
En el caso lazy, podemos decir que si t es de tipo alfa entonces t es un valor de tipo alfa o t computa en muchos pasos a un sucesor de w con w de la forma w_p (fórmulas incoherentes en el lenguaje):
![[Pasted image 20250510160142.png]]
![[Pasted image 20250510160156.png]]

Para el caso eager, si t es de tipo alfa entonces t es un valor de tipo alfa (ideal). Esto no es recíproco.
![[Pasted image 20250510160314.png]]
