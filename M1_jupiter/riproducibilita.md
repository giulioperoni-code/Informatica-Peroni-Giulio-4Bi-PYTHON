# Riproducibilità e notebook locale

## Obiettivo

Questo documento descrive come un notebook può perdere la riproducibilità se una cella di definizione viene rimossa senza riavviare il kernel. Il metodo usato in questo repository è locale e non usa il server remoto del laboratorio.

## Defetto intenzionale

Se una cella crea una variabile e la cella successiva usa quella variabile, ma poi la cella di definizione viene cancellata senza riavviare il kernel, la successiva esecuzione causa un errore di tipo `NameError`. In pratica il kernel conserva lo stato precedente e quindi la variabile può sembrare ancora presente fino a quando non viene riavviato.

## Messaggio di errore reale

Il messaggio tipico è il seguente:

```text
NameError: name 'variabile_di_test' is not defined
```

## Correzione

La soluzione corretta è riavviare il kernel, ricompilare il notebook e assicurarsi che ogni variabile sia definita prima del suo utilizzo. Dopo la correzione, l'esecuzione completa termina senza errori.

## Verifica locale

I notebook in questa cartella sono stati eseguiti con `jupyter nbconvert --to notebook --execute --inplace` e con il kernel locale di VS Code. Il metodo evita il server remoto e mantiene il lavoro nel repository in modo verificabile e controllato.
