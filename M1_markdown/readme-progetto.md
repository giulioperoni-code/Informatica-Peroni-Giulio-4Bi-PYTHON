# README del progetto MediaVoti

## Descrizione

MediaVoti legge un file di voti e calcola la media complessiva. Il programma è utile per verificare rapidamente il rendimento scolastico e per avere un riepilogo senza fare calcoli a mano.

È pensato per essere semplice da eseguire con una sola classe di entry point e per lavorare su file di testo in formato CSV.

## Requisiti

| Requisito | Dettaglio |
| --- | --- |
| Java | JDK 17 o superiore |
| Sistema operativo | Windows, Linux o macOS |
| File in ingresso | `voti.csv` con dati numerici |
| Cartella di lavoro | repository locale con sorgenti e file di output |

## Installazione

1. Clonare il repository e aprire la cartella del progetto.
2. Verificare che i file sorgente si trovino nella cartella `src/`.
3. Creare la cartella `bin/` se non esiste.
4. Compilare il progetto con il comando seguente:

```bash
mkdir -p bin
javac -d bin $(find src -name "*.java")
```

5. Controllare che non compaiano errori di compilazione prima di eseguire il programma.

## Uso

Per eseguire il programma, usare il comando:

```bash
java -cp bin MediaVoti
```

### Formato del file di ingresso

Il file `voti.csv` deve contenere una sequenza di valori numerici separati da virgole o da linee separate. Esempio:

```text
7,8,6,9,8
```

### Output atteso

Il programma stampa la media complessiva dei voti e un riepilogo in console. Un esempio di output atteso:

```text
Media dei voti: 7.6
```

## Struttura del progetto

```text
MediaVoti/
├── src/
│   └── MediaVoti.java
├── bin/
├── voti.csv
├── README.md
└── .gitignore
```

## Autore e licenza

Autore: Giulio Peroni  
Licenza: uso didattico per il corso di Informatica, con finalità di laboratorio e apprendimento.
