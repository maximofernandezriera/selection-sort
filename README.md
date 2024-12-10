# El método de ordenación Selection Sort

Un vistazo:

- https://es.wikipedia.org/wiki/Ordenamiento_por_selecci%C3%B3n

### Una explicación excelente (en inglés).

[Video de la Carlos III ](https://www.dropbox.com/scl/fi/8mbhnh3psja9evilxaccd/p1b9g9un9q1tad1924187c1f60on04.mp4?rlkey=qu40r0l1vrjhzu0w0q4x647iy&st=stkam13a&dl=0)
[Subtítulos y transcripción ](https://www.dropbox.com/scl/fi/lm387d2mij7azv5i1u5k8/external-video-en.txt?rlkey=apx1mmy5ja5t1asn87z0gd6nz&st=4jxmylgq&dl=0)

## ¿Cómo funciona?

   * Recibe un array como entrada.  
   * Itera a través del array desde el primer elemento hasta el penúltimo (n \- 1).  
   * En cada iteración, encuentra el índice del elemento mínimo en el subarray no ordenado (desde i \+ 1 hasta el final del array).  
   * Llama al método swap para intercambiar el elemento mínimo encontrado con el primer elemento del subarray no ordenado.  

### Recordemos como funciona un método swap:

   * Recibe el array arr y dos índices i y j como entrada.  
   * Intercambia los elementos en las posiciones i y j del array utilizando una variable temporal temp.

![Selection Sort Animation](https://upload.wikimedia.org/wikipedia/commons/9/94/Selection-Sort-Animation.gif)
[![Selection Sort Video](https://img.youtube.com/vi/Ns4TPTC8whw/0.jpg)](https://youtu.be/Ns4TPTC8whw?si=NJI7jV-V3Loi2GzM)

### El algoritmo Selection Sort funciona encontrando repetidamente el elemento mínimo del subarray no ordenado y colocándolo en su posición correcta.
### Es un algoritmo simple de entender e implementar, pero no es muy eficiente para arrays grandes.


#### Ejercicio 1.  Implementa el método selectionSortDescendingOrder moviendo el elemento más pequeño hacia el final (en lugar del más grande). 10 minutos.

#### Ejercicio 2.  Implementa el método selectionSortAlternativeVersion buscando el elemento más pequeño y colocándolo a la izquierda (al principio del array) . 10 minutos.

## SELECTION SORT
  
            public static void selectionSort(int[] arr) {
                int n = arr.length;
        
                // Recorrer el array
                for (int i = 0; i < n - 1; i++) {
                    // Encontrar el índice del elemento mínimo en el subarray no ordenado
                    int minIndex = i;
                    for (int j = i + 1; j < n; j++) {
                        if (arr[j] < arr[minIndex]) {
                            minIndex = j;
                        }
                    }
        
                    // Intercambiar el elemento mínimo encontrado con el primer elemento del subarray no ordenado
                    swap(arr, minIndex, i);
                }
            }

             public static void swap(int[] arr, int i, int j) {
                int temp = arr[i];
                arr[i] = arr[j];
                arr[j] = temp;
            }

--------------------------------------------------------------------------------------------------------------------------------------

## SOLUCIÓN EJERCICIO 1
        
            public static void selectionSortDescendingOrder(int[] arr) {
                int n = arr.length;
        
                // Recorrer el array
                for (int i = 0; i < n - 1; i++) {
                    // Encontrar el índice del elemento máximo en el subarray no ordenado
                    int maxIndex = i;
                    for (int j = i + 1; j < n; j++) {
                        if (arr[j] > arr[maxIndex]) { // Cambiado a '>' para encontrar el máximo
                            maxIndex = j;
                        }
                    }
        
                    // Intercambiar el elemento máximo encontrado con el último elemento del subarray no ordenado
                    swap(arr, maxIndex, n - i - 1); // Intercambiar con el último elemento del subarray
                }
            }

## SOLUCIÓN EJERCICIO 2

            public static void selectionSortAlternativeVersion(int[] arr) {
                int n = arr.length;
        
                // Recorrer el array desde el final hasta el segundo elemento
                for (int i = n - 1; i > 0; i--) { 
                    // Encontrar el índice del elemento mínimo en el subarray no ordenado
                    int minIndex = i;
                    for (int j = i - 1; j >= 0; j--) { // Recorrer el subarray en orden inverso
                        if (arr[j] < arr[minIndex]) {
                            minIndex = j;
                        }
                    }
        
                    // Intercambiar el elemento mínimo encontrado con el último elemento del subarray no ordenado
                    swap(arr, minIndex, i); 
                }
            }


## EJEMPLO DE PROGRAMA PRINCIPAL
        
            public static void main(String[] args) {
                int[] arr = {64, 25, 12, 22, 11};
                // selectionSortAlternativeVersion(arr);
                System.out.println("Array ordenado:");
                for (int num : arr) {
                    System.out.print(num + " ");
                }
            }
