# Note di Rilascio

## Rel. 4.6.10 del 11/06/2014

### Anomalie

**_Problema su erronea cancellazione righe di testate per ordini Taglie e Colori_** - (rif: 9243)

Risolto ora il problema.

**_Risolto problema su valorizzazione pagamento_** - (rif: 9254)

Ora il codice viene sempre correttamente valorizzato.
Il problema era presente solo sulla versione 4.6.0 dell'app.

### Novità

**_Aggiunte nuove informazione nella visualizzazione della lista delle testate documenti._** - (rif: 9233)

Aggiunte nuove informazione nella visualizzazione della lista delle testate documenti: descrizione, numdoc/serie e note.

**_Alert pagamenti scaduti_** - (rif: 9234)

Nel dettaglio della scheda cliente presentazione "alert" nel caso di pagamenti scaduti; l'alert permette di portarsi nel dettaglio delle scadenze.

-------

## Rel. 4.6.0 del 19/05/2014

### Anomalie

**_Corretto problema su ordini Taglie e Colori_** - (rif: 9138)

Fix Ordini senza cliente codificato/ragione sociale

**_Risolto problema "Aggiorna Dati si blocca su valute"_** - (rif: 9206)

Ora non si blocca più durante la sincronizzazione dei dati generali, anche se non sono presenti dei dati obbligatori 

**_Migliorata visualizzazione delle anteprime nel catalogo._** - (rif: 9212)

Migliorata visualizzazione delle anteprime nel catalogo. Ora le anteprime vengono caricate più velocemente.

### Novità

**_Aggiunta nuova gestione listini per ordini Taglie e Colori_** - (rif: 9058)

Gestiti i listini per varianti/combinazioni.

**_Inserimento Clienti_** - (rif: 9087)

E' prevista una nuova modalità di inserimento nuovi clienti contestualmente alla presa dell'ordine.



**_Inserimento nuovi clienti in connettore iB_** - (rif: 9211)

Il connettore di iB e' stato modificato per consentire l'inserimento di nuovi clienti in creazione nuovi ordini

-------

## Rel. 4.5.0 del 30/04/2014

### Anomalie

**_Gestione code sul web service esportazione ordini_** - (rif: 9155)

E' stata cambiata la logica di esportazione dei dati dell'ordine da web service.
Ora, gli ordini da trattare, vengono messi in una cosa di elaborazione.
Il web service ritorna i dati basandosi su questa coda.
Inoltre viene effettuata una sola chiamata per l'esportazione dei dati e non 2 come prima

**_Sistemate anteprime catalogo che sparivano dopo una sincronizzazione_** - (rif: 9174)

Ora il problema è stato risolto.

**_Visualizzazione scelta clienti più vicini in presa ordine_** - (rif: 9185)

Corretta la visualizzazione della distanza in km nella visualizzazione clienti più vicini, nella presa ordine.

**_Risolto possibile crash che avviene se l'utente non ha mai scelto un progetto di lavoro._** - (rif: 9208)

Risolto possibile crash che avviene se l'utente non ha mai scelto un progetto di lavoro.

### Novità

**_Introdotta la possibilità di avere la schermata centrale insieme al menu laterale._** - (rif: 9131)

Possibilità di mettere a tutto schermo la schermata centrale tramite un bottone o una gesture (swipe verso dx/sx).

**_Introdotto salvataggio delle date di ultima sincronizzazione ed invio per multi-azienda._** - (rif: 9136)

Ora chi utilizza più aziende (e quindi DB) non vedrà più resettarsi le date di sincronizzazione ed invio.

**_Migliorata gestione della memoria nella galleria._** - (rif: 9186)

Migliorata gestione della memoria nella galleria nel caso di visualizzazione anteprime.

-------

## Rel. 4.4.0 del 17/04/2014

### Anomalie

**_Crash occasionale in navigazione catalogo per foto a tutto schermo_** - (rif: 9132)

Quando si navigava velocemente sulle foto a tutto schermo, nel caso di cartelle con molte foto e/o pesanti, la memoria del dispositivo viene esaurita in breve tempo.
E' stata migliorata la gestione della memoria nel caso descritto, evitando in questo modo il crash dell'app. 

