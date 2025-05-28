# 7. Cercar amb vectors

Existeixen dues maneres de buscar un element dins d'un vector: la cerca seqüencial i la cerca dicotòmica o binària.

## 7.1. Cerca seqüencial

La cerca seqüencial és la més fàcil de les dues, ja que consisteix a comparar els elements del vector amb l'element a buscar.

Un exemple és el següent, on es retorna la posició de l'element en el vector i si no el troba, retorna el valor-1:

::: tabs
== Java

```java
public static int busquedaSequencial(int[] v, int element){
  int i, posicio = -1;
  for(i = 0; i < v.length && posicio == -1; i++)
    if(v[i] == elemento)
      posicion = i;
  
  return posicio;
}
```

:::

## 7.2. Cerca dicotòmica o binària

En aquest cas el vector ha d'estar ordenat. Es dividirà en dos per a buscar l'element en una part del vector o en una altra i així successivament fins a trobar, o no, l'element.

Un exemple és el següent:

![Exemples de búsqueda dicotòmica](/uf5/busquedaDicotomica.jpg)

En aquest cas, igual que en l'anterior, la funció retorna la posició de l'element o -1 si no el troba. És important veure que el vector ha d'estar ordenat per a quedar-nos amb la part des de l'esquerra al centre del vector o des del centre del vector a la dreta, depenent si l'element a buscar és major o menor a l'element del centre del vector.

Aquesta cerca és més òptima que la seqüencial ja que no ha de recórrer el vector sencer.
