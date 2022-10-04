---
titolo: Collectors Site
numero: 2
versione: 2.0
lingua: IT
anno: 2021
materia: IW
mainfile: Progetto_Master.rcp
thisfile: specifica
---

-------

{#specifiche}

Il sito *Collectors Site* rappresenta un punto di
incontro per i collezionisti di dischi (anche se lo stesso tipo di sito
potrebbe adattarsi quasi a qualunque tipo di collezione, useremo i dischi come
caso di studio in modo da poter aggiungere più dettagli alla specifica).

Gli utenti di questo sito, o *collezionisti* , una volta
registrati potranno inserire tutti i dati relativi alle proprie *collezioni* di
dischi(dovete prevedere che ogni collezionista possa creare più
collezioni, ciascuna con un nome distinto). Per ogni *disco* in una
collezione, dovranno essere specificati gli autori, il titolo, l'anno di uscita,
l'etichetta (casa editrice), il genere (scelto da una lista predefinita di generi
musicali), lo stato (di conservazione dell'oggetto, scelto da una lista
predefinita), il formato (vinile, CD, digitale,...), il numero di *barcode*,
se disponibile (i codici a barre garantiscono l'identificazione univoca
dell'elemento), e poi ovviamente la lista delle tracce, ciascuna con titolo,
durata, ed eventuali informazioni su compositore ed esecutore (cantante,
musicista), se diverso da quelli dell'intero disco. Infine, ogni disco può
essere associato a una o più immagini (copertina, retro, eventuali facciate
interne o libretti, ecc.). Insomma, cercate di essere il più realistici
possibile.

Per ogni disco, il collezionista potrà inoltre indicare
l'eventuale numero di *doppioni* a sua disposizione (spesso si hanno più
copie dello stesso disco, magari a seguito di scambi, e magari anche perché se
ne prevede la rivendita).

I collezionisti potranno decidere di *condividere* la
propria collezione con specifici utenti o in maniera pubblica. Ogni
collezionista avrà quindi a disposizione un pannello con una lista delle
collezioni condivise specificamente con lui, che potrà visualizzare
liberamente.

Il sito disporrà di una funzionalità di ricerca avanzata
(per artista, titolo, collezionista, ecc.), utilizzabile anche dagli utenti
anonimi, che prenderà in considerazione tutte le collezioni pubbliche e, per un
utente che abbia eseguito l'accesso, anche la collezione personale e tutte le
collezioni condivise con lui (*suggerimento: potete eseguire la stessa
ricerca su ogni collezione accessibile dall'utente e poi fondere i risultati*).

È importante che, nel sistema, gli stessi dischi, anche se
appartenenti a collezioni e collezionisti diversi, siano messi in relazione, in
modo da poterli raggruppare se necessario, proprio per rispondere più
facilmente a interrogazioni del tipo "chi ha questo disco?". A questo scopo,
cercate sempre, quando viene immesso un nuovo disco, di "suggerire" al
collezionista di importare (come valori iniziali) i dati dello stesso disco, se
già presente nel sistema in altre collezioni. Così facendo, internamente
creerete una connessione tra i dischi "uguali", anche se poi il collezionista
sarà libero di editare i dati della propria copia. Inoltre, sarebbe opportuno
inserire l'autocompletamento ovunque possibile, usando come origine i dati
dello stesso campo già presenti nella base di dati: ad esempio, inserendo il
nome di un cantante, il sistema dovrebbe suggerire il completamento usando i
nomi dei cantanti già inseriti. Questo accorgimento non ha solo lo scopo di
velocizzare l'input, ma è utile anche per evitare che nella base di dati lo
stesso oggetto (in questo caso, un cantante) sia inserito più volte con piccole
variazioni di scrittura (ad esempio spazi, apostrofi, ecc.).

-------

{#operazioni}

- I collezionisti potranno registrarsi nel sistema fornendo un
  nickname e un indirizzo email. Non è richiesto, anche se possibile, inserire il
  proprio nome e cognome.

- Ogni collezionista avrà un profilo pubblico, visibile anche agli
  utenti anonimi, contenente i dati personali inseriti e la lista delle sole
  collezioni pubbliche.

- I collezionisti, una volta autenticati, potranno gestire le
  proprie collezioni, e in particolare creare o cancellare una collezione e
  inserire/cancellare/modificare i singoli dischi contenuti nella collezione, con
  le caratteristiche descritte precedentemente nella specifica.

- Il sito dovrà prevedere (almeno) due viste sulle collezioni:
  lista dell'intera collezione e dettaglio disco contenuto nella collezione. In
  entrambi i casi, dovrete decidere quali informazioni mostrare e come
  organizzarle. Ovviamente la vista sulla collezione e sui relativi contenuti
  sarà accessibile al proprietario e a tutti coloro che posseggano diritti di
  accesso alla collezione stessa (nel caso di collezioni pubbliche o condivise).

- Un'importante elemento del sito sarà la funzionalità di ricerca. Dovrà
  essere possibile effettuare ricerche in base a nomi di
  autori/compositori/interpreti, in base a titoli e in base al nickname dei
  collezionisti. I risultati potranno essere di tipo diverso in base agli
  elementi trovati: singoli dischi, intere collezioni, profili di collezionisti.
  Si potrà decidere di includere nella ricerca solo le proprie collezioni (se si
  è autenticati) o anche quelle condivise/pubbliche.

- Ogni collezionista avrà a disposizione un pannello con la lista
  delle collezioni condivise con lui, dalle quali accedere in maniera diretta
  alla vista della relativa collezione.

- Ogni collezionista potrà decidere se rendere ciascuna propria
  collezione privata (default), pubblica o condividerla con altri specifici
  utenti. Quando si condivide la collezione con un utente, questo riceverà una
  email di notifica (*suggerimento: potete simulare l'invio, non è necessario
  usare realmente la posta elettronica*).

- Il sito dovrà fornire una serie di statistiche, pubbliche o
  personali (per collezionista). Siete liberi di individuare quelle più
  interessanti. Suggerimenti possono essere il numero dischi per autore, per
  genere, ecc. (in una collezione, per il collezionista, o in tutto il sistema,
  come statistica globale)  