**_Crash in modifica dati cliente_** - (rif: 9152)

Risolto crash in ordini salvati dopo aver modificato i dati del cliente

**_Crash occasionale al ritorno da background app sul catalogo_** - (rif: 9153)

Risolto il crash quando viene riaperta l'app dal background sul catalogo

**_Anomalia inserimento ordine da Catalogo (form veloce)_** - (rif: 9158)

Nel caso del controllo per colli con proposta della quantità, quest'ultima non veniva proposta correttamente

**_Errore filtro in Giro visita_** - (rif: 9164)

E' stato rivisto l'applicazione del filtro "visitati" nel girovisita al fine di visualizzare correttamente i clienti su cui è stato preso un ordine.

**_Semplificato inserimento ordine da catalogo (form veloce)_** - (rif: 9165)

L'interfaccia utente è stata semplificata, il form completo ordine può essere aperto una volta salvata la quantità.

**_Bug in ordini salvati_** - (rif: 9166)

Risolto problema crash nel caso sia presente una sola riga negli ordini salvati per il cliente e sia di tipo omaggio.

**_Crash occasionale in selezione cliente per ordine_** - (rif: 9170)

Risolto problema nella selezione del cliente. Andando in ricerca e saltando dalla selezioni standard, clienti vicini e girovisita 
poteva manifestarsi questo problema.


### Novità

**_Aggiunto sconto in testata ordine, modificabile (versione taglie e colori)_** - (rif: 9059)

Viene proposto come default lo sconto associato al pagamento se presente, e se non viene trovato viene utilizzato lo sconto valorizzato in anagrafica cliente.

**_Configurazione prezzo minimo su esportazione tracciati iB_** - (rif: 9124)

Nel connettore di iB e' stata implementata la possibilità di configurare una percentuale  da applicare al prezzo di acquisto di un prodotto per impostare un prezzo minimo di vendita nell'ipad.
Il parametro si chiama PercentualeSuPrezzoMinimoVendita

-------

## Rel. 4.3.0 del 21/03/2014

### Anomalie

**_Report standard degli ordini salvati_** - (rif: 9037)

Viene ora visualizzata la descrizione della riga ordine e non la descrizione dell'articolo.

**_In caso di un solo colore non richiedere la scelta all'utente_** - (rif: 9067)

Se in fase di immissione riga ordine, siamo in presenza di un solo colore per il materiale appena scelto, viene ora automaticamente selezionato

**_Corretta gestione di etichetta e scatola_** - (rif: 9077)

Corretta gestione di etichetta e scatola in testata ordine

**_Soglia prezzi_** - (rif: 9083)

Corretta gestione soglia prezzi nel caso di modifica riga ordine

**_Foto prodotto durante modifica ordine_** - (rif: 9093)

Corretto refresh di foto-prodotto nel caso di ritorno da riga ordine.

**_Migliorata la compatibilità con iOS 7.1_** - (rif: 9112)

Sono stati corretti alcuni problemi di visibilità di "buttons" in navigation bar.

### Novità

**_Introdotta nuova gestione per regole e combinazioni._** - (rif: 9013)

Introdotta nuova gestione per regole e combinazioni che migliora significativamente l'esperienza utente (memoria, velocitá).

**_Supporto 64 bit_** - (rif: 9035)

Abilitazione supporto builds 64 bit in modalità nativa

**_Aggiunta a testata ordini spedizioni_** - (rif: 9039)

Aggiunta a testata ordini gli indirizzi di Spedizione legati al cliente.

**_Abilitazione persistenza dati al cambio progetto_** - (rif: 9040)

Possibilità di passare tra progetti (aziende) differenti abilitati per il proprio account senza perdere i dati (db + files della galleria) già sincronizzati.

**_Gestione avviso per ordini taglie e colori_** - (rif: 9075)

Aggiunto alert di warning se cancello ordine

**_Report Stampa Copia Commissione - aggiunta_** - (rif: 9078)

La Stampa Copia Commissione deve riportare anche le righe a qta 0

**_Stampa copia commissione_** - (rif: 9094)

Ora vengono stampate le note di riga se esistono

-------

## Rel. 4.2.0 del 31/01/2014

### Anomalie

**_Verifica stati documenti_** - (rif: 8861)

