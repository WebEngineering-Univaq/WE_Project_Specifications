---
titolo: TestOnLine
numero: 1
vestione: 1.0
lingua: IT
anno: 2011
materia: IW
mainfile: Progetto_Master.rcp
thisfile: specifica
---

-------

{#specifiche}

Il sito Test*OnLine* rappresenta un semplice sistema
web per la definizione, la somministrazione e la valutazione di test.

Ciascun test gestito dal nostro sistema consisterà in una
serie di quesiti a risposta multipla, con una sola risposta esatta e un numero
arbitrario di risposte scorrette. Un quesito sarà a sua volta composto da un
testo illustrativo (obbligatorio, *opzionalmente* contenente codice HTML
di formattazione semplice, come i tag \<b\> e \<i\>) e da una serie
opzionale di immagini illustrative (che potrebbero rappresentare, ad esempio,
equazioni, grafi, ecc.), mentre le possibili risposte saranno composte da soli
blocchi di testo, oltre a un flag che ne indichi l'esattezza.

Il sistema prevederà tre tipi di utenza: il coordinatore, il
docente e lo studente.

-------

{#operazioni}

- I docenti potranno inserire nuovi quesiti (o modificare i quesiti
  già inseriti), associandoli a uno dei settori didattici di riferimento
  preimpostati nel sistema, ad esempio "Reti di Calcolatori",
  "Tecnologie del Web" o "Algoritmi". Per ciascun quesito
  dovranno inoltre fornire una valutazione del livello di difficoltà, in scala
  1-5, nell'ambito del settore prescelto, e ovviamente un insieme di risposte,
  tra cui almeno una dovrà essere indicata come corretta.

- I coordinatori potranno gestire la lista dei settori didattici
  disponibili, accreditare nuovi docenti (cioè eseguirne la registrazione sul
  sistema), e creare i test.

- Per creare i test, i coordinatori assegneranno loro un nome, il
  periodo di erogazione (cioè l'intervallo di giorni all'interno del quale potrà
  essere sostenuto) e le composizione, secondo una delle seguenti modalità:
1) indicando una serie di docenti e, per ciascuno di essi, uno dei settori
   didattici per i quali hanno predisposto dei quesiti, un livello di difficoltà e
   un numero di quesiti (ad esempio: 5 quesiti di livello 3 sulle Reti di
   Calcolatori redatti dal prof. X, 12 quesiti di livello 5 sulle Tecnologie del
   Web redatti dal prof. Y);

2) indicando solamente una serie di settori didattici con associato un
   livello di difficoltà e un numero di quesiti (ad esempio 5 quesiti di livello 3
   sulle Reti di Calcolatori, 12 quesiti di livello 5 sulle Tecnologie del Web);

In base alle scelte del
coordinatore, il sistema dovrà verificare che un test della composizione data
possa essere effettivamente generato (cioè se il numero e la tipologia di
quesiti richiesti è effettivamente disponibile.).

- La durata di un test sarà calcolata automaticamente, in base alla
  sua composizione, secondo la formula ![](Progetti%20IW%202012%20-1_file/image001.gif), dove *T* è
  l'insieme dei quesiti componenti il test, *L(q)* è il livello di
  difficoltà del quesito *q* e *K(l)* restituisce il tempo (in minuti)
  concesso per risolvere un quesito di livello *l* (scelto da voi!).

- La homepage del sito dovrà mostrare tutti i test in programma,
  evidenziando quelli che si terranno a breve. Ciascun test sarà descritto
  indicando il numero di quesiti contenuti, con il settore didattico ed
  eventualmente il nome del docente di riferimento, nonché dalla sua durata
  complessiva.

- Gli studenti potranno registrarsi nel sistema fornendo le proprie
  credenziali (tra le quali è richiesto un indirizzo email e un numero di
  matricola), e poi iscriversi ai test in programma (non sarà ovviamente
  possibile iscriversi più di una volta allo stesso test, o iscriversi a test che
  si sono già tenuti).

- In qualunque momento nell'intervallo di validità di un test, uno
  studente iscritto potrà connettersi, autenticarsi e sostenerlo.

- Nel momento in cui uno studente richiederà di sostenere un test,
  il sistema ne genererà *un'istanza casuale* nel modo che segue:
1) nel caso in cui il test sia stato definito come al punto (1), il sistema
   selezionerà, per ciascuna tupla (*docente* , *settore* , *livello* ,
   *numero* ) presente nella definizione del test stesso, un *numero* di
   quesiti (scelti a caso) tra quelli inseriti dal *docente* per quello
   specifico *settore* con il *livello* di difficoltà specificato;

2) nel caso in cui invece il test sia stato definito come al punto (2), il
   sistema selezionerà, per ciascuna tupla (*settore* , *livello* , *numero* )
   presente nella definizione del test stesso, un *numero* di quesiti (scelti
   a caso) tra quelli inseriti da tutti i docenti per quello specifico *settore*
   con il *livello* di difficoltà specificato.

In entrambi i casi, infine, il
sistema selezionerà *casualmente* , tra le risposte possibili di ciascun
quesito così prescelto, *tre risposte*, tra cui figuri sempre anche quella
corretta.

- Il test verrà presentato allo studente come sequenza di quesiti,
  suddivisi per settore, con le risposte associate tra cui effettuare una scelta.
  Una volta avviato il test, lo studente potrà scegliere le risposte e poi
  sottometterle (tutte insieme) al sistema per la valutazione.

- Se le risposte saranno inviate dopo la durata massima consentita
  (calcolata come visto sopra), il sistema rifiuterà il test, che non potrà
  essere più sostenuto. Se invece le risposte saranno fornite nei termini
  previsti, il sistema mostrerà all'utente un riepilogo delle domande, indicando
  la sua risposta e quella effettivamente esatta. I quesiti in cui la risposta
  data risulta scorretta saranno evidenziati. Alla fine del test, verrà riportato
  il punteggio finale calcolato assegnando un punto a ciascuna risposta esatta,
  -1 a ciascuna risposta errata e zero a ciascuna risposta non data.

- Il voto dello studente per il particolare test sarà registrato
  nella base di dati del sistema, insieme al tempo impiegato per risolverlo e
  alla risposta data a ciascun quesito.

- Il coordinatore potrà consultare in qualsiasi momento l'elenco
  dei risultati di ciascun test, corredato da qualche statistica significativa (ad
  esempio media punteggi, tempo medio di risoluzione del test, ecc.). Sarà
  inoltre possibile consultare voti e statistiche relative a tutti i test
  sostenuti da un particolare studente.

- *Opzionalmente*, è possibile fare in modo che ciascun
  docente possa visualizzare delle statistiche sui propri quesiti (ad esempio,
  numero di volte in cui il quesito è stato utilizzato in un test e numero di
  persone che hanno scelto la risposta giusta).  
