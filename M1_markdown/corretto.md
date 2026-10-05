# README del progetto

## Descrizione

Questo programma legge un file CSV contenente i voti di un gruppo di studenti e mostra un riepilogo dei dati in console. L'obiettivo è semplificare il calcolo e la lettura dei risultati senza eseguire i passaggi a mano.

## Requisiti

| Requisito | Dettaglio |
| --- | --- |
| Java | JDK 17 o superiore |
| Sistema operativo | Windows, Linux o macOS |
| File in ingresso | `dati.csv` con valori numerici |
| Ambiente di lavoro | Cartella del progetto con sorgenti e file di output |

## Come usare

1. Scaricare il repository e aprire la cartella del progetto.
2. Verificare che i sorgenti Java siano presenti nella cartella `src/`.
3. Compilare il progetto con il comando:

```bash
mkdir -p bin
javac -d bin $(find src -name "*.java")
```

4. Eseguire il programma con:

```bash
java -cp bin Main
```

5. Verificare che il file `dati.csv` sia presente nella cartella corretta.

## Output atteso

Il programma stampa il riepilogo dei valori in console e termina dopo aver mostrato i risultati. Il comportamento atteso dipende dai dati contenuti nel file di ingresso.

## Nota

Il nome della classe principale e il nome del file di input devono essere verificati prima della consegna. La documentazione originale contiene alcuni riferimenti generici, ma il comportamento reale del programma va controllato nel sorgente prima di pubblicare il README.
