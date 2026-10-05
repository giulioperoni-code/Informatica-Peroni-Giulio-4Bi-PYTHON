# Come compilare ed eseguire un programma Java

Per compilare ed eseguire un programma Java partendo da un repository appena clonato, è necessario seguire alcuni passaggi in ordine. In questo esempio il codice sorgente si trova in `src/`, la compilazione va fatta in `bin/` e la classe con il metodo `main` si chiama `MediaVoti`.

1. Aprire il terminale nella cartella del repository appena clonato e verificare la struttura delle directory.

   ```bash
   cd ~/Documents/Java/MediaVoti
   ls -R
   ```

2. Controllare che i sorgenti Java siano presenti nella cartella `src/` e che il nome della classe principale corrisponda a `MediaVoti`.

   ```bash
   find src -name "*.java"
   ```

3. Creare la cartella di output `bin/` se non esiste e compilare tutti i file sorgente con `javac`, indicando la destinazione di compilazione.

   ```bash
   mkdir -p bin
   javac -d bin $(find src -name "*.java")
   ```

4. Verificare che la compilazione abbia creato i file `.class` nella cartella `bin/` e che il progetto sia pronto per l'esecuzione.

   - Controllare la struttura del progetto
   - Verificare la presenza di `MediaVoti.class`
   - Assicurarsi che non ci siano errori di compilazione

5. Eseguire la classe principale con `java`, specificando il nome della classe senza estensione `.class`.

   ```bash
   java -cp bin MediaVoti
   ```

Se il JDK non è installato, il comando `javac` fallisce e il sistema mostra un messaggio simile a:

> `javac: command not found`
> `bash: javac: command not found`

Per risolvere il problema, installare un JDK completo e riavviare il terminale oppure controllare che il percorso di Java sia stato aggiunto alla variabile `PATH`.

La procedura è valida per tutti i progetti Java del corso e permette di compilare ed eseguire rapidamente un programma senza usare strumenti aggiuntivi.
