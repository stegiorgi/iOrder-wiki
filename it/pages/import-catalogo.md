
Import del catalogo
===================

Introduzione
---
Questo articolo fornisce una linea guida per effettuare l'import dei file multimediali che compongono il modulo catalogo.
L'importazione dei file descritta in questo articolo per la creazione del catalogo, può essere effettuata in 2 diverse modalità:

  *  Import basato su tracciato
  *  Import basato su file system

Indipendentemente dal metodo adottato, i file da importare devono essere copiati nella cartella **multimedia** di [dropbox](https://www.dropbox.com). 

Import da tracciato
---
Questa metodologia di importazione prevede che i file vengano copiati nella cartella multimedia.
I files devono essere copiati tutti nella cartella principale e non possono essere create cartella.
Un stesso file può essere presente  più volte in cartelle differenti senza essere presente piuù volte nella cartella. E' sufficiente che venga inserito più volte nel tracciato record.

### Creare il tracciato io_catalogo.dat
Il tracciato io_catalogo.dat deve essere creato anch'esso nella cartella principale in cui vengono messi i files multimediali.
La struttura gerarchica con cui vengono mostrati i dati del catalogo sono definiti nei campi L2, L2, L3, L4 del tracciato.
Ogni campo è suddiviso dagli altri tramite il carattere separatore “|”.
Il catalogo risultante nel dispositivo rispecchierà la struttura inserita nel tracciato tramite i nomi dei file e i livelli di appartenenza.

### Esempio
Il seguente tracciato, mostra 2 cartelle (Detersivi e Prodotti casa.
All'interno della cartella Detersivi viene mostrata la cartella Naturale e, all'interno della cartella Prodotti casa vengono mostrati 3 immagini. Sotto la cartella Naturale vengono mostrate 2 immagini.


 | NOMEFILE     | TITOLO         | COD_ART | L1                   | L2       | L3 | L4       | DAT_ULT_MOD |
 | -
 | Listino1.pdf | Listino art. 1 | COD001  | Detersivi            | Naturale |    | 01012010 | 01012010    |
 | Listino2.pdf | Listino art. 2 | COD002  | Detersivi            | Naturale |    |          | 01012010    |
 | Listino3.pdf | Listino art. 3 | COD003  | Prodotti per la casa |          |    |          | 01012010    |
 | Listino4.pdf | Listino art. 4 | COD004  | Prodotti per la casa |          |    |          | 01012010    |


### Visualizzazione risultante

  *  Cartella Detersivi
  *  Cartella Naturale
  * * File Listino 1
  * * File Listino 2
  *  Cartella Prodotti casa
  *  File Listino 3
  *  File Listino 4
  *  File Listino 5


Import da file system
---
L'import da filesystem, prevede che i file vengano copiati ed eventualmente raggruppati in cartelle e sottocartelle, all'interno della sopracitata cartella **multimedia**.
Il catalogo risultante nel dispositivo rispecchierà fedelmente la struttura dei file e cartelle desiderata.
Un stesso file può essere presente  più volte però ovviamente in cartelle differenti.
I nomi delle cartelle si visualizzeranno anche nel dispositivo.
I nomi dei file devono seguire le regole di nomenclatura descritte di seguito

### Regole di nomenclatura di file e cartelle
I nomi dei file e delle cartelle che si vogliono importare nel catalogo, devono soddisfare delle regole per una loro corretta visualizzazione e possibile associazione con gli articoli presenti.
Il nome di un file può essere così espresso:

  nome\[CodiceArticolo\]\{ordinamento\}\.estensione 

Questo vuol dire che è possibile specificare un nome al file e associarlo ad un articolo mettendo il rispettivo codice tra parentesi quadre.
E' possibile specificare inoltre un eventuale ordinamento tra i file mettendo un numero tra parentesi graffe.

#### Esempi

 | Nome file                          | Descrizione                                                                                                  |
 | -
 | Listino.pdf                        | Documento con nome _Listino_ non associato ad alcun articolo e senza ordinamento specifico                   |
 | Libreria Kwaba [kw07](kw07.md).jpg | Immagine con nome _Libreria Kwaba_ associata all'articolo avente codice _kw07_ e senza ordinamento specifico |
 | Foresta {1}.png                    | Immagine con nome _Foresta_ non associata ad alcun articolo ma avente un ordinamento di valore 1             |
 | Dépliant [0567](0567.md) {2}.avi   | Video con nome _Dépliant_ associato all'articolo avente codice _0567_ e con ordinamento di valore 2          |
 | [123](123.md).jpg                  | immagine associata direttamente all'articolo avente codice _123_ e senza ordinamento specifico               |

Tipi di file supportati
---

### Immagini
Le estensioni supportate per le immagini sono:
  *  .jpg
  *  .jpeg
  *  .png
  *  .gif 

### Video
Le estensioni supportate per i file video sono:
  *  .mov,
  *  .avi,
  *  .mpg,
  *  .mpeg,
  *  .m4v
  *  .mp4

Nota: Alcuni codec (es. xvid o divx), non sono nativamente supportati sul iOs.

### Documenti

Le estensioni supportate per i documenti sono:
  *  .pdf

### Dimensione (larghezza x altezza) immagini
Tenendo in considerazione che le immagini devono essere visualizzate nei dispositivi mobile, occorre prestare attenzione anche alla dimensione delle immagini stesse.

Una dimensione molto elevata implica una mole maggiore di dati da spostare (quindi maggiore lentezza nella sincronizzazione).

Nei dispositivi (es. ipad) una dimensione in pixel maggiore della risoluzione gestita dal dispositivo farà si che l'immagine venga adattata automaticamente ridimensionandola perdendo qualche dettaglio (che verrà recuperato effettuando lo zoom).
Nel caso in cui invece la dimensione in pixel della foto risulti inferiore alla risoluzione gestita dal dispositivo, l'immagina viene lasciata invariata e quindi non si vedrà a schermo intero.

In fase di importazione catalogo, dentro l'appmanager viene eseguito un ridimensionamento delle immagini che superano una determinata dimensione, esso si può modificare a piacimento entrando in appmanager e andando sul progetto (campo Max Pixel Foto).

Il default di tale parametro è 1028 (risoluzione ipad 2) ma è possibile cambiarlo ad esempio a 2048 (dimensione ipad retina, air, etc.).

Ogni immagine con larghezza o altezza massima superiore a questo valore verrà ridimensionata in base al valore del parametro.

Anteprime folder
---
Per quanto riguarda le anteprime delle folder che contengono le immagini, attualmente non c'è una logica o definizione particolare ma viene visualizzata in automatico una delle immagini contenute al suo interno.



