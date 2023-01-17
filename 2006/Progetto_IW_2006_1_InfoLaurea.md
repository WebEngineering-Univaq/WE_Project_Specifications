# Corso di Web Engineering
*Progetti A.A. 2006/2007* - Specifica 1

## Progetto "InfoLaurea"

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

Il sito *InfoLaurea* ha lo scopo di fornire agli studenti tutte le informazioni concernenti la laurea, guidandoli nei passi da compiere prima e dopo questo importante momento. Le informazioni necessarie a creare e popolare il sito potranno essere prelevate dalle varie fonti ufficiali (guida dello studente, sito di informatica, ecc.) o ottenute richiedendole al personale di riferimento (manager didattico, segreteria, docenti, ecc.).

Di seguito sono illustrati schematicamente i contenuti e le
funzionalità minime che dovrebbero essere inseriti nel sito. Ovviamente, ogni
ulteriore raffinamento o arricchimento di queste specifiche aumenterà il valore
del progetto.
* Il sito dovrà fornire tre tipologie di accesso: *pubblico* , *laureando* e *docente*. Gli utenti registrati potranno avvalersi di alcune funzionalità personalizzate, descritte di seguito. La registrazione dei laureandi dovrà effettuarsi comunicando i dati completi dello studente (compreso il numero di matricola).
* Un'area importante dovrà essere dedicata alle offerte di tesi, pubblicate dai singoli docenti (registrati) o dalle aziende (tramite i docenti). Le informazioni su ciascuna tesi dovranno includere l'area scientifica/insegnamento di riferimento, il relatore (ed eventualmente il responsabile aziendale), i tempi (alcune tesi sono offerte per un periodo limitato, altre vanno svolte in un periodo preciso) e i modi (in azienda, all'estero, ecc.) di realizzazione, il livello (base, specialistica), i prerequisiti richiesti e gli obiettivi da raggiungere. Per le tesi aziendali andranno specificate le condizioni dello stage. Dovrà essere presente un sistema di ricerca adeguato, che permetta di cercare tesi in base a parole chiave, materia, livello, ecc. I laureandi registrati, infine, potranno inserire un "profilo di tesi" e richiedere di essere avvisati automaticamente via email quando una tesi corrispondente viene inserita nel sistema.
* Per un'informazione completa e dettagliata, il sito dovrà permettere la navigazione in un estratto del regolamento del CdL in cui risultino le voci riguardanti la laurea (quando si può fare richiesta? Quali sono i prerequisiti? Quali sono le modalità di svolgimento?).
* Per quel che concerne la parte burocratica, invece, il sito dovrà presentare un calendario che specifichi quali operazioni effettuare, dove (segreteria, relatore, ecc.) e con quali tempi, sia prima che dopo la laurea (ad es. richiesta di ammissione alla seduta 4 mesi prima, consegna della bozza 15 giorni prima, richiesta per il rilascio del diploma di laurea, ecc.), e fornisca un accesso alla modulistica elettronica necessaria in ogni passo.
* Una sezione del sito dovrà poi contenere informazioni su come redigere la tesi: indicazioni tipografiche e di impaginazione (caratteri, margini, spaziature, modalità di rilegatura/stampa, ecc.), ma anche consigli generali di impostazione e forma dell'esposizione (non parlare in prima persona, evitare periodi troppo lunghi, citare i riferimenti, ecc.). Potranno anche essere forniti in download esempi di tesi (bozze reali o fittizie) e/o modelli in vari formati (Word, LaTeX, ecc.).
* Il sito dovrà ovviamente contenere una lista aggiornata delle sedute di laurea, in cui siano specificati i candidati, le commissioni, il calendario e le informazioni logistiche. Le informazioni di ogni seduta potranno essere completate con un'area contenente avvisi (ad es. spostamenti, variazioni di calendario, ecc.). Questi dati saranno inseriti nel sistema da un docente registrato tramite il backoffice del sito.
* Dovrà essere possibile inserire i voti finali dei laureati, che saranno accessibili solo ai docenti registrati, e potranno essere usati per generare statistiche di vario tipo (andamento per sessione, per anno accademico, per relatore, ecc.).
* I laureandi interessati, infine, potranno pubblicare online la versione elettronica della loro tesi, o un estratto delle stessa. Il sito offrirà un sistema di ricerca adeguato (per parole chiave, materia, ecc.) per permettere agli utenti di individuare le tesi di loro interesse e contattarne gli autori.
* Per completare le informazioni presenti sul sito sarà inoltre opportuno prevedere un'area pubblica di scambio informazioni a cui potranno accedere tutti gli utenti registrati.

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
