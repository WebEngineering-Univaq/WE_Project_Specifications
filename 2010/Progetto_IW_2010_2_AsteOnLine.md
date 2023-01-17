# Corso di Web Engineering
*Progetti A.A. 2010/2011* - Specifica 2

## Progetto "AsteOnLine"

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

Il sito *AsteOnLine* rappresenta un semplice sistema di aste, in cui dei venditori mettono all'asta dei beni e dei compratori fanno delle offerte per acquistarli.

Gli oggetti messi all'asta avranno ciascuno una pagina dedicata sul sito, che ne riporterà le informazioni essenziali, cioè nome, descrizione, stato di conservazione (nuovo, usato, danneggiato, ecc.), eventuali link informativi e una foto opzionale. Una serie di *tag,* cioè parole o frasi brevi, potranno essere associati agli oggetti per meglio classificarli e facilitarne la ricerca. Infine, la pagina relativa a un oggetto dovrà mostrare lo stato dell'asta associata: data di inizio e fine della messa all'asta, modalità di consegna (spedizione postale, corriere, ecc.) e pagamento (contrassegno, carta di credito, bonifico, ecc.), prezzo base e rilancio minimo.

Il sito prevede due tipologie di utenza: utenti *anonimi* e utenti *registrati*. Andranno quindi predisposte opportune funzionalità di registrazione e di login. Gli utenti anonimi potranno solo effettuare ricerche sul sito, mentre quelli registrati potranno agire sia da venditori che da compratori.

Di seguito sono illustrati schematicamente i contenuti e le
funzionalità minime che dovrebbero essere inseriti nel sito. Ovviamente, ogni
ulteriore raffinamento o arricchimento di queste specifiche aumenterà il valore
del progetto.
* Tutti gli utenti potranno ricercare oggetti di loro interesse in base a: (1) parole o frasi contenute nel nome o nella descrizione, (2) i *tag* associati, (3) il venditore, (4) il prezzo (base). La completezza e la versatilità della funzione di ricerca, essenziale per un sito come questo, è lasciata all'iniziativa dei realizzatori. I risultati della ricerca dovranno essere presentati elencando gli oggetti trovati con nome, venditore e data di inizio/chiusura asta. Cliccando su ciascun oggetto si aprirà la corrispondente pagina descrittiva.

* Nella pagina descrittiva di un oggetto dovrà essere possibile cliccare sul nome del venditore per visualizzare il relativo profilo (dati anagrafici, indirizzo email, ecc.) e la lista degli eventuali altri oggetti che ha posto all'asta.

* Nella pagina descrittiva di un oggetto, e in generale ovunque compaiano dei *tag*, dovrà essere possibile cliccare su uno di essi avviando automaticamente una ricerca di tutti gli oggetti associati.

* Ogni utente registrato potrà inserire nuovi oggetti da mettere all'asta, specificandone i dati descritti sopra, modificare propri oggetti già inseriti, ma solo entro la data di inizio dell'asta, e ritirare (cancellare) propri oggetti anche durante l'asta.

* Ogni utente registrato potrà visionare la lista degli oggetti che ha messo all'asta e, per quelli la cui asta è correntemente in corso, sapere quante sono state le offerte, il tempo rimanente prima della chiusura dell'asta, nonché la data, l'utente e l'ammontare relativi all'ultima offerta.

* Ogni utente registrato potrà partecipare a un numero arbitrario di aste attive, facendo un'offerta che sia maggiore o uguale alla relativa base d'asta e aumenti l'eventuale offerta precedente di una somma almeno corrispondente al rilancio minimo.

* Ogni utente registrato potrà visionare la lista degli oggetti per cui ha fatto un'offerta, unitamente al tempo rimanente prima della fine dell'asta corrispondente. Nel caso ci sia stata una successiva offerta superiore alla sua, il sistema ne mostrerà l'ammontare dandogli la possibilità di effettuare un rilancio.

* Una volta raggiunto il termine dell'asta, l'oggetto corrispondente non sarà più visibile nelle ricerche. L'offerente maggiore riceverà una notifica (sulla homepage dopo la login e *opzionalmente* per email) della sua vittoria, con allegate le informazioni di pagamento. Allo stesso modo, al venditore verrà notificato l'avvenuto acquisto con i dati del compratore. Nel caso in cui un oggetto non abbia ricevuto alcuna offerta, invece, alla chiusura dell'asta il venditore potrà modificarne le informazioni ed eventualmente stabilire le date di una nuova asta.

* La homepage del sito dovrà mostrare alcune informazioni a carattere generale, ad esempio gli ultimi oggetti messi all'asta, quelli con rilanci più alti, ecc..

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

Questa specifica è disponibile nel repository del corso di Web Engineering, all'indirizzo https://github.com/WebEngineering-Univaq/WE_Project_Specifications. Ulteriori informazioni e chiarimenti sulle specifiche possono essere richiesti direttamente via email all'indirizzo giuseppe.dellapenna@univaq.it.

Si ricorda che i progetti vanno svolti in *piccoli* gruppi (tre persone è il numero consigliato). Eccezioni a questa regola andranno concordate direttamente col docente.

An English translation of this project specification is also available in the course repository (https://github.com/WebEngineering-Univaq/WE_Project_Specifications). If the translation is not there, ask the teacher to publish it 😄
