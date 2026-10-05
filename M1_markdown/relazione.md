# Relazione di laboratorio

## Indice

- [Obiettivo](#obiettivo)
- [Materiale](#materiale)
- [Procedimento](#procedimento)
- [Risultati](#risultati)
- [Conclusioni](#conclusioni)

## Obiettivo

L'obiettivo dell'esercitazione è valutare il tempo di esecuzione di un algoritmo di ordinamento su array di dimensioni crescenti, in modo da capire come il costo computazionale cresce all'aumentare dei dati.

## Materiale

Per l'esecuzione sono stati usati un computer di laboratorio con Java installato, un file di dati sintetici e un programma di test che misura il tempo necessario per ordinare gli array.

## Procedimento

Il test è stato eseguito su array di dimensioni 100, 1000, 10000 e 100000. Per ogni dimensione si è ripetuta la misurazione per ridurre la variabilità dovuta al carico del sistema.

```bash
javac Ordinamento.java
java Ordinamento
```

## Risultati

| Dimensione | Tempo (ms) |
| ---: | ---: |
| 100 | 1 |
| 1000 | 14 |
| 10000 | 142 |
| 100000 | 1602 |

I risultati mostrano un aumento netto del tempo quando la dimensione dell'array cresce. La crescita non è lineare, ma il trend conferma che il costo cresce in modo sensibile con il numero di elementi.[^1]

## Conclusioni

L'algoritmo si comporta in modo corretto e i tempi ottenuti confermano la relazione tra dimensione dei dati e costo computazionale. La verifica è utile per capire non solo se il programma funziona, ma anche quanto sia efficiente in condizioni diverse.

[^1]: La misura è stata fatta in ambiente di laboratorio e riflette il tempo osservato in quella sessione di esecuzione.
