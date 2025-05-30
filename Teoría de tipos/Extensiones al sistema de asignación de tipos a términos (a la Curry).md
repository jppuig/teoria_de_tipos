#clase9
Esta es una extensión al type-checker creado en la clase anterior, detallado en [[Lógica y surgimiento del Cálculo Lambda]].

![[Pasted image 20250530191013.png]]

La primer extensión que vimos fue la de constantes, son los términos (funciones o variables) a los que se le asigna un nombre para referenciarlos:
![[Pasted image 20250530191148.png]]

Debemos agregar un nuevo tipo al que llamaremos cuantificaciones prefijas (sigma) que puede ser otro término cuantificado o un alpha:
![[Pasted image 20250530191308.png]]

El sistema pasa a tener las siguientes reglas:
![[Pasted image 20250530191510.png]]

Se modifica la regla de la variable ya que x puede ser sigma o alpha y x tiene que estar declarada en el contexto, se mantienen las otras dos anteriores, pero se agregan tres nuevas: la regla let , la generalización y la instanciación. La primera permite reservar x de tipo sigma en M, la segunda aplica el cuantificador a con un t paramétrico al término, mientras que la tercera sustituye ese t paramétrico de la generalización por una variable. 
![[Pasted image 20250530191446.png]]
![[Pasted image 20250530191434.png]]

Falta extensión de listas, data y case.