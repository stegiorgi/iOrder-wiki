Connettore di Gamma (Team System)
===

## Installazione

L'integrazione fra il gestionale Gamma e iGamma, avviene attraverso lo scambio di files in formato ascii delimitato.
Il programma che si occupa di esportare e importare i dati da e per il gestionale, è chiamato **Connettore**, ed è composto da un programma dedicato chiamato Prosync e da un insieme di configurazioni da effettuare nel gestionale.

  *  Sulla macchina dedicata ad iGamma deve essere stata preventivamente installata e configurata la cartella DROPBOX (vedi apposito manuale)
  *  Creare una cartella “ \TeamSystem Software\Installazione_Igamma” dove mettere i seguenti file necessari per la configurazione:

1.  igamma_views_vx_x.sql
2.  igamma_view_hypermedia_vx_x.sql
3.  Tracciati_iGAMMA_vx_x.zip
4.  Sposta.bat (vedi punto 10 per la creazione)

Note: Per viste e tracciati verificare sempre di utilizzare le ultime versioni rilasciate.

  *  Creare una cartella C:\TEMP nella quale andranno a finire i file esportati da Gamma e che successivamente si andranno a sincronizzare sull'iPad.

## Configurazione Gamma Enterprise - Sprint

### Restore database (SQL)

### ****Gamma:**** Aggiornamento database

### Configurazione azienda

****Gamma:**** Eliminazione delle eventuali altre aziende gestite compresa l'azienda di prova sul
database di riferimento. (deve rimanere solo l'azienda in uso).

NB: questa operazioni va fatta solamente quando si gestiscono le fasi di import\export manualmente, senza l'ausilio del
prosync)

### </span><span style="text-decoration:underline">Installazione viste</span><span style="text-decoration:underline">

****SQL:**** Importazione viste da \TeamSystem Software\Installazione Igamma sul database di
riferimento

(files: igamma_views_vx_x.sql e igamma_view_hypermedia_vx_x.sql)

### </span><span style="text-decoration:underline">Configurazione parametri</span><span style="text-decoration:underline">

Dopo aver lanciato le viste sul database, è necessario richiamare la tabella IGAMMA_PARAMETRI tramite il seguente comando:

     SQL
    select * from IGAMMA_PARAMETRI


sarà visualizzata la relativa tabella; da qui abbiamo la possibilità di parametrizzare le estrazioni
dei dati:

![Immagine](../Attachments/iOrder.connettore_IGAMMA/gamma1.png)

Per aggiornare il VALORE in tabella utilizzare il seguente comando (esempio):

     SQL
    exec dbo.IGAMMA_SET_PARAM 'DITTA', 102


Per aggiornare il VALORE in tabella inserendo un elenco (es: di famiglie) da estrarre:

     SQL
    exec dbo.IGAMMA_SET_PARAM 'FILTRO_FAMIGLIE', 'AA-BB-CC'


Per verificare quante righe documenti sono presenti nell'esportazione:

     SQL
    select COUNT(*) from IGAMMA_CLIFOR_RIGHDOC


NB: si consiglia di impostare il paramentro “FILTRO_GIORNI_STORICO_ARTICOLI” su 90/180 giorni per non appesantire troppo l'operazione di estrazione se la ditta ha un notevole numero di documenti.

### </span><span style="text-decoration:underline">Importazione tracciati</span><span style="text-decoration:underline">

Caricare in gamma i tracciati messi in c:\TeamSystem Software\Installazione Igamma (da fileTracciati_iGAMMA_vx_x.zip)

![Immagine](../Attachments/iOrder.connettore_IGAMMA/gamma2.png)

### </span><span style="text-decoration:underline">Gestione Tracciati</span><span style="text-decoration:underline">

****Import modifiche anagrafiche:**** Da "Gestione Tracciati" modificare il tracciato IGAMMA_AM_CF (struttura anagrafica cli\for)
con il percorso della sottocartella appmanager di dropbox come segue:

![Immagine](../Attachments/iOrder.connettore_IGAMMA/immagine.png)

Andare in "Impostazioni" + "Altre Impostazioni" ed impostare come segue:

![Immagine](../Attachments/iOrder.connettore_IGAMMA/immagine1.png)

