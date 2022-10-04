---
titolo: BiblioManager
numero: 1
vestione: 1.0
lingua: IT
anno: 2014
materia: IW
mainfile: Progetto_Master.rcp
thisfile: specifica
---

-------

{#specifiche}

Il sito *BiblioManager* rappresenta un semplice gestore
di catalogo bibliografico online.

Il catalogo conterrà una serie di *pubblicazioni* ,
ciascuna delle quali caratterizzata da un *titolo* , una lista di *autori* ,
un *editore* , una serie di *metadati* (vedi dopo) e, opzionalmente,
una *descrizione* testuale (sunto del contenuto o presentazione della
pubblicazione), un *indice* (composto dai titoli dei vari capitoli/sezioni
della pubblicazione, numerati e ordinati) e una serie di *sorgenti*
tramite le quali poter accedere alla pubblicazione o a parti di essa. Ciascuna
sorgente sarà caratterizzata da un *tipo* , una *URI* , da un *formato*
e da una *descrizione*. Esempi di sorgenti valide potrebbero essere i
seguenti:

- tipo="immagine", URI="http://server.net/cover.jpg",
  formato="image/jpeg", descrizione="copertina"

- tipo="download", URI="http://server.net/book.pdf",
  formato="application/pdf", descrizione="versione elettronica gratuita"

- tipo="acquisto", URI="http://www.amazon.it/xyz", formato="cartaceo,
  copertina rigida", descrizione="acquista online"

Per quanto riguarda invece i *metadati* , questi saranno
costituiti (almeno) dalle seguenti informazioni: codice *ISBN* , numero di *pagine* ,
*lingua* , *data* di pubblicazione, lista delle *ristampe*
(numero e data) e *parole chiave* identificative (zero o più).

-------

{#operazioni}

- Il sistema prevedrà due tipologie di utenza: *attiva* e *passiva* .
  L'utenza passiva potrà solo consultare il catalogo, quella attiva anche
  modificarlo. Gli utenti *anonimi* potranno vedere solo la homepage del
  sito, ma dovranno necessariamente effettuare la login per poter accedere a
  tutti gli altri contenuti.

- Gli utenti passivi potranno registrarsi nel sito tramite un
  modulo in cui inseriranno i loro dati anagrafici, un indirizzo email (che verrà
  usato anche come username) e, ovviamente, la password scelta. Gli utenti attivi
  potranno "promuovere" qualsiasi utente passivo già registrato rendendolo a sua
  volta attivo. Il sistema dovrà quindi prevedere un utente attivo iniziale di
  default preregistrato.

- Nella homepage del sito saranno elencate le ultime pubblicazioni
  inserite e quelle aggiornate di recente. Sarà inoltre presentata una lista
  degli utenti attivi più "collaborativi" (cioè quelli che hanno inserito più
  pubblicazioni) e, cliccando sul loro nome, si potrà visualizzare la lista delle
  pubblicazioni che hanno inserito (*opzionalmente* formattata come i
  risultati di ricerca descritti nei punti successivi).

- Gli utenti potranno consultare il catalogo completo tramite una
  visualizzazione paginata che elenca tutte le pubblicazioni con titolo, autori,
  editore e anno di pubblicazione. Dovrà essere possibile ordinare questa lista almeno
  in base a titolo e anno (l'ordinamento per titolo sarà il default) e *opzionalmente*
  in base a tutte le altre colonne. Selezionando una pubblicazione, verrà
  visualizzata la sua scheda bibliografica completa.

- Dovrà essere ovviamente presente anche un sistema di ricerca, per
  permettere agli utenti di trovare le pubblicazioni di loro interesse
  utilizzando vari criteri, senza necessariamente scorrere la lista completa del
  punto precedente. Le chiavi di ricerca da supportare *necessariamente*
  dovranno essere ISBN, titolo, autore, editore, anno di pubblicazione, parole
  chiave, lingua, presenza di sorgenti di tipo "download" (quindi pubblicazioni
  gratuite). L'utente dovrà poter specificare uno o più dei suddetti criteri, che
  verranno considerati in AND. La lista dei risultati ottenuti dalla ricerca avrà
  la stessa forma e funzionalità della lista completa del catalogo illustrata al
  punto precedente. Ovviamente, qualsiasi miglioramento a questa funzionalità di
  ricerca, ad esempio con l'aggiunta di ulteriori criteri, aumenterà il valore
  del progetto.

- La scheda bibliografica di una pubblicazione dovrà presentare,
  nella maniera più chiara e meglio organizzata possibile, tutte le informazioni
  legate ad essa. Se necessario, sarà possibile avvalersi anche di sotto-pagine
  accessibili dalla scheda bibliografica principale per organizzare meglio tali
  informazioni. Le sorgenti di tipo immagine, se presenti tra i dati della
  pubblicazione, dovranno venir usate per creare una galleria di immagini
  visualizzabili nella scheda bibliografica o in un'opportuna sotto-pagina. In
  particolare, supporremo che una sorgente di tipo immagine con descrizione
  "copertina" venga caricata, se disponibile, e mostrata come illustrazione all'inizio
  della scheda bibliografica, magari accanto al titolo.

- Sarà presente anche una (immancabile) parte social, tramite la
  quale gli utenti (anche quelli passivi) potranno *consigliare* la lettura
  di una pubblicazione o inserirne una *recensione* testuale. Il numero di
  "consigli" dati alla pubblicazione sarà mostrato nella scheda bibliografica
  insieme alla recensione più recente, e sarà possibile accedere a una
  sotto-pagina contenente la lista completa (*opzionalmente* paginata) delle
  recensioni. Queste ultime, tuttavia, non saranno visibili immediatamente dopo
  il loro inserimento, ma saranno soggette a moderazione, come descritto più
  avanti.

- Agli utenti attivi verrà data la possibilità di modificare la
  lista delle pubblicazioni. Dovrete quindi predisporre delle opportune maschere
  di input tramite le quali inserire, modificare e cancellare ogni dettaglio
  delle pubblicazioni stesse. In particolare, le funzioni di modifica e
  cancellazione di una pubblicazione saranno accessibili tramite opportuni link
  visibili direttamente nella scheda bibliografica quando l'accesso è effettuato
  da un utente attivo. Allo stesso modo, i link per l'inserimento potranno essere
  mostrati agli utenti attivi all'inizio della lista/catalogo generale.

- Gli utenti attivi vedranno inoltre, sempre accedendo a una scheda
  bibliografica, quante nuove recensioni (per quella pubblicazione) sono in
  attesa di essere approvate. Tali recensioni saranno visibili, nel loro caso,
  insieme alle recensioni già approvate, ma opportunamente evidenziate come "in
  attesa di moderazione" e dotate di un link tramite il quale approvarle,
  rendendole visibili a tutti, o eliminarle definitivamente.

- Per tener traccia delle modifiche effettuate alla bibliografia
  dai vari utenti attivi, il sistema dovrà mantenere una "storia" di ciascuna
  scheda bibliografica. Ogni *entry* di tale storia conterrà un *timestamp*,
  il nome dell'utente e una descrizione della modifica. Potete scegliere voi il
  dettaglio di questa descrizione: di base, sono accettabili anche descrizioni
  del tipo "ha modificato la pubblicazione", "ha inserito la pubblicazione", "ha
  approvato una recensione dell'utente X", ecc. La storia, opportunamente
  formattata, sarà accessibile a tutti gli utenti attivi sempre a partire dalla
  corrispondente scheda bibliografica.
