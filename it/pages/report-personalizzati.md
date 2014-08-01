
Personalizzazione dei Report
===

## Introduzione

L'applicazione iPad consente - a partire dalla versione 4.1.0 - la generazione, visualizzazione e condivisione di report. Tali report vengono scaricati durante la sincronizzazione (sezione _Generali_ - _Modelli report_).
La generazione dei report avviene a partire da un template, editale da _AppManager_.

Il template è un foglio HTML (comprensivo anche di regole di stile) integrato con alcuni segnaposti. I segnaposti consentono all'applicazione di popolare il report dinamicamente con valori opportuni. La loro sintassi è: {{nomesegnaposto}}.

Note: La modifica errata del report potrebbe causare una errata visualizzazione del report e, in casi particolari,
il crash dell'applicazione.
Si consiglia di effettuare una copia di backup del template prima di iniziarne l'editing.

### Segnaposti di default
I seguenti segnaposti sono utilizzati dall'app per il rendering della pagina html:

  * {{#documentHeader}} ... {{/documentHeader}}
  * {{#pageHeader}} ... {{/pageHeader}}
  * {{#pageContent}} ... {{/pageContent}}
  * {{#pageFooter}} ... {{/pageFooter}}
  * {{#pageNumber}} ... {{/pageNumber}}

È possibile modificare il codice contenuto in tali segnaposti, inserendo direttive html.
Si consiglia di non rimuovere tali segnaposti.


### Contesti report
L'applicazione supporta la generazione di report nei seguenti contesti. Per ogni contesto viene elencato l'elenco di voci che l'applicazione provvede a valorizzare.
È a discrezione di chi modifica il report la scelta di cosa far vedere/non far vedere, ed eventualmente la modifica delle regole di stile/layout html.


## Report ordini salvati
Tale report comprende i seguenti segnaposti, popolati dinamicamente dall'applicazione:

  *   {{#rows}} ... {{#/rows}} : sezione contenente la lista di ordini salvati. Per ogni elemento della lista, vengono mostrati i seguenti campi:
    *   {{codArt}} : valorizzato con il codice articolo a cui la riga ordine si riferisce.
    *   {{desArt}} :  valorizzato con la descrizione articolo a cui la riga ordine si riferisce.
    *   {{dataConsegna}} :  valorizzato con la data di consegna a cui la riga ordine si riferisce.
    *   {{prz1}} :  valorizzato con il prezzo in unità di misura principale a cui la riga ordine si riferisce.
    *   {{qta1}} :  valorizzato con la quantità in unità di misura principale a cui la riga ordine si riferisce.
    *   {{importoRiga}} : valorizzato con l'importo della riga ordine.
    *   {{umRiga}} : valorizzato con l'unità di misura secondaria.
    *   {{qtaRiga}} : valorizzato la quantità in unità di misura secondaria.
    *   {{#scontiRiga.withPosition(scontiRiga.sconti) }} ... {{/scontiRiga.withPosition(scontiRiga.sconti) }} : contenente la lista degli sconti applicati alla riga ordine.
      * {{sconto}} : contenente il singolo sconto.

  *   {{orderNumber}}: Numero ordine (In realtà e' GUID temporaneo. Il numero ordine vero viene assegnato dal gestionale)
  *   {{appLogoSrc}} : valorizzato con il sorgente del logo visualizzato nel report.
  *   {{appName}} : valorizzato con il nome dell'applicazione.
  *   {{title}} : valorizzato con il titolo del report.
  *   {{alertMessage}} : valorizzato con un messaggio di alert ("documento senza valore fiscale").
  *   {{printDate}} : valorizzato con la data di creazione del documento.
  *   {{codAgente}} : valorizzato con il codice agente dell'utente loggato.
  *   {{desAgente}} : valorizzato con la descrizione dell'utente loggato.
  *   {{codCliente}} : valorizzato con il codice del cliente relativo all'ordine.
  *   {{ragSocCliente}} : valorizzato con il la ragione sociale del cliente relativo all'ordine.
  *   {{indirizzoCliente}}  valorizzato con l'indirizzo del cliente relativo all'ordine.
  *   {{capCliente}}  valorizzato con il CAP del cliente relativo all'ordine.
  *   {{cittaCliente}}  valorizzato con la città del cliente relativo all'ordine.
  *   {{provCliente}}  valorizzato con la provincia del cliente relativo all'ordine.
  *   {{telefonoCliente}}  valorizzato con il telefono del cliente relativo all'ordine.
  *   {{faxCliente}}  valorizzato con il fax del cliente relativo all'ordine.
  *   {{emailCliente}}  valorizzato con l'email del cliente relativo all'ordine.
  *   {{#scontiIndexes.withPosition(scontiIndexes.indexes)}} ... {{/scontiIndexes.withPosition(scontiIndexes.indexes)}} : sezione contenente la lista di sconti applicati sull'ordine.
  *   {{index}} : valorizzato con l'indice relativo ad uno sconto.
  *   {{total}} : valorizzato con il totale del documento.


## Report ordini inviati
Tale report comprende i seguenti segnaposti, popolati dinamicamente dall'applicazione:

  *   {{#rows}} ... {{#/rows}} : sezione contenente la lista di ordini inviati. Per ogni elemento della lista, vengono mostrati i seguenti campi:
    *   {{codArt}} : valorizzato con il codice articolo a cui la riga ordine si riferisce.
    *   {{desArt}} :  valorizzato con la descrizione articolo a cui la riga ordine si riferisce.
    *   {{dataConsegna}} :  valorizzato con la data di consegna a cui la riga ordine si riferisce.
    *   {{prz1}} :  valorizzato con il prezzo in unità di misura principale a cui la riga ordine si riferisce.
    *   {{qta1}} :  valorizzato con la quantità in unità di misura principale a cui la riga ordine si riferisce.
    *   {{importoRiga}} : valorizzato con l'importo della riga ordine.
    *   {{umRiga}} : valorizzato con l'unità di misura secondaria.
    *   {{qtaRiga}} : valorizzato la quantità in unità di misura secondaria.
    *   {{#scontiRiga.withPosition(scontiRiga.sconti) }} ... {{/scontiRiga.withPosition(scontiRiga.sconti) }} : contenente la lista degli sconti applicati alla riga ordine.
    * * {{sconto}} : contenente il singolo sconto.

  *   {{appLogoSrc}} : valorizzato con il sorgente del logo visualizzato nel report.
  *   {{appName}} : valorizzato con il nome dell'applicazione.
  *   {{title}} : valorizzato con il titolo del report.
  *   {{alertMessage}} : valorizzato con un messaggio di alert ("documento senza valore fiscale").
  *   {{printDate}} : valorizzato con la data di creazione del documento.
  *   {{codAgente}} : valorizzato con il codice agente dell'utente loggato.
  *   {{desAgente}} : valorizzato con la descrizione dell'utente loggato.
  *   {{codCliente}} : valorizzato con il codice del cliente relativo all'ordine.
  *   {{ragSocCliente}} : valorizzato con il la ragione sociale del cliente relativo all'ordine.
  *   {{indirizzoCliente}}  valorizzato con l'indirizzo del cliente relativo all'ordine.
  *   {{capCliente}}  valorizzato con il CAP del cliente relativo all'ordine.
  *   {{cittaCliente}}  valorizzato con la città del cliente relativo all'ordine.
  *   {{provCliente}}  valorizzato con la provincia del cliente relativo all'ordine.
  *   {{telefonoCliente}}  valorizzato con il telefono del cliente relativo all'ordine.
  *   {{faxCliente}}  valorizzato con il fax del cliente relativo all'ordine.
  *   {{emailCliente}}  valorizzato con l'email del cliente relativo all'ordine.
  *   {{#scontiIndexes.withPosition(scontiIndexes.indexes)}} ... {{/scontiIndexes.withPosition(scontiIndexes.indexes)}} : sezione contenente la lista di sconti applicati sull'ordine.
  *   {{index}} : valorizzato con l'indice relativo ad uno sconto.
  *   {{total}} : valorizzato con il totale del documento.


#### Report ordini veloci
Tale report comprende i seguenti segnaposti, popolati dinamicamente dall'applicazione:

  *   {{#rows}} ... {{#/rows}} : sezione contenente la lista di ordini salvati da ordini veloci. Per ogni elemento della lista, vengono mostrati i seguenti campi:
    *   {{codArt}} : valorizzato con il codice articolo a cui la riga ordine si riferisce.
    *   {{desArt}} :  valorizzato con la descrizione articolo a cui la riga ordine si riferisce.
    *   {{dataConsegna}} :  valorizzato con la data di consegna a cui la riga ordine si riferisce.
    *   {{prz1}} :  valorizzato con il prezzo in unità di misura principale a cui la riga ordine si riferisce.
    *   {{qta1}} :  valorizzato con la quantità in unità di misura principale a cui la riga ordine si riferisce.
    *   {{importoRiga}} : valorizzato con l'importo della riga ordine.
    *   {{umRiga}} : valorizzato con l'unità di misura secondaria.
    *   {{qtaRiga}} : valorizzato la quantità in unità di misura secondaria.
    *   {{#scontiRiga.withPosition(scontiRiga.sconti) }} ... {{/scontiRiga.withPosition(scontiRiga.sconti) }} : contenente la lista degli sconti applicati alla riga ordine.
      * {{sconto}} : contenente il singolo sconto.

  *   {{appLogoSrc}} : valorizzato con il sorgente del logo visualizzato nel report.
  *   {{appName}} : valorizzato con il nome dell'applicazione.
  *   {{title}} : valorizzato con il titolo del report.
  *   {{alertMessage}} : valorizzato con un messaggio di alert ("documento senza valore fiscale").
  *   {{printDate}} : valorizzato con la data di creazione del documento.
  *   {{codAgente}} : valorizzato con il codice agente dell'utente loggato.
  *   {{desAgente}} : valorizzato con la descrizione dell'utente loggato.
  *   {{codCliente}} : valorizzato con il codice del cliente relativo all'ordine.
  *   {{ragSocCliente}} : valorizzato con il la ragione sociale del cliente relativo all'ordine.
  *   {{indirizzoCliente}}  valorizzato con l'indirizzo del cliente relativo all'ordine.
  *   {{capCliente}}  valorizzato con il CAP del cliente relativo all'ordine.
  *   {{cittaCliente}}  valorizzato con la città del cliente relativo all'ordine.
  *   {{provCliente}}  valorizzato con la provincia del cliente relativo all'ordine.
  *   {{telefonoCliente}}  valorizzato con il telefono del cliente relativo all'ordine.
  *   {{faxCliente}}  valorizzato con il fax del cliente relativo all'ordine.
  *   {{emailCliente}}  valorizzato con l'email del cliente relativo all'ordine.
  *   {{#scontiIndexes.withPosition(scontiIndexes.indexes)}} ... {{/scontiIndexes.withPosition(scontiIndexes.indexes)}} : sezione contenente la lista di sconti applicati sull'ordine.
  *   {{index}} : valorizzato con l'indice relativo ad uno sconto.
  *   {{total}} : valorizzato con il totale del documento.


#### Report copia commissione
Tale report comprende i seguenti segnaposti, popolati dinamicamente dall'applicazione:

  * {{#rows}} ... {{#/rows}} : sezione contenente la lista di ordini salvati. Per ogni elemento della lista, vengono mostrati i seguenti campi:
    * {{codArt}} : valorizzato con il codice articolo a cui la riga ordine si riferisce.
    * {{desArt}} :  valorizzato con la descrizione articolo a cui la riga ordine si riferisce.
    * {{campione}} : valorizzato con un carattere che indica se il dettaglio di riga è un campione.
    * {{desAssort}} : valorizzato con la descrizione dell'assortimento relativo al dettaglio di riga.
    * {{nAssort}} : valorizzato con il numero di assortimenti relativi al dettaglio di riga.
    * {{totPaia}} : valorizzato con il totale delle paia ordinate.
    * {{prz}} : valorizzato con il prezzo unitario.
    * {{img}} : valorizzato con il sorgente dell'immagine associata all'articolo.
    * {{#taglieRiga.withPosition(taglieRiga.taglie)}} ... {{/taglieRiga.withPosition(taglieRiga.taglie) }} : sezione contenente la lista di quantità delle taglie presenti nella numerata.
      * {{qtaTaglia}} : valorizzato con la quantità relativa ad una taglia.

  * {{appLogoSrc}} : valorizzato con il sorgente del logo visualizzato nel report.
  * {{appName}} : valorizzato con il nome dell'applicazione.
  * {{title}} : valorizzato con il titolo del report.
  * {{alertMessage}} : valorizzato con un messaggio di alert ("documento senza valore fiscale").
  * {{printDate}} : valorizzato con la data di creazione del documento.
  * {{noteTestata}} : valorizzato con le note di testata dell'ordine.
  * {{dataConsegna}} : valorizzato con la data di consegna presente nella testata dell'ordine.
  * {{desPagamento}} : valorizzato con la descrizione della condizione di pagamento presente nella testata dell'ordine.
  * {{desDestinazione}} : valorizzato con la descrizione della destinazione presente nella testata dell'ordine.
  * {{desScatola}} : valorizzato con  la descrizione della scatola presente nella testata dell'ordine.
  * {{desEtichetta}} : valorizzato con la descrizione dell'etichetta presente nella testata dell'ordine.
  * {{codAgente}} : valorizzato con il codice agente dell'utente loggato.
  * {{desAgente}} : valorizzato con la descrizione dell'utente loggato.
  * {{ragSocCliente}} : valorizzato con la ragione sociale del cliente a cui si riferisce l'ordine.
  * `{{#taglieIndexes.withPosition(taglieIndexes.indexes) }} ... {{/taglieIndexes.withPosition(taglieIndexes.indexes) }} : sezione contenente la lista di indici relativi alle taglie (numerata).
  * {{index}} : valorizzato con l'indice relativo a una taglia.
  * {{total}} : valorizzato con il totale del documento.


## Report incassi
Tale report comprende i seguenti segnaposti, popolati dinamicamente dall'applicazione:

  *   {{#rows}} ... {{#/rows}} : sezione contenente la lista di incassi effettuati. Per ogni elemento della lista, vengono mostrati i seguenti campi:
    *   {{codCliente}} : valorizzato con il codice del cliente a cui l'incasso si riferisce.
    *   {{ragScociale}} :  valorizzato con la ragione sociale del cliente a cui l'incasso si riferisce.
    *   {{numDoc}} :  valorizzato con il numero documento a cui l'incasso si riferisce.
    *   {{dataDoc}} :  valorizzato con la data del documento a cui l'incasso si riferisce.
    *   {{dataScad}} :  valorizzato con la data di scadenza del documento a cui l'incasso si riferisce.
    *   {{tipoInc}} : valorizzato con il tipo di incasso.
    *   {{dataInc}} : valorizzato con la data in cui l'incasso è avvenuto.
    *   {{impScad}} : valorizzato l'importo della scadenza a cui l'incasso si riferisce.
    *   {{impInc}} : valorizzato con l'importo incassato.

  *   {{appLogoSrc}} : valorizzato con il sorgente del logo visualizzato nel report.
  *   {{appName}} : valorizzato con il nome dell'applicazione.
  *   {{title}} : valorizzato con il titolo del report.
  *   {{startDate}} : valorizzato con la data da cui parte il periodo di visualizzazione delle scadenze.
  *   {{startDate}} : valorizzato con la data da cui finisce il periodo di visualizzazione delle scadenze.
  *   {{printDate}} : valorizzato con la data di creazione del documento.
  *   {{codAgente}} : valorizzato con il codice agente dell'utente loggato.
  *   {{desAgente}} : valorizzato con la descrizione dell'agebte loggato.
  *   {{total}} : valorizzato con il totale del documento.

  ## Dimensione del logo
  I report standard prevedono un logo di 512x512 pixel con estensione PNG. Questa è la dimensione consigliata ma,
  ovviamente, se si effettua una personalizzazione del report, è probabilmente necessario adattare anche la dimensione
  del logo.
