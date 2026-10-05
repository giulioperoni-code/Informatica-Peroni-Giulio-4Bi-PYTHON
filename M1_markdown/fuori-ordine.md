# Notebook eseguito fuori ordine

## Ordine di esecuzione reale

Le quattro celle sono state eseguite nell'ordine `1`, `3`, `4`, `2` o, più precisamente, nell'ordine indicato dai numeri di esecuzione salvati: `[1]`, `[3]`, `[4]`, `[2]`. Si deduce questo dato dal fatto che i numeri tra parentesi quadre non sono in ordine di scrittura, ma riflettono l'ordine effettivo con cui il kernel ha eseguito le celle.

## Perché la cella [4] mostra 22?

La cella `[4]` mostra `22` perché viene eseguita dopo la cella `[3]` e dopo che la variabile `posti` è stata modificata. In questo caso, la cella `[3]` calcola `posti - iscritti` usando il valore di `posti` ancora pari a `24`, mentre la cella `[4]` aggiorna `posti` a `22` e stampa il nuovo valore.

## Output previsto dopo Restart Kernel and Run All Cells

Se il notebook viene eseguito dall'alto verso il basso da un kernel vuoto, l'ordine esatto è:

```text
[1] iscritti = 22
    print("Iscritti:", iscritti)
    Iscritti: 22

[2] aula = "Laboratorio 3"
    posti = 24

[3] print(aula, "-", "liberi:", posti - iscritti)
    Laboratorio 3 - liberi: 2

[4] posti = posti - 2
    print("Posti disponibili:", posti)
    Posti disponibili: 22
```

Le celle che non verrebbero eseguite affatto sono quelle già salvate come output statico ma non presenti nel flusso eseguito da un kernel vuoto. In pratica, se il notebook viene riavviato e l'ordine di esecuzione viene ricalcolato, le celle con output già preesistente non sono considerate un punto di partenza affidabile.

## Errore con kernel appena avviato

Se il notebook viene eseguito dall'alto in basso da un kernel appena avviato, la cella che produce errore è la cella `[3]`, perché usa la variabile `posti` prima che sia stata definita in questo flusso. Il messaggio esatto è:

```text
NameError: name 'posti' is not defined
```

## Correzione del notebook

Per far sì che il notebook, eseguito dall'alto verso il basso da un kernel vuoto, arrivi in fondo senza errori, bisogna far sì che tutte le variabili siano definite prima del loro uso. In pratica, la cella con `posti = 24` deve precedere la cella che la utilizza, e la variabile `aula` deve essere inizializzata prima della stampa. In questo caso, il valore al posto di `liberi: 2` rimane `2`, perché la formula `24 - 22` restituisce `2`.
