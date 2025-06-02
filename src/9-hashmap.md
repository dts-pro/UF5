# 9. La classe HashMap (Java)

Un HashMap és un tipus de col·lecció en Java que ens permet emmagatzemar dades en forma de clau-valor. És a dir, podrem guardar un valor i després accedir a este valor fent servir una clau.

Els HashMaps són molt útils quan volem associar dades, i són molt eficients a l'hora de fer cerques per clau.

Per exemple, podem crear un HashMap per a emmagatzemar el nom i edat d'una persona:

::: tabs
== Java

```java
HashMap<String, Integer> persona = new HashMap<>();
```

:::

Ací declarem un HashMap que tindrà cadenes (String) com a claus i enters (Integer) com a valors.

Per a afegir dades al HashMap fem servir el mètode `put`:

::: tabs
== Java

```java
persona.put("Josep", 30); 
persona.put("Maria", 25);
```

:::

Ara hem afegit les dades de Josep (30 anys) i Maria (25 anys) al HashMap, fent servir els seus noms com a clau.

Per a obtindre un valor donada una clau utilitzem el mètode "get":

::: tabs
== Java

```java
int edatMaria = persona.get("Maria"); //edatMaria = 25
```

:::

Vorem que és molt ràpid i fàcil accedir als valors a partir de la clau.

El exemple complet podria ser el següent:  

::: tabs
== Java

```java
//Importem la llibreria per a poder-la utilitzar
import java.util.HashMap; 
public class ExempleHashMap {
  public static void main(String[] args) {

    //Creem el HashMap
    HashMap<String, Integer> persona = new HashMap<>();

    // Afegir parella clau-valor
    persona.put("Josep", 30); 
    persona.put("Maria", 25);

    // Obtindre valor per clau 
    int edatMaria = persona.get("Maria"); //edatMaria = 25

    // Recórrer el hashMap persona amb un “foreach”
    for (String clau: persona.keySet()) {
      Int valor = persona.get(clau);
      System.out.println(clau + " - " + valor);
    }
  }
}
```

:::
