---
titolo: PollWeb
numero: 2
lingua: IT
anno: 2019
materia: IW
mainfile: Progetto_Master.rcp
thisfile: specifica
---

-------

{#specifiche}

Il sito *PollWeb* rappresenta un semplice sistema per la
realizzazione di sondaggi online. Ciascun sondaggio avrà un utente *responsabile*,
un titolo, un testo di apertura e uno di chiusura, e sarà composto da una serie
di domande. Ciascuna domanda, a sua volta, potrà essere di una delle seguenti
tipologie:

1) *Testo
   breve*: una riga di testo;

2) *Testo
   lungo*: più righe di testo;

3) *Numero*:
   solo numeri;

4) *Data*:
   solo date, opzionalmente con ora associata;

5) *Scelta
   singola*: vengono presentate una serie di opzioni e l'utente deve sceglierne
   esattamente una;

6) *Scelta
   multipla*: vengono presentate una serie di opzioni e l'utente può sceglierne
   una o più.

Tutti i tipi di domanda appena elencati avranno degli
attributi comuni: *codice* (usato per identificare univocamente la
domanda), *testo* (il testo della domanda, *opzionalmente* in HTML), *nota*
(una nota esplicativa che potrebbe apparire dopo il quesito per guidarne la
compilazione), *obbligatoria* (se impostato, indica che l'utente deve
necessariamente rispondere alla domanda, o scegliere (almeno) una delle
risposte nel caso delle domande a scelta multipla). Altri attributi specifici
potranno essere aggiunti a ciascun tipo di domanda per definirla meglio, ad
esempio

· Lunghezza minima e massima di un campo di testo;

· *Valore* *minimo e massimo* per i campi numerici (e
magari anche per quelli data);

· *Espressione regolare* che deve fare match con un campo di
testo;

· Numero minimo e/o massimo di opzioni selezionabili per le scelte
multiple.

Questi attributi sono tutti *opzionali*, ma più ne
gestirete più realistico diverrà il vostro progetto.

*Suggerimento:*una parte molto importante di questo
progetto sarà, chiaramente, la definizione e la realizzazione di una struttura
dati che possa modellare i sondaggi aggregando domande che a loro volta possano
essere definite, ciascuna con le proprie caratteristiche, nella maniera più
efficiente possibile, e associate alle risposte in maniera altrettanto efficace.

-------

{#operazioni}

- Il sistema dovrà prevedere tre tipologie di utenza: *partecipante* ,
  *responsabile* e *amministratore*. Le tipologie sono a cascata,
  quindi, ad esempio, un responsabile potrà essere anche un partecipante. I dati
  associati a ciascun utente dovranno includere almeno un indirizzo email valido.

- *L'amministratore* è unico e lo supporremo preregistrato nel
  sistema. I responsabili dovranno essere registrati dagli amministratori. Per i
  partecipanti vedremo più avanti la procedura di registrazione nel sistema.

- Ciascun utente *responsabile* potrà creare nuovi sondaggi, a
  cui verrà associato. Nel creare un sondaggio, andranno forniti tutti i campi
  testuali (vedi sopra), dopodiché si passerà alla definizione delle domande,
  come descritto nei punti seguenti.

- Per comporre il sondaggio, il responsabile inserirà le singole domande
  una alla volta, in sequenza. Deve essere possibile rivedere la sequenza dei
  quesiti già inseriti in una schermata riassuntiva, nella quale siano anche
  presentate le caratteristiche più importanti di ciascun quesito.

- Le domande già inserite nella sequenza del sondaggio devono poter
  essere modificate, cancellate o riordinate (spostandole più in alto o più in
  basso nella sequenza).

- Ogni tipo di domanda avrà una schermata di input
  (inserimento/modifica) propria, anche se ovviamente le varie schermate
  dovrebbero mantenere una certa uniformità, almeno per gli elementi comuni a
  tutte le tipologie.

- Il sondaggio potrà essere *riservato* o *pubblico* . Nel
  primo caso (sondaggio *riservato* ), il responsabile dovrà inserire
  manualmente nel sistema i dati (nome, email, password) dei partecipanti che
  potranno accedere al sondaggio. *Opzionalmente* , questi dati potrebbero
  essere anche importati da un file CSV.   

*Nota bene: ogni sondaggio avrà il suo insieme di partecipanti, quindi gli
utenti inseriti in un sondaggio non potranno accedere ad altri sondaggi, a meno
che non siano registrati (replicandone i dati) anche in questi ultimi.* Nel
caso invece il sondaggio sia *pubblico*, chiunque potrà accedervi, cioè
non sarà prevista una procedura di autenticazione.

- Una volta soddisfatto della definizione del sondaggio, il
  responsabile potrà *attivarlo* , rendendolo compilabile al pubblico.
  All'atto dell'attivazione, gli verrà presentata la URL che i partecipanti
  potranno utilizzare per accedere alla compilazione del sondaggio. *Opzionalmente*,
  nel caso di sondaggi riservati, all'attivazione il sistema potrebbe inviare un'email
  di invito, completa di URL di accesso e credenziali, a tutti i partecipanti
  registrati.

- Accedendo alla URL del sondaggio (quella presentata al
  responsabile al momento della sua attivazione), ai partecipanti dei sondaggi *riservati*
  verrà richiesto di autenticarsi, per poi passare alla compilazione. Per i
  sondaggi *pubblici* , invece, si passerà direttamente alla compilazione. *Nota
  bene: nei sondaggi riservati, ciascun utente potrà partecipare solo una volta,
  quindi dopo una compilazione conclusasi con successo, la sua utenza verrà
  disabilitata.*

- La compilazione del sondaggio si svolgerà mostrando all'utente
  tutti i quesiti in esso definiti, nella sequenza impostata. Scegliete la
  tecnica di input più consona a ciascun tipo di quesito. *Opzionalmente*,
  potrete anche presentare il sondaggio paginato, un certo numero di quesiti per
  volta.

- Una volta inviate le risposte al sondaggio, il server effettuerà
  tutti i dovuti controlli sulla validità e sui vincoli impostati sui singoli
  quesiti, e in caso di successo registrerà le risposte. In caso di errore,
  l'utente verrà invitato a ripetere la compilazione.

- Il responsabile potrà in ogni momento *chiudere* il
  sondaggio, inibendone l'accesso ai partecipanti.

- Il responsabile potrà *esportare i dati* delle risposte in
  formato CSV e/o in altri formati utili. Potete scegliere il formato dei dati in
  maniera da rendere questo file il più chiaro e informativo possibile. *Opzionalmente*,
  il responsabile potrà anche visualizzare le singole risposte pervenute
  direttamente via web (in sola lettura ovviamente).  
