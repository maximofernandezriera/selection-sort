# El método de ordenación Selection Sort

## ¿Cómo funciona?

   * Recibe un array como entrada.  
   * Itera a través del array desde el primer elemento hasta el penúltimo (n \- 1).  
   * En cada iteración, encuentra el índice del elemento mínimo en el subarray no ordenado (desde i \+ 1 hasta el final del array).  
   * Llama al método swap para intercambiar el elemento mínimo encontrado con el primer elemento del subarray no ordenado.  

### Recordemos como funciona un método swap:

   * Recibe el array arr y dos índices i y j como entrada.  
   * Intercambia los elementos en las posiciones i y j del array utilizando una variable temporal temp.

![Selection Sort Animation](https://es.wikipedia.org/wiki/Ordenamiento_por_selecci%C3%B3n#/media/Archivo:Selection-Sort-Animation.gif)

### El algoritmo Selection Sort funciona encontrando repetidamente el elemento mínimo del subarray no ordenado y colocándolo en su posición correcta.
### Es un algoritmo simple de entender e implementar, pero no es muy eficiente para arrays grandes.


#### Ejercicio 1.  Implementa el método selectionSortDescendingOrder moviendo el elemento más pequeño hacia el final (en lugar del más grande). 10 minutos.

#### Ejercicio 2.  Implementa el método selectionSortAlternativeVersion buscando el elemento más pequeño y colocándolo a la izquierda (al principio del array) . 10 minutos.