Risolta anomalia su stati documenti

### Novità

**_Nuovi filtri articolo impostabili nella tab. IGAMMA_PARAMETRI: GRUPPO STATISTICO 2/3/4 e MARCA_** - (rif: 8859)

Aggiunti nuovi filtri sulle viste di estrazione: GRUPPO STATISTICO 2/3/4 e MARCA.

**_Implementato calcolo coordinate con prosync_** - (rif: 8860)

Ora il prosync calcola le coordinate geografiche degli indirizzi dei clienti e le invia all'appmanager

**_Implementati tracciati girovisita_** - (rif: 8862)

Implementati tracciati girovisita

**_Adeguamento tracciati_** - (rif: 8863)

Attualmente il tracciato righe ordini prende 2 valori data e num reg da dati di testata.
Questo non va bene. Si sono verificati problemi in fase di import.
Bisogna adeguare il tracciato.

**_Aggiunta validazione ordini in appmanager_** - (rif: 9028)

In appmanager e' stata aggiunta la possibilità' di validare un ordine e renderlo disponibile per l'esportazione.
Nota: Questa modifica e' attiva solo per le integrazioni mediante web service (no tracciato)

**_Sviluppo assortimento in report copia commissione_** - (rif: 9029)

Nel report del copia commissione, nel caso di taglie e colori, vengono mostrate anche le taglie presenti in un assortimento.

-------

## Rel. 4.1.0 del 24/01/2014

### Anomalie

**_Corretto crash nella galleria, solo su iPhone_** - (rif: 8944)

Il problema, che si verificava solo su iphone e nella condivisione dei files, è stato risolto 

### Novità

**_Nuovo splendido design per iOS 7_** - (rif: 8827)

Abbiamo completamente rinnovato la nostra app per te che usi iOS 7.

**_Ordini veloci: icona sconti evidenzia la presenza di sconti_** - (rif: 8895)

Ora l'icona degli sconti rende più evidente la presenza o meno degli sconti

**_Miglioramenti per ordini Taglie e Colori_** - (rif: 8937)

Aggiunto totale importo nel report.
Migliorato riepilogo ordini temporanei.
Aggiunta la data di consegna per i campioni.
Fixati malfunzionamenti con i picker di scelta nella testata ordine.
Altri bug fix minori.


-------

## Rel. 3.3.0 del 28/11/2013

### Anomalie

**_Sincronizzazione righe documento Cliente_** - (rif: 8969)

Risolto problema sincronizzazione righe documento Cliente, che non erano sempre correttamente sincronizzate

### Novità

**_Sincronizzazione e visualizzazione della descrizione dei prodotti e dei pagamenti nella lingua del dispositivo_** - (rif: 8874)

Sincronizzazione e visualizzazione della descrizione dei prodotti e dei pagamenti nella lingua del dispositivo

**_Aggiunta la gestione delle valute_** - (rif: 8875)

Aggiunta la gestione delle valute

**_Aggiunta nazione in clienti/fornitori_** - (rif: 8936)

Aggiunta visualizzazione attributo nazione in visualizzazione schede cliente/fornitori

-------

## Rel. 3.2.0 del 18/11/2013

### Anomalie

**_Corretta gestione date per filtri schede_** - (rif: 8940)

Nel caso di utilizzo in app con scelta localizzazione diversa da italiana erano possibili degli errori nella gestione delle date nei filtri.  

**_Form ordine da Catalogo_** - (rif: 8941)

Corretto funzionalità su form ordine da catalogo su iOS 7

**_Crash in ordini salvati_** - (rif: 8953)

Se si prova a cancellare gli ordini relativi ad un cliente (tramite swipe), l'app andava in crash.
Ora risolto il problema.

**_Lentezza digitazione ricerca in ordini veloci_** - (rif: 8959)

Corretto problema su iOS 7

### Novità

**_Migliorata gestione delle risorse durante la sincronizzazione dei dati_** - (rif: 8372)

Sono state migliorate la gestione della memoria e della stabilità generale dell'applicazione durante il processo di sincronizzazione

-------

## Rel. 3.1.0 del 29/10/2013

### Anomalie

**_Corretto problema visibilità note Leads_** - (rif: 8894)

