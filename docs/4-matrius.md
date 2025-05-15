# 4. Matrius (arrays multidimensionals)

Els arrays poden tindre més d'una dimensió. Els més utilitzats són els arrays de 2 dimensions, coneguts com a matrius.

Les matrius es defineixen de les següents formes:

`tipus identificador[][]; tipus[][] identificador;`

![Matriu](../UD5/img/Matriu.jpg)

Per exemple, declarem i instanciem un array de 3 x 3 (3 files x 3 columnes).

`double preus[][] = new int[3][3];`

Accedim als seus valors utilitzant dobles claudàtors.

```java
preus[0][0] = 7.5;
preus[0][1] = 12;
preus[0][2] = 0.99;
preus[1][0] = 4.75;
// etc.
```

Vegem un altre exemple en el qual declarem i instanciem un array de 3 files x 6 columnes per emmagatzemar les notes de 3 alumnes (la fila correspon a un alumne, i cada columna a les notes d'aquest alumne):

```java
int notes[][] = new int[3][6]; // És equivalent a 3 vectors de grandària 6
```

Suposant que les notes ja estan emmagatzemades, recorrerem la matriu (array bidimensional) pera mostrar les notes per pantalla. Cal tindre en compte que com té dues dimensions necessitaremn bucle niat (un per a les files i un altre per a les columnes de cada fila):

```java
// Per a cada fila (alumne)
for (int i = 0; i < notes.length; i++) {
  System.out.print("Notes de l'alumne" + i + ": ");
  // Per a cada columna (nota)
  for (int j = 0; j < notes[i].length; j++) 
    System.out.print(notes[i][j] + “ “);
}
```