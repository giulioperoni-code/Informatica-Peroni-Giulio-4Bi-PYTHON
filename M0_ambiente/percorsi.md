# Percorsi e cartelle di lavoro

Sequenza di comandi PowerShell usata per creare e raggiungere le cartelle dell'esercizio.

PS Z:\> cd .\Documenti\
PS Z:\Documenti>
PS Z:\Documenti> mkdir esercizio-percorsi

    Directory: Z:\Documenti

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----        14/09/2026     10:41                esercizio-percorsi

PS Z:\Documenti> cd .\esercizio-percorsi\
PS Z:\Documenti\esercizio-percorsi> mkdir dati

    Directory: Z:\Documenti\esercizio-percorsi

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----        14/09/2026     10:42                dati

PS Z:\Documenti\esercizio-percorsi> mkdir risultati

    Directory: Z:\Documenti\esercizio-percorsi

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----        14/09/2026     10:42                risultati

PS Z:\Documenti\esercizio-percorsi> cd .\dati\
PS Z:\Documenti\esercizio-percorsi\dati> cd ..\risultati\
PS Z:\Documenti\esercizio-percorsi\risultati> Get-Location

Path
----
Z:\Documenti\esercizio-percorsi\risultati
