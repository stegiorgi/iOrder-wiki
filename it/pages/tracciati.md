
# Specifiche Tracciati Record


# Import DATI
I files di import (verso gli ipad), devono essere creati dal gestionale e depositati nella cartella c:\dropbox\nomeazienda\gestionali, e devono seguire le seguenti regole:

  * Il separatore dei campi e' il pipe
  * I files devono avere tutti le intestazione di colonna (Es: COD_DITTA|CHIAVE|...ecc)
  * Le date devono avere il formato ddmmyyyy e riempimento a sx con zeri (es: per 10 gennaio 2013, 10012013)
  * Il separatore decimale è la virgola
  * La data di ultima modifica (DAT_ULT_MOD) è obsoleta e va impostata a 01011900000000 per motivi di compatibilità.
  * Le righe non devono concludersi con un separatore (es: DAT_ULT_MOD, no DAT_ULT_MOD|)
  * I testi NON devono MAI contenere il carattere separatore | (pipe).
  * Eventuali newline (chr(10, char(13), presenti nei testi devono essere sostituiti con il carattere §
  * I testi non devono mai superare i 4000 caratteri

##io_art.dat
Tabella anagrafica che contiene tutti i prodotti

| Prg| Campo | Descrizione| Tipo| Lungh.|  
|- 
| 1| CHIAVE| Chiave univoca del record composta dai dati di origine| Character| 250|
| 2| COD_DITTA| Codice della ditta. Identifica univocamente una ditta dentro il gestionale che, nel caso sia multisocietario, può contenere dati di più aziende| Character| 50|
| 3| COD_ART| Codice dell'articolo| Character| 25|
| 4| DES_ART| Descrizione dell'articolo| Text| 8000|
| 5| COD_FAM| Codice della famiglia degli articoli| Character| 4|
| 6| DES_FAM| Descrizione della famiglia| Character| 30|
| 7| COD_SFAM| Codice della sottofamiglia degli articoli| Character| 4|
| 8| DES_SFAM| Descrizione della sottofamiglia| Character| 30|
| 9| COD_GRUPPO1| Codice del Gruppo merceologico dell'articolo (1)| Character| 4|
| 10| DES_GRUPPO1| Descrizione del gruppo merceologico dell'articolo (1)| Character| 30|
| 11| COD_GRUPPO2| Codice del Gruppo merceologico dell'articolo (2)| Character| 4|
| 12| DES_GRUPPO2| Descrizione del gruppo merceologico dell'articolo (2)| Character| 30|
| 13| UM1| Unità di misura 1| Character| 3|
| 14| UM2| Seconda unità di misura| Character| 3|
| 15| FATTORE_CONVERSIONE| Fattore di conversione. Coefficiente che se moltiplicato alla quantità 1 riporta la quantità di una seconda unità di misura. Per passare dalla unità di misura 2 alla unità di misura 1 occorre eseguire una divisione| Decimal| 16,10|
| 16| DES_GR_STAT1| Descrizione del gruppo statico dell'articolo (1)| Character| 30|
| 17| DES_GR_STAT2| Descrizione del gruppo statico dell'articolo (2)| Character| 30|
| 18| QTA_MIN_VEND| Quantità minima di vendita| Decimal| 25,8|
| 19| COD_CLASSE_SCONTO| Codice identificativo della classe sconto del cliente| Character| 50|
| 20| COD_DEPERIBILITA| Codice identificativo della deperibilità dell'articolo. Questo codice viene utilizzato per determinare la rottura degli ordini. Ad esempio per l'art.62 gli articoli di tipo deperibile non possono essere messi in ordini con articoli non deperibili.| Character| 50|
| 21| PREZZO_MIN_VEN| prezzo minimo di vendita| Decimal| 28,8|
| 22| SCONTO_MAX_VEN| massimo sconto di vendita| Decimal| 14,6|
| 23| MAX_EXTRA_SCONTO| massimo extra sconto consentito| Decimal| 14,6|
| 24| COD_SVILUPPO_BASE| Codice sviluppo base (wtrendy)| Character| 255|
| 25| DAT_ULT_MOD| Data di ultima modifica del record. Attenzione: Questa data deve essere composta nel seguente formato: Giorno (2 caratteri) + Mese (2 caratteri) + Anno (4 caratteri) + Ore (2 caratteri) + Minuti (2 caratteri) + Secondi (2 caratteri).| DateTime| 16|

##io_art_conf.dat
Anagrafica dei codici confezione

| Prg| Campo | Descrizione| Tipo| Lungh.|  
|- 
| 1| CHIAVE| Chiave univoca del record composta dai dati di origine| Character| 250|
| 2| COD_ART| Codice dell'Articolo| Character| 25|
| 3| COD_DITTA| Codice della ditta. Identifica univocamente una ditta dentro il gestionale che, nel caso sia multisocietario, può contenere dati di più aziende| Character| 50|
| 4| COD_CONF| Codice della confezione| Character| 4|
| 5| PZ_CONF| Pezzi della confezione| Decimal| 12,3|
| 6| FLG_PREF| Flag per definire il preferenziale| Integer| 10|
| 7| DAT_ULT_MOD| Data di ultima modifica del record. Attenzione: Questa data deve essere composta nel seguente formato: Giorno (2 caratteri) + Mese (2 caratteri) + Anno (4 caratteri) + Ore (2 caratteri) + Minuti (2 caratteri) + Secondi (2 caratteri).| DateTime| 16|

##io_art_lang.dat
articoli in lingua

| Prg| Campo | Descrizione| Tipo| Lungh.|  
|- 
| 1| CHIAVE| Chiave univoca del record composta dai dati di origine| Character| 250|
| 2| COD_DITTA| Codice della ditta. E' il codice che identifica univocamente una ditta dentro il gestionale che, nel caso sia multisocietario, può contenere dati di più aziende| Character| 50|
| 3| COD_ART| Codice dell'articolo| Character| 50|
| 4| COD_LINGUA| Codice della lingua| Character| 50|
| 5| DES_ART| Descrizione dell'articolo| Character| 255|
| 6| DAT_ULT_MOD| Data di ultima modifica del record| DateTime| 16|

##io_art_ultacq.dat
Tabella di anagrafica del prodotto ultimo acquisto del fornitore

| Prg| Campo | Descrizione| Tipo| Lungh.|  
|- 
| 1| CHIAVE| Chiave univoca del record composta dai dati di origine| Character| 250|
| 2| COD_DITTA| Codice della ditta. Identifica univocamente una ditta dentro il gestionale che, nel caso sia multisocietario, può contenere dati di più aziende| Character| 50|
| 3| COD_ART| Codice dell'articolo| Character| 25|
| 4| PROG| Numero progressivo| Integer| 3|
| 5| VALUTA| Valuta| Character| 4|
| 6| PRZ| Prezzo| Decimal| 28,8|
| 7| DATA_DOC| Data del documento| Date| 10|
| 8| NUM_DOC| Numero del documento| Integer| 7|
| 9| COD_CLFOR| Codice Cliente / Fornitore| Character| 50|
| 10| TIPO_DOC| Indicatore sulla tipologia di documento| Character| 50|
| 11| DAT_ULT_MOD| Data di ultima modifica del record. Attenzione: Questa data deve essere composta nel seguente formato: Giorno (2 caratteri) + Mese (2 caratteri) + Anno (4 caratteri) + Ore (2 caratteri) + Minuti (2 caratteri) + Secondi (2 caratteri).| DateTime| 16|

##io_art_ultven.dat
Tabella di anagrafica del prodotto ultima vendita del cliente

| Prg| Campo | Descrizione| Tipo| Lungh.|  
|- 
| 1| CHIAVE| Chiave univoca del record composta dai dati di origine| Character| 250|
| 2| COD_DITTA| Codice della ditta. Identifica univocamente una ditta dentro il gestionale che, nel caso sia multisocietario, può contenere dati di più aziende| Character| 50|
| 3| COD_ART| Codice dell'articolo| Character| 25|
| 4| PROG| Numero progressivo| Integer| 3|
| 5| VALUTA| Valuta| Character| 4|
| 6| PRZ| Prezzo| Decimal| 28,8|
| 7| DATA_DOC| Data del documento di riferimento| Date| 10|
| 8| NUM_DOC| Numero del documento di riferimento| Integer| 7|
| 9| COD_CLFOR| Codice Cliente / Fornitore| Character| 50|
| 10| DAT_ULT_MOD| Data di ultima modifica del record. Attenzione: Questa data deve essere composta nel seguente formato: Giorno (2 caratteri) + Mese (2 caratteri) + Anno (4 caratteri) + Ore (2 caratteri) + Minuti (2 caratteri) + Secondi (2 caratteri).| DateTime| 16|

##io_art_um.dat
Unità di misura degli articoli

| Prg| Campo | Descrizione| Tipo| Lungh.|  
|- 
| 1| CHIAVE| Chiave univoca del record composta dai dati di origine| Character| 250|
| 2| COD_DITTA| Codice della ditta. Identifica univocamente una ditta dentro il gestionale che, nel caso sia multisocietario, può contenere dati di più aziende| Character| 50|
| 3| COD_ART| Codice dell'articolo| Character| 50|
| 4| UM| Unità di misura| Character| 50|
| 5| DESC_UM| Descrizione Unita di misura| Character| 1000|
| 6| FAT_CONV| Fattore di conversione. Coefficiente che se moltiplicato alla quantità 1 riporta la quantità di una seconda unità di misura. Per passare dalla unità di misura 2 alla unità di misura 1 occorre eseguire una divisione (vuoto per unità di misura 1)| Decimal| 15,5|
| 7| TIPO_UM| Tipo unita di misura (1= Principale, 2=Secondarie, 3=Confezione)| Integer| 1|
| 8| DAT_ULT_MOD| Data di ultima modifica del record| DateTime| 16|

##io_campagne.dat
Anagrafica delle campagne marketing

| Prg| Campo | Descrizione| Tipo| Lungh.|  
|- 
| 1| CHIAVE| Chiave univoca del record composta dai dati di origine| Character| 250|
| 2| COD_DITTA| Codice della ditta. Identifica univocamente una ditta dentro il gestionale che, nel caso sia multisocietario, può contenere dati di più aziende| Character| 50|
| 3| COD_CAMPAGNA| Codice Campagna| Character| 50|
| 4| DES_CAMPAGNA| descrizione campagna| Character| 255|
| 5| DAT_ULT_MOD| Data di ultima modifica del record| DateTime| 16|

##io_citta.dat
Lista anagrafica delle città

| Prg| Campo | Descrizione| Tipo| Lungh.|  
|- 
| 1| CHIAVE| Chiave univoca del record composta dai dati di origine| Character| 250|
| 2| COD_DITTA| Codice della ditta. Identifica univocamente una ditta dentro il gestionale che, nel caso sia multisocietario, può contenere dati di più aziende| Character| 50|
| 3| CODICE| Codice della citta| Character| 4|
| 4| DESCRIZIONE| descrizione della citta| Character| 40|
| 5| CAP| Codice Avviamento Postale| Character| 8|
| 6| PROVINCIA| provincia| Character| 2|
| 7| DAT_ULT_MOD| Data di ultima modifica del record| DateTime| 16|

##io_clifor_gen.dat
tabella di anagrafica clienti/fornitore di un progetto o ditta (azienda) che viene importata in automatico; ogni riga è un cliente della ditta

| Prg| Campo | Descrizione| Tipo| Lungh.|  
|- 
| 1| CHIAVE| Chiave univoca del record composta dai dati di origine| Character| 250|
| 2| COD_DITTA| Codice della ditta. E' il codice che identifica univocamente una ditta dentro il gestionale che, nel caso sia multisocietario, può contenere dati di più aziende| Character| 50|
| 3| TIPO_CLIFOR| Tipologia (0=Cliente, 1=Fornitore)| Integer| 2|
| 4| COD_CLIFOR| Codice Cliente / Fornitore| Character| 50|
| 5| RAG_SOC| Ragione sociale| Character| 255|
| 6| INDIRIZZO| Indirizzo| Character| 255|
| 7| PARTITA_IVA| Partita iva| Character| 50|
| 8| CODICE_FISCALE| Codice fiscale| Character| 20|
| 9| TELEFONO1| Numero di telefono 1 del cliente/fornitore| Character| 255|
| 10| TELEFONO2| Numero di telefono 2 del cliente/fornitore| Character| 255|
| 11| FAX| Fax| Character| 255|
| 12| CELLULARE| Telefono cellulare| Character| 255|
| 13| EMAIL| Indirizzo email| Character| 255|
| 14| INTERNET| WEB| Character| 255|
| 15| CAP| Codice di avviamento postale| Character| 20|
| 16| CITTA| Città| Character| 255|
| 17| PROVINCIA| Provincia| Character| 255|
| 18| LATITUDINE| Chiave univoca del record ereditata dai dati di origine| Character| 50,6|
| 19| LONGITUDINE| Chiave univoca del record ereditata dai dati di origine| Character| 50,6|
| 20| COD_CLASSE_SCONTO| Codice identificativo della classe sconto del cliente| Character| 50|
| 21| FLG_MOD_NEL_DISP| flag per specificare se questo cliente o fornitore può essere modificato nel dispositivo| Integer| 2|
| 22| FLG_DEPERIBILITA| serve per attivare la gestione degli articoli deperibili e quindi suddividere gli ordini che arrivano dai dispositivi| Integer| 2|
| 23| COD_CAT_EXTRA_SCONTO| Codice identificativo della categoria extra sconto (es. 01 = affiliati; 02 = non affilitati; 03= con griglia; 04=normali)| Character| 50|
| 24| COD_SVILUPPO| Chiave dello sviluppo| Character| 255|
| 25| NAZIONE| Descrizione della nazione| Character| 255|
| 26| PAGAMENTO| Pagamento (es: Rimessa diretta a vista fattura; R.D. 60 GG. DATA FATTURA)| Character| 255|
| 27| BANCA| Banca| Character| 255|
| 28| AGENZIA| Agenzia| Character| 255|
| 29| LISTINO_ANAGRAFICO| Listino anagrafico| Character| 255|
| 30| VALUTA| Descrizione della valuta (Es: Euro)| Character| 100|
| 31| SCONTI_ANAG_PERC| Sconti anagrafici in percentuale| Character| 255|
| 32| SCONTI_ANAG_IMP| Sconti anagrafica imponibile| Decimal| 14,6|
| 33| MAGGIORAZIONE_ANAG_PERC| Maggiorazione anagrafica percentuale| Decimal| 6,3|
| 34| SCONTO_PIEDE| Sconto piede| Decimal| 6,3|
| 35| COD_LISTINO| Codice del listino anagrafico| Character| 50|
| 36| COD_CONDPAG| Codice del listino anagrafico| Character| 50|
| 37| COD_VALUTA| | Character| 50|
| 38| MACROAREA| Macroarea di riferimento dell'azienda| Character| 255|
| 39| DATA_CREAZIONE| Data di creazione del record| Date| 10|
| 40| AREA| Area di appartenenza dell'azienda| Character| 255|
| 41| ZONA| Zona (campo descrittivo)| Character| 255|
| 42| MACROCATEGORIA| Macrocategoria di appartenenza dell'azienda| Character| 255|
| 43| DATA_ULT_DOC_NO_FT| Data dell'ultimo documento non fatturato| Date| 10|
| 44| CATEGORIA| Categoria di appartenenza dell'azienda| Character| 255|
| 45| SOTTOCATEGORIA| Categoria di appartenenza dell'azienda| Character| 255|
| 46| DATA_ULT_DOC_FT| Data ultimo documento fatturato| Date| 10|
| 47| DATA_ULT_ORDINE| Data dell'ultimo ordine| Date| 10|
| 48| FIDO_AZIENDALE| Fido aziendale| Decimal| 15,2|
| 49| DES_RAGGR1| Raggruppamento 1 (campo descrittivo)| Character| 255|
| 50| DES_RAGGR2| Raggruppamento 2 (campo descrittivo)| Character| 255|
| 51| DES_RAGGR3| Raggruppamento 3 (campo descrittivo)| Character| 255|
| 52| COD_MACROAREA| Codice della Macroarea| Character| 50|
| 53| COD_AREA| Codice dell'area| Character| 50|
| 54| COD_ZONA| Codice dell'area| Character| 50|
| 55| COD_MACROCATEGORIA| Codice della Macroarea| Character| 50|
| 56| COD_CATEGORIA| Codice della Macroarea| Character| 50|
| 57| COD_SOTTOCATEGORIA| Codice della Macroarea| Character| 50|
| 58| FLG_NEW_CLIFOR| flag per specificare se questo cliente o fornitore deve abilitare l'inserimento di un nuovo cliente in fase di inserimento ordine| Integer| 2|
| 59| DAT_ULT_MOD| Data di ultima modifica del record| DateTime| 16|

##io_clifor_age.dat
tabella di anagrafica agenti di un cliente/fornitore

| Prg| Campo | Descrizione| Tipo| Lungh.|  
|- 
| 1| CHIAVE| Chiave univoca del record composta dai dati di origine| Character| 250|
| 2| COD_DITTA| Codice della ditta. Identifica univocamente una ditta dentro il gestionale che, nel caso sia multisocietario, può contenere dati di più aziende| Character| 50|
| 3| TIPO_CLIFOR| Tipologia (0=Cliente, 1=Fornitore)| Integer| 1|
| 4| COD_CLIFOR| Codice Cliente / Fornitore| Character| 50|
| 5| COD_AGE| Codice dell'agente| Character| 50|
| 6| RAGSOC_AGE| Ragione sociale dell'agente| Character| 40|
| 7| PREFERENZIALE| Flag agente preferenziale (1 o 0)| Integer| 1|
| 8| DAT_ULT_MOD| Data di ultima modifica del record| DateTime| 16|

##io_clifor_blo.dat
Tabella di anagrafica del blocco di un cliente/fornitore

| Prg| Campo | Descrizione| Tipo| Lungh.|  
|- 
| 1| CHIAVE| Chiave univoca del record composta dai dati di origine| Character| 250|
| 2| COD_DITTA| Codice della ditta. Identifica univocamente una ditta dentro il gestionale che, nel caso sia multisocietario, può contenere dati di più aziende| Character| 50|
| 3| TIPO_CLIFOR| Tipologia (0=Cliente, 1=Fornitore)| Integer| 1|
| 4| COD_CLIFOR| Codice Cliente / Fornitore| Character| 50|
| 5| COD_BLOCCO| Codice blocco | Integer| 2|
| 6| TIPO_BLOCCO| Tipologia del blocco | Character| 15|
| 7| NOTA_BLOCCO| Descrizione del blocco del cliente/fornitore| Text| 4000|
| 8| DATA_BLOCCO| Data blocco | Date| 10|
| 9| DAT_ULT_MOD| Data di ultima modifica del record| DateTime| 16|

##io_clifor_dest.dat
Tabella di anagrafica della destinazione dei prodotti acquistati da un cliente/fornitore

| Prg| Campo | Descrizione| Tipo| Lungh.|  
|- 
| 1| CHIAVE| Chiave univoca del record composta dai dati di origine| Character| 250|
| 2| COD_DITTA| Codice della ditta. Identifica univocamente una ditta dentro il gestionale che, nel caso sia multisocietario, può contenere dati di più aziende| Character| 50|
| 3| TIPO_CLIFOR| Tipologia (0=Cliente, 1= Fornitore)| Integer| 1|
| 4| COD_CLIFOR| Codice Cliente/Fornitore| Character| 50|
| 5| PREFERENZIALE| Flag di destinazione Preferenziale| Integer| 10|
| 6| COD_DEST| Codice della Destinazione dei prodotti| Character| 4|
| 7| RAG_SOC_DEST| Ragione Sociale della Destinazione dei pordotti| Text| 8000|
| 8| INDIRIZZO| Indirizzo di destinazione| Text| 8000|
| 9| CAP| Codice Avviamento Postale della destinazione| Character| 8|
| 10| CITTA| Citta di destinazione dei prodotti| Text| 8000|
| 11| PROVINCIA| Provincia di destinazione| Character| 2|
| 12| STAMPA_PREF_DOC| Descrizione del tipo di stampa preferito per li documento| Character| 6|
| 13| TELEFONO| Recapito telefonico della destinazione dei prodotti| Character| 20|
| 14| CELLULARE| Recapito telefonico della destinazione dei prodotti| Character| 20|
| 15| MAIL| Recapito posta elettronica della destinazione dei prodotti| Character| 40|
| 16| FAX| Recapito fax della destinazione dei prodotti| Character| 20|
| 17| NOTE_DEST| Campo descrittivo libero per la destinazione dei prodotti| Text| 512|
| 18| DAT_ULT_MOD| Data di ultima modifica del record| DateTime| 16|

##io_clifor_detcon.dat
Tabella di anagrafica dei dettagli contatto di un cliente/fornitore

| Prg| Campo | Descrizione| Tipo| Lungh.|  
|- 
| 1| CHIAVE| Chiave univoca del record composta dai dati di origine| Character| 250|
| 2| COD_DITTA| Codice della ditta. Identifica univocamente una ditta dentro il gestionale che, nel caso sia multisocietario, può contenere dati di più aziende| Character| 50|
| 3| TIPO_CLIFOR| Tipologia (0=Cliente, 1=Fornitore)| Integer| 1|
| 4| COD_CLIFOR| Codice Cliente / Fornitore| Character| 50|
| 5| ID_CONTATTO| Identificativo univoco del contatto| Integer| 8|
| 6| TIPO_CONTATTO| Tipologia del contatto (es: uff. acquisti)| Character| 40|
| 7| PREF| Preferenziale (1 o 0)| Integer| 1|
| 8| COGNOME| Cognome del contatto| Character| 50|
| 9| NOME| Nome del contatto| Character| 255|
| 10| INDIRIZZO| indirizzo| Character| 50|
| 11| CAP| Codice Avviamento Postale| Character| 8|
| 12| CITTA| Città| Character| 50|
| 13| PR| Provincia| Character| 2|
| 14| ORARIO_LAVORO| Orario di Lavoro| Character| 100|
| 15| TELEFONO1| Numero di telefono 1| Character| 20|
| 16| TELEFONO2| Numero di telefono 2| Character| 20|
| 17| CELLULARE1| Numero di telefono cellulare 1| Character| 20|
| 18| CELLULARE2| Numero di telefono cellulare 2| Character| 20|
| 19| TELEF_CASA| Numero di telefono casa| Character| 20|
| 20| FAX| Numero di FAX| Character| 20|
| 21| EMAIL1| Indirizzo e-mail del contatto 1| Character| 100|
| 22| EMAIL2| Indirizzo e-mail del contatto 2| Character| 100|
| 23| ALTRO_INDIRIZZO1| Altro indirizzo 1| Character| 50|
| 24| ALTRO_INDIRIZZO2| Altro indirizzo 2| Character| 50|
| 25| NOTE| Campo Note Libero| Text| 9999|
| 26| DAT_ULT_MOD| Data di ultima modifica del record| DateTime| 16|

##io_clifor_fatt.dat
Tabella di anagrafica del fatturato mensile di un cliente/fornitore

| Prg| Campo | Descrizione| Tipo| Lungh.|  
|- 
| 1| CHIAVE| Chiave univoca del record composta dai dati di origine| Character| 250|
| 2| COD_DITTA| Codice della ditta. Identifica univocamente una ditta dentro il gestionale che, nel caso sia multisocietario, può contenere dati di più aziende| Character| 50|
| 3| TIPO_CLIFOR| Tipologia (0=Cliente, 1=Fornitore)| Integer| 1|
| 4| COD_CLIFOR| Codice Cliente / Fornitore| Character| 50|
| 5| ANNO| Anno| Integer| 10|
| 6| MESE| Mese| Integer| 10|
| 7| FATTURATO| Fatturato Totale| Decimal| 28,8|
| 8| DAT_ULT_MOD| Data di ultima modifica del record| DateTime| 16|

##io_clifor_girovisita.dat
Tracciato girovisite. In questo tracciato, per ogni agente, sono associati i clienti suddivisi per giorno della settimana. I dati qui contenuto vengono mostrati nella maschera di ricerca del cliente in fase di inserimento dell'ordine. In tale maschera i clienti sono suddivisi per giorno della settimana. In tal modo l'agente ha una sorta di agenda di quali clienti deve visitare in un determinato giorno.

| Prg| Campo | Descrizione| Tipo| Lungh.|  
|- 
| 1| CHIAVE| Chiave univoca del record composta dai dati di origine| Character| 250|
| 2| COD_DITTA| Codice della ditta. Identifica univocamente una ditta dentro il gestionale che, nel caso sia multisocietario, può contenere dati di più aziende| Character| 50|
| 3| COD_CLIFOR| Codice Cliente / Fornitore| Character| 50|
| 4| COD_AGE| Codice dell'agente| Character| 50|
| 5| COD_DEST| Codice della destinazione| Character| 50|
| 6| GG_VISITA| Giorno definito per la visita dal cliente (1= Lunedì, 2=Martedì, ecc)| Integer| 2|
| 7| SEQUENZA| sequenza di vista in un determinato giorno| Integer| 9|
| 8| GG_ULT_VISITA| giorno dell'ultima visita fatta dal cliente| Integer| 2|
| 9| DAT_ULT_VISITA| data dell'ultima vista fatta dal cliente| Date| 10|
| 10| DAT_ULT_MOD| Data di ultima modifica del record| DateTime| 16|

##io_clifor_note.dat
tabella delle note di un cliente/fornitore

| Prg| Campo | Descrizione| Tipo| Lungh.|  
|- 
| 1| CHIAVE| Chiave univoca del record composta dai dati di origine| Character| 250|
| 2| COD_DITTA| Codice della ditta. Identifica univocamente una ditta dentro il gestionale che, nel caso sia multisocietario, può contenere dati di più aziende| Character| 50|
| 3| TIPO_CLIFOR| Tipologia (0=Cliente, 1=Fornitore)| Integer| 1|
| 4| COD_CLIFOR| Codice Cliente / Fornitore| Character| 50|
| 5| PROGRESSIVO| Progressivo di nota| Integer| 3|
| 6| TIPO_NOTA| Tipologia di nota (es: resp acquisti)| Text| 4000|
| 7| NOTA| Note libere| Text| 4000|
| 8| DAT_ULT_MOD| Data di ultima modifica del record| DateTime| 16|

##io_clifor_righdoc.dat
Tabella di anagrafica per le righe documento di un cliente/fornitore

| Prg| Campo | Descrizione| Tipo| Lungh.|  
|- 
| 1| CHIAVE| Chiave univoca del record composta dai dati di origine| Character| 250|
| 2| COD_DITTA| Codice della ditta. Identifica univocamente una ditta dentro il gestionale che, nel caso sia multisocietario, può contenere dati di più aziende| Character| 50|
| 3| NUM_REG| Numero di registrazione del documento| Character| 12|
| 4| DATA_DOC| Data del documento| Date| 10|
| 5| PRG_RIGA| Progressivo di riga| Integer| 6|
| 6| COD_RIGA| Codice riga (es. R3IRB; 02661; F94PA13150; F7CSTP; F6SC10510)| Character| 25|
| 7| DES_RIGA| Descrizione riga| Text| 1600|
| 8| COD_UM| Codice unità di misura (es: KG, PZ, CT)| Character| 3|
| 9| QTA| Quantità| Decimal| 25,8|
| 10| PRZ_LORDO| Prezzo lordo, comprensivo di IVA del prodotto | Decimal| 28,8|
| 11| PRZ_NETTO| Prezzo Netto del prodotto | Decimal| 28,8|
| 12| IMPORTO| Importo della riga del documento| Decimal| 28,8|
| 13| SC_1| Sconto 1 in percentuale| Decimal| 6,3|
| 14| SC_2| Sconto 2 in percentuale| Decimal| 6,3|
| 15| DATA_CONFERMA| Data del documento| Date| 10|
| 16| TIPO_CLIFOR| Tipologia (0=Cliente, 1=Fornitore)| Integer| 1|
| 17| COD_CLIFOR| Codice Cliente / Fornitore| Character| 50|
| 18| DAT_ULT_MOD| Data di ultima modifica del record| DateTime| 16|

##io_clifor_scadoc.dat
tabella delle scadenze dei documenti del cliente/fornitore

| Prg| Campo | Descrizione| Tipo| Lungh.|  
|- 
| 1| CHIAVE| Chiave univoca del record composta dai dati di origine| Character| 154|
| 2| COD_DITTA| Codice della ditta. Identifica univocamente una ditta dentro il gestionale che, nel caso sia multisocietario, può contenere dati di più aziende| Character| 50|
| 3| NUM_REG| Numero di registrazione del documento (numero di collegamento alla testata del documento)| Character| 12|
| 4| COD_RATA| Codice della rata| Character| 7|
| 5| DAT_SCAD| Data di scadenza| Date| 10|
| 6| IMPORTO| Importo della scadenza| Decimal| 28,8|
| 7| DES_TIPO| Descrizione del tipo (es: Rim.diretta; Ric. banc.; Bonifico)| Character| 255|
| 8| DES_STATO| Descrizione dello stato (Puo' valere solo questi Chiuso o Aperto)| Character| 255|
| 9| DES_OPERAZIONE| #NON Visibile in IPAD # Descrizione dell'operazione (es: Pag/Risc; Chiusura; Creazione; Insoluto)| Character| 255|
| 10| DES_BANCA_AGENZIA| #NON Visibile in IPAD #  Descrizione banca / agenzia| Character| 255|
| 11| COD_CLIFOR| Codice Cliente / Fornitore| Character| 50|
| 12| TIPO_CLIFOR| Tipologia (0=Cliente, 1=Fornitore)| Integer| 1|
| 13| DATA_DOC| Data del documento| Date| 10|
| 14| NUM_DOC| Numero del dcumento| Character| 20|
| 15| COD_VALUTA| Codice della valuta| Character| 50|
| 16| DAT_ULT_MOD| Data di ultima modifica del record| DateTime| 16|

##io_clifor_testdoc.dat
tabella anagrafica delle testate dei documenti di cliente/fornitore

| Prg| Campo | Descrizione| Tipo| Lungh.|  
|- 
| 1| CHIAVE| Chiave univoca del record composta dai dati di origine| Character| 250|
| 2| COD_DITTA| Codice della ditta. Identifica univocamente una ditta dentro il gestionale che, nel caso sia multisocietario, può contenere dati di più aziende| Character| 50|
| 3| TIPO_CLIFOR| Tipologia (0=Cliente, 1=Fornitore)| Integer| 1|
| 4| COD_CLIFOR| Codice Cliente / Fornitore| Character| 50|
| 5| COD_TIPODOC| Codice tipo documento| Integer| 2|
| 6| COD_STIPODOC| Codice sottotipo documento| Integer| 2|
| 7| FLGDAEVADERE| Flag da evadere| Integer| 10|
| 8| DATADOC| Data del documento| Date| 10|
| 9| NUMREG| Numero di registrazione del documento utilizzato come collegamento tra la testata e le righe| Character| 12|
| 10| TIPODOC| Tipo documento gestionale (CLS-DDT; CLS-ORDINE; CLP-ORDINE)| Character| 14|
| 11| TIPO| Tipo (es:DdT; Ordine Cl.)| Character| 20|
| 12| SOTTOTIPO| Sottotipo (es: Ven/Acq; Normale)| Character| 20|
| 13| NUMDOC| Numero del documento| Integer| 7|
| 14| VALUTA| Valuta| Character| 4|
| 15| TOTALEDOC| Totale del documento| Decimal| 28,8|
| 16| TIPOSTATO_DOC| Tipo stato documento| Integer| 2|
| 17| DESSTATO_DOC| Sottotipo (es: Ven/Acq; Normale)| Character| 100|
| 18| DATA_FATTURA| Data della fattura| Date| 10|
| 19| NUM_FATTURA| Numero di fattura| Character| 20|
| 20| NOTE_DOC| Note libere| Character| 4000|
| 21| DATA_CONFERMA| Data del documento| Date| 10|
| 22| DAT_ULT_MOD| Data di ultima modifica del record| DateTime| 16|

##io_condpag.dat
Condizioni di pagamento

| Prg| Campo | Descrizione| Tipo| Lungh.|  
|- 
| 1| CHIAVE| Chiave univoca del record composta dai dati di origine| Character| 250|
| 2| COD_DITTA| Codice della ditta. Identifica univocamente una ditta dentro il gestionale che, nel caso sia multisocietario, può contenere dati di più aziende| Character| 50|
| 3| CODICE| Codice condizioni di pagamento| Character| 6|
| 4| DESCRIZIONE| descrizione condizioni di pagamento| Character| 40|
| 5| SCONTO1| Ultimo sconto percentuale 1| Decimal| 14,6|
| 6| DAT_ULT_MOD| Data di ultima modifica del record| DateTime| 16|

##io_condpag_lang.dat
Condizioni di pagamento in lingua

| Prg| Campo | Descrizione| Tipo| Lungh.|  
|- 
| 1| CHIAVE| Chiave univoca del record composta dai dati di origine| Character| 250|
| 2| COD_DITTA| Codice della ditta. E' il codice che identifica univocamente una ditta dentro il gestionale che, nel caso sia multisocietario, può contenere dati di più aziende| Character| 50|
| 3| COD_COND_PAG| Codice condizioni di pagamento| Character| 50|
| 4| COD_LINGUA| Codice della lingua| Character| 50|
| 5| DES_COND_PAG| descrizione condizioni di pagamento| Character| 255|
| 6| DAT_ULT_MOD| Data di ultima modifica del record| DateTime| 16|

##io_customfields.dat
Questo tracciato viene utilizzato solo per aggiungere campi personalizzati. Per il dettaglio delle specifiche contattare il personale Apex-net

| Prg| Campo | Descrizione| Tipo| Lungh.|  
|- 
| 1| CHIAVE| Chiave univoca del record composta dai dati di origine| Character| 250|
| 2| COD_DITTA| Codice della ditta. Identifica univocamente una ditta dentro il gestionale che, nel caso sia multisocietario, può contenere dati di più aziende| Character| 50|
| 3| NOME| nome del campo personalizzato| Character| 255|
| 4| VALORE| valore del campo personalizzato| Text| 4000|
| 5| TIPO| tipologia (0=group, 1=item,....)| Integer| 50|
| 6| CHIAVE_PADRE| chiave de| Character| 250|
| 7| CONTESTO| identifica il contesto (lead, clienti, articoli)| Character| 255|
| 8| COD_EXT| codice dell'elemento  associato a questa customizzazione (es. codice  del lead)| Character| 50|
| 9| ORIENTAMENTO_NOME| orientamento del campo rispetto a quello precedente (orrizzontale starà di fianco, verticale starà sotto)| Integer| 2|
| 10| ORIENTAMENTO_VALORE| orientamento del valore rispetto al nome campo (normalmente è orrizzontale, mentre può essere verticale per i campi note che sono più alti)| Integer| 2|
| 11| ORDINAMENTO| ordinamento dei vari campi| Character| 50|
| 12| TIPO_DATO| tipo di dato (string, date, datetime, number, currency)| Integer| 2|
| 13| DAT_ULT_MOD| Data di ultima modifica del record| DateTime| 16|

##io_giacenze.dat
Tabella delle giacenze dei prodotti

| Prg| Campo | Descrizione| Tipo| Lungh.|  
|- 
| 1| CHIAVE| Chiave univoca del record composta dai dati di origine| Character| 250|
| 2| COD_DITTA| Codice della ditta. Identifica univocamente una ditta dentro il gestionale che, nel caso sia multisocietario, può contenere dati di più aziende| Character| 50|
| 3| COD_ARTICOLO| Codice dell'articolo| Character| 25|
| 4| COD_DEPOSITO| Codice identificativo del deposito| Character| 2|
| 5| DES_DEPOSITO| Descrizione deposito| Character| 255|
| 6| GIACENZA| Quantità disponibile in giacenza| Decimal| 25,8|
| 7| DISPONIBILITA| disponibilità in giacenza| Decimal| 25,8|
| 8| UM1| Unità di misura 1| Character| 3|
| 9| DAT_ULT_MOD| Data di ultima modifica del record| DateTime| 16|

##io_lead_acccrm.dat
Definizione accessi si offerte operatore su leads.

| Prg| Campo | Descrizione| Tipo| Lungh.|  
|- 
| 1| CHIAVE| Chiave univoca del record composta dai dati di origine| Character| 250|
| 2| COD_DITTA| Codice della ditta. Identifica univocamente una ditta dentro il gestionale che, nel caso sia multisocietario, può contenere dati di più aziende| Character| 50|
| 3| COD_OPERATORE| Codice operatore| Character| 50|
| 4| COD_OPERATORE_FIGLIO| operatore figlio gestito dall'operatore padre| Character| 50|
| 5| FLG_VISUALIZZA| flag di visualizzaizone| Character| 10|
| 6| FLG_MODIFICA| flag di modifica| Character| 10|
| 7| DAT_ULT_MOD| Data di ultima modifica del record| DateTime| 16|

##io_lead_accessi.dat
Associazione lead operatore. Ogni operatore vede i lead associati in questa tabella

| Prg| Campo | Descrizione| Tipo| Lungh.|  
|- 
| 1| CHIAVE| Chiave univoca del record composta dai dati di origine| Character| 250|
| 2| COD_DITTA| Codice della ditta. Identifica univocamente una ditta dentro il gestionale che, nel caso sia multisocietario, può contenere dati di più aziende| Character| 50|
| 3| COD_OPERATORE| Codice operatore| Character| 50|
| 4| COD_LEAD| Codice Cliente / Fornitore| Character| 50|
| 5| FLG_VISUALIZZA| flag di visualizzaizone| Character| 10|
| 6| FLG_MODIFICA| flag di modifica| Character| 10|
| 7| DAT_ULT_MOD| Data di ultima modifica del record| DateTime| 16|

##io_lead_detcon.dat
Dettagli anagrafici dei contatti clienti e fornitori

| Prg| Campo | Descrizione| Tipo| Lungh.|  
|- 
| 1| CHIAVE| Chiave univoca del record composta dai dati di origine| Character| 250|
| 2| COD_DITTA| Codice della ditta. Identifica univocamente una ditta dentro il gestionale che, nel caso sia multisocietario, può contenere dati di più aziende| Character| 50|
| 3| COD_LEAD| Codice Cliente / Fornitore| Character| 50|
| 4| COD_CONTATTO| Identificativo univoco del contatto| Character| 50|
| 5| TIPO_CONTATTO| Tipologia del contatto (es: uff. acquisti)| Character| 255|
| 6| COGNOME| Cognome del contatto| Character| 255|
| 7| NOME| Nome del contatto| Character| 255|
| 8| INDIRIZZO| Indirizzo| Character| 255|
| 9| CAP| Codice di avviamento postale| Character| 20|
| 10| CITTA| Città| Character| 255|
| 11| PROVINCIA| Provincia| Character| 255|
| 12| TELEFONO| Numero di telefono| Character| 255|
| 13| CELLULARE| Numero di cellulare| Character| 255|
| 14| FAX| Numero di fax| Character| 255|
| 15| EMAIL| Indirizzo email del contatto| Character| 255|
| 16| DAT_ULT_MOD| Data di ultima modifica del record| DateTime| 16|

##io_lead_note.dat
Note dei leads. Ricordarsi che nelle note i campi descrittivi non possono superare i 4000 caratteri. I newline devono essere sostituiti con il carattere §

| Prg| Campo | Descrizione| Tipo| Lungh.|  
|- 
| 1| CHIAVE| Chiave univoca del record composta dai dati di origine| Character| 250|
| 2| COD_DITTA| Codice della ditta. Identifica univocamente una ditta dentro il gestionale che, nel caso sia multisocietario, può contenere dati di più aziende| Character| 50|
| 3| COD_LEAD| Codice lead| Character| 50|
| 4| PROGRESSIVO| Progressivo di nota| Integer| 3|
| 5| TIPO_NOTA| Tipologia di nota (es: resp acquisti)| Text| 4000|
| 6| NOTA| Note libere| Text| 4000|
| 7| DAT_ULT_MOD| Data di ultima modifica del record| DateTime| 16|

##io_lead_righoff.dat
Righe delle offerte associate ai leads

| Prg| Campo | Descrizione| Tipo| Lungh.|  
|- 
| 1| CHIAVE| Chiave univoca del record composta dai dati di origine| Character| 250|
| 2| CHIAVE_TESTATA| Chiave della relativa testata offerta| Character| 250|
| 3| COD_DITTA| Codice della ditta. Identifica univocamente una ditta dentro il gestionale che, nel caso sia multisocietario, può contenere dati di più aziende| Character| 50|
| 4| COD_LEAD| Codice Cliente / Fornitore| Character| 50|
| 5| PRG_RIGA| Progressivo di riga| Integer| 6|
| 6| COD_RIGA| Codice riga (es. R3IRB; 02661; F94PA13150; F7CSTP; F6SC10510)
| Character| 50|
| 7| DES_RIGA| Descrizione riga| Character| 3900|
| 8| COD_UM| Codice unità di misura (es: KG, PZ, CT)| Character| 50|
| 9| QTA| Quantità| Decimal| 25,8|
| 10| PRZ_LORDO| Prezzo lordo, comprensivo di IVA del prodotto (non visibile in IPAD)| Decimal| 28,8|
| 11| PRZ_NETTO| Prezzo Netto del prodotto (non visibile in IPAD)| Decimal| 28,8|
| 12| IMPORTO| Importo della riga del documento| Decimal| 28,8|
| 13| SC_1| Percentuale di SCONTO 1| Decimal| 14,6|
| 14| SC_2| Percentuale Sconto 2| Decimal| 14,6|
| 15| SC_3| Percentuale Sconto 3| Decimal| 14,6|
| 16| SC_4| Percentuale Sconto 4| Decimal| 14,6|
| 17| SC_5| Percentuale Sconto 5| Decimal| 14,6|
| 18| SC_6| Percentuale Sconto 6| Decimal| 14,6|
| 19| DATA_CONFERMA| Data del documento| Date| 10|
| 20| COD_CLIFOR| Codice Cliente / Fornitore| Character| 50|
| 21| DAT_ULT_MOD| Data di ultima modifica del record| DateTime| 16|

##io_lead_sconti.dat
Sconti associati ai leads

| Prg| Campo | Descrizione| Tipo| Lungh.|  
|- 
| 1| CHIAVE| Chiave univoca del record composta dai dati di origine| Character| 250|
| 2| COD_DITTA| Codice della ditta. Identifica univocamente una ditta dentro il gestionale che, nel caso sia multisocietario, può contenere dati di più aziende| Character| 50|
| 3| COD_ART| Codice dell'articolo| Character| 50|
| 4| COD_LEAD| Codice lead| Character| 50|
| 5| CLASSE_ARTICOLO| Codice identificativo del deposito| Character| 50|
| 6| DES_CLASSE_ARTICOLO| descrizione della classe articolo| Character| 255|
| 7| QUANTITA_INIZIO| Quantità minima di vendita| Decimal| 25,8|
| 8| QUANTITA_FINE| Quantità minima di vendita| Decimal| 25,8|
| 9| DATA_INIZIO| Data di inizio validità del listino| Date| 10|
| 10| DATA_FINE| Data di fine validità del listino| Date| 10|
| 11| SCONTO1| Ultimo sconto percentuale 1| Decimal| 14,6|
| 12| TIPO_SCONTO1| Ttipologia di sconto S = sostitutivo C = cumulativo| Character| 5|
| 13| SCONTO2| Ultimo sconto percentuale 1| Decimal| 14,6|
| 14| TIPO_SCONTO2| Ttipologia di sconto S = sostitutivo C = cumulativo| Character| 5|
| 15| SCONTO3| Ultimo sconto percentuale 1| Decimal| 14,6|
| 16| TIPO_SCONTO3| Ttipologia di sconto S = sostitutivo C = cumulativo| Character| 5|
| 17| SCONTO4| Ultimo sconto percentuale 1| Decimal| 14,6|
| 18| TIPO_SCONTO4| Ttipologia di sconto S = sostitutivo C = cumulativo| Character| 5|
| 19| SCONTO5| Ultimo sconto percentuale 1| Decimal| 14,6|
| 20| TIPO_SCONTO5| Ttipologia di sconto S = sostitutivo C = cumulativo| Character| 5|
| 21| SCONTO6| Ultimo sconto percentuale 1| Decimal| 14,6|
| 22| TIPO_SCONTO6| Ttipologia di sconto S = sostitutivo C = cumulativo| Character| 5|
| 23| PRIORITA| Identifica il listino con priorità di importanz | Integer| 9|
| 24| DAT_ULT_MOD| Data di ultima modifica del record| DateTime| 16|

##io_lead_testoff.dat
Testate delle offerte associate ai leads

| Prg| Campo | Descrizione| Tipo| Lungh.|  
|- 
| 1| CHIAVE| Chiave univoca del record composta dai dati di origine| Character| 250|
| 2| COD_DITTA| Codice della ditta. Identifica univocamente una ditta dentro il gestionale che, nel caso sia multisocietario, può contenere dati di più aziende| Character| 50|
| 3| COD_LEAD| Codice Cliente / Fornitore| Character| 50|
| 4| COD_CLIFOR| Codice Cliente / Fornitore| Character| 50|
| 5| ANNO| anno| Character| 50|
| 6| SERIE| serie| Character| 50|
| 7| NUMERO| Numero offerta| Character| 50|
| 8| REVISIONE| revisione| Character| 50|
| 9| DATA| Data offerta| Date| 10|
| 10| REFERENTE| alla cortese attenzione di| Character| 255|
| 11| RIFERIMENTO| | Character| 255|
| 12| OGGETTO| oggetto| Character| 255|
| 13| COD_OPPORTUNITA| Codice opportunità| Character| 50|
| 14| DES_OPPORTUNITA| Tipo opportunita| Character| 255|
| 15| GG_VALIDITA| giorni di validità| Integer| 9|
| 16| COD_TIPO_OPERAZIONE| | Character| 50|
| 17| DES_TIPO_OPERAZIONE| | Character| 255|
| 18| COD_LISTINO| | Character| 50|
| 19| DES_LISTINO| | Character| 255|
| 20| COD_PAGAMENTO| | Character| 50|
| 21| DES_PAGAMENTO| | Character| 255|
| 22| DATA_CONSEGNA| | Date| 10|
| 23| GG_CONSEGNA| giorni di validità| Integer| 9|
| 24| DES_CONSEGNA| | Character| 255|
| 25| RILASCIATO| status rilasciato| Character| 255|
| 26| STAMPATO| | Character| 255|
| 27| CONFERMATO| | Character| 255|
| 28| RIFIUTATO| | Character| 255|
| 29| EVASO| | Character| 255|
| 30| ANNULLATO| | Character| 255|
| 31| CHIUSO| | Character| 255|
| 32| NOTE| Note libere| Character| 4000|
| 33| TOTALE_OFFERTA| Totale dell'offerta| Decimal| 28,8|
| 34| DAT_ULT_MOD| Data di ultima modifica del record| DateTime| 16|

##io_leads.dat
Anagrafica dei leads

| Prg| Campo | Descrizione| Tipo| Lungh.|  
|- 
| 1| CHIAVE| Chiave univoca del record composta dai dati di origine| Character| 250|
| 2| COD_DITTA| Codice della ditta. Identifica univocamente una ditta dentro il gestionale che, nel caso sia multisocietario, può contenere dati di più aziende| Character| 50|
| 3| COD_LEAD| Codice Cliente / Fornitore| Character| 50|
| 4| COD_CLIFOR| Codice Cliente / Fornitore| Character| 50|
| 5| DESCRIZIONE1| Ragione sociale| Character| 255|
| 6| DESCRIZIONE2| Ragione sociale| Character| 255|
| 7| INDIRIZZO| Indirizzo| Character| 255|
| 8| CITTA| Città| Character| 255|
| 9| CAP| Codice di avviamento postale| Character| 20|
| 10| PROVINCIA| Provincia| Character| 255|
| 11| NAZIONE| NAZIONE| Character| 255|
| 12| DES_NOTE| Note libere| Character| 4000|
| 13| PARTITA_IVA| Partita iva| Character| 50|
| 14| CODICE_FISCALE| Codice fiscale| Character| 20|
| 15| TELEFONO| Numero di telefono 1 del cliente/fornitore| Character| 255|
| 16| FAX| Fax| Character| 255|
| 17| CELLULARE| Telefono cellulare| Character| 255|
| 18| EMAIL| Indirizzo email| Character| 255|
| 19| INTERNET| WEB| Character| 255|
| 20| LATITUDINE| Chiave univoca del record ereditata dai dati di origine| Character| 50,6|
| 21| LONGITUDINE| Chiave univoca del record ereditata dai dati di origine| Character| 50,6|
| 22| FLG_MOD_NEL_DISP| flag per specificare se questo cliente o fornitore può essere modificato nel dispositivo| Integer| 2|
| 23| COD_STATUS| codice stato del lead| Character| 50|
| 24| STATUS| descrizione dello stato del lead| Character| 255|
| 25| COD_CATEGORIA| Codice della Macroarea| Character| 50|
| 26| CATEGORIA| Categoria di appartenenza dell'azienda| Character| 255|
| 27| COD_ZONA| Codice dell'area| Character| 50|
| 28| ZONA| Zona (campo descrittivo)| Character| 255|
| 29| DATA_ULT_OFFERTA| Data dell'ultima offerta| Date| 10|
| 30| DATA_CREAZIONE| Data di creazione del record| Date| 10|
| 31| BANCA1| Banca| Character| 255|
| 32| BANCA2| Banca| Character| 255|
| 33| COD_LISTINO| Codice del listino anagrafico| Character| 50|
| 34| LISTINO| Listino anagrafico| Character| 255|
| 35| FLG_PRIVACY| flag di autorizzazione privacy| Character| 10|
| 36| DES_PRIVACY| descrizione per il flag di autorizzazione privacy| Character| 80|
| 37| FLG_CONTATTATO| flag già contattato| Character| 10|
| 38| DES_CONTATTATO| descrizione per il flag contattato| Character| 255|
| 39| FLG_NON_INTERESSATO| flag non interessato| Character| 10|
| 40| DES_NON_INTERESSATO| descrizione per il flag non interessato| Character| 255|
| 41| DAT_ULT_MOD| Data di ultima modifica del record| DateTime| 16|

##io_listini_full.dat
Tabella di anagrafica dei listini per prodotto completa.
Questa tabella va riempita con tutti i prezzi lordi. Le colonne sono gli elementi discriminanti (filtri) che partecipano alla selezione del prezzo.
Un valore null in uno di questi campi significa che il prezzo indicato vale per tutti i valori possibili.{br}
Esempio 1:
* COD_CLIFOR = 10
* COD_ART = null (empty string)
* PREZZO 20
In questo caso, il prezzo è 20 per il cliente 10 e per tutti gli articoli.

Esempio 2:
* COD_CLIFOR = 10
* COD_ART = ART02
* PREZZO 25
Se fosse presente una seconda riga con questi valori, nel caso in cui l'articolo vale ART02, il prezzo e' 25. Per tutti gli altri articoli vale 20.

Il funzionamento sull'algoritmo di calcolo dei listini è descritto nell'articolo [iOrder-Gestione-listini|Gestione listini]


| Prg| Campo | Descrizione| Tipo| Lungh.|  
|- 
| 1| CHIAVE| Chiave univoca del record composta dai dati di origine| Character| 250|
| 2| COD_DITTA| Codice della ditta. Identifica univocamente una ditta dentro il gestionale che, nel caso sia multisocietario, può contenere dati di più aziende| Character| 50|
| 3| TIPO_LISTINO| | Character| 50|
| 4| COD_ART| Codice dell'articolo| Character| 50|
| 5| TIPO_CLIFOR| Tipologia (0=Cliente, 1=Fornitore)| Integer| 2|
| 6| COD_CLIFOR| Codice Cliente / Fornitore| Character| 50|
| 7| COD_DEPOSITO| Codice identificativo del deposito| Character| 50|
| 8| COD_MACROAREA| Codice della Macroarea| Character| 50|
| 9| COD_AREA| Codice dell'area| Character| 50|
| 10| COD_ZONA| Codice dell'area| Character| 50|
| 11| COD_MACROCATEGORIA| Codice della Macroarea| Character| 50|
| 12| COD_CATEGORIA| Codice della Macroarea| Character| 50|
| 13| COD_SOTTOCATEGORIA| Codice della Macroarea| Character| 50|
| 14| COD_FAM_INIZIO| Famiglia di partenza| Character| 50|
| 15| COD_FAM_FINE| Famiglia di partenza| Character| 50|
| 16| COD_SFAM_INIZIO| Famiglia di partenza| Character| 50|
| 17| COD_SFAM_FINE| Famiglia di partenza| Character| 50|
| 18| COD_GRUPPO_INIZIO| Gruppo di partenza| Character| 50|
| 19| COD_GRUPPO_FINE| Gruppo di fine selezione| Character| 50|
| 20| COD_SGRUPPO_INIZIO| Gruppo di partenza| Character| 50|
| 21| COD_SGRUPPO_FINE| Gruppo di partenza| Character| 50|
| 22| COD_LISTINO| Codice del listino| Character| 50|
| 23| COD_CAMPAGNA| Codice della campagna| Character| 50|
| 24| COD_DESTINAZIONE| Codice destinazione| Character| 50|
| 25| COD_CLASSE| Codice classe| Character| 50|
| 26| COD_COMBINAZIONE| Codice della combinazione sulla gestione taglie e colori (Mettere null se la gestione taglie e colori non è utilizzata)| Character| 255|
| 27| COD_VALUTA| Definire il codice della valuta per la gestione del listino in valuta estera| Character| 50|
| 28| FLG_ESCLUDI_SCONTI| Flag che identifica un prezzo al quale non bisogna applicare gli scontidefiniti nel tracciato sconti| Character| 16|
| 29| QUANTITA_INIZIO| Quantità minima di vendita| Decimal| 25,8|
| 30| QUANTITA_FINE| Quantità minima di vendita| Decimal| 25,8|
| 31| DATA_INIZIO| Data di inizio validità del listino| Date| 10|
| 32| DATA_FINE| Data di fine validità del listino| Date| 10|
| 33| PREZZO| Prezzo dell'articolo per il listino in corso (lordo)| Decimal| 28,8|
| 34| PRIORITA| Identifica il listino con priorità di importanz | Integer| 9|
| 35| SCONTO1| Sconto in percentuale (Impostare a zero se si usa il tracciato sconti)| Decimal| 14,6|
| 36| SCONTO2| Sconto in percentuale (Impostare a zero se si usa il tracciato sconti)| Decimal| 14,6|
| 37| SCONTO3| Sconto in percentuale (Impostare a zero se si usa il tracciato sconti)| Decimal| 14,6|
| 38| SCONTO4| Sconto in percentuale (Impostare a zero se si usa il tracciato sconti)| Decimal| 14,6|
| 39| SCONTO5| Sconto in percentuale (Impostare a zero se si usa il tracciato sconti)| Decimal| 14,6|
| 40| SCONTO6| Sconto in percentuale (Impostare a zero se si usa il tracciato sconti)| Decimal| 14,6|
| 41| SCONTO_IMP| Sconto a importo| Decimal| 28,8|
| 42| MAG_PERC1| Maggiorazione 1 in percentuale (Impostare a zero se si usa il tracciato sconti)| Decimal| 14,6|
| 43| MAG_PERC2| Maggiorazione 2 in percentuale (Impostare a zero se si usa il tracciato sconti)| Decimal| 14,6|
| 44| MAG_IMP| Maggiorazione a importo (Impostare a zero se si usa il tracciato sconti)| Decimal| 28,8|
| 45| IND_GES_PREZZO| Indicatore gestione prezzo (Impostare a 4 se si usano gli sconti sul tracciato io_sconti.dat)| Character| 5|
| 46| IND_GES_SC1_PER| Indicatore gestione sconto 1 in percentuale (Impostare a zero se si usa il tracciato sconti)| Character| 5|
| 47| IND_GES_SC2_PER| Indicatore gestione sconto 2 in percentuale (Impostare a zero se si usa il tracciato sconti)| Character| 5|
| 48| IND_GES_SC3_PER| Indicatore gestione sconto 3 in percentuale (Impostare a zero se si usa il tracciato sconti)| Character| 5|
| 49| IND_GES_SC4_PER| Indicatore gestione sconto 4 in percentuale (Impostare a zero se si usa il tracciato sconti)| Character| 5|
| 50| IND_GES_SC5_PER| Indicatore gestione sconto 5 in percentuale (Impostare a zero se si usa il tracciato sconti)| Character| 5|
| 51| IND_GES_SC6_PER| Indicatore gestione sconto 6 in percentuale (Impostare a zero se si usa il tracciato sconti)| Character| 5|
| 52| IND_GES_SC_IMP| Indicatore gestione sconto importo (Impostare a zero se si usa il tracciato sconti)| Character| 5|
| 53| IND_GES_MAG1_PER| Indicatore gestione maggiorazione percentuale 1 (Impostare a zero se si usa il tracciato sconti)| Character| 5|
| 54| IND_GES_MAG2_PER| Indicatore gestione maggiorazione percentuale 2 (Impostare a zero se si usa il tracciato sconti)| Character| 5|
| 55| IND_GES_MAG_IMP| Indicatore gestione maggiorazione importo (Impostare a zero se si usa il tracciato sconti)| Character| 5|
| 56| COD_CATALOGO| Descrivi il contenuto del campo| Character| 255|
| 57| COD_MATERIALE_COMB| Descrivi il contenuto del campo| Character| 255|
| 58| COD_MATERIALE1| Codice materiale| Character| 255|
| 59| COD_COLORE1| Codice colore| Character| 255|
| 60| COD_MATERIALE2| Codice materiale| Character| 255|
| 61| COD_COLORE2| Codice colore| Character| 255|
| 62| COD_MATERIALE3| Codice materiale| Character| 255|
| 63| COD_COLORE3| Codice colore| Character| 255|
| 64| COD_MATERIALE4| Codice materiale| Character| 255|
| 65| COD_COLORE4| Codice colore| Character| 255|
| 66| COD_MATERIALE5| Codice materiale| Character| 255|
| 67| COD_COLORE5| Codice colore| Character| 255|
| 68| COD_MATERIALE6| Codice materiale| Character| 255|
| 69| COD_COLORE6| Codice colore| Character| 255|
| 70| COD_MATERIALE7| Codice materiale| Character| 255|
| 71| COD_COLORE7| Codice colore| Character| 255|
| 72| COD_MATERIALE8| Codice materiale| Character| 255|
| 73| COD_COLORE8| Codice colore| Character| 255|
| 74| COD_MATERIALE9| Codice materiale| Character| 255|
| 75| COD_COLORE9| Codice colore| Character| 255|
| 76| COD_MATERIALE10| Codice materiale| Character| 255|
| 77| COD_COLORE10| Codice colore| Character| 255|
| 78| DAT_ULT_MOD| Data di ultima modifica del record| DateTime| 16|

##io_sconti.dat
Tabella di anagrafica degli sconti

| Prg| Campo | Descrizione| Tipo| Lungh.|  
|- 
| 1| CHIAVE| Chiave univoca del record composta dai dati di origine| Character| 250|
| 2| COD_DITTA| Codice della ditta. Identifica univocamente una ditta dentro il gestionale che, nel caso sia multisocietario, può contenere dati di più aziende| Character| 50|
| 3| COD_ART| Codice dell'articolo| Character| 50|
| 4| TIPO_CLIFOR| Tipologia (0=Cliente, 1=Fornitore)| Integer| 2|
| 5| COD_CLIFOR| Codice Cliente / Fornitore| Character| 50|
| 6| CLASSE_ARTICOLO| Codice identificativo del deposito| Character| 50|
| 7| DES_CLASSE_ARTICOLO| descrizione della classe articolo| Character| 255|
| 8| CLASSE_CLIENTE| Codice identificativo del deposito| Character| 50|
| 9| DES_CLASSE_CLIENTE| descrizione della classe cliente| Character| 255|
| 10| COD_PROMO| Codice dell'articolo| Character| 50|
| 11| QUANTITA_INIZIO| Quantità minima di vendita| Decimal| 25,8|
| 12| QUANTITA_FINE| Quantità minima di vendita| Decimal| 25,8|
| 13| DATA_INIZIO| Data di inizio validità del listino| Date| 10|
| 14| DATA_FINE| Data di fine validità del listino| Date| 10|
| 15| PRIORITA| Identifica il listino con priorità di importanz | Integer| 9|
| 16| SCONTO1| Ultimo sconto percentuale 1| Decimal| 14,6|
| 17| SCONTO2| Ultimo sconto percentuale 1| Decimal| 14,6|
| 18| SCONTO3| Ultimo sconto percentuale 1| Decimal| 14,6|
| 19| SCONTO4| Ultimo sconto percentuale 1| Decimal| 14,6|
| 20| SCONTO5| Ultimo sconto percentuale 1| Decimal| 14,6|
| 21| SCONTO6| Ultimo sconto percentuale 1| Decimal| 14,6|
| 22| TIPO_SCONTO1| Tipologia di sconto S = sostitutivo C = cumulativo| Character| 5|
| 23| TIPO_SCONTO2| Tipologia di sconto S = sostitutivo C = cumulativo| Character| 5|
| 24| TIPO_SCONTO3| Tipologia di sconto S = sostitutivo C = cumulativo| Character| 5|
| 25| TIPO_SCONTO4| Tipologia di sconto S = sostitutivo C = cumulativo| Character| 5|
| 26| TIPO_SCONTO5| Tipologia di sconto S = sostitutivo C = cumulativo| Character| 5|
| 27| TIPO_SCONTO6| Tipologia di sconto S = sostitutivo C = cumulativo| Character| 5|
| 28| COD_VALUTA| Codice della valuta| Character| 50|
| 29| DAT_ULT_MOD| Data di ultima modifica del record| DateTime| 16|

##io_stoart.dat
Dati storici degli articoli

| Prg| Campo | Descrizione| Tipo| Lungh.|  
|- 
| 1| CHIAVE| Chiave univoca del record composta dai dati di origine| Character| 250|
| 2| COD_DITTA| Codice della ditta. Identifica univocamente una ditta dentro il gestionale che, nel caso sia multisocietario, può contenere dati di più aziende| Character| 50|
| 3| COD_CLIFOR| Codice Cliente Fornitore| Character| 50|
| 4| COD_ART| Codice Articolo| Character| 25|
| 5| DESC_ARTICOLO| Descrizione Articolo| Text| 1600|
| 6| NUM_RIGHE| Numero identificativo di riga| Integer| 10|
| 7| ULT_NUM_REG| Ultimo Numero registro| Character| 12|
| 8| ULT_PROG_RIGA| Ultimo Progressivo riga| Integer| 6|
| 9| ULT_QTA| Ultimo valore di quantità| Decimal| 25,8|
| 10| ULT_PRZ| Ultimo prezzo| Decimal| 28,8|
| 11| ULT_UM| Unità di misura 1| Character| 50|
| 12| ULT_QTA2| Ultimo valore di quantità| Decimal| 25,8|
| 13| ULT_PRZ2| Ultimo prezzo| Decimal| 28,8|
| 14| ULT_UM2| Seconda unità di misura| Character| 50|
| 15| COD_DEST| Codice della destinazione| Character| 50|
| 16| ULT_SC_PER1| Ultimo sconto percentuale 1| Decimal| 6,3|
| 17| ULT_SC_PER2| Ultimo sconto percentuale 2| Decimal| 6,3|
| 18| ULT_SC_PER3| Ultimo sconto percentuale 3| Decimal| 6,3|
| 19| ULT_SC_PER4| Ultimo sconto percentuale 4| Decimal| 6,3|
| 20| ULT_SC_PER5| Ultimo sconto percentuale 5| Decimal| 6,3|
| 21| ULT_SC_PER6| Ultimo sconto percentuale 6| Decimal| 6,3|
| 22| ULT_SC_IMPORTO| Ultimo sconto importo| Decimal| 28,8|
| 23| ULT_MAG_PER1| Ultimo sconto maggiorazione percentuale 1| Decimal| 6,3|
| 24| ULT_MAG_PER2| Ultimo sconto maggiorazione percentuale 2| Decimal| 6,3|
| 25| ULT_MAG_IMPORTO| Ultimo sconto maggiorazione importo| Decimal| 28,8|
| 26| ULT_DATA| Ultima data ordine| Date| 10|
| 27| DAT_ULT_MOD| Data di ultima modifica del record| DateTime| 16|

##io_nazioni
Tabella anagrafica delle nazioni

| Prg| Campo | Descrizione| Tipo| Lungh.|  
|- 
| 1| PRG_CITTA| Progressivo univoco| Integer| 9|
| 2| ID_PROGETTO| Identificativo univoco del progetto| Integer| 9|
| 3| CHIAVE| Chiave univoca del record ereditata dai dati di origine| Character| 250|
| 4| COD_DITTA| Codice della ditta. E' il codice che identifica univocamente una ditta dentro il gestionale che, nel caso sia multisocietario, può contenere dati di più aziende| Character| 50|
| 5| COD_NAZIONE| Codice della nazione| Character| 50|
| 6| DES_NAZIONE| Nome della nazione| Character| 255|
| 7| DAT_ULT_MOD| Data di ultima modifica del record| DateTime| 16|

##io_porto.dat
Tabella delle modalita' di consegna (esempio Porto franco)

| Prg| Campo | Descrizione| Tipo| Lungh.|  
|- 
| 1| PRG_CITTA| Progressivo univoco| Integer| 9|
| 2| ID_PROGETTO| Identificativo univoco del progetto| Integer| 9|
| 3| CHIAVE| Chiave univoca del record ereditata dai dati di origine| Character| 250|
| 4| COD_DITTA| Codice della ditta. E' il codice che identifica univocamente una ditta dentro il gestionale che, nel caso sia multisocietario, può contenere dati di più aziende| Character| 50|
| 5| COD_NAZIONE| Codice della nazione| Character| 50|
| 6| DES_NAZIONE| Nome della nazione| Character| 255|
| 7| DAT_ULT_MOD| Data di ultima modifica del record| DateTime| 16|

##io_clifor_cate.dat
Liste di categorie clienti

| Prg| Campo | Descrizione| Tipo| Lungh.|  
|- 
| 1| PRG_CITTA| Progressivo univoco| Integer| 9|
| 2| ID_PROGETTO| Identificativo univoco del progetto| Integer| 9|
| 3| CHIAVE| Chiave univoca del record ereditata dai dati di origine| Character| 250|
| 4| COD_DITTA| Codice della ditta. E' il codice che identifica univocamente una ditta dentro il gestionale che, nel caso sia multisocietario, può contenere dati di più aziende| Character| 50|
| 5| COD_NAZIONE| Codice della nazione| Character| 50|
| 6| DES_NAZIONE| Nome della nazione| Character| 255|
| 7| DAT_ULT_MOD| Data di ultima modifica del record| DateTime| 16|

##io_classi_sconto.dat
Anagrafica delle classi sconto

| Prg| Campo | Descrizione| Tipo| Lungh.|  
|- 
| 1| PRG_CITTA| Progressivo univoco| Integer| 9|
| 2| ID_PROGETTO| Identificativo univoco del progetto| Integer| 9|
| 3| CHIAVE| Chiave univoca del record ereditata dai dati di origine| Character| 250|
| 4| COD_DITTA| Codice della ditta. E' il codice che identifica univocamente una ditta dentro il gestionale che, nel caso sia multisocietario, può contenere dati di più aziende| Character| 50|
| 5| COD_NAZIONE| Codice della nazione| Character| 50|
| 6| DES_NAZIONE| Nome della nazione| Character| 255|
| 7| DAT_ULT_MOD| Data di ultima modifica del record| DateTime| 16|

##io_canali_vendita.dat
Canali di vendita

| Prg| Campo | Descrizione| Tipo| Lungh.|  
|- 
| 1| PRG_CITTA| Progressivo univoco| Integer| 9|
| 2| ID_PROGETTO| Identificativo univoco del progetto| Integer| 9|
| 3| CHIAVE| Chiave univoca del record ereditata dai dati di origine| Character| 250|
| 4| COD_DITTA| Codice della ditta. E' il codice che identifica univocamente una ditta dentro il gestionale che, nel caso sia multisocietario, può contenere dati di più aziende| Character| 50|
| 5| COD_NAZIONE| Codice della nazione| Character| 50|
| 6| DES_NAZIONE| Nome della nazione| Character| 255|
| 7| DAT_ULT_MOD| Data di ultima modifica del record| DateTime| 16|

# Import Dati Wtrendy
Tracciati per l'importazione dei dati per l'applicazione wTrendy


##io_var_combinazioni.dat


| Prg| Campo | Descrizione| Tipo| Lungh.|  
|- 
| 1| CHIAVE| Chiave univoca del record composta dai dati di origine| Character| 250|
| 2| COD_DITTA| Codice della ditta. Identifica univocamente una ditta dentro il gestionale che, nel caso sia multisocietario, può contenere dati di più aziende| Character| 50|
| 3| ORDINAMENTO| ordinamento tra tutto il catalogo| Integer| 9|
| 4| COD_COMBINAZIONE| Descrivi il contenuto del campo| Character| 255|
| 5| DES_COMBINAZIONE| Descrizione della combinazione| Character| 255|
| 6| COD_ARTICOLO| Codice dell'articolo| Character| 255|
| 7| COD_SVILUPPO| Chiave dello sviluppo| Character| 255|
| 8| COD_CATALOGO| Descrivi il contenuto del campo| Character| 255|
| 9| POSIZIONE1| Intestazione della colonna della prima variante (chiamata in gergo scelta cliente)| Character| 255|
| 10| COD_MATERIALE1| Chiave del materiale| Character| 255|
| 11| DES_MATERIALE1| Descrizione del materiale| Character| 255|
| 12| COD_COLORE1| codice colore| Character| 255|
| 13| DES_COLORE1| Descrizione colore| Character| 255|
| 14| POSIZIONE2| Intestazione della colonna della prima variante (chiamata in gergo scelta cliente)| Character| 255|
| 15| COD_MATERIALE2| Chiave del materiale| Character| 255|
| 16| DES_MATERIALE2| Descrizione del materiale| Character| 255|
| 17| COD_COLORE2| codice colore| Character| 255|
| 18| DES_COLORE2| Descrizione colore| Character| 255|
| 19| POSIZIONE3| Intestazione della colonna della prima variante (chiamata in gergo scelta cliente)| Character| 255|
| 20| COD_MATERIALE3| Chiave del materiale| Character| 255|
| 21| DES_MATERIALE3| Descrizione del materiale| Character| 255|
| 22| COD_COLORE3| codice colore| Character| 255|
| 23| DES_COLORE3| Descrizione colore| Character| 255|
| 24| POSIZIONE4| Intestazione della colonna della prima variante (chiamata in gergo scelta cliente)| Character| 255|
| 25| COD_MATERIALE4| Chiave del materiale| Character| 255|
| 26| DES_MATERIALE4| Descrizione del materiale| Character| 255|
| 27| COD_COLORE4| codice colore| Character| 255|
| 28| DES_COLORE4| Descrizione colore| Character| 255|
| 29| POSIZIONE5| Intestazione della colonna della prima variante (chiamata in gergo scelta cliente)| Character| 255|
| 30| COD_MATERIALE5| Chiave del materiale| Character| 255|
| 31| DES_MATERIALE5| Descrizione del materiale| Character| 255|
| 32| COD_COLORE5| codice colore| Character| 255|
| 33| DES_COLORE5| Descrizione colore| Character| 255|
| 34| POSIZIONE6| Intestazione della colonna della prima variante (chiamata in gergo scelta cliente)| Character| 255|
| 35| COD_MATERIALE6| Chiave del materiale| Character| 255|
| 36| DES_MATERIALE6| Descrizione del materiale| Character| 255|
| 37| COD_COLORE6| codice colore| Character| 255|
| 38| DES_COLORE6| Descrizione colore| Character| 255|
| 39| POSIZIONE7| Intestazione della colonna della prima variante (chiamata in gergo scelta cliente)| Character| 255|
| 40| COD_MATERIALE7| Chiave del materiale| Character| 255|
| 41| DES_MATERIALE7| Descrizione del materiale| Character| 255|
| 42| COD_COLORE7| codice colore| Character| 255|
| 43| DES_COLORE7| Descrizione colore| Character| 255|
| 44| POSIZIONE8| Intestazione della colonna della prima variante (chiamata in gergo scelta cliente)| Character| 255|
| 45| COD_MATERIALE8| Chiave del materiale| Character| 255|
| 46| DES_MATERIALE8| Descrizione del materiale| Character| 255|
| 47| COD_COLORE8| codice colore| Character| 255|
| 48| DES_COLORE8| Descrizione colore| Character| 255|
| 49| POSIZIONE9| Intestazione della colonna della prima variante (chiamata in gergo scelta cliente)| Character| 255|
| 50| COD_MATERIALE9| Chiave del materiale| Character| 255|
| 51| DES_MATERIALE9| Descrizione del materiale| Character| 255|
| 52| COD_COLORE9| codice colore| Character| 255|
| 53| DES_COLORE9| Descrizione colore| Character| 255|
| 54| POSIZIONE10| Intestazione della colonna della prima variante (chiamata in gergo scelta cliente)| Character| 255|
| 55| COD_MATERIALE10| Chiave del materiale| Character| 255|
| 56| DES_MATERIALE10| Descrizione del materiale| Character| 255|
| 57| COD_COLORE10| codice colore| Character| 255|
| 58| DES_COLORE10| Descrizione colore| Character| 255|
| 59| POSIZIONE11| Intestazione della colonna della prima variante (chiamata in gergo scelta cliente)| Character| 255|
| 60| COD_MATERIALE11| Chiave del materiale| Character| 255|
| 61| DES_MATERIALE11| Descrizione del materiale| Character| 255|
| 62| POSIZIONE12| Intestazione della colonna della prima variante (chiamata in gergo scelta cliente)| Character| 255|
| 63| COD_MATERIALE12| Chiave del materiale| Character| 255|
| 64| DES_MATERIALE12| Descrizione del materiale| Character| 255|
| 65| COD_COLORE11| codice colore| Character| 255|
| 66| DES_COLORE11| Descrizione colore| Character| 255|
| 67| COD_COLORE12| codice colore| Character| 255|
| 68| DES_COLORE12| Descrizione colore| Character| 255|
| 69| POSIZIONE13| Intestazione della colonna della prima variante (chiamata in gergo scelta cliente)| Character| 255|
| 70| COD_MATERIALE13| Chiave del materiale| Character| 255|
| 71| DES_MATERIALE13| Descrizione del materiale| Character| 255|
| 72| COD_COLORE13| codice colore| Character| 255|
| 73| DES_COLORE13| Descrizione colore| Character| 255|
| 74| POSIZIONE14| Intestazione della colonna della prima variante (chiamata in gergo scelta cliente)| Character| 255|
| 75| COD_MATERIALE14| Chiave del materiale| Character| 255|
| 76| DES_MATERIALE14| Descrizione del materiale| Character| 255|
| 77| COD_COLORE14| codice colore| Character| 255|
| 78| DES_COLORE14| Descrizione colore| Character| 255|
| 79| POSIZIONE15| Intestazione della colonna della prima variante (chiamata in gergo scelta cliente)| Character| 255|
| 80| COD_MATERIALE15| Chiave del materiale| Character| 255|
| 81| DES_MATERIALE15| Descrizione del materiale| Character| 255|
| 82| COD_COLORE15| codice colore| Character| 255|
| 83| DES_COLORE15| Descrizione colore| Character| 255|
| 84| DAT_ULT_MOD| Data di ultima modifica del record| DateTime| 16|

##io_taglie_sviluppi.dat
Tracciato con gli sviluppi taglie

| Prg| Campo | Descrizione| Tipo| Lungh.|  
|- 
| 1| CHIAVE| Chiave univoca del record composta dai dati di origine| Character| 250|
| 2| COD_DITTA| Codice della ditta. Identifica univocamente una ditta dentro il gestionale che, nel caso sia multisocietario, può contenere dati di più aziende| Character| 50|
| 3| COD_SVILUPPO| Chiave dello sviluppo| Character| 255|
| 4| DES_SVILUPPO| Sviluppo predefinito (in Modwin e' sul singolo articolo. Quello predefinito con il quale raccogliere l'ordine se non viene specificato uno diverso - UK) - 1; 1,5; 2, ecc..| Character| 255|
| 5| COD_TAGLIA| Descrivi il contenuto del campo| Character| 255|
| 6| DES_TAGLIA| Descrivi il contenuto del campo| Character| 255|
| 7| ORDINAMENTO| Ordinamento con il quale mostrare le taglie (all'interno dello stesso sviluppo)| Integer| 9|
| 8| FLG_PREFERENZIALE| Identifica lo sviluppo preferenziale. 0 per non preferenziale, -1 per preferenziale| Integer| 2|
| 9| COD_TAGLIA_GUIDA| Descrivi il contenuto del campo| Character| 255|
| 10| FLG_VISIBILE| Se impostato a -1 devo dare la possibilità di inserire la taglia, altrimento 0| Integer| 2|
| 11| DAT_ULT_MOD| Data di ultima modifica del record| DateTime| 16|

##io_taglie_sviluppi_art.dat
Tracciato associativo sviluppo

| Prg| Campo | Descrizione| Tipo| Lungh.|  
|- 
| 1| CHIAVE| Chiave univoca del record composta dai dati di origine| Character| 250|
| 2| COD_DITTA| Codice della ditta. Identifica univocamente una ditta dentro il gestionale che, nel caso sia multisocietario, può contenere dati di più aziende| Character| 50|
| 3| COD_ARTICOLO| Codice dell'articolo| Character| 255|
| 4| COD_SVILUPPO| Chiave dello sviluppo| Character| 255|
| 5| COD_TAGLIA| Descrivi il contenuto del campo| Character| 255|
| 6| FLG_VISIBILE| Se impostato a -1 devo dare la possibilità di inserire la taglia, altrimenti 0| Integer| 2|
| 7| DAT_ULT_MOD| Data di ultima modifica del record| DateTime| 16|

##io_assortimenti.dat
Tracciato assortimenti

| Prg| Campo | Descrizione| Tipo| Lungh.|  
|- 
| 1| CHIAVE| Chiave univoca del record composta dai dati di origine| Character| 250|
| 2| COD_DITTA| Codice della ditta. Identifica univocamente una ditta dentro il gestionale che, nel caso sia multisocietario, può contenere dati di più aziende| Character| 50|
| 3| COD_ASSORTIMENTO| Codice dell'assortimento| Character| 255|
| 4| DES_ASSORTIMENTO| Descrizione dell'assortimento| Character| 255|
| 5| COD_SVILUPPO| Codice dello sviluppo| Character| 255|
| 6| DAT_ULT_MOD| Data di ultima modifica del record| DateTime| 16|

##io_taglie_assortimenti.dat
Tracciato assortimenti per taglia

| Prg| Campo | Descrizione| Tipo| Lungh.|  
|- 
| 1| CHIAVE| Chiave univoca del record composta dai dati di origine| Character| 250|
| 2| COD_DITTA| Codice della ditta. Identifica univocamente una ditta dentro il gestionale che, nel caso sia multisocietario, può contenere dati di più aziende| Character| 50|
| 3| COD_ASSORTIMENTO| Chiave dello sviluppo| Character| 255|
| 4| COD_TAGLIA| Descrivi il contenuto del campo| Character| 255|
| 5| QUANTITA| Quantita predefinita dell'assortimento| Decimal| 25,8|
| 6| DAT_ULT_MOD| Data di ultima modifica del record| DateTime| 16|

##io_taglie_cataloghi.dat
Tracciato cataloghi

| Prg| Campo | Descrizione| Tipo| Lungh.|  
|- 
| 1| CHIAVE| Chiave univoca del record composta dai dati di origine| Character| 250|
| 2| COD_DITTA| Codice della ditta. Identifica univocamente una ditta dentro il gestionale che, nel caso sia multisocietario, può contenere dati di più aziende| Character| 50|
| 3| COD_CATALOGO| Descrivi il contenuto del campo| Character| 255|
| 4| DES_CATALOGO| Descrizione del materiale| Character| 255|
| 5| DAT_ULT_MOD| Data di ultima modifica del record| DateTime| 16|

##io_taglie_cataloghi_art.dat
Tracciato cataloghi articoli

| Prg| Campo | Descrizione| Tipo| Lungh.|  
|- 
| 1| CHIAVE| Chiave univoca del record composta dai dati di origine| Character| 250|
| 2| COD_DITTA| Codice della ditta. Identifica univocamente una ditta dentro il gestionale che, nel caso sia multisocietario, può contenere dati di più aziende| Character| 50|
| 3| COD_CATALOGO| Descrivi il contenuto del campo| Character| 255|
| 4| COD_ARTICOLO| Codice dell'articolo| Character| 255|
| 5| DAT_ULT_MOD| Data di ultima modifica del record| DateTime| 16|

##io_clienti_assortimenti.dat
Tracciato clienti assortimenti

| Prg| Campo | Descrizione| Tipo| Lungh.|  
|- 
| 1| CHIAVE| Chiave univoca del record composta dai dati di origine| Character| 250|
| 2| COD_DITTA| Codice della ditta. Identifica univocamente una ditta dentro il gestionale che, nel caso sia multisocietario, può contenere dati di più aziende| Character| 50|
| 3| COD_CLIFOR| Codice Cliente / Fornitore| Character| 50|
| 4| COD_ASSORTIMENTO| Codice dell'assortimento| Character| 255|
| 5| DAT_ULT_MOD| Data di ultima modifica del record| DateTime| 16|

##io_articoli_assortimenti.dat
Tracciato articoli assortimenti

| Prg| Campo | Descrizione| Tipo| Lungh.|  
|- 
| 1| CHIAVE| Chiave univoca del record composta dai dati di origine| Character| 250|
| 2| COD_DITTA| Codice della ditta. Identifica univocamente una ditta dentro il gestionale che, nel caso sia multisocietario, può contenere dati di più aziende| Character| 50|
| 3| COD_ART| Codice dell'articolo| Character| 50|
| 4| COD_ASSORTIMENTO| Codice dell'assortimento| Character| 255|
| 5| DAT_ULT_MOD| Data di ultima modifica del record| DateTime| 16|

##io_taglie_estensioni.dat
Tracciato taglie estensioni

| Prg| Campo | Descrizione| Tipo| Lungh.|  
|- 
| 1| CHIAVE| Chiave univoca del record composta dai dati di origine| Character| 250|
| 2| COD_DITTA| Codice della ditta. Identifica univocamente una ditta dentro il gestionale che, nel caso sia multisocietario, può contenere dati di più aziende| Character| 50|
| 3| COD_TIPO| scatola, etichetta| Character| 255|
| 4| COD_CLIENTE| | Character| 255|
| 5| COD_MATERIALE| Chiave del materiale| Character| 255|
| 6| DES_MATERIALE| Descrizione del materiale| Character| 255|
| 7| COD_COLORE| codice colore| Character| 255|
| 8| DES_COLORE| Descrizione colore| Character| 255|
| 9| DAT_ULT_MOD| Data di ultima modifica del record| DateTime| 16|

##io_regole.dat
Tracciato definizione regole wtrendy

| Prg| Campo | Descrizione| Tipo| Lungh.|  
|- 
| 1| CHIAVE| Chiave univoca del record composta dai dati di origine| Character| 250|
| 2| COD_DITTA| Codice della ditta| Character| 50|
| 3| COD_ARTICOLO| Codice dell'articolo| Character| 255|
| 4| COD_CATALOGO| Descrivi il contenuto del campo| Character| 255|
| 5| COD_SVILUPPO| Chiave dello sviluppo| Character| 255|
| 6| COD_LISTA_MATERIALE_COMB| Descrivi il contenuto del campo| Character| 255|
| 7| ORDINAMENTO| ordinamento tra tutto il catalogo| Integer| 9|
| 8| COD_LISTA_MATERIALE1| Chiave della lista materiali| Character| 255|
| 9| DES_SCELTA1| Descrizione della scelta| Character| 255|
| 10| COD_LISTA_MATERIALE2| Chiave della lista materiali| Character| 255|
| 11| DES_SCELTA2| Descrizione della scelta| Character| 255|
| 12| COD_LISTA_MATERIALE3| Chiave della lista materiali| Character| 255|
| 13| DES_SCELTA3| Descrizione della scelta| Character| 255|
| 14| COD_LISTA_MATERIALE4| Chiave della lista materiali| Character| 255|
| 15| DES_SCELTA4| Descrizione della scelta| Character| 255|
| 16| COD_LISTA_MATERIALE5| Chiave della lista materiali| Character| 255|
| 17| DES_SCELTA5| Descrizione della scelta| Character| 255|
| 18| COD_LISTA_MATERIALE6| Chiave della lista materiali| Character| 255|
| 19| DES_SCELTA6| Descrizione della scelta| Character| 255|
| 20| COD_LISTA_MATERIALE7| Chiave della lista materiali| Character| 255|
| 21| DES_SCELTA7| Descrizione della scelta| Character| 255|
| 22| COD_LISTA_MATERIALE8| Chiave della lista materiali| Character| 255|
| 23| DES_SCELTA8| Descrizione della scelta| Character| 255|
| 24| COD_LISTA_MATERIALE9| Chiave della lista materiali| Character| 255|
| 25| DES_SCELTA9| Descrizione della scelta| Character| 255|
| 26| COD_LISTA_MATERIALE10| Chiave della lista materiali| Character| 255|
| 27| DES_SCELTA10| Descrizione della scelta| Character| 255|
| 28| DAT_ULT_MOD| Data di ultima modifica del record| DateTime| 16|

##io_liste_materiali.dat
Liste dei materiali disponibili

| Prg| Campo | Descrizione| Tipo| Lungh.|  
|- 
| 1| CHIAVE| Chiave univoca del record composta dai dati di origine| Character| 250|
| 2| COD_DITTA| Codice della ditta| Character| 50|
| 3| COD_LISTA_MATERIALE| Codice lista materiale| Character| 255|
| 4| COD_MATERIALE| Codice del materiale| Character| 255|
| 5| DES_MATERIALE| Descrizione del materiale| Character| 255|
| 6| COD_LISTA_COLORI| Codice della lista colore| Character| 255|
| 7| DAT_ULT_MOD| Data di ultima modifica del record| DateTime| 16|

##io_liste_colori.dat
Liste colori

| Prg| Campo | Descrizione| Tipo| Lungh.|  
|- 
| 1| CHIAVE| Chiave univoca del record composta dai dati di origine| Character| 250|
| 2| COD_DITTA| Codice della ditta| Character| 50|
| 3| COD_LISTA_COLORE| Codice della lista colore| Character| 255|
| 4| COD_COLORE| Codice colore| Character| 255|
| 5| DES_COLORE| Descrizione del colore| Character| 255|
| 6| DAT_ULT_MOD| Data di ultima modifica del record| DateTime| 16|

# Import Catalogo
Import Catalogo



##io_catalogo.dat
Tracciato per l'importazione di dati multimediali.</br>
All'interno dell'iPad, nella sezione catalogo, è possibile mostrare le fotografie degli articoli in una gerarchia di cartelle che rappresentano la struttura merceologica ( famiglia, gruppo, ecc).</br>
Questo tracciato descrive tale gerarchia.
La cartella con le immagini da importare deve rispcchiare questo criterio:

* Deve contenere tutte le fotografie da importare.
* Le fotografie devono essere tutte nella cartella principale
* Le fotografie devono contenere, nel nome, il codice dell'articolo.
* La cartella deve contenere il file tracciato del catalogo che descrive la struttura merceologica degli articoli

| Prg| Campo | Descrizione| Tipo| Lungh.|  
|- 
| 1| NOMEFILE| Nome del file da importare.| Character| 25|
| 2| TITOLO| Nome descrittivo del file (es: Piatto in porcellana)| Text| 8000|
| 3| COD_ART| Codice dell'articolo| Character| 25|
| 4| L1| Livello 1 (es: Piatti)| Character| 30|
| 5| L2| Livello 2 (es: Porcellane)| Character| 30|
| 6| L3| Livello 3| Character| 30|
| 7| L4| Livello 4| Character| 30|
| 8| DAT_ULT_MOD| Data di ultima modifica del record| DateTime| 16|

# Import Reports
Import Report

##io_reports.dat
Tracciato per l'importazione di dati multimediali.</br>
All'interno dell'iPad, nella sezione catalogo, è possibile mostrare le fotografie degli articoli in una gerarchia di cartelle che rappresentano la struttura merceologica ( famiglia, gruppo, ecc).</br>
Questo tracciato descrive tale gerarchia.
La cartella con le immagini da importare deve rispcchiare questo criterio:

* Deve contenere tutte le fotografie da importare.
* Le fotografie devono essere tutte nella cartella principale
* Le fotografie devono contenere, nel nome, il codice dell'articolo.
* La cartella deve contenere il file tracciato del catalogo che descrive la struttura merceologica degli articoli

| Prg| Campo | Descrizione| Tipo| Lungh.|  
|- 
| 1| NOMEFILE| Nome del file da importare. Deve contenere il codice dell'articolo (13243.jpg)| Character| 25|
| 2| TITOLO| Nome descrittivo del file (es: Piatto in porcellana)| Text| 8000|
| 3| COD_ART| Codice dell'articolo| Character| 25|
| 4| COD_OPERATORE| Codice operatore nel rispettivo gestionale associato all'agente che si collega al device; utilizzato ad esempio per filtrare i leads.| Character| 50|
| 5| COD_AGENTE| Codice Esterno dell'agente che si collega al device. Deve esserci corrispondenza con il codice agente di Gamma, per poter inserire gli ordini.| Character| 50|
| 6| ORDINAMENTO| ordinamento tra tutto il catalogo| Integer| 9|
| 7| L1| Livello 1 (es: Piatti)| Character| 30|
| 8| L2| Livello 2 (es: Porcellane)| Character| 30|
| 9| L3| Livello 3| Character| 30|
| 10| L4| Livello 4| Character| 30|
| 11| DAT_ULT_MOD| Data di ultima modifica del record| DateTime| 16|
