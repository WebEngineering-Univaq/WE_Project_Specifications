---
titolo: CollaborativeGenealogy
numero: 2
vestione: 2.0
lingua: IT
anno: 2014
materia: IW
mainfile: Progetto_Master.rcp
thisfile: specifica
---

-------

{#specifiche}

Il sito *CollaborativeGenealogy* rappresentaun
metodo sociale per costruire il proprio albero genealogico contribuendo
contemporaneamente al completamento di quello degli altri utenti.

Il sito dovrà essere accessibile solo a un'utenza
registrata. Ciascun utente dovrà fornire (e non potrà più aggiornare) i propri
dati anagrafici completi, comprensivi di data e luogo di nascita, e un
indirizzo email, all'atto della registrazione. L'utente potrà poi fornire i
propri contatti (indirizzo, numeri di telefono, ecc.) e, *opzionalmente*,
tenere aggiornata anche una propria biografia testuale e caricare una foto da
utilizzare per il suo profilo. L'aspetto "sociale" del sistema risiede nel modo
in cui vengono costruiti gli alberi genealogici.

-------

{#operazioni}

- Gli utenti anonimi, cioè che accedono al sito senza fare login,
  vedranno una semplice pagina di presentazione, un modulo di login/registrazione
  e uno di ricerca. La ricerca sarà effettuata solo su nome e cognome degli
  utenti registrati e i risultati mostreranno solo il nome completo degli utenti
  e il numero di "parenti" nel loro albero genealogico. In questo modo l'utente
  anonimo potrà "testare" l'utilità del servizio, pur senza violare la privacy
  degli utenti registrati, e decidere di iscriversi per poter usare il sistema
  nella sua totalità.

- Un utente registrato potrà eseguire ricerche nel sistema sulla
  base di vari parametri, tra cui i più importanti sono nome e cognome (trovare
  persone con il proprio cognome è un buon punto di partenza per ricercare una
  possibile parentela!), data e luogo di nascita. Dovrà essere data all'utente la
  massima libertà nel combinare questi parametri per effettuare ricerche
  "mirate". I risultati della ricerca conterranno, in questo caso, nome, cognome,
  data e luogo di nascita.

- Per creare il proprio albero genealogico, l'utente avrà tre
  modalità. *Nota bene:* per semplificare il sistema, l'utente potrà aggiungere
  di volta in volta solo parenti diretti, cioè *padre* , *madre,* *figli* e*fratelli*, di persone già nel suo albero genealogico. Quindi, per
  inserire il suo nonno materno, dovrà prima inserire sua madre e poi il padre di
  quest'ultima.
   1. Dopo aver effettuato una ricerca, individuando dei possibili parenti, l'utente avrà la possibilità di aggiungerli al proprio albero genealogico.
   2. Se un parente non è già presente nel sistema, ma è noto all'utente, questo potrà creare il suo profilo di base (nome, cognome, email, data e luogo di nascita) e aggiungerlo contestualmente al proprio albero genealogico.
   3. Infine, per gestire parenti non raggiungibili (o defunti) l'utente potrà creare un profilo base come specificato sopra ma *senza
   un indirizzo email* e aggiungerlo al proprio albero genealogico, ma in questo caso la relazione parentela sarà sempre mostrata dal sistema con la segnalazione "*non verificato*" a fianco.
   
- In tutti i casi, l'utente dovrà poter specificare il componente
  del suo albero genealogico con cui la persona trovata è legata e il relativo
  grado di parentela (*padre* , *madre* , *figlio, fratello*).

- Nei casi 1 e 2, cioè quando si aggiunge un parente già registrato
  o lo si specifica manualmente, il possibile nuovo parente dovrà approvare la
  parentela dichiarata, prima che l'inserimento sia considerato definitivo.
  Finché non lo farà, ovviamente, la parentela non sarà considerata effettiva e
  non sarà mostrata nella genealogia dell'utente. Una volta approvata la
  parentela, i due utenti diverranno ufficialmente "parenti" e ciascuno potrà
  vedere tutti i dati e navigare nell'albero genealogico dell'altro.

- Il potenziale parente riceverà una notifica per email *(Suggerimento:
  non c'è bisogno che inviate delle vere email, per questo prototipo basterà che
  mostriate il testo che vorreste inviare...)* con i dati della persona
  "proponente" e il tipo di parentela proposta, che potrà approvare o rifiutare.
  Per gli utenti già registrati (aggiunti come al punto 1), sarà possibile fare
  login nel loro account ed effettuare questa scelta. Gli utenti non registrati
  (aggiunto come al punto 2) riceveranno nell'email di notifica un invito a
  registrarsi nel sistema e approvare la parentela.

- Il sistema dovrà infine permettere a ciascun utente registrato di
  "navigare" nel proprio albero genealogico, mostrando per prime le parentele dirette
  e permettendo di espandere passo dopo passo i "parenti dei parenti", e così via.
  Questa navigazione comprenderà sia la parte di albero da lui direttamente
  costruita, sia i sotto-alberi costruiti dai suoi parenti anch'essi registrati
  nel sistema. Un sistema di *breadcrumbs,* il classico percorso di
  navigazione a segmenti, permetterà in questo caso di ricostruire il rapporto di
  parentela del parente attualmente selezionato. Ad esempio: sulla pagina
  principale del mio profilo, clicco su mio padre "Tizio". La pagina mi mostrerà
  allora il percorso attuale "Io \> Tizio (padre)", i dati di Tizio e tutti i
  parenti a lui direttamente legati. Cliccando su suo padre "Caio" passerò alla
  sua pagina il cui percorso sarà "Io \> Tizio (padre) \> Caio (padre)" e
  così via. *Opzionalmente*, potreste cercare di calcolare il rapporto di
  parentela complessivo del parente selezionato in base al percorso seguito: in
  questo caso, ad esempio, la pagina potrebbe mostrare "Caio è il tuo nonno
  paterno".
