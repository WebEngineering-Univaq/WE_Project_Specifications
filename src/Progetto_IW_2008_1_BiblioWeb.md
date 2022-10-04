---
titolo: BiblioWeb
numero: 1
vestione: 1.0
lingua: IT
anno: 2008
materia: IW
mainfile: Progetto_Master.rcp
thisfile: specifica
---

-------

{#specifiche}

Il sito *BiblioWeb* è un sistema per la creazione collaborativa
di bibliografie. Una bibliografia è una raccolta di riferimenti bibliografici,
raggruppati in base a un fattore comune, come l'autore, l'editore, l'argomento o
una serie di *tag* (parole o frasi chiave) specificati dagli utenti.

Un riferimento bibliografico è costituito, al minimo, da una
lista di autori, dal titolo della pubblicazione, dal tipo (libro, articolo su
rivista, e-book, pubblicazione online, ecc.) e da tutte le altre informazioni
utili a descrivere e identificare la pubblicazione stessa, dipendenti dal suo
tipo: ad esempio nome dell'editore, numero di pagine, volume e numero della
rivista, url di pubblicazione, ecc. Per identificare il maggior numero di
informazioni associabili alle varie tipologie di pubblicazione, si vedano i
tipi di pubblicazione e le corrispondenti voci standard delle entry **BibTeX**
(http://it.wikipedia.org/wiki/BibTeX). Inoltre, i nostri riferimenti potranno
essere associati a una o più parole/frasi chiave (*tag* ) ed anche a un
breve sunto del loro contenuto (*abstract*).

Queste informazioni saranno inserite e aggiornate dagli
utenti in maniera collaborativa, similmente a quello che avviene con i Wiki.

-------

{#operazioni}

- Il sito dovrà prevedere due tipi di visualizzazione per i
  riferimenti: *compatta* , in cui il riferimento è formattato in maniera da
  contenere solo le informazioni essenziali (titolo, autori e altre informazioni
  di base legate al tipo: ad esempio nome, numero e editore della rivista), e *completa* ,
  in cui tutte le informazioni disponibili sono visibili con opportuna
  formattazione. La visualizzazione compatta verrà usata in associazione con alcune
  funzionalità, come la ricerca (si veda dopo). Cliccando su un riferimento in
  modalità compatta, ovunque questo venga visualizzato, dovrà essere possibile
  aprire una pagina specifica che mostri il riferimento in modalità completa. *Opzionalmente*,
  questa stessa pagina potrà offrire la possibilità di scaricare (o mostrare a
  video) lo stesso riferimento in formato BibTeX o come testo semplice
  (formattato con soli spazi e ritorni a capo, niente HTML).

- Allo stesso modo, per le bibliografie (intese, come già detto,
  come raccolte "tematiche" di riferimenti) esisterà una visualizzazione *compatta*
  e cliccabile, contenente solo il nome e il numero di riferimenti che la
  compongono, e una *completa*, visualizzata su una pagina specifica e
  contenente tutti i dettagli sulla raccolta, compresa la lista dei riferimenti
  corrispondenti (questi ultimi mostrati in modalità compatta).

- Il sito dovrà prevedere una semplice procedura di registrazione
  per gli utenti.

- Tutti gli utenti (registrati e non) avranno la possibilità di
  ricercare riferimenti bibliografici inserendo uno o più dettagli degli stessi
  (ad esempio parte del titolo, parte del nome di uno degli autori, nome della
  rivista, nome e numero della rivista, ecc.). In risposta il sito mostrerà una
  lista paginata di tutti i riferimenti coerenti con i criteri specificati, in
  forma compatta (e quindi cliccabile, come descritto sopra).

- Tutti gli utenti potranno effettuare una ricerca per *tag* ,
  specificandone uno o più e ricevendo come risultato la lista paginata di tutti
  i riferimenti e le bibliografie (in modalità compatta) associate ai *tag*
  specificati. *Opzionalmente* , è possibile fare in modo che, in qualunque
  parte del sito in cui siano visualizzati dei *tag* (ad esempio nelle
  pagine di visualizzazione completa di riferimenti o bibliografie), questi
  possano essere cliccati avviando la corrispondente ricerca per *tag*.

- Gli utenti *registrati* nel sito potranno, a partire da una
  pagina di visualizzazione completa, editare le informazioni presenti nel
  corrispondente riferimento o bibliografia oppure, a partire dalla homepage del
  sito, aggiungere nuovi riferimenti/bibliografie. Nel caso dei riferimenti,
  l'utente potrà inserire/modificare tutti e soli i dettagli associabili con lo
  specifico tipo di riferimento. Nel caso delle bibliografie, gli utenti potranno
  anche aggiungere o rimuovere riferimenti dalla raccolta (i riferimenti
  aggiunti alle bibliografie devono essere già stati inseriti nel sistema). In
  tutti i casi l'utente sarà libero anche di modificare i *tag* associati al
  riferimento o alla bibliografia. *Opzionalmente* , il sistema potrà
  prevedere la generazione e l'associazione automatica di *tag* ai
  riferimenti in base alle informazioni di base ad essi associate (ad esempio i
  nomi degli autori potranno diventare automaticamente *tag*).

- Il sistema terrà traccia di tutti gli utenti che sono intervenuti
  su un riferimento o bibliografia, e potrà (a partire dalla pagina di
  visualizzazione completa) mostrare il log (data, ora, utente) degli
  aggiornamenti.

- La homepage del sito dovrà presentare delle statistiche sul
  numero di riferimenti e bibliografie disponibili, sulle ultime modifiche e
  sulle bibliografie più "attive" (cioè più spesso modificate) e più "ricche"
  (cioè contenenti più riferimenti). Le voci visualizzate dovranno essere
  cliccabili per accedere agli oggetti (riferimenti o bibliografie complete)
  corrispondenti.  
