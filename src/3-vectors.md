# 3. Vectors (arrays unidimensionals)

## 3.1. Declaració

**Un array es declara de manera similar a una variable simple però afegint claudàtors** per a indicar que estracta d'un array i no d'una variable simple del tipus especificat.

Un Vector (array unidimensional) es pot declarar de dues formes:

`tipus identificador[]; tipus[] identificador;`

On `tipus` és el tipus de dada dels elements del vector i `identificador` és el nom de la variable.

Exemples:

`int notes[]; double comptes[];`

Declara un array de tipus int i un altre de tipus double. Aquesta declaració indica per a què servirà el array, però **no reserva espai en la memòria RAM al no saber-se encara la grandària d'aquest**. Encara no pot utilitzar-se el array, falta instanciarlo.

## 3.2. Instància

**Després de la declaració del array, s'ha d'instanciar**, per a això s'utilitza l'operador `new`, que és el que realment crea el array indicant una grandària. Quan s'usa new, és quan es reserva l'espai necessari en memòria. Un array no inicialitzat és un array **null** (sense valor).

Exemple:

```java
int notes[]; // Declarem ‘notes’ com array de tipus int
notes = new int[5]; // Instanciem ‘notes’ a grandària 5

// És habitual declarar i instanciar en una sola línia
int notes[] = new int[5];
```

En l'exemple anterior es crea un array de cinc enters (amb els tipus bàsics es crea en memòria l’array i s'inicialitzen els valors, **els númeross'inicialitzen a 0**).

## 3.3. Emmagatzematge

Els valors del array s'assignen (emmagatzemen) utilitzant l'índex del mateix entre claudàtors.

**IMPORTANT!**: El **primer element del vector** sempre estarà en la posició o **índex 0**.

![Índex vectors](/uf5/IndexVectors.jpg)

Per exemple, per a emmagatzemar el valor 2 en la tercera posició del array escriuríem:

```java
notes[2] = 2;
```

També es poden assignar valors al array en la pròpia declaració i instanciació:

```java
int notes[] = {8, 10, 2, 3, 5};
int notes[]= new int[] {8, 10, 2, 3, 5}; //Equivalent a l'anterior
```

Això declara i inicialitza un array de cinc elements. L’exemple seria equivalent a:

```java
notes[0] = 8;
notes[1] = 10;
notes[2] = 2;
notes[3] = 3;
notes[4] = 5;
```

A Java (com en altres llenguatges) el primer element d'un array éstá en la posició zero. El
primerelement del array notes, és notes[0].

**Es poden declarar arrays** a qualsevol mena de dades (**enters, booleans, doubles**... i, fins i tot, **objectes**)

## 3.4. Longitud d'un vector

Els arrays posseeixen una propietat anomenada length que indica la seua grandària.

Exemple:

```java
int notes[] = new int[5]; // Vector tipus int de grandària 5
System.out.println( notes.length ); // Mostrarà un 5
```

Si el vector té com en l'exemple 5 elements, la propietat `length` ens retornarà el valor sencer 5, però el primer element estroba en notes[0] i l'últim en notes[4].

## 3.5. Recorregut d'un vector

Per a recórrer un vector (accedir a tots els seus elements) sempre serà necessari un bucle.

En el següent exemple declarem i instanciem un vector tipus int amb les notes d'un alumne idesprés utilitzem un bucle for per a recórrer el vector i mostrar tots els elements.

```java
// Declarem i instanciem vector tipus int
int notas[] = new int[] {7, 3, 9, 6, 5};
// Com all vector és de grandària 5 els seus elements estaran en les posicions de 0 a 4

// Recorrem el vector des d'i=0 fins a i<5 (és a dir, des de 0 fins a 4)
for (int i = 0; i < notas.length; i++) {
  System.out.println(notas[i]);
}
```

Ara calcularem la nota mitjana (sumar totes i després dividir entre el nombre de notes):

```java
// Declarem suma i mitja int suma = 0;
int mitjana;
// Recorrem el vector des de 0 fins a 4, acumulant les notes en suma 
for (int i = 0; i < notas.length; i++) {
  summa += notas[i]; // Equival a: suma = summa + notas[i]
}
// Calculem la mitjana i la vam mostrar per pantalla 
mitjana = summa / notas.length; 
System.out.println(“La nota mitjana és: “ + mitjana);
```

## 3.6. Còpia de vectors

Per a copiar vectors no n'hi ha prou amb igualar un vector a un altre com si fora una variable simple.

Si partim de dos vectors v1, v2 i férem v2=v1, el que ocorreria seria que v2 apuntaria a la posició de memòria de v1. Això és el que es denomina un copia de referència:

![Apuntar memòria vector](/uf5/ApuntarMemoriaVector.jpg)

Si per exemple volem copiar tots els elements del vector v2 en el vector v1, existeixen dues formes per a fer-ho.

### 3.6.1. Copiar els elements un a un

```java
for (i = 0; i < v1.length; i++)
  v2[i] = v1[i];
```

### 3.6.2. Utilitzar la funció arraycopy

```java
System.arraycopy(v_origen, i_origen, v_destí, i_destí, length);
// v_origen: Vector orígen
// i_origen: Posició inicial de la còpia v_destí: Vector destine
// i_destí: Posició final de la còpia length: Quantitat d'elements a copiar

// Copiem tots els elements de v1 en v2
System.arraycopy(v1, 0, v2, 0, v1.length);
```