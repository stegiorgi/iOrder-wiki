Utilizzo di Dropbox
===

Introduzione
---
L'installazione del client dropbox viene utilizzata, nell'architettura di iOrder, per trasferire i dati dal server del cliente all'AppManager e viceversa.
Per questo motivo, Dropbox non deve essere configurato sugli iPad degli utenti finali.

I dati estratti dal gestionale vengono depositati in una specifica cartella condivisa di Dropbox che è configurata in ogni installazione cliente.

Passi da effettuare
---
I passi da effettuare sono i seguenti:

1. Registrare un account dropbox
2. Installare dropbox sul [server del cliente](attivazione-nuovo-progetto.md)
3. Comunicare ad apexnet l'account creato
4. A questo punto Apexnet imposta la condivisione di una cartella per l'account creato.
5. Il cliente deve accettare la condivisione della cartella.

Struttura delle cartelle
---
Al termine delle operazioni descritte, sul server del gestionale apparirà una cartella (es: c:\ic.azienda)
All'interno di tale cartella saranno presenti 4 sottocartelle chiamate

* gestionale (cartella in cui il gestionale deve estrarre i tracciati - export)
* appmanager (cartella in cui appmanager deposita i dati degli ordini - import)
* report (cartella in cui il gestionale copia i report da visualizzare nell'iPad - export)
* multimedia (cartella in cui il gestionale mette le immagini da mostrare nel catalogo dell'ipad)
