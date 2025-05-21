#clase4 

- <mark style="background-color: rgba(115, 239, 97, 0.31); color: rgb(0, 190, 79);">Para diseño:</mark> la notación BNF (lo realizado en las [[Expresiones aritméticas]]).
- <mark style="background-color: rgba(115, 239, 97, 0.31); color: rgb(0, 190, 79);">Para las propiedades:</mark> las reglas de inferencia (caso de sintaxis abstracta).
- <mark style="background-color: rgba(115, 239, 97, 0.31); color: rgb(0, 190, 79);">Para la implementación:</mark> el data de Haskell.![[Pasted image 20250404184427.png]]

## <mark style="background-color: rgba(255, 131, 195, 0.31); color: rgb(255, 134, 226); text-decoration: underline;">Principios de inducción</mark>

En N: sea P un predicado sobre N.
- <mark style="background-color: rgba(115, 239, 97, 0.31); color: rgb(0, 190, 79);">Inducción matemática (llamada completa en Uruguay y Argentina):</mark>
![[Pasted image 20250404184654.png]]
- <mark style="background-color: rgba(115, 239, 97, 0.31); color: rgb(0, 190, 79);">Inducción Noetherian (o completa):</mark>
![[Pasted image 20250404184802.png]]

Con la segunda puedo probar la primera, ya que el P 0 es un caso específico de la segunda.

Aplicando estos principios a la notación forma de implementación obtenemos lo siguiente:
![[Pasted image 20250404185016.png]]

## <mark style="background-color: rgba(255, 131, 195, 0.31); color: rgb(255, 134, 226); text-decoration: underline;">Principios de recursión</mark>

Para definir f: N -> B
f 0 = b ---> b :: B
f (S n) = h n (f n) ---> h :: N -> B -> B

Entonces:

![[Pasted image 20250404185237.png]]