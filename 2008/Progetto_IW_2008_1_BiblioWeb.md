# Corso di Web Engineering
*Progetti A.A. 2008/2009* - Specifica 1

## Progetto "BiblioWeb"

> Versione 1.0

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

Il sito *BiblioWeb* è un sistema per la creazione collaborativa di bibliografie. Una bibliografia è una raccolta di riferimenti bibliografici, raggruppati in base a un fattore comune, come l'autore, l'editore, l'argomento o una serie di *tag* (parole o frasi chiave) specificati dagli utenti.

Un riferimento bibliografico è costituito, al minimo, da una lista di autori, dal titolo della pubblicazione, dal tipo (libro, articolo su rivista, e-book, pubblicazione online, ecc.) e da tutte le altre informazioni utili a descrivere e identificare la pubblicazione stessa, dipendenti dal suo tipo: ad esempio nome dell'editore, numero di pagine, volume e numero della rivista, url di pubblicazione, ecc. Per identificare il maggior numero di informazioni associabili alle varie tipologie di pubblicazione, si vedano i tipi di pubblicazione e le corrispondenti voci standard delle entry **BibTeX** (http://it.wikipedia.org/wiki/BibTeX). Inoltre, i nostri riferimenti potranno essere associati a una o più parole/frasi chiave (*tag* ) ed anche a un breve sunto del loro contenuto (*abstract*).

Queste informazioni saranno inserite e aggiornate dagli utenti in maniera collaborativa, similmente a quello che avviene con i Wiki.

Di seguito sono illustrati schematicamente i contenuti e le
funzionalità minime che dovrebbero essere inseriti nel sito. Ovviamente, ogni
ulteriore raffinamento o arricchimento di queste specifiche aumenterà il valore
del progetto.
* Il sito dovrà prevedere due tipi di visualizzazione per i riferimenti: *compatta* , in cui il riferimento è formattato in maniera da contenere solo le informazioni essenziali (titolo, autori e altre informazioni di base legate al tipo: ad esempio nome, numero e editore della rivista), e *completa* , in cui tutte le informazioni disponibili sono visibili con opportuna formattazione. La visualizzazione compatta verrà usata in associazione con alcune funzionalità, come la ricerca (si veda dopo). Cliccando su un riferimento in modalità compatta, ovunque questo venga visualizzato, dovrà essere possibile aprire una pagina specifica che mostri il riferimento in modalità completa. *Opzionalmente*, questa stessa pagina potrà offrire la possibilità di scaricare (o mostrare a video) lo stesso riferimento in formato BibTeX o come testo semplice (formattato con soli spazi e ritorni a capo, niente HTML).

* Allo stesso modo, per le bibliografie (intese, come già detto, come raccolte "tematiche" di riferimenti) esisterà una visualizzazione *compatta* e cliccabile, contenente solo il nome e il numero di riferimenti che la compongono, e una *completa*, visualizzata su una pagina specifica e contenente tutti i dettagli sulla raccolta, compresa la lista dei riferimenti corrispondenti (questi ultimi mostrati in modalità compatta).

* Il sito dovrà prevedere una semplice procedura di registrazione per gli utenti.

* Tutti gli utenti (registrati e non) avranno la possibilità di ricercare riferimenti bibliografici inserendo uno o più dettagli degli stessi (ad esempio parte del titolo, parte del nome di uno degli autori, nome della rivista, nome e numero della rivista, ecc.). In risposta il sito mostrerà una lista paginata di tutti i riferimenti coerenti con i criteri specificati, in forma compatta (e quindi cliccabile, come descritto sopra).

* Tutti gli utenti potranno effettuare una ricerca per *tag* , specificandone uno o più e ricevendo come risultato la lista paginata di tutti i riferimenti e le bibliografie (in modalità compatta) associate ai *tag* specificati. *Opzionalmente* , è possibile fare in modo che, in qualunque parte del sito in cui siano visualizzati dei *tag* (ad esempio nelle pagine di visualizzazione completa di riferimenti o bibliografie), questi possano essere cliccati avviando la corrispondente ricerca per *tag*.

