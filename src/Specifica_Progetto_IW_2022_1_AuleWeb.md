---
titolo: AuleWeb
numero: 1
lingua: IT
anno: 2022
materia: IW
mainfile: Progetto_Master.rcp
thisfile: specifica
---

-------

{#specifiche}

Il sito *AuleWeb* rappresenta una versione semplificata (*e magari visivamente migliorata!*) del sistema di gestione aule del nostro Ateneo (https://aule.linfcop.univaq.it).

Ogni *aula* gestita dal sistema avrà associati un nome, una posizione (luogo, edificio, piano), una capienza (numero posti), l’email del responsabile, il numero di prese
elettriche e di rete presenti, delle generiche note e la lista delle attrezzature disponibili, scelte tra le seguenti: Proiettore, Schermo Motorizzato, Schermo Manuale, Impianto Audio, PC Fisso, Microfono a Filo, Microfono senza Filo, Lavagna Luminosa, WiFi. Opzionalmente è possibile rendere tale lista configurabile tramite l’applicazione stessa.

Le aule saranno suddivise in *gruppi* (che potranno rappresentare dipartimenti, poli, ecc.) configurabili tramite l’applicazione stessa. Ogni gruppo avrà un nome e una descrizione.

Sarà possibile allocare le aule assegnandovi degli *eventi*. Per semplicità, assumeremo che un evento non possa essere a cavallo di due o più giorni: in altre parole ogni evento si svolgerà in una singola giornata (di cui dovrà essere specificata la data), con una determinata ora di inizio e di fine. Anche qui, per semplicità, assumeremo di poter inserire orari con scarti di 15 minuti (quindi non potremo mai specificare le 10.16, per esempio, ma solo 10.15 o 10.30). L’evento avrà associate anche una descrizione, il nome e l’email del responsabile dell’evento, una tipologia (lezione, esame, seminario, parziale, riunione, lauree, altro) e, per le tipologie lezione, esame e parziale, anche il nome di un corso. Per i corsi e i responsabili dovrà essere possibile scegliere da una lista o inserire un nuovo nome, che sarà poi aggiunto automaticamente alla lista per le successive immissioni.

Un evento potrà essere dichiarato come *ricorrente*, e in tal caso si dovrà specificare il tipo di ricorrenza (giornaliera, settimanale o mensile) e fino a che data ripeterlo. *Suggerimento: un evento ricorrente corrisponde a tutti gli effetti a un evento copiato nello stesso slot orario per tutti i giorni determinati dal tipo di ricorrenza, fino al termine specificato. Al momento della definizione di un evento ricorrente, quindi, potreste semplicemente creare tutta la serie di eventi singoli corrispondenti e inserirli nel calendario. Tali eventi avranno, però, un "ID master" in comune, in modo che il sistema possa capire che sono in relazione (ad esempio, se si cancella o modifica uno degli elementi del gruppo, il sistema potrebbe chiedere all’utente se modificare solo quello o anche tutti gli altri dello stesso gruppo). Ovviamente questa è un’idea, potete trovare anche altre soluzioni ugualmente o maggiormente valide.*

-------

{#operazioni}

- L’accesso in lettura al front-end del sito sarà libero e non richiederà alcuna autenticazione.
  
- Nel front-end sarà possibile visualizzare lo stato di allocazione delle aule in diverse modalità:
  
   - Mostrare gli eventi associati a una specifica aula in una determinata settimana,
  
   - Mostrare gli eventi associati a ciascuna aula in un determinato giorno,
  
   - Mostrare tutti gli eventi attuali e quelli delle prossime tre ore,
  
   - Mostrare gli eventi associati a uno specifico corso in una determinata settimana.
  
   Per tutte le viste di cui sopra, le sole aule da considerare dovranno essere solo quelle relative a un *gruppo*
  specifico, che andrà sempre selezionato prima di scegliere gli altri parametri
  della vista. Dovrete realizzare le viste al meglio possibile, in modo da
  rendere i dati principali visibili “a colpo d’occhio” e prevedendo, se occorre,
  sotto-viste di dettaglio raggiungibili cliccando su determinati elementi.
  
- Dal front-end gli utenti potranno esportare tutti gli eventi relativi a un certo intervallo di tempo, e opzionalmente
  relativi anche a un determinato corso, in formato CSV (*suggerimento: per manipolare agevolmente i CSV in Java potete usare https://commons.apache.org/proper/commons-csv*) oppure, *opzionalmente*, iCalendar (ad esempio usando https://github.com/ical4j/ical4j).
  
- Il sistema disporrà inoltre di un gruppo di utenti-amministratori che, una volta effettuata la login, potranno modificarne
  i dati. In particolare, gli amministratori potranno:
  
  - inserire e modificare la configurazione delle aule e dei relativi gruppi,
  
  - inserire e modificare eventi,
  
  - esportare e importare in CSV la configurazione delle aule.
