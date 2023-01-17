# Corso di Web Engineering
*Progetti A.A. 2011/2012* - Specifica 2

## Progetto "SondaggiOnLine"

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

Il sito Sondaggi*OnLine* rappresenta un semplice sistema per condurre sondaggi tramite web.

Ciascun sondaggio, definibile dall'amministratore del sistema, avrà un titolo e una descrizione testuale, e sarà costituito da una sequenza arbitraria di quesiti. Un quesito sarà caratterizzato da un testo descrittivo, e potrà prevedere quattro tipologie di risposta:

1. un numero (che potrebbe ad esempio rappresentare un "livello") all'interno da un determinato intervallo (ad esempio "indicare la qualità del prodotto, da 0 (orribile) a 10 (meraviglioso)");

2. una risposta singola, scelta tra una serie di possibili risposte predefinite (ad esempio: "quale di questi cibi ti piace di più? (selezionare una sola risposta): a. il gelato, b. la pizza");

3. più risposte selezionate tra una serie di possibili risposte predefinite (ad esempio: "quale di questi cibi ti piace? (selezionare una o più risposte): a. il gelato, b. la pizza"),

4. una risposta testuale libera, con una lunghezza massima (in caratteri, ad esempio "inserire un commento, max 500 caratteri" ).

Supporremo che il sistema disponga di una base di dati precostituita composta da dati anagrafici e indirizzi email della popolazione che può essere sottoposta a sondaggio. I soggetti selezionati per la compilazione di un particolare sondaggio potranno accedere al questionario tramite un link specifico, che sarà inviato loro per email. Questo link sarà generato automaticamente e conterrà una chiave (ad esempio una serie di numeri casuali) univoca che il sistema dovrà identificare come l'associazione tra il soggetto e il sondaggio (ad esempio http://mioserver.com/poll?accesskey=JD83MG92Y6MSK4). Cliccando sul link, quindi, verrà automaticamente mostrato nel browser il sondaggio "intestato" al soggetto corrispondente.

Di seguito sono illustrati schematicamente i contenuti e le
funzionalità minime che dovrebbero essere inseriti nel sito. Ovviamente, ogni
ulteriore raffinamento o arricchimento di queste specifiche aumenterà il valore
del progetto.
* La homepage del sito non dovrà presentare informazioni particolari: è sufficiente che permetta il login dell'amministratore. Il resto del sito deve essere inaccessibile agli utenti anonimi.

* L'amministratore potrà definire i sondaggi e modificarli, ma solo se non sono già in fase di compilazione. Ciascun quesito dovrà avere la struttura descritta in precedenza, e potrà essere indicato come obbligatorio o opzionale. I quesiti saranno suddivisi in gruppi, ciascuno dei quali avrà una sua descrizione testuale introduttiva.

* Dovrà essere possibile definire semplici regole di correlazione tra quesiti, nel seguente modo. Per ciascuna risposta di un quesito a risposta singola (tipo 2), sarà possibile specificare una sequenza di quesiti (tra quelli già inseriti nello stesso sondaggio) che devono essere compilati solo nel caso in cui quella risposta sia scelta (ad esempio, il campo di input "Nazione di nascita" è obbligatorio, ma deve essere compilato solo se si risponde "No" alla domanda "Siete italiani?").

* Quando l'amministratore del sistema deciderà di attivare un dato sondaggio, dovrà anche indicare la dimensione del campione a cui sottoporlo, il sesso (maschile, femminile o entrambi) e l'intervallo di età. Verrà inoltre fissato un intervallo di date all'interno del quale il sondaggio dovrà essere compilato. Il sistema selezionerà quindi casualmente dalla sua base di dati il numero richiesto di soggetti aventi le caratteristiche specificate e invierà loro un'email (*potete simulare questo invio, non è necessario che lo facciate veramente!*) indicando il titolo del sondaggio, la sua descrizione, le date in cui potrà essere compilato e fornendo il link per la sua compilazione, generato come descritto sopra.

* All'utente, che accederà al sito tramite il link in suo possesso, il sondaggio andrà presentato opportunamente formattato, *opzionalmente* prevedendone la suddivisione su più pagine. Sarà necessario scegliere i controlli HTML più opportuni per garantire l'input richiesto dal tipo di quesito, cercando di minimizzare le possibilità di errore. E' possibile prevedere controlli avanzati lato client, ma gli stessi controlli dovranno essere sempre ripetuti sul server. Per quel che riguarda le regole di correlazione tra quesiti discusse sopra, queste dovranno almeno essere utilizzate per generare automaticamente opportuni avvertimenti testuali (ad esempio, "se rispondete Y a questa domanda, allora non dovrete rispondere alla domanda N").

* Una volta terminata la compilazione, l'utente invierà le sue risposte al sistema. Quest'ultimo non permetterà di proseguire con la sottomissione del modulo nel caso in cui si verifichino errori: ad esempio, input non corretto rispetto ai vincoli imposti dal quesito, quesito obbligatorio senza risposta, ecc. Il server dovrà anche implementare le verifiche corrispondenti alle regole di correlazione, ad esempio ignorando il valore di una risposta (quindi omettendo anche gli altri controlli su di essa: obbligatorietà, ecc.) se una regola la disabilita (con riferimento all'esempio fatto in precedenza, il sistema non controllerà che il campo "Nazione di nascita" sia stato compilato, sebbene obbligatorio, e non ne salverà il valore nel caso in cui si sia risposto "Sì" alla domanda "Siete italiani?").

* Nel caso in cui le risposte fornite dall'utente siano coerenti con le regole di compilazione, il sistema provvederà a registrarle e a disabilitare l'accesso al sondaggio tramite il link originariamente fornito all'utente, in modo che non possa più compilarlo.

* L'amministratore potrà, in ogni momento, leggere una serie di statistiche ricavate da ciascun sondaggio. E' possibile inserire ogni tipo di statistica sensata, ma le seguenti dovranno necessariamente essere realizzate:

(a) numero e percentuale (rispetto al campione) di utenti che hanno risposto al sondaggio;

(b) per le domande a risposta multipla (tipo 2 e 3), e per quelle a risposta numerica (tipo 1), distribuzione percentuale delle risposte degli utenti rispetto a ciascuna delle opzioni proposte;

(c) per le domande a risposta testuale libera (tipo 4), lunghezza media delle stesse;

(d) per ogni domanda non obbligatoria, percentuale degli utenti che hanno deciso di rispondere.

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
