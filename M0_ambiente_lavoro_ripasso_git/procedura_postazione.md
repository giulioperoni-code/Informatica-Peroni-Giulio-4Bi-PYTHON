# Procedura di allestimento postazione Windows

Procedura numerata per portare una postazione Windows appena ripristinata
allo stato di lavoro del modulo M0_ambiente. Seguibile senza altre informazioni.
Nessuna credenziale; percorsi personali solo con `$HOME`.

## 1. Verifica prerequisiti
Apri Git Bash e controlla Git.
```bash
git --version
uname -a
```
**Verifica** – Output atteso: `git version 2.xx.x.windows.x` e stringa `MINGW64_NT-...`.
Se `git` non trovato: installare Git for Windows e riaprire il terminale.

## 2. Configurazione identità Git
```bash
git config --global user.name "Studente Corso"
git config --global user.email "studente@example.com"
git config --global init.defaultBranch main
git config --global core.autocrlf true
```
**Verifica**
```bash
git config --global --list
```
Output atteso (almeno): `user.name=Studente Corso`, `user.email=studente@example.com`,
`init.defaultBranch=main`, `core.autocrlf=true`.

## 3. Struttura di lavoro sotto `$HOME`
```bash
mkdir -p "$HOME/lavoro/M0_ambiente"
mkdir -p "$HOME/lavoro/test_verifica"
cd "$HOME/lavoro"
pwd
ls -la
```
**Verifica** – `pwd` termina con `/lavoro`; `ls` elenca le due cartelle create.

## 4. Inizializzazione repository
```bash
cd "$HOME/lavoro/M0_ambiente"
git init
git status
```
**Verifica** – Output atteso:
```
Initialized empty Git repository in .../M0_ambiente/.git/
On branch main
No commits yet
nothing to commit ...
```

## 5. Commit del documento di procedura
Posiziona `procedura_postazione.md` nella cartella, poi:
```bash
cd "$HOME/lavoro/M0_ambiente"
git add procedura_postazione.md
git commit -m "docs: procedura completa postazione Windows"
git log --oneline -1
git status
```
**Verifica** – `git log` mostra il messaggio; `git status` = `nothing to commit, working tree clean`.

## 6. Verifica su cartella di prova distinta
Usa una cartella diversa da quelle degli esercizi precedenti.
```bash
cd "$HOME/lavoro/test_verifica"
mkdir prova_proc && cd prova_proc
git init
echo "# test" > README.md
git add README.md
git commit -m "test: verifica su cartella distinta"
git status
```
**Verifica** – Output atteso: `nothing to commit, working tree clean`.

## 7. Controlli finali
```bash
echo "HOME=$HOME"
git --version
ls "$HOME/lavoro/M0_ambiente"
```
**Verifica** – `$HOME` valorizzato; Git 2.x presente; cartella contiene `.git` e il file md.

---
## Messaggi di errore tipici (causa e rimedio)
1. **`git: command not found`** – Causa: Git assente dal PATH. Rimedio: installare Git for Windows (opzione “Git from the command line…”), riavviare terminale.
2. **`fatal: not a git repository`** – Causa: comando fuori da directory con `.git`. Rimedio: `cd` nella cartella corretta oppure `git init`.
3. **`error: could not write config file ... Input/output error`** – Causa: filesystem non scrivibile o permessi su `.git`. Rimedio: lavorare sotto `$HOME` e controllare `ls -la .git`.
4. **`fatal: Unable to create '.../.git/index.lock': File exists`** – Causa: processo git precedente interrotto. Rimedio: `rm -f .git/index.lock` e ripetere il comando.
5. **`warning: LF will be replaced by CRLF`** – Causa: differenza fine-riga Windows/Unix. Rimedio: già mitigato da `core.autocrlf true`; è solo un avviso.
