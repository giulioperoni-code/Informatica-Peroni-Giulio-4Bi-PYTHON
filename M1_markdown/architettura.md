# Architettura del progetto

Il progetto scelto rappresenta una semplice applicazione di gestione prenotazioni. La parte principale è composta da tre classi: `Utente`, `Prenotazione` e `SistemaPrenotazioni`.

```mermaid
classDiagram
    class Utente {
        -String nome
        -String email
        +Utente(String nome, String email)
        +String getNome()
        +String getEmail()
    }

    class Prenotazione {
        -String codice
        -Utente utente
        -String data
        +Prenotazione(String codice, Utente utente, String data)
        +String getCodice()
        +Utente getUtente()
        +String getData()
    }

    class SistemaPrenotazioni {
        -List<Prenotazione> prenotazioni
        +SistemaPrenotazioni()
        +void aggiungiPrenotazione(Prenotazione p)
        +List<Prenotazione> elencoPrenotazioni()
    }

    SistemaPrenotazioni "1" *-- "0..*" Prenotazione
    Prenotazione "many" --> "1" Utente
```

Il diagramma delle classi mostra che `SistemaPrenotazioni` contiene una collezione di prenotazioni, mentre ogni prenotazione è associata a un solo utente. La relazione di composizione indica che la lista di prenotazioni appartiene al sistema, mentre l'associazione mostra il legame tra prenotazione e utente.

```mermaid
sequenceDiagram
    participant U as Utente
    participant S as SistemaPrenotazioni
    participant P as Prenotazione

    U->>S: aggiungiPrenotazione(p)
    S->>P: crea nuova prenotazione
    alt dati validi
        P-->>S: prenotazione confermata
        S-->>U: messaggio di conferma
    else dati non validi
        S-->>U: errore di input
    end
```

La sequenza descrive il flusso di registrazione di una prenotazione: il cliente interagisce con il sistema, il sistema crea la prenotazione e decide, in base ai dati ricevuti, se confermarla o segnalare un errore.
