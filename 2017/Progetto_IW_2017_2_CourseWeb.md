# Corso di Web Engineering
*Progetti A.A. 2017/2018* - Specifica 2

## Progetto "CourseWeb"

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

*Dopo un decennio passato a cercare di inventarsi il modo migliore per organizzare online le informazioni sugli insegnamenti universitari, incrociando i desiderata di studenti, docenti, personale amministrativo e delle varie normative al riguardo, il vostro docente ha (momentaneamente) esaurito le idee, e quindi ha deciso di chiedere a voi di realizzare il vostro "sito della didattica ideale", nella speranza di trovare nuova ispirazione* *J*

Il sito *CourseWeb* rappresenta un catalogo di corsi universitari online, semplificato ma rispondente ai principali requisiti di trasparenza e completezza necessari per questo tipo di sito.

Per prima cosa, il sito dovrà supportare la **pubblicazione bilingue** (italiano e inglese) di tutti i contenuti, requisito necessario per l'internazionalizzazione. Dovrete quindi avere, per ogni vista, almeno due template (uno in italiano e uno in inglese), progettare un sistema per inserire le informazioni in entrambe le lingue nel back-office e uno per selezionare quale lingua visualizzare nel front-office (*opzionalmente*, in assenza del contenuto in una lingua, verrà sempre utilizzata l'altra lingua a disposizione).

Ciascun corso dovrà essere necessariamente associato alle informazioni che seguono. Qualunque altro extra, derivante dalla vostra esperienza diretta, sarà apprezzato e magari di ispirazione per il futuro.

* Dati di base: nome, codice, settore scientifico-disciplinare (SSD, ad esempio INF/01), lingua, semestre
* Lista docenti titolari
* Descrizione del corso: prerequisiti, obiettivi di apprendimento, modalità d'esame, modalità di insegnamento, sillabo/programma analitico (suddiviso per punti, in generale un punto per ciascun credito)
* Libri di testo (autore, titolo, volume, anno, editore, link web se disponibile)
* Relazioni con altri insegnamenti: corsi propedeutici, corsi mutuati, moduli (nel caso di corsi integrati)
* Collegamenti esterni (link): homepage del corso, risorse esterne, forum/eLearning
* Note (ogni dettaglio per il quale non è prevista una voce specifica)

*Opzionalmente* , gli *obiettivi di apprendimento* citati nella lista possono essere strutturati secondo i cosiddetti *descrittori di Dublino* , richiesti dai processi di standardizzazione europei. I descrittori richiedono che gli obiettivi del corso siano descritti sulla base dei risultati raggiunti in cinque aree: *Knowledge* (quali conoscenze sono acquisite con il corso?), *Application* (come e dove sono applicabili le conoscenze derivanti dal corso?), *Evaluation* (se e in che modo le conoscenze acquisite possono aiutare nel valutare, giudicare, comparare...?), *Communication* (se e in che modo gli studenti possono trasmettere la conoscenza acquisita?), *Lifelong learning skills* (il corso fornisce strumenti per continuare ad apprendere determinati argomenti?).

Infine, anche le informazioni che seguono, pur necessarie in un sistema realistico, nel nostro progetto saranno *opzionali*: più ne aggiungete, più il vostro progetto avrà valore.

* Informazioni sull'erogazione: lista dei corsi di laurea/curriculum per il quale il corso è fruibile, con indicazione del suo valore in crediti (CFU) e della rispettiva tipologia (A, B, C, D, F)
* Materiale: una lista di elementi (con nome, descrizione e dimensioni) scaricabili dal sito (come i PDF)

Per poter creare una "guida virtuale" sarà necessario che **il sistema raccolga tutte queste informazioni anno per anno** . Ciò significa che dovrete **predisporre un sistema col quale i dati appena esposti siano associati a un anno accademico**, e che ne possano quindi esistere diverse copie, per differenti anni accademici.

Di seguito sono illustrati schematicamente i contenuti e le
funzionalità minime che dovrebbero essere inseriti nel sito. Ovviamente, ogni
ulteriore raffinamento o arricchimento di queste specifiche aumenterà il valore
del progetto.
* Il sistema dovrà prevedere tre tipologie di utenza: *anonimo* , *docente* e *amministratore*. Solo gli amministratori potranno registrare nuovi utenti e assegnare loro un tipo.

* Tutti gli utenti, anche*anonimi,* potranno visualizzare la lista completa dei corsi, eventualmente filtrata per nome (anche parziale), codice, SSD, semestre, docente, lingua e corsi di laurea per i quali è disponibile (se avete inserito anche quest'ultima informazione). Cliccando su un corso si visualizzerà la sua scheda completa.

* Ovviamente, la scheda del corso andrà curata nei minimi dettagli, per rendere più chiara possibile la presentazione delle informazioni a esso relative. È possibile suddividere la scheda su più pagine, ricordando però che le informazioni essenziali devono essere raggiungibili con un numero basso di click.

* Gli amministratori del sito saranno gli unici a poter creare i corsi (inserendo almeno le informazioni essenziali: nome e codice) e assegnare loro i titolari.

* I docenti potranno inserire e modificare tutte le informazioni inerenti i soli corsi loro assegnati, mentre ovviamente gli amministratori potranno intervenire su tutti i corsi.

* Il back-office per i docenti dovrà essere ugualmente molto curato e intuitivo, considerato che anche l'utenza di questo lato del sistema sarà ampia e variegata. Sarà utile predisporre help contestuali che chiariscano il significato dei vari campi da valorizzare, ed eventualmente suddividere la compilazione della scheda di un corso in segmenti logici, stile *wizard*. Ove possibile (ad esempio nella selezione dei corsi in relazione, delle lingue, dei semestri, dei SSD, delle tipologie di credito, ecc.) si prevedano sempre campi con compilazione assistita o guidata.

* Il sito disporrà di un *log* in cui dovranno essere annotate tutte le operazioni svolte tramite il back-office (ad esempio "l'utente X ha modificato le informazioni del corso Y": decidete voi quale livello di dettaglio raggiungere in queste *entry*).

* Infine, per realizzare la "guida virtuale" introdotta più in alto, quello che ci si aspetta dal sito è che:

  1. le informazioni presentate nella scheda di ciascun corso siano, di default, quelle riferite all'ultimo anno accademico (che deve essere evidenziato nella scheda) per il quale il corso è stato aggiornato.
  2. all'utente sia offerta la possibilità di visionare la scheda di un corso relativa a uno degli altri anni accademici per i quali le informazioni sono disponibili (ad esempio tramite dei controlli sulla scheda del corso, oppure con opportuni filtri sull'elenco corsi generale)
  3. nel back office, le informazioni inserite o modificate dai docenti siano sempre quelle relative all'anno accademico corrente. Quando un docente cerca di modificare le informazioni di un corso e queste non sono già presenti per l'anno accademico corrente, verranno automaticamente copiate, come base, quelle dell'anno più prossimo, se presenti. *Opzionalmente*, gli amministratori potranno modificare anche le informazioni relative ad altri anni accademici.

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
