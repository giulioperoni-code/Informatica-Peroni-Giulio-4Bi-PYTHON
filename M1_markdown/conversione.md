# Conversione controllata con Pandoc

Per trasformare la relazione in HTML e PDF, usiamo i comandi di Pandoc direttamente da terminale.

```bash
pandoc relazione.md -f markdown -t html5 --standalone --toc --toc-depth=2 --metadata title="Relazione di laboratorio" -o relazione.html
```

```bash
pandoc relazione.md -f markdown -t pdf --pdf-engine=pdflatex -V geometry:margin=2.5cm -V fontsize=11pt -V lang=it -o relazione.pdf
```

## Opzioni usate

- `-f markdown`: specifica il formato di input.
- `-t html5` / `-t pdf`: indica il formato di output desiderato.
- `--standalone`: genera un documento completo, non solo un frammento.
- `--toc`: inserisce la tabella dei contenuti.
- `--toc-depth=2`: limita l'indice al secondo livello.
- `--metadata title="..."`: imposta il titolo del documento.
- `-o relazione.html` / `-o relazione.pdf`: indica il nome del file risultato.
- `--pdf-engine=pdflatex`: usa LaTeX per la conversione PDF.
- `-V geometry:margin=2.5cm`: imposta i margini di 2,5 cm.
- `-V fontsize=11pt`: imposta il corpo del testo a 11 punti.
- `-V lang=it`: imposta la lingua italiana.

## Avvisi

Durante la conversione potrebbe apparire un avviso sulla mancanza di un motore PDF o di alcuni pacchetti di LaTeX. In quel caso è necessario installare i componenti richiesti e ripetere il comando. La corretta configurazione del motore PDF garantisce anche la resa corretta delle lettere accentate.

I file `relazione.html` e `relazione.pdf` non vanno caricati nel repository perché sono file derivati e non prodotti a mano; per questo motivo vanno esclusi con `.gitignore`.