* Gli utenti *registrati* nel sito potranno, a partire da una pagina di visualizzazione completa, editare le informazioni presenti nel corrispondente riferimento o bibliografia oppure, a partire dalla homepage del sito, aggiungere nuovi riferimenti/bibliografie. Nel caso dei riferimenti, l'utente potrà inserire/modificare tutti e soli i dettagli associabili con lo specifico tipo di riferimento. Nel caso delle bibliografie, gli utenti potranno anche aggiungere o rimuovere riferimenti dalla raccolta (i riferimenti aggiunti alle bibliografie devono essere già stati inseriti nel sistema). In tutti i casi l'utente sarà libero anche di modificare i *tag* associati al riferimento o alla bibliografia. *Opzionalmente* , il sistema potrà prevedere la generazione e l'associazione automatica di *tag* ai riferimenti in base alle informazioni di base ad essi associate (ad esempio i nomi degli autori potranno diventare automaticamente *tag*).

* Il sistema terrà traccia di tutti gli utenti che sono intervenuti su un riferimento o bibliografia, e potrà (a partire dalla pagina di visualizzazione completa) mostrare il log (data, ora, utente) degli aggiornamenti.

* La homepage del sito dovrà presentare delle statistiche sul numero di riferimenti e bibliografie disponibili, sulle ultime modifiche e sulle bibliografie più "attive" (cioè più spesso modificate) e più "ricche" (cioè contenenti più riferimenti). Le voci visualizzate dovranno essere cliccabili per accedere agli oggetti (riferimenti o bibliografie complete) corrispondenti.

# Indicazioni per lo Sviluppo del Progetto

### Tecnologie da utilizzare

