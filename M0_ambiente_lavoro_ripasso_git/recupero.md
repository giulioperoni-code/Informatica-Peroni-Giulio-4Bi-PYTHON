# Recupero di file temporanei già tracciati

## Simulazione dell'errore

```text
mkdir -p M0_ambiente_lavoro_ripasso_git/temporanei
git add M0_ambiente_lavoro_ripasso_git/temporanei
git commit -m "chore(m0): aggiunge file temporanei"
```

La cartella contiene i file `nota.txt` e `bozza.txt`, entrambi registrati nel commit di simulazione.

## Diagnosi dopo l'aggiunta della regola

```text
$ git status
modified:   .gitignore

$ git ls-files M0_ambiente_lavoro_ripasso_git/temporanei
M0_ambiente_lavoro_ripasso_git/temporanei/bozza.txt
M0_ambiente_lavoro_ripasso_git/temporanei/nota.txt

$ git check-ignore -v M0_ambiente_lavoro_ripasso_git/temporanei/nota.txt
# Nessun output: il file è già tracciato.
```

## Correzione

```text
$ git rm --cached -r M0_ambiente_lavoro_ripasso_git/temporanei
rm 'M0_ambiente_lavoro_ripasso_git/temporanei/bozza.txt'
rm 'M0_ambiente_lavoro_ripasso_git/temporanei/nota.txt'

$ git ls-files M0_ambiente_lavoro_ripasso_git/temporanei
# Nessun output.

$ git check-ignore -v M0_ambiente_lavoro_ripasso_git/temporanei/nota.txt
.gitignore:21:M0_ambiente_lavoro_ripasso_git/temporanei/	M0_ambiente_lavoro_ripasso_git/temporanei/nota.txt
```

I file `nota.txt` e `bozza.txt` sono ancora presenti sul disco dopo `git rm --cached`.
La regola `.gitignore` agisce sui file non tracciati e non rimuove automaticamente quelli già presenti nell'indice Git.
Per questo è necessario usare `git rm --cached`: il comando rimuove i file soltanto dal versionamento, senza cancellarli dalla cartella locale.
Dopo la rimozione dall'indice, la regola `temporanei/` impedisce che i due file vengano aggiunti di nuovo per errore.
