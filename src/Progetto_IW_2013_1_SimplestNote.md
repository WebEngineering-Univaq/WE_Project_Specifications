---
titolo: SimplestNote
numero: 1
vestione: 1.0
lingua: IT
anno: 2013
materia: IW
mainfile: Progetto_Master.rcp
thisfile: specifica
---

-------

{#specifiche}

Il sito *SimplestNote* rappresenta un semplice blocco
note online, con possibilità di condivisione delle note.

Il sito dovrà essere accessibile solo a un'utenza
registrata. Ciascun utente avrà a disposizione un blocco note virtuale,
composto da un numero arbitrario di pagine, che di seguito chiameremo
semplicemente *note* , ognuna dotata di titolo e contenuto, entrambi
testuali. La lunghezza del titolo può essere limitata, mentre quella del
contenuto dovrebbe essere illimitata. Le singole note saranno inoltre associate
alla data di creazione, la data di ultima modifica, il numero di versione
(corrispondente al numero di volte in cui la nota è stata modificata) e a un
numero arbitrario di *tag* , intesi come parole o brevi sequenze di parole
(ad esempio "*novità* ", "*lavoro* " o "*corrispondenza privata*").

Il sistema provvederà a salvare tutte le versioni di
ciascuna nota, in modo da prevenire modifiche involontarie e fornire una storia
della sua stesura. Sarà possibile condividere una nota con altri utenti del
sistema, facendola apparire nei loro blocchi ed eventualmente permettendone la
modifica.

-------

{#operazioni}

- Gli utenti potranno registrarsi su *SimplestNote* fornendo i
  propri dati e un indirizzo email valido (il controllo di validità, effettuabile
  inviando un'email con un link da cliccare per la verifica dell'indirizzo, è *opzionale*)
  e ricevendo delle credenziali di accesso. L'indirizzo email sarà usato come
  username, mentre la password dovrà essere generata in maniera casuale al
  momento della registrazione.

- Una volta effettuata la login, l'utente potrà consultare la lista
  delle proprie note (mostrate con titolo e data di ultima modifica).
  Selezionando una nota si aprirà la vista di lettura/editing della stessa.
  L'interfaccia dovrà inoltre permettere la creazione di nuove note (con un
  titolo iniziale "standard" predefinito, magari basato sulla data/ora correnti)
  e l'eliminazione delle note esistenti.

- La vista di lettura/editing per una nota dovrà permettere la
  modifica del titolo, del contenuto nonché dei tag. *Opzionalmente*, quando
  si aggiunge un tag, il sistema potrebbe suggerire uno dei tag già utilizzati
  dall'utente in altre note, oltre che permettere l'inserimento di un nuovo tag
  sotto forma di breve testo.

- Ad ogni modifica, il sistema salverà prima lo stato corrente
  della nota (titolo, contenuto, tag, data di ultima modifica) in una *history*,
  e solo a questo punto applicherà le modifiche richieste (salvando il nuovo
  stato della nota, incrementando il numero di versione, aggiornando la data di
  ultima modifica). In questo modo la history sarà via via popolata con tutte le
  versioni precedenti della nota stessa.

- Dovrà essere possibile accedere alla history di ogni singola
  nota, visualizzando il numero di versione e la data di modifica di tutte le sue
  versioni precedenti. Cliccando su un elemento della history, sarà possibile vedere
  titolo, contenuto e tag della nota per quella versione, ma *in sola lettura*.

- Dovrà essere possibile condividere una nota con altri utenti
  dello stesso sistema, specificandone l'indirizzo email utilizzato per la
  registrazione. La condivisione sarà effettuabile in sola lettura o in
  lettura/scrittura. Un utente vedrà le note condivise con lui all'interno della
  propria lista note, evidenziate in modo da renderne chiara la provenienza
  (indirizzo email del proprietario) e i permessi di accesso (lettura o
  lettura/scrittura). Le note condivise in sola lettura potranno essere lette ma
  non modificate. Su quelle in lettura/scrittura sarà possibile effettuare ogni
  tipo di modifica, esattamente come per le note di cui si è proprietari. Il
  proprietario di una nota condivisa potrà interromperne la condivisione in
  qualsiasi momento.

- *Opzionalmente* , potrete realizzare l'*endpoint* per un
  eventuale client mobile del nostro servizio: un semplice sistema di
  esportazione JSON delle note.  Il sito dovrà rispondere a due URL speciali, che indicheremo rispettivamente
con *http://server.it/notepad/getList?user=email\&pass=password* e con *http://server.it/notepad/getNote?user=email\&pass=password\&note=ID.*   Chiamando la prima, il server dovrà restituire una struttura JSON (attenzione al *content type* !) che rappresenta la lista di tutte le note dell'utente
avente l'*email* specificata, autenticato tramite la *password*
inserita anch'essa nella URL. Ovviamente, in caso di problemi con
l'autenticazione, la risposta sarà vuota. La lista dovrà contenere, per ogni
nota, il suo ID (chiaramente il vostro sistema dovrà dotare ogni nota di un
identificatore per inserirlo nella base di dati) e il titolo.   Chiamando invece la seconda URL, verrà restituita una struttura JSON contenente data di creazione, data di modifica, numero di versione, titolo, contenuto e
tags della nota specificata dall'ID inserito nella URL stessa e appartenente
all'utente autenticato con le credenziali specificate. *Nota bene:* in
un'applicazione reale, trasmettere username e password ad ogni chiamata del
servizio sarebbe poco efficiente e sicuro, ma qui utilizzeremo quest'approccio
per semplificare l'implementazione.
