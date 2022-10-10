---
titolo: AsteOnLine
numero: 2
vestione: 1.0
lingua: IT
anno: 2010
materia: IW
mainfile: Progetto_Master.rcp
thisfile: specifica
---

-------

{#specifiche}

Il sito *AsteOnLine* rappresenta un semplice sistema di
aste, in cui dei venditori mettono all'asta dei beni e dei compratori fanno
delle offerte per acquistarli.

Gli oggetti messi all'asta avranno ciascuno una pagina
dedicata sul sito, che ne riporterà le informazioni essenziali, cioè nome,
descrizione, stato di conservazione (nuovo, usato, danneggiato, ecc.),
eventuali link informativi e una foto opzionale. Una serie di *tag,* cioè
parole o frasi brevi, potranno essere associati agli oggetti per meglio
classificarli e facilitarne la ricerca. Infine, la pagina relativa a un oggetto
dovrà mostrare lo stato dell'asta associata: data di inizio e fine della messa
all'asta, modalità di consegna (spedizione postale, corriere, ecc.) e pagamento
(contrassegno, carta di credito, bonifico, ecc.), prezzo base e rilancio minimo.

Il sito prevede due tipologie di utenza: utenti *anonimi*
e utenti *registrati*. Andranno quindi predisposte opportune funzionalità
di registrazione e di login. Gli utenti anonimi potranno solo effettuare
ricerche sul sito, mentre quelli registrati potranno agire sia da venditori che
da compratori.

-------

{#operazioni}

- Tutti gli utenti potranno ricercare oggetti di loro interesse in
  base a: (1) parole o frasi contenute nel nome o nella descrizione, (2) i *tag*
  associati, (3) il venditore, (4) il prezzo (base). La completezza e la
  versatilità della funzione di ricerca, essenziale per un sito come questo, è
  lasciata all'iniziativa dei realizzatori. I risultati della ricerca dovranno
  essere presentati elencando gli oggetti trovati con nome, venditore e data di
  inizio/chiusura asta. Cliccando su ciascun oggetto si aprirà la corrispondente
  pagina descrittiva.

- Nella pagina descrittiva di un oggetto dovrà essere possibile
  cliccare sul nome del venditore per visualizzare il relativo profilo (dati
  anagrafici, indirizzo email, ecc.) e la lista degli eventuali altri oggetti che
  ha posto all'asta.

- Nella pagina descrittiva di un oggetto, e in generale ovunque
  compaiano dei *tag*, dovrà essere possibile cliccare su uno di essi
  avviando automaticamente una ricerca di tutti gli oggetti associati.

- Ogni utente registrato potrà inserire nuovi oggetti da mettere
  all'asta, specificandone i dati descritti sopra, modificare propri oggetti già
  inseriti, ma solo entro la data di inizio dell'asta, e ritirare (cancellare) propri
  oggetti anche durante l'asta.

- Ogni utente registrato potrà visionare la lista degli oggetti che
  ha messo all'asta e, per quelli la cui asta è correntemente in corso, sapere
  quante sono state le offerte, il tempo rimanente prima della chiusura
  dell'asta, nonché la data, l'utente e l'ammontare relativi all'ultima offerta.

- Ogni utente registrato potrà partecipare a un numero arbitrario
  di aste attive, facendo un'offerta che sia maggiore o uguale alla relativa base
  d'asta e aumenti l'eventuale offerta precedente di una somma almeno
  corrispondente al rilancio minimo.

- Ogni utente registrato potrà visionare la lista degli oggetti per
  cui ha fatto un'offerta, unitamente al tempo rimanente prima della fine
  dell'asta corrispondente. Nel caso ci sia stata una successiva offerta
  superiore alla sua, il sistema ne mostrerà l'ammontare dandogli la possibilità
  di effettuare un rilancio.

- Una volta raggiunto il termine dell'asta, l'oggetto
  corrispondente non sarà più visibile nelle ricerche. L'offerente maggiore
  riceverà una notifica (sulla homepage dopo la login e *opzionalmente* per
  email) della sua vittoria, con allegate le informazioni di pagamento. Allo stesso
  modo, al venditore verrà notificato l'avvenuto acquisto con i dati del
  compratore. Nel caso in cui un oggetto non abbia ricevuto alcuna offerta,
  invece, alla chiusura dell'asta il venditore potrà modificarne le informazioni
  ed eventualmente stabilire le date di una nuova asta.

- La homepage del sito dovrà mostrare alcune informazioni a
  carattere generale, ad esempio gli ultimi oggetti messi all'asta, quelli con
  rilanci più alti, ecc..  
