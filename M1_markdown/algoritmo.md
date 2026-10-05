# Ricerca sequenziale in un array

In un array ordinato o non ordinato, la ricerca sequenziale controlla gli elementi uno per uno finché non trova il valore cercato oppure termina la scansione. In Java, l'algoritmo è semplice da implementare e aiuta a comprendere il concetto di controllo del flusso.

```java
public class RicercaSequenziale {
    public static int cerca(int[] array, int valore) {
        for (int i = 0; i < array.length; i++) {
            if (array[i] == valore) {
                return i;
            }
        }
        return -1;
    }

    public static void main(String[] args) {
        int[] array = {7, 6, 8, 5, 9};
        int trovato = cerca(array, 8);
        System.out.println(trovato);
    }
}
```

```mermaid
flowchart TD
    A[Inizio] --> B[Leggi array e valore da cercare]
    B --> C{i = 0; i < lunghezza array?}
    C -- Sì --> D{array[i] == valore?}
    D -- Sì --> E[Restituisci indice i]
    D -- No --> F[i = i + 1]
    F --> C
    C -- No --> G[Restituisci -1]
    G --> H[Fine]
    E --> H
```

Se l'elemento cercato non è presente nell'array, il ciclo termina senza trovare una corrispondenza e il metodo restituisce `-1`. Questo valore segnala al programma che la ricerca è fallita e che l'elemento non appartiene all'insieme dei dati analizzati.