Dopo sincronizzazione, se presenti nuove note da inviare, ora sono visibili sia le nuove note che quelle sincronizzate

**_Bug fixing Alerts in iOS 7_** - (rif: 8911)

Corretti vari problemi con Alerts (sincronizzazione dati, login, ...) dovuti al cambio di gestione in iOS 7.

**_Aggiunto controllo sulla lunghezza delle note_** - (rif: 8923)

Aggiunto controllo sulla lunghezza delle note in input, al fine di evitare di importare sul gestionale dati troncati.

### Novità

**_Aggiunta la possibilità di aprire l'immagine del prodotto dagli ordini veloci_** - (rif: 8870)

Aggiunta la possibilità di aprire l'immagine del prodotto dagli ordini veloci

**_Aggiunta la funzionalità dei Report per gli ordini veloci_** - (rif: 8871)

Aggiunta la funzionalità dei Report per gli ordini veloci

**_Aggiunto form ordine da catalogo con la modifica della quantità_** - (rif: 8872)

Aggiunto form ordine da catalogo con la modifica della quantità, attivabile da apposito parametro

**_Aggiunta la possibilità di utilizzare l'app in lingua inglese_** - (rif: 8873)

Aggiunta la possibilità di utilizzare l'app in lingua inglese (oltre che italiano).

**_Gestione taglie e colori_** - (rif: 8884)

Possibilità di attivare il modulo ordini taglie e colori per mondo fashion

**_Gestione reports personalizzati_** - (rif: 8889)

E' resa disponibile la possibilità di personalizzare i layout dei reports in AM

**_Aggiunto filtri nella visualizzazione dei Lead_** - (rif: 8900)

Aggiunto il filtro sugli stati nella visualizzazione dei Lead e esteso la ricerca standard agli altri attriubuti visibili nella lista.

**_Migliorato l'inserimento della descrizione di una nuova nota per i Clienti e per i Lead_** - (rif: 8901)

Migliorato l'inserimento della descrizione di una nuova nota per i Clienti e per i Lead

### Modifiche

**_Possibiltà di aggiungere sempre nuove note_** - (rif: 8876)

Ora la possibilita' di aggiungere nuove note non dipende dalla modificabilita' dei dati anagrafici del cliente.

-------

## Rel. 3.0.0 del 09/09/2013

### Anomalie

**_Corretto bug su salto pagina dei reports pdf generati_** - (rif: 8750)

E' stato reso dinamico il numero degli elementi nel dettaglio del report

**_Bug filtro documenti in schede_** - (rif: 8837)

Eliminato crash in selezione tipi documento se non presenti documenti

**_Mappa Clienti: corretto controllo su ultimo ordine effettuato_** - (rif: 8847)

Ora il controllo su "ultimo ordine effettuato" valorizza il colore del pin correttamente

### Novità

**_Aggiunta funzionalità di ricerca alla galleria._** - (rif: 8373)

Aggiunta funzionalità di ricerca alla galleria.

**_Interfaccia LM Partner_** - (rif: 8829)

Nascosti i pulsanti in alto che non servono.
Aggiunto pulsante per configurare i parametri a livello di progetto

**_Aggiunta presa ordini da foto._** - (rif: 8846)

Aggiunta presa ordini da item foto (preview item a tutto schermo).

**_Miglioramenti login/logout_** - (rif: 8857)

- non è possibile rientrare nell'applicazione una volta fatto il logout/esci
- altri miglioramenti validazione login

### Modifiche

**_Non viene ricalcolato il prezzo automatico se viene imputato un prezzo da parte dell'utente_** - (rif: 8809)

In inserimento ordine viene disabilitato il caricamento di default degli sconti o del prezzo dopo aver modificato la quantita se, almeno una volta, i prezzi o gli sconti sono stati modificati direttamente dall'utente. In questo caso questi non vengono più ricalcolati.

-------

## Rel. 2.9.0 del 05/07/2013

### Anomalie

**_Risolto problema con destinazioni diverse._** - (rif: 8850)

Risolto problema con destinazioni diverse.

-------

## Rel. 2.8.0 del 27/06/2013

### Anomalie

**_Corretto posizionamento in selezione giro visite_** - (rif: 8807)

