# incApache
## 1. Il metodo HEAD
Il metodo HEAD viene usato principalmente per scopi di debug. Di fatto viene restituita una risposta del tutto analoga a quella che si avrebbe con il metodo GET ma non si restituisce la risorsa richiesta, bensì solo la parte di header.
## 2. Il metodo GET
Il metodo GET viene usato ogni volta che si vuole richiedere un file.
Supponiamo che un client voglia richiedere un'immagine, per esempio il logo di incApache.
## 3. I Cookies
In questo laboratorio viene usato il meccanismo dei Cookie per tener traccia delle azioni compiute dai vari client, in particolare per contare il numero di richieste HTTP inviate da ciascun client.

Questo avviene assegnando ad ogni client un identificatore univoco, al quale viene associato un contatore del numero di richieste ricevute. Data l'implementazione multithread del servizio, occorre prevenire corse critiche nell'accesso alla struttura dati che mantiene il contatore del numero di Cookies assegnati. La prima volta che un client si connette non ha Cookies da includere nella richiesta, e il server genera un nuovo Cookie da includere nell'header della risposta, azzerando il contatore del numero di accessi per il nuovo client; le volte successive che il client si connette include il suo Cookie nell'header della richiesta, permettendo cosi` al server di riconoscere il client e di incrementare il relativo contatore del numero di richieste. Occorre generare un Cookie con associata una data di scadenza abbastanza lontana nel tempo da permettere il conteggio delle richieste per almeno un anno.
## Versione HTTP corrente: 1.0
