# Corso di Web Engineering<br/>*Progetti A.A. 2023/2024* - Specifica 2

<section class="specifica">

## Progetto "AuleWeb"
> Versione 2

### Premessa

I progetti di fine corso si ispirano sempre ad esigenze
reali, e fanno solitamente riferimento a tipologie di sito già presenti sulla
rete. Nello svolgere il progetto, gli studenti dovranno attenersi alla
specifica data in questo documento, ma potranno raffinarla tramite l'interazione
col docente e l'analisi di siti web analoghi. In ogni caso, la realizzazione
finale dovrà essere completamente originale. Le informazioni pubblicate
dovranno essere sempre ben organizzate ed accessibili, date le varie tipologie
di utenza associate alle applicazioni web pubbliche.  

### Specifiche del Sito

<section class="descrizione">



Il sito *AuleWeb* rappresenta una versione semplificata (*e magari visivamente migliorata!*) del sistema di gestione aule del nostro Ateneo (https://aule.univaq.it).

Ogni *aula* gestita dal sistema avrà associati un nome, una posizione (luogo, edificio, piano), una capienza (numero posti), l’email del responsabile, il numero di prese elettriche e di rete presenti, delle generiche note e la lista delle attrezzature disponibili scelte da una lista configurabile tramite l’applicazione stessa, che comprenderà inizialmente gli elementi Proiettore, Schermo Motorizzato, Schermo Manuale, Impianto Audio, PC Fisso, Microfono a Filo, Microfono senza Filo, Lavagna Luminosa, WiFi.

Le aule saranno suddivise in *gruppi* (che potranno rappresentare dipartimenti, poli, ecc.) configurabili tramite l’applicazione stessa. Ogni gruppo avrà un nome e una descrizione.

Sarà possibile allocare le aule assegnandovi degli *eventi*. Per semplicità, assumeremo che un evento non possa essere a cavallo di due o più giorni: in altre parole ogni evento si svolgerà in una singola giornata (di cui dovrà essere specificata la data), con una determinata ora di inizio e di fine. L’evento avrà associate anche una descrizione, il nome e l’email del responsabile dell’evento, una tipologia (lezione, esame, seminario, parziale, riunione, lauree, altro) e, per le tipologie lezione, esame e parziale, anche il nome di un corso. Per i corsi e i responsabili dovrà essere possibile scegliere da una lista o inserire un nuovo nome, che sarà poi aggiunto automaticamente alla lista per le successive immissioni.

Un evento potrà essere dichiarato come *ricorrente*, e in tal caso si dovrà specificare il tipo di ricorrenza (giornaliera, settimanale o mensile) e fino a che data ripeterlo. *Suggerimento: un evento ricorrente corrisponde a tutti gli effetti a un evento copiato nello stesso slot orario per tutti i giorni determinati dal tipo di ricorrenza, fino al termine specificato. Al momento della definizione di un evento ricorrente, quindi, potreste semplicemente creare tutta la serie di eventi singoli corrispondenti e inserirli nel calendario. Tali eventi avranno, però, un "ID master" in comune, in modo che il sistema possa capire che sono in relazione (ad esempio, se si cancella o modifica uno degli elementi del gruppo, il sistema potrebbe chiedere all’utente se modificare solo quello o anche tutti gli altri dello stesso gruppo). Ovviamente questa è un’idea, potete trovare anche altre soluzioni ugualmente o maggiormente valide.*


</section>


Di seguito sono illustrati schematicamente i contenuti e le
funzionalità minime che dovrebbero essere inseriti nel sito. Ovviamente, ogni
ulteriore raffinamento o arricchimento di queste specifiche aumenterà il valore
del progetto.

  <section class="operazioni">
  


- L'accesso in lettura al front-end del sito sarà libero e non richiederà alcuna autenticazione.
- Nel front-end sarà possibile visualizzare lo stato di allocazione delle aule in diverse modalità:
   - Mostrare gli eventi associati a una specifica aula in una determinata settimana,
   - Mostrare gli eventi associati a ciascuna aula in un determinato giorno,
   - Mostrare tutti gli eventi attuali (cioè attualmente in corso) e quelli delle prossime tre ore (cioè che inizieranno nelle prossime tre ore),
   - Mostrare gli eventi associati a uno specifico corso in una determinata settimana.
  
  Per tutte le viste di cui sopra, le sole aule da considerare dovranno essere solo quelle relative a un *gruppo*
  specifico, che andrà sempre selezionato prima di scegliere gli altri parametri
  della vista. Dovrete realizzare le viste al meglio possibile, in modo da
  rendere i dati principali visibili "a colpo d’occhio" e prevedendo, se occorre,
  sotto-viste di dettaglio raggiungibili cliccando su determinati elementi.
  
- Dal front-end gli utenti potranno esportare tutti gli eventi relativi a un certo intervallo di tempo, ed eventualmente
  relativi anche a un determinato corso, in formato CSV (*suggerimento: per manipolare agevolmente i CSV in Java potete usare https://commons.apache.org/proper/commons-csv*) oppure, *opzionalmente*, iCalendar (ad esempio usando https://github.com/ical4j/ical4j).
- Il sistema disporrà inoltre di un gruppo di utenti-amministratori che, una volta effettuata la login, potranno modificarne
  i dati. In particolare, gli amministratori potranno:
  - inserire e modificare la configurazione delle aule e dei relativi gruppi,
  - inserire e modificare eventi,
  - inserire e modificare le attrezzature disponibili
  - esportare e importare in CSV la configurazione delle aule.
  
  </section>

<section class="indicazioni break">

# Indicazioni per lo Sviluppo del Progetto

### Tecnologie da utilizzare

- La *struttura* base del sito deve essere realizzata in **HTML5**. La validazione
delle principali pagine del sito è parte integrante dello sviluppo e deve essere
riportata nella documentazione.

- Per la realizzazione del *layout* devono essere utilizzati il più
possibile i figli di stile CSS. Il layout può liberamente basarsi su quelli
disponibili in rete o utilizzati a lezione. Il grado di **personalizzazione**
del layout sarà comunque tenuto in considerazione in sede di valutazione. **Un
layout responsive non è strettamente richiesto ma fortemente consigliato.**

- Per la programmazione lato *client* il linguaggio richiesto
è JavaScript. Si possono liberamente includere nel progetto librerie sviluppate
da terze parti, a patto che la loro portabilità cross-browser sia adeguata e
che nella relazione siano citate e descritte. È in ogni caso **sconsigliato
l'abuso di tali tecnologie** , soprattutto quando sia possibile sostituirle
con un adeguato uso di HTML, CSS, ecc. In linea generale, è **ammissibile che gli
script giochino un ruolo più importante nelle funzionalità la cui utenza è
ristretta e predeterminata**, ad esempio nelle funzionalità *back-end*
per gli amministratori, ma non nel *front-end* pubblico del sito o in una
procedura di login. Su queste parti, invece, **l'uso del sito senza script potrebbe
essere meno "agevole" o permettere di accedere solo alle funzionalità "vitali"**. 

- Per la programmazione lato *server* è **richiesto** l'uso
di Java (*servlet*), eventualmente associato a qualsiasi *DBMS* (se necessario)
e a un *template engine* (come *Freemarker*). Anche in questo caso è
possibile avvalersi di librerie esterne.

- Il sito, in generale, deve funzionare ed avere un buon *rendering*
sulle versioni più recenti di Edge, Firefox e Chrome, e *possibilmente*
essere compatibile con i browser più datati (in questo caso non c'è bisogno che
tutto funzioni perfettamente, ma almeno che le funzionalità *degradino bene*)
e con le ultime versioni di altri browser, come Opera. Tale compatibilità **deve**
essere esplicitamente dichiarata nella documentazione.  

### Svolgimento e Documentazione del Progetto

Le specifiche fornite potrebbero non risultare esaustive o
completamente definite. Ogni funzionalità aggiunta o raffinata, anche tramite
l'interazione con il committente o con gli utenti finali del sito, sarà
adeguatamente valutata. Tutte le scelte progettuali vanno comunque discusse e
motivate.

Il progetto, svolto secondo le linee guida date dalle
specifiche, dovrà essere consegnato nella forma di un sito web completamente
funzionante, i cui contenuti e le cui caratteristiche saranno valutati in sede
d'esame. Le parti della specifica marcate come *opzionali*, se omesse, non
renderanno il progetto insufficiente ma non gli permetteranno comunque di
raggiungere il massimo dei voti. Nel caso si decida di realizzarle, non sarà
necessario che siano perfette o complete, ma che dimostrino chiaramente il
vostro impegno nell'affrontare una tematica avanzata.

La documentazione (**in formato elettronico**) che
accompagna il progetto **deve** contenere almeno le seguenti informazioni:

- Indicazione delle dipendenze software (di quali librerie avete
bisogno dal lato server e client?).

- Indicazione delle funzionalità realizzate e di quelle
eventualmente non realizzate. Descrizione dettagliata delle eventuali
funzionalità extra o opzionali inserite nel progetto.

- Diagramma che illustra la struttura e la navigabilità del sito (ad es.
un *navigation diagram*).

- Schema relazionale della base di dati (se presente).

- Descrizione analitica del layout del sito, con indicazione delle
sue principali componenti statiche/dinamiche.

- Descrizione delle eventuali tecnologie avanzate (linguaggi,
framework, plugin, librerie, ...) utilizzate, del motivo per cui sono state
adottate e del contributo effettivo che hanno dato alla realizzazione del
progetto.

- Descrizione di *eventuali* problemi riscontrati nella
fruizione del sito su browser differenti, lista dei browser compatibili.

- Screenshot delle pagine più importanti del sito (*opzionale*).

Nel caso di gruppi di lavoro composti da più componenti, *il
contributo effettivo offerto da ciascun componente* alla realizzazione
finale **deve** essere descritto nella documentazione (indicando, ad
esempio, chi si è dedicato prevalentemente alla programmazione server, chi ha
realizzato il layout, chi ha programmato lato client, ecc.). In sede di esame,
i responsabili potranno essere chiamati a riferire sugli aspetti loro delegati.  

### Valutazione del Progetto

Nel valutare il progetto consegnato saranno prese in
considerazione le seguenti caratteristiche (in ordine di importanza):
1. Rispetto delle specifiche.
2. Correttezza tecnica.
3. Chiarezza e correttezza organizzativa dei contenuti.
4. Accessibilità e conformità agli standard.
5. Uso appropriato di contenuti statici e dinamici.
6. Qualità del design.
7. Adeguatezza della documentazione.

A questa valutazione si aggiungerà quella generale derivata
dalla discussione del progetto in sede d'esame.  

### Ulteriori Informazioni

Questa specifica è disponibile nel repository del corso di Web Engineering, 
all'indirizzo https://github.com/WebEngineering-Univaq/WE_Project_Specifications.
Ulteriori informazioni e chiarimenti sulle specifiche possono essere richiesti
direttamente via email all'indirizzo giuseppe.dellapenna@univaq.it.

Si ricorda che i progetti vanno svolti in *piccoli* gruppi (tre persone è il numero consigliato). 
Eccezioni a questa regola andranno concordate direttamente col docente.

An English translation of this project specification is also available in the course repository (https://github.com/WebEngineering-Univaq/WE_Project_Specifications).
If the translation is not there, ask the teacher to publish it :smile:
</section>