Ora la lista dei clienti in inserimento ordine, nel caso di selezione giro visite, è correttamente posizionata alla sezione del giorno corrente

**_Inibita selezione clienti bloccati in girovisite_** - (rif: 8808)

Anche nel popup del girovisite non è possibile prendere ordini su clienti bloccati.

**_Sistemata regressione galleria_** - (rif: 8811)

Dal catalogo, apro una foto, scorro in avanti per una decina di foto, fine, mi posiziona nella foto su cui mi sono fermato, non più su quella di partenza.

**_Incassi non visibili dopo aggiornamento_** - (rif: 8823)

Ora si vedono gli incassi salvati associati a scadenze, anche dopo la ri-sincronizzazione delle scadenze.


### Novità

**_Blocchi modifica prezzi o sconti per utente_** - (rif: 8579)

Vengono gestiti dei parametri lato license manager che impediscono la modifica di prezzi o sconti proposti dal sistema

**_Aggiunto nuovo modulo: Reports_** - (rif: 8720)

Aggiunto nuovo modulo contenente i report di BI.

**_Cambiato il messaggio di errore nel caso di "Server non raggiungibile"_** - (rif: 8777)

Ora questo tipo di errore viene mappato con un errore comprensibile per l'utente finale e non con "errore generico".

**_Estesa la ricerca dei clienti_** - (rif: 8789)

Nella ricerca del cliente o fornitore, oltre che per codice e descrizione, aggiunta ricerca per i seguenti attributi: 
CAP, Provincia, Città, Indirizzo.

**_Miglioramenti UI in modulo CRM_** - (rif: 8810)

Rivista gestione filtri offerte (leads, stati, date).
Miglioramenti visuali nella lista delle offerte.
Inserito controllo obbligatorietà ragione sociale e gestione note in "popover" per inserimento nuovo lead.


**_Invio notifiche push da am_** - (rif: 8828)

Sono state implementate alcune modifiche al form di invio notifiche push da am:
1. Aggiunta l'opzione tutti per mandare la notifica a tutti quanti.
2. Aggiunto un messaggio che indica l'avvenuto invio
3. Gestiti errori su contenuto messaggio

### Modifiche

**_Inclusa visibilita clienti anche per agenti associati a destinazioni_** - (rif: 8840)

In fase di estrazione dati dal connettore, ora vengono inclusi anche i clienti associati ad agenti collegati alle destinazioni.


-------

## Rel. 2.7.0 del 07/06/2013

### Anomalie

**_Scheda Prodotti: risolto problema di visualizzazione dati_** - (rif: 8783)

Quando la descrizione dell'articolo e' molto lunga, i prezzi venivano sovrascritti nei dettagli "ultimi prezzi di acquisto e vendita"

**_Filtro in ordini veloci_** - (rif: 8797)

Corretto il filtro per destinazione

### Modifiche

**_Cambiata dicitura "Uguale sede" con "Nessuna destinazione diversa"_** - (rif: 8780)

Nel form ordine, quando si sceglie destinazioni diverse ora viene proposto:
- "Nessuna destinazione diversa" (default, in inserimento)
- Tutte le altre destinazioni diverse associate al cliente

Da ricordare che se viene preso un ordine da storico, la destinazione selezionata è l'ultima destinazione (quella presente sullo storico).

-------

## Rel. 2.6.0 del 31/05/2013

### Novità

**_CRM:  nuova funzione Schede Leads_** - (rif: 8717)

Aggiunta nuova funzione Schede Leads in modulo CRM

**_CRM: Aggiunta nuova funzione Offerte_** - (rif: 8719)

Possibilità di vedere le offerte raggruppate per lead. Varie possibilità di filtro ed ordinamento.

**_CRM: Nuovi Leads_** - (rif: 8743)

Aggiunta nuova funzione Nuovi Leads in modulo CRM.

**_Giro visite: selezione cliente_** - (rif: 8753)

Aggiunta possibilità di selezionare il cliente con cui viene effettuato l'ordine attraverso il giro viste.

**_Scheda prodotti: miglioramenti visualizzazione dati_** - (rif: 8779)

Ad esempio nella lista prodotti aggiunta una gestione ordinamento (simile a quella di ordini veloci)



