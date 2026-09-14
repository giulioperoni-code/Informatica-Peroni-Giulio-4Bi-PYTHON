# Cronologia dei commit

## `git log --oneline --graph --decorate`

```text
* 05a6a6d (HEAD -> main) docs(m0): descrive la rilevazione delle versioni
* 647481a docs(m0): contestualizza l'esercizio sui percorsi
* 401a2a6 docs(m0): annota l'esito dell'esecuzione
* 9ff63d5 docs(m0): descrive gli esercizi sull'ambiente
* 28476e8 docs: chiarisce lo scopo del repository
* 93f58fd (origin/main, origin/HEAD) Documenta autenticazione SSH
* 5496321 Aggiunge regole gitignore e verifica
* 96b2fb2 Crea struttura moduli M0-M8
* 364ce8d Esercizio 4
* 8bb6d0e Esercizio 3
* e1f25e0 Esercizio 2
* 89f9381 Esercizio 1
* b0bd1bb Initial commit
```

## `git log -5 --pretty=format:"%h %ad %an %s" --date=short`

```text
05a6a6d 2026-09-14 Giulio docs(m0): descrive la rilevazione delle versioni
647481a 2026-09-14 Giulio docs(m0): contestualizza l'esercizio sui percorsi
401a2a6 2026-09-14 Giulio docs(m0): annota l'esito dell'esecuzione
9ff63d5 2026-09-14 Giulio docs(m0): descrive gli esercizi sull'ambiente
28476e8 2026-09-14 Giulio docs: chiarisce lo scopo del repository
```

## Commento

Il commit `28476e8` aggiorna il README principale e chiarisce lo scopo del repository.
Il commit `9ff63d5` descrive i materiali e gli esercizi raccolti nel modulo M0.
Il commit `401a2a6` aggiunge una nota che interpreta l'esito dell'esecuzione dello script.
Il commit `647481a` rende più leggibile il file che documenta percorsi e cartelle di lavoro.
Il commit `05a6a6d` presenta le versioni degli strumenti rilevate nella postazione.
L'etichetta `HEAD` indica il commit attualmente selezionato nella copia locale.
L'etichetta `main` identifica il ramo locale che contiene gli ultimi cinque commit mostrati.
L'etichetta `origin/main` indica il riferimento locale all'ultimo stato noto del ramo remoto su GitHub.
L'etichetta `origin/HEAD` segnala che il ramo principale predefinito del remoto è `main`.
Al momento dell'estrazione il repository locale non era allineato: `main` era avanti di cinque commit rispetto a `origin/main`.