**</span>**NOTE:**<span style="text-decoration:underline">**

· Mettere il flag per l'eliminazione del file dopo l'import.

· Consigliamo di creare una cartella cha andrà a contenere copia dei file importati.
  Nell'esempio, l'attributo “%93” provvederà a copiare il file IGAMMA_AM_CF_ANA*.DAT
  (dove l'asterisco prevede data ed ora di creazione) nella cartella prevista a contenere i file copia.

****Import note cliente:**** Da "Gestione Tracciati" modificare il tracciato IGAMMA_AM_CF_NOTE (struttura anagrafica cli\for)
con il percorso della sottocartella appmanager di dropbox come segue:

![Immagine](../Attachments/iOrder.connettore_IGAMMA/immagine2.png)

Andare in “Impostazioni” + “Altre Impostazioni” ed impostare come segue:

![Immagine](../Attachments/iOrder.connettore_IGAMMA/immagine3.png)

**</span>**NOTE:**<span style="text-decoration:underline">**

· Mettere il flag per l'eliminazione del file dopo l'import.

· Consigliamo di creare una cartella cha andrà a contenere copia dei file importati.
  Nell'esempio, l'attributo “%93” provvederà a copiare il file IGAMMA_AM_CF_NOTE*.DAT
  (dove l'asterisco prevede data ed ora di creazione) nella cartella prevista a contenere i file copia.

****Import Documenti:**** Da "Gestione Tracciati" modificare il tracciato IGAMMA_AM_ORD (struttura documenti, articoli, cli\for)
con il percorso della sottocartella appmanager di dropbox come segue:

![Immagine](../Attachments/iOrder.connettore_IGAMMA/immagine4.png)

Andare in “Impostazioni” + “Altre Impostazioni” ed impostare come segue:

![Immagine](../Attachments/iOrder.connettore_IGAMMA/immagine5.png)

**</span>**NOTE:**<span style="text-decoration:underline">**

· Mettere il flag per l'eliminazione del file dopo l'import.

· Consigliamo di creare una cartella che andrà a contenere copia dei file importati.
  Nell'esempio, l'attributo “%93” provvederà a copiare il file IGAMMA_AM_ORD*.DAT
  (dove l'asterisco prevede data ed ora di creazione) nella cartella prevista a contenere i file copia.

### </span><span style="text-decoration:underline">Gestione Insiemi</span><span style="text-decoration:underline">

Aprire la "Gestione Insiemi" di Gamma e richiamare l'insieme "IMP_IGAMMA"

![Immagine](../Attachments/iOrder.connettore_IGAMMA/immagine7.png)

Verificare per ciascuna struttura che risultino flaggati i seguenti parametri:

- "Eliminazione File dopo Import" 
- "Creazione File Copia". 

Se non risultano flaggati impostare il tutto come da figura.

![Immagine](../Attachments/iOrder.connettore_IGAMMA/immagine8.png)

NB: dalla "Gestione Insiemi" sarà possibile anche disattivare eventuali tracciati di import/export non di interesse.

### </span><span style="text-decoration:underline">Creazione Documenti "Mobile"</span><span style="text-decoration:underline">

Dentro Gamma creare in Gamma i documenti ****CLI-MOBORD**** e ****CLI-MOBPRE**** duplicandoli dai documenti
utilizzati dall'azienda come “ordine” e “preventivo”. Post creazione procedere all'attivazione ed
eventualmente se presenti assegnare il report di stampa personalizzato.

### </span><span style="text-decoration:underline">Creazione Batch "Sposta.bat"</span><span style="text-decoration:underline">

Creare un file “batch” chiamato ****“sposta.bat”**** la cui funzione sarà quella (tramite pianificazione di Prosync)
di spostare i file esportati da Gamma nella cartella di sincronizzazione di Dropbox (C:\dropbox\xxxx\gestionale).

**</span>**move C:\TEMP\azienda\gamma\*.dat C:\Dropbox\xxxxxxxxxxxxx\gestionale**_'''''

<span style="text-decoration:underline">__sostituire alle X il progetto di riferimento all'interno della dropbox</span>__





































### TODO
<embed id="embed_npwlo" type="application/npwlo" height="0"></embed>
