---
titolo: LibriOnLine
numero: 1
vestione: 1.0
lingua: IT
anno: 2010
materia: IW
mainfile: Progetto_Master.rcp
thisfile: specifica
---

-------

{#specifiche}

Il sito *LibriOnLine* rappresenta una semplice
interfaccia web per la gestione di una biblioteca.

La base di dati del sito conterrà informazioni riguardanti i
volumi gestiti dalla biblioteca, gli utenti e i prestiti. In particolare, per
ogni libro avremo il codice ISBN, il titolo, la lingua, l'editore, l'anno di
pubblicazione, i nomi di tutti gli autori e, opzionalmente, una recensione o breve
descrizione (come quella che spesso appare sulla copertina posteriore del libro
o sul risvolto interno della sovracopertina). Una serie di *tag,* cioè
parole o frasi brevi (ad. es. "botanica", "informatica",
"programmazione","novità", ecc.), saranno associati a ciascun volume e potranno
essere, ad esempio, estratte dal titolo del libro stesso o/e decise dai
bibliotecari. Ogni libro avrà una durata massima di prestito (*default* un
mese) e potrà essere presente in biblioteca anche in più copie. Infine, alcuni
libri potranno essere contrassegnati "di libera lettura" ed accessibili
direttamente online, sotto forma di file di testo o PDF scaricabili. Per ogni
libro il sito dovrà generare una pagina descrittiva che contenga,
opportunamente organizzate, tutte le informazioni di cui sopra.

Il sito dovrà prevedere tre
tipologie di utenza: *bibliotecari* , utenti *registrati* e utenti *anonimi* .
Andranno quindi previste opportune procedure di login. **Supporremo che** **solo
i bibliotecari possano aggiungere nuovi utenti (compresi altri bibliotecari)
nel sistema** (che sarà inizializzato con un singolo bibliotecario di
default), ad esempio registrando un utente quando questo deposita le proprie
credenziali presso la biblioteca. Ogni utente registrato avrà un profilo
contenente i suoi dati anagrafici, l'indirizzo email e un numero di telefono.

-------

{#operazioni}

- Tutti gli utenti dovranno poter ricercare i libri in base a: (1)
  il titolo o parte di esso, (2) i *tag* associati, (3) uno o più degli
  autori, (4) il codice ISBN. La completezza e la versatilità della funzione di
  ricerca, essenziale per un sito come questo, è lasciata all'iniziativa dei
  realizzatori. I risultati della ricerca dovranno essere presentati elencando i
  libri trovati, ciascuno con titolo, autori, editore e anno. Cliccando su
  ciascun libro si aprirà la corrispondente pagina di dettaglio.

- Nella pagina di dettaglio di un libro dovrà essere possibile
  cliccare sul nome di un autore avviando automaticamente una ricerca di tutti i
  libri da lui scritti (la sua bibliografia completa).

- Nella pagina di dettaglio di un libro, e in generale ovunque
  compaiano dei *tag*, dovrà essere possibile cliccare su uno di essi
  avviando automaticamente una ricerca di tutti i libri associati.

- A partire dalla pagina di dettaglio di un libro gli utenti
  dovranno poter conoscere il numero di copie presenti nella biblioteca e il
  numero di quelle attualmente libere (non in prestito). *Opzionalmente*, è
  possibile indicare all'utente, nel caso in cui tutte le copie siano in
  prestito, la data presunta di restituzione della prima copia, calcolata sulla
  base della sua data di prestito e della durata massima prevista.

- I bibliotecari, dopo aver cercato e individuato un particolare
  libro (usando le funzioni appena elencate), potranno registrarne il prestito a
  nome di uno degli utenti noti al sistema.

- Gli utenti registrati potranno visualizzare la lista dei volumi
  che hanno in prestito e le relative date di riconsegna. I libri la cui data di
  riconsegna è stata superata dovranno essere opportunamente evidenziati. Gli
  utenti potranno inoltre visionare lo storico dei volumi già presi in prestito e
  restituiti.

- I bibliotecari potranno, a partire dalla pagina di dettaglio di un
  libro, verificare i dati di tutti i prestiti, presenti o passati, relativi ad
  esso. Inoltre, i bibliotecari potranno visualizzare una lista (eventualmente
  paginata) di tutti i libri in prestito, tra cui saranno evidenziati quelli la
  cui data di riconsegna è stata superata.

- La homepage del sito dovrà mostrare alcune informazioni a
  carattere generale, ad esempio i libri maggiormente prestati e gli ultimi
  aggiunti alla biblioteca. Per gli utenti registrati, la homepage potrà anche
  segnalare i libri da riconsegnare a breve.

- Il sito dovrà essere provvisto di un adeguato *backoffice*,
  accessibile ai soli bibliotecari, tramite il quale inserire e modificare tutti i
  dati associati ai libri.  
