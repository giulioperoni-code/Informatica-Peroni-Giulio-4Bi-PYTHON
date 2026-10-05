# Guida ai recinti annidati

Questo documento mostra come inserire un blocco di codice dentro un altro blocco di codice. Il primo esempio riproduce un file Java standard, mentre i successivi mostrano come il codice venga "rappresentato come sorgente" all'interno di un recinto esterno.

## Esempio 1: blocco Java normale

Un blocco Java semplice viene scritto così:

```java
public class Esempio {
    public static void main(String[] args) {
        System.out.println("Salve dal laboratorio");
    }
}
```

## Esempio 2: blocco Java dentro un recinto esterno

Di seguito il codice Java appare come testo all'interno di un altro blocco di codice, quindi non viene interpretato come codice eseguibile dal lettore.

````markdown
```java
public class Esempio {
    public static void main(String[] args) {
        System.out.println("Salve dal laboratorio");
    }
}
```
````

## Esempio 3: terzo livello di annidamento

Nel caso più complesso, il codice Java viene mostrato dentro un blocco Markdown che a sua volta è inserito in un altro recinto. In questo modo il lettore vede solo la struttura del testo, ma non viene confuso da un'interpretazione automatica.

````markdown
````markdown
```java
public class Esempio {
    public static void main(String[] args) {
        System.out.println("Salve dal laboratorio");
    }
}
```
````
````

Il paragrafo finale è scritto come testo normale e non come codice, perché il corretto annidamento dei recinti è fondamentale per evitare che l'intero documento venga letto come un unico blocco di codice.
