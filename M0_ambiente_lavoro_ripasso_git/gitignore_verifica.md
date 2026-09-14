# Verifica delle regole `.gitignore`

L'ambiente virtuale di prova è stato creato in `M0_ambiente/.venv` usando l'interprete Python disponibile sul computer.

## `git status`

```text
On branch main
Your branch is up to date with 'origin/main'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
	modified:   .gitignore

no changes added to commit (use "git add" and/or "git commit -a")
```

La cartella `M0_ambiente/.venv` non è elencata tra i file non tracciati.

## `git check-ignore -v M0_ambiente/.venv/pyvenv.cfg`

```text
.gitignore:6:.venv/	M0_ambiente/.venv/pyvenv.cfg
```

La riga 6 di `.gitignore` applica la regola `.venv/` al file di configurazione dell'ambiente virtuale.
