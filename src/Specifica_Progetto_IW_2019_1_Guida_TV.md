---
titolo: Guida TV
numero: 1
versione: 1.0
lingua: IT
anno: 2019
materia: IW
mainfile: Progetto_Master.rcp
thisfile: specifica
---

-------

{#specifiche}

Il sito "Guida TV" rappresenta una guida online ai programmi
televisivi. Il sito gestirà il palinsesto di un certo numero di canali
televisivi, per ognuno dei quali sarà disponibile l'elenco dei programmi per
ogni giorno. Verranno pubblicati i programmi dei sette giorni successivi a
quello corrente (ovviamente potranno essercene anche meno, in base ai dati
forniti dai vari editori), mentre per i programmi dei giorni passati, anch'essi
disponibili, è possibile prevedere un limite oltre il quale tali informazioni
saranno cancellate dal database, per evitare inutile carico.

Di ogni programma avremo l'ora di inizio e fine, il nome, una
breve descrizione e il genere (i generi dovrebbero essere prelevati da una
lista predefinita). Se il programma rappresenta un episodio di una serie,
avremo anche il numero di stagione e il numero di episodio nella stagione.
Potrà essere presente anche un link a una scheda di approfondimento (non
necessariamente interna al sito stesso: pensate alle pagine della Wikipedia, ad
esempio) nonché un'immagine. Quest'ultima potrà essere interna al sito o
collegata tramite un link esterno.

Sarà possibile consultare il palinsesto di ogni canale
(programmi di un certo giorno) ed effettuare ricerche per titolo e/o genere,
eventualmente ristrette a uno specifico canale. L'intervallo temporale di tali
ricerche potrà essere altresì specificato dall'utente.

*Suggerimento: considerate che molto spesso nei palinsesti
figurano più volte gli stessi programmi, oppure episodi di una stessa serie.
Nel progettare il modello dati, e quindi anche le operazioni che lo riguardano,
provate a ottimizzarne al meglio la struttura in base a questa considerazione.
Ad esempio, se un film viene replicato in due giorni diversi, il database non
dovrebbe contenerne due volte tutte le informazioni di base (titolo,
descrizione, link...): solo i dati di messa in onda (canale, ora, ecc.), che sono
gli unici a cambiare, dovrebbero esistere in due versioni diverse.*

Sul sito sarà possibile registrarsi inserendo la propria
email e una password. Gli utenti registrati, una volta eseguita la login,
potranno specificare le modalità di ricezione di una email giornaliera con gli
ultimi aggiornamenti al palinsesto. La mail potrà contenere i programmi del
giorno per alcuni canali selezionati, eventualmente solo per certe fasce orarie
(mattino/pomeriggio/sera/notte) e/o i risultati di una ricerca salvata (del
tipo appena descritto), per essere aggiornati, ad esempio, sul momento in cui
nel palinsesto appare un programma che si vuole seguire. *Nota:
l'applicazione realizzata per il progetto non dovrà necessariamente inviare
queste email, ma dovrete comunque realizzare tutto il codice per crearne il
contenuto, riversandolo poi, in fase di demo, su un file esterno.*

Nota bene: trattandosi di un sito che verrà sicuramente
usato molto in mobilità, si curi particolarmente l'aspetto della *responsiveness*.

-------

{#operazioni}

- La homepage mostrerà la lista dei canali a disposizione, nonché
  le trasmissioni correntemente in onda su ciascuno di essi.

- Dalla homepage si potrà accedere a una seconda vista simile a
  quella della homepage stessa, in cui sono elencati tutti i canali con
  associati, però, i programmi del loro palinsesto giornaliero *relativi a una
  specifica fascia oraria* (mattina/pomeriggio/sera/notte).

- In qualsiasi vista, cliccando su un canale, sarà possibile
  visualizzare il suo palinsesto completo per la giornata attuale. In questa
  vista, quella classica da "guida tv", saranno mostrati tutti i programmi (ordinati!)
  con l'ora di inizio, quella di fine, il genere e il titolo. Se disponibile, a
  fianco di un programma potrà essere mostrata la relativa immagine
  opportunamente scalata.

- In qualsiasi vista, cliccando su un programma si accederà alla
  scheda con i dettagli: immagine a dimensione maggiore (se disponibile),
  descrizione, link di approfondimento.

- Se il programma è parte di una serie, nella sua scheda di
  dettaglio dovrà essere possibile visualizzare data/ora e canale di trasmissione
  di tutti i relativi episodi nell'ultimo mese.

- La funzionalità di ricerca, accessibile in ogni punto del sito, dovrà
  permettere di specificare uno o più dei seguenti criteri, combinati in AND: (parte
  del) titolo, genere, ora di inizio massima e minima, canali, intervallo
  temporale (date). I risultati di ricerca saranno mostrati in maniera simile
  alla vista della guida TV, ma in questo caso ordinati per data, ora di inizio e
  canale.

- Un utente potrà registrarsi fornendo una email valida e una
  password a sua scelta. L'email dovrà essere confermata cliccando su un link
  inviato allo stesso indirizzo. *Nota: scrivete il codice necessario a
  generare il link di convalida e gestirne il click, ma in sede di demo potrete
  semplicemente far stampare il link da qualche parte e immetterlo nel browser,
  senza bisogno di inviare veramente delle email.*

- Nel proprio profilo l'utente potrà abilitare l'email giornaliera
  di informazioni, descritta più in alto, specificando eventualmente una lista di
  canali e una o più fasce orarie di interesse.

- L'utente autenticato, inoltre, una volta eseguita una ricerca
  come visto sopra, avrà a disposizione un bottone per salvarne i criteri, in
  modo che possano essere usati per generare ulteriori informazioni da inserire
  nella sua mail giornaliera, come già illustrato.

- Ovviamente, l'utente registrato potrà in ogni momento
  disabilitare l'invio dei risultati di una ricerca e/o del palinsesto
  giornaliero.

- L'amministratore del sito, che immagineremo unico e preregistrato
  nel sistema, potrà inserire, modificare o cancellare i canali e i relativi
  palinsesti, cioè i programmi e le informazioni sulla loro messa in onda.  
