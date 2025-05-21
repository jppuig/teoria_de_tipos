#clase1 

Los tipos en lógica tienen una historia que comienza comienza con 3 matemáticos lógicos alemanes: [[Leibniz]], [[Frege]] y [[Hilbert]].
## <mark style="background-color: rgba(255, 131, 195, 0.31); color: rgb(255, 134, 226); text-decoration: underline;">¿Cuál es el fundamento de los axiomas de la matemática?</mark>
Existen tres ramas en cuanto a esta pregunta que se realiza Frege:
- <mark style="background-color: rgba(115, 239, 97, 0.31); color: rgb(0, 190, 79);">Platonismo:</mark> plantea que los números naturales pertenecen al mundo de las ideas y que son previos y posteriores a nosotros. Siempre existieron. Los conocemos de antes de la vida, pero al venir a este mundo los recordamos, pero no siempre con la mejor precisión por eso nos equivocamos.
- <mark style="background-color: rgba(115, 239, 97, 0.31); color: rgb(0, 190, 79);">Formalismo:</mark> no les interesa de dónde vienen, sino cómo usarlos (en una mezcla entre esta y el platonismo es donde se ubican la mayoría de los matemáticos).
- <mark style="background-color: rgba(115, 239, 97, 0.31); color: rgb(0, 190, 79);">Constructivismo:</mark> son puramente creación humana lo que significa que no existían previo a nosotros y no existirán después (donde se ubican la mayoría de los programadores).

Frege es formalista y dice que lo único que existen son las verdades lógicas, por lo que toma del logicismo que parte del platonismo el para todo (con tipo de enunciado con objeto), la negación, el implica,  el True y el False. Estos son los tipos de Frege.

Aristóteles plantea que existe un sujeto y predicado y el sujeto es o no es el predicado. Hasta Frege, no hubo ningún cambio, sin embargo, hubo mucho que intentaron hacerlo pero no pudieron. Por otro lado, <mark style="background-color: rgba(2, 214, 234, 0.31); color: #2ab7de; ">Frege plantea que únicamente existen enunciados y objetos</mark>, también establece una serie de axiomas necesarios para que su cálculo proposicional funcionase. Sin embargo, es a través de uno de estos (axioma V) por el cual [[Russell]] descubre una paradoja ([[Paradoja de Russell]]) demostrando que dicho cálculo contenía falencias.

En la época persistían varios modelos que coexistían con sus paradojas como la Teoría de conjuntos de Cantor (a Cantor no le importaba, mientras que a Frege si), también estaba la paradoja de Richard de los números reales definidos con strings finitos. [[Russell]] se dio cuenta que todas las paradojas tenían dentro una definición impredicativa.

#clase3 

Salía un modelo y al tiempo se descubría una paradoja con definición impredicativa dentro. <mark style="background-color: rgba(115, 239, 97, 0.31); color: rgb(0, 190, 79);">El único de estos modelos que utilizó tipos en su momento fue Frege con [] y () para los enunciados y objetos.</mark> En 1908 [[Russell]] publica su teoría de tipos (junto con Whitehead) llamada <mark style="background-color: rgba(115, 239, 97, 0.31); color: rgb(0, 190, 79);">Principia Mathematica</mark>. Más tarde en 1940, [[Church]] plantea su teoría de tipos que es una simplificación del trabajo de [[Russell]], el cual comenzó simple y fue complejizándose.

Entonces por un lado quedaron los conjuntos con Cantor y Zermelo-Frankl que continuó por otro camino (no lo cubrimos, la teoría de conjuntos de Cantor no se puede comprobar ni se ha descubierto un contraejemplo aún, ya que para esto no se pueden utilizar los axiomas ni reglas del mismo modelo). Por otro lado, se encuentra el camino de las funciones con Frege, Russell y Church, todos con falencias de cierto tipo. Con esto, obtenemos la Higher Order Logic (HOL).

Hasta acá fueron los tipos en lógica. En no muchos años surgen las máquinas y con ellas la programación y sus tipos. Estos fueron trabajados hasta los 70' por un camino diferente, hasta que en esta década se juntan ambas corrientes y surge con lo que vamos a terminar el curso que es la teoría constructivista de tipos.