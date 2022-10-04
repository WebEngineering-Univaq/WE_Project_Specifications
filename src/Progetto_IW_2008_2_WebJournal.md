---
titolo: WebJournal
numero: 2
vestione: 1.0
lingua: IT
anno: 2008
materia: IW
mainfile: Progetto_Master.rcp
thisfile: specifica
---

-------

{#specifiche}

Il sito *WebJournal* rappresenta un semplice giornale
pubblicato online. Il giornale sarà diviso in *sezioni* (cronaca nera,
cronaca rosa, spettacolo, sport, ecc.) e la sua prima pagina corrisponderà alla
homepage del sito.

Gli articoli presenti sul nostro giornale online dovranno
contenere, oltre al loro titolo, al testo vero e proprio e alla lista degli
autori, una serie di informazioni: l'occhiello (riga di "lancio" mostrata
solitamente sopra il titolo), il sommario (una o più righe "riassuntive" poste
solitamente sotto il titolo), la data, la sezione (del giornale) di
pubblicazione, il livello di importanza della notizia (in scala 1...10) e una
serie di parole o frasi chiave, dette *tag*.

-------

{#operazioni}

- Il sito dovrà prevedere due tipi di visualizzazione per le
  notizie: *compatta* , contenente cioè solo data, occhiello, titolo e
  sommario, e *completa* , in cui tutte le informazioni disponibili sono
  visibili con opportuna formattazione (il più possibile simile a quella di un
  giornale cartaceo). Nel caso di articoli molto lunghi si potrà prevedere la
  loro paginazione. Cliccando su un articolo in modalità compatta, ovunque questo
  venga visualizzato, dovrà essere possibile aprire una pagina specifica che
  mostri l'articolo stesso in modalità completa. *Opzionalmente*, questa
  stessa pagina potrà offrire la possibilità di scaricare il testo dell'articolo
  come testo semplice (formattato con soli spazi e ritorni a capo, niente HTML).

- La homepage del sito, come già accennato, corrisponderà alla
  prima pagina del giornale. Su questa pagina andranno mostrate, con un layout
  opportuno che tenga conto dell'importanza e della sezione di appartenenza di
  ciascuna notizia, tutte le notizie odierne la cui importanza sia maggiore di una
  certa soglia (che fisseremo a 7), in modalità compatta.

- Dovrà essere poi possibile accedere a pagine specifiche che mostrino
  solo le notizie odierne (di qualunque importanza) appartenenti a ciascuna
  sezione del giornale (ad es. la pagina dello spettacolo, dello sport, ecc.). La
  formattazione di queste notizie dovrà seguire criteri simili a quelli usati
  nella prima pagina.

- Dovrà essere prevista una sezione archivio, a partire dalla quale
  sia possibile consultare la prima pagina e le pagine di sezione relative al
  giornale di qualsiasi giorno. In altre parole, dovrà essere possibile ricostruire
  e mostrare la prima pagina o, ad esempio, la pagina della cronaca nera
  corrispondenti a un giorno specificato dall'utente.

- Gli utenti avranno la possibilità di ricercare articoli per
  autore, data di pubblicazione, *tag* (specificandone uno o più) o
  specificando delle parole da cercare all'interno del testo dell'articolo
  (ricerca *fulltext* ). In risposta il sito mostrerà una lista di tutti gli
  articoli coerenti con i criteri specificati, in forma compatta (e quindi
  cliccabile, come descritto sopra). *Opzionalmente* , è possibile fare in
  modo che, in qualunque parte del sito in cui siano visualizzati dei *tag*
  (ad esempio nelle pagine di visualizzazione completa degli articoli), questi
  possano essere cliccati avviando la corrispondente ricerca per *tag*.

- Il sito dovrà prevedere una semplice procedura di registrazione
  per gli utenti.

- Gli utenti *registrati* nel sistema avranno la possibilità,
  a partire dalla pagina di visualizzazione completa di un articolo, di lasciare
  un loro commento. I commenti inseriti potranno essere mostrati unitamente
  all'articolo o in una sotto-pagina apposita.

- Gli utenti registrati potranno, a partire dalla pagina di
  visualizzazione completa di un articolo, inserire nuovi *tag*, da
  associare alla notizia (ma non modificare quelli già esistenti).

- Il sito dovrà inoltre essere dotato di un opportuno *backoffice*
  che permetta di inserire e modificare gli articoli pubblicati.  
