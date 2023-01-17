# Corso di Web Engineering
*Progetti A.A. 2008/2009* - Specifica 2

## Progetto "WebJournal"

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

Il sito *WebJournal* rappresenta un semplice giornale pubblicato online. Il giornale sarà diviso in *sezioni* (cronaca nera, cronaca rosa, spettacolo, sport, ecc.) e la sua prima pagina corrisponderà alla homepage del sito.

Gli articoli presenti sul nostro giornale online dovranno contenere, oltre al loro titolo, al testo vero e proprio e alla lista degli autori, una serie di informazioni: l'occhiello (riga di "lancio" mostrata solitamente sopra il titolo), il sommario (una o più righe "riassuntive" poste solitamente sotto il titolo), la data, la sezione (del giornale) di pubblicazione, il livello di importanza della notizia (in scala 1...10) e una serie di parole o frasi chiave, dette *tag*.

Di seguito sono illustrati schematicamente i contenuti e le
funzionalità minime che dovrebbero essere inseriti nel sito. Ovviamente, ogni
ulteriore raffinamento o arricchimento di queste specifiche aumenterà il valore
del progetto.
* Il sito dovrà prevedere due tipi di visualizzazione per le notizie: *compatta* , contenente cioè solo data, occhiello, titolo e sommario, e *completa* , in cui tutte le informazioni disponibili sono visibili con opportuna formattazione (il più possibile simile a quella di un giornale cartaceo). Nel caso di articoli molto lunghi si potrà prevedere la loro paginazione. Cliccando su un articolo in modalità compatta, ovunque questo venga visualizzato, dovrà essere possibile aprire una pagina specifica che mostri l'articolo stesso in modalità completa. *Opzionalmente*, questa stessa pagina potrà offrire la possibilità di scaricare il testo dell'articolo come testo semplice (formattato con soli spazi e ritorni a capo, niente HTML).

* La homepage del sito, come già accennato, corrisponderà alla prima pagina del giornale. Su questa pagina andranno mostrate, con un layout opportuno che tenga conto dell'importanza e della sezione di appartenenza di ciascuna notizia, tutte le notizie odierne la cui importanza sia maggiore di una certa soglia (che fisseremo a 7), in modalità compatta.

* Dovrà essere poi possibile accedere a pagine specifiche che mostrino solo le notizie odierne (di qualunque importanza) appartenenti a ciascuna sezione del giornale (ad es. la pagina dello spettacolo, dello sport, ecc.). La formattazione di queste notizie dovrà seguire criteri simili a quelli usati nella prima pagina.

* Dovrà essere prevista una sezione archivio, a partire dalla quale sia possibile consultare la prima pagina e le pagine di sezione relative al giornale di qualsiasi giorno. In altre parole, dovrà essere possibile ricostruire e mostrare la prima pagina o, ad esempio, la pagina della cronaca nera corrispondenti a un giorno specificato dall'utente.

* Gli utenti avranno la possibilità di ricercare articoli per autore, data di pubblicazione, *tag* (specificandone uno o più) o specificando delle parole da cercare all'interno del testo dell'articolo (ricerca *fulltext* ). In risposta il sito mostrerà una lista di tutti gli articoli coerenti con i criteri specificati, in forma compatta (e quindi cliccabile, come descritto sopra). *Opzionalmente* , è possibile fare in modo che, in qualunque parte del sito in cui siano visualizzati dei *tag* (ad esempio nelle pagine di visualizzazione completa degli articoli), questi possano essere cliccati avviando la corrispondente ricerca per *tag*.

* Il sito dovrà prevedere una semplice procedura di registrazione per gli utenti.

* Gli utenti *registrati* nel sistema avranno la possibilità, a partire dalla pagina di visualizzazione completa di un articolo, di lasciare un loro commento. I commenti inseriti potranno essere mostrati unitamente all'articolo o in una sotto-pagina apposita.

* Gli utenti registrati potranno, a partire dalla pagina di visualizzazione completa di un articolo, inserire nuovi *tag*, da associare alla notizia (ma non modificare quelli già esistenti).

* Il sito dovrà inoltre essere dotato di un opportuno *backoffice* che permetta di inserire e modificare gli articoli pubblicati.

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
