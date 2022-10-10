# Corso di Web Engineering
*Progetti A.A. 2012/2013* - Specifica 2

## Progetto "MeetingPlanner"

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

Il sito *MeetingPlanner* rappresenta un semplice sistema per organizzare riunioni.

Il sito sarà accessibile a tre tipologie di utenza: amministratori, organizzatori e partecipanti. I partecipanti, come vedremo, non saranno utenti registrati nel sistema, ma avranno la possibilità di accedere a delle parti specifiche dello stesso *su invito* e per un periodo di tempo limitato.

Il database del sito conterrà informazioni su tutte le riunioni in via di definizione e su quelle fissate in maniera definitiva. Il database, inoltre, conterrà una lista di sale riunioni disponibili. A ciascuna sala andranno associati il nome, l'ubicazione, la capienza e una serie di attrezzature, scelte tra una lista predefinita (ad es. proiettore di lucidi, aria condizionata, impianto microfonico, ecc.).

Gli organizzatori potranno creare delle richieste di riunione specificando quando e dove la riunione potrebbe svolgersi e invitando una serie di partecipanti. Questi ultimi riceveranno l'invito via email e potranno usare il link presente nell'invito stesso per connettersi e dichiarare la propria disponibilità. L'organizzatore, viste le preferenze degli invitati, fisserà quindi la riunione definitiva e il sistema provvederà a darne segnalazione a tutti i partecipanti.

Di seguito sono illustrati schematicamente i contenuti e le
funzionalità minime che dovrebbero essere inseriti nel sito. Ovviamente, ogni
ulteriore raffinamento o arricchimento di queste specifiche aumenterà il valore
del progetto.
* La homepage del sito non dovrà presentare informazioni particolari: è sufficiente che permetta il login dell'amministratore e degli organizzatori registrati. Il resto del sito non deve essere accessibile agli utenti anonimi.
* La definizione di nuovi amministratori e organizzatori sarà di esclusiva competenza degli amministratori (andrà quindi previsto un amministratore predefinito per inizializzare il sistema).
* Gli amministratori potranno definire e modificare le sale riunioni disponibili, con le caratteristiche viste sopra.
* Un organizzatore potrà creare degli *inviti a riunione* specificando una descrizione della riunione stessa e indicando la lista dei partecipanti, con nome, cognome e indirizzo email. Dovranno essere inoltre allegate all'invito una serie di date, intervalli orari e corrispondenti luoghi ammissibili per la riunione, ad esempio "3/4/2014 dalle 15 alle 18 in sala riunioni 2, oppure 7/6/2015 dalle 9.30 alle 13.30 in via Garibaldi 12".
* L'organizzatore potrà chiedere al sistema di verificare la disponibilità, in una certa data/ora, di una sala riunioni dotata delle attrezzature desiderate. In questo caso il sistema, in base ai dati in suo possesso, indicherà all'organizzatore se e quali sale riunioni libere abbiano le caratteristiche richieste (compresa una capienza compatibile col numero di partecipanti invitati). L'organizzatore potrà quindi scegliere una delle proposte del sistema come luogo per la riunione nella data/ora corrispondente. In ogni caso, l'organizzatore non sarà vincolato, nella scelta del luogo della riunione, a specificare una delle sale riunioni gestite da sistema, ma potrà liberamente indicare qualsiasi altro luogo o indirizzo.
* Agli inviti a riunione potranno essere opzionalmente allegati uno o più file in formato testo o PDF, che l'organizzatore potrà caricare nel sistema.
* Dopo aver completato la definizione di un invito a riunione, l'organizzatore potrà chiedere al sistema di inviare per email gli inviti così definiti a tutti i partecipanti. *Suggerimento*: nella versione "giocattolo" di questa applicazione, potrete non realizzare veramente l'invio delle email e, ad esempio, stamparne solo il testo a video.
* Le email inviate ai potenziali partecipanti dovranno contenere la descrizione della riunione, il nome del suo organizzatore e un link da cliccare per esprimere la propria disponibilità alla partecipazione. Questo link, generato automaticamente, dovrà contenere i dati (ad esempio come parametri di una *query string* ) necessari al sistema per riconoscere la riunione in oggetto e l'utente invitato. *Suggerimento*: invece di includere direttamente dati come l'ID della riunione o il nome dell'invitato all'interno del link, rendendolo così molto fragile e soggetto a contraffazioni o manipolazioni, è più opportuno inserirvi una stringa alfanumerica univoca generata casualmente (del tipo http://\<URL_base_della_web_application\>/invite?ticket=AJCH5E35NCH36I45GS), alla quale nel database del sito vengano associate tutte le informazioni necessarie.
* All'utente invitato a una riunione, accedendo al sistema tramite il link inviatogli, verrà presentato un prospetto di tutte le combinazioni di data/ora/luogo possibili. L'utente potrà quindi spuntare le proposte per le quali si dichiara disponibile ed opzionalmente lasciare una nota testuale. L'utente potrà, inoltre, scaricare e consultare i documenti eventualmente allegati all'invito a riunione. Una volta espresse le proprie preferenze, l'utente non avrà più modo di modificarle, e il link usato per accedere al sistema non sarà più valido.
* L'organizzatore, in ogni momento, potrà controllare quali invitati hanno risposto e come. Il sistema, inoltre, calcolerà e mostrerà all'organizzatore le combinazioni di data/ora/luogo che sono compatibili con tutte le disponibilità comunicate dai partecipanti (se possibile) o con la maggioranza di essi.
* L'organizzatore potrà, infine, scegliere una data definitiva tra quelle proposte, fissando la riunione i cui dettagli verranno registrati nel sistema (questo sarà molto utile nel caso in cui il luogo scelto sia una delle sale riunioni, perché in questo modo il sistema potrà sapere che la sala rimarrà occupata in quel periodo di tempo)
* Nel momento in cui una riunione verrà definitivamente fissata, il sistema invierà una email di conferma a tutti i partecipanti che si erano dichiarati disponibili per la data/ora/luogo prescelti, e una email di scuse a tutti quelli che non potranno partecipare.

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
