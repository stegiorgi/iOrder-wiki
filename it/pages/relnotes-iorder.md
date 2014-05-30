# Note di rilascio

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

## Versioni vecchie