* La struttura base del sito va realizzata in HTML5. La validazione di tutte le pagine del sito rispetto alla tipologia di HTML prescelta è parte integrante dello sviluppo e **deve** essere riportata nella documentazione.
* Per la realizzazione del layout devono essere utilizzati il più possibile i figli di stile CSS. Il layout può liberamente basarsi su quelli disponibili in rete o utilizzati a lezione. Il grado di **personalizzazione** del layout sarà comunque tenuto in considerazione in sede di valutazione. **Un layout responsive non è strettamente richiesto ma fortemente consigliato.**
* Per la programmazione lato *client* il linguaggio richiesto è JavaScript. Si possono liberamente includere nel progetto librerie sviluppate da terze parti, a patto che la loro portabilità cross-browser sia adeguata e che nella relazione siano citate e descritte. È in ogni caso **sconsigliato l'abuso di tali tecnologie** , soprattutto quando sia possibile sostituirle con un adeguato uso di HTML, CSS, ecc. **In linea generale, il vostro sito dovrà essere utilizzabile anche con JavaScript disattivato.** L'uso del sito senza script potrebbe essere meno "agevole" o permettere di accedere solo alle funzionalità "vitali", ma non è consentito presentare siti la cui dinamica sia totalmente basata sull'uso degli script. È tuttavia **ammissibile che gli script giochino un ruolo più importante nelle funzionalità la cui utenza è ristretta e predeterminata** (ad esempio nelle funzionalità *back-end* per gli amministratori, ma non nel *front-end* pubblico del sito o in una procedura di login).
* Per la programmazione lato *server* è **richiesto** l'uso di Java (*servlet* ), eventualmente associato a qualsiasi DBMS (se necessario) e a un *template engine* come*Freemarker*. Anche in questo caso è possibile avvalersi di librerie esterne.
* Il sito, in generale, deve funzionare ed avere un buon *rendering* sulle versioni più recenti di Edge, Firefox e Chrome, e *possibilmente* essere compatibile con i browser più datati (in questo caso non c'è bisogno che tutto funzioni perfettamente, ma almeno che le funzionalità *degradino bene* ) e con le ultime versioni di altri browser, come Opera. Tale compatibilità **deve** essere esplicitamente dichiarata nella documentazione.

### Svolgimento e Documentazione del Progetto

Le specifiche fornite potrebbero non risultare esaustive o completamente definite. Ogni funzionalità aggiunta o raffinata, anche tramite l'interazione con il committente o con gli utenti finali del sito, sarà adeguatamente valutata. Tutte le scelte progettuali vanno comunque discusse e motivate.

Il progetto, svolto secondo le linee guida date dalle specifiche, dovrà essere consegnato nella forma di un sito web completamente funzionante, i cui contenuti e le cui caratteristiche saranno valutati in sede d'esame. Le parti della specifica marcate come *opzionali*, se omesse, non renderanno il progetto insufficiente ma non gli permetteranno comunque di raggiungere il massimo dei voti. Nel caso si decida di realizzarle, non sarà necessario che siano perfette o complete, ma che dimostrino chiaramente il vostro impegno nell'affrontare una tematica avanzata.

La documentazione (**in formato elettronico** ) che accompagna il progetto **deve** contenere almeno le seguenti informazioni:

* Indicazione delle dipendenze software (di quali librerie avete bisogno dal lato server e client?).
* Indicazione delle funzionalità realizzate e di quelle eventualmente non realizzate. Descrizione dettagliata delle eventuali funzionalità extra o opzionali inserite nel progetto.
* Diagramma che illustra la struttura e la navigabilità del sito.
* Schema relazionale della base di dati (se presente).
* Descrizione analitica del layout del sito, con indicazione delle sue principali componenti statiche/dinamiche.
* Descrizione delle eventuali tecnologie avanzate (linguaggi, framework, plugin, librerie, ...) utilizzate, del motivo per cui sono state adottate e del contributo effettivo che hanno dato alla realizzazione del progetto.
* Descrizione di *eventuali* problemi riscontrati nella fruizione del sito su browser differenti, lista dei browser compatibili.
* Screenshot delle pagine più importanti del sito (*opzionale*).

Nel caso di gruppi di lavoro composti da più componenti, *il contributo effettivo offerto da ciascun componente* alla realizzazione finale **deve** essere descritto nella documentazione (indicando, ad esempio, chi si è dedicato prevalentemente alla programmazione server, chi ha realizzato il layout, chi ha programmato lato client, ecc.). In sede di esame, i responsabili potranno essere chiamati a riferire sugli aspetti loro delegati.

### Valutazione del Progetto

Nel valutare il progetto consegnato saranno prese in considerazione le seguenti caratteristiche (in ordine di importanza):

1. Rispetto delle specifiche.
2. Correttezza tecnica.
3. Chiarezza e correttezza organizzativa dei contenuti.
4. Accessibilità e conformità agli standard.
5. Uso appropriato di contenuti statici e dinamici.
6. Qualità del design.
7. Adeguatezza della documentazione.

A questa valutazione si aggiungerà quella generale derivata dalla discussione del progetto in sede d'esame.

### Ulteriori Informazioni

Questa specifica è disponibile in formato PDF sulla pagina web del corso di Web Engineering, all'indirizzo http://people.disim.univaq.it/dellapenna. Ulteriori informazioni e chiarimenti sulle specifiche possono essere richiesti direttamente via email all'indirizzo giuseppe.dellapenna@univaq.it.

Si ricorda che i progetti vanno svolti in *piccoli* gruppi (tre persone è il numero consigliato). Eccezioni a questa regola andranno concordate direttamente col docente.

An English translation of this project specification is also available on the teacher's website (http://people.disim.univaq.it/dellapenna). To access it, open the didactic page for this course, select "English version", and go to the projects listing at the page bottom. If the translation is not there, ask the teacher to publish it 😄
