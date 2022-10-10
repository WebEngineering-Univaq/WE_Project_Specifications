# Corso di Web Engineering
*Progetti A.A. 2011/2012* - Specifica 1

## Progetto "TestOnLine"

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

Il sito Test*OnLine* rappresenta un semplice sistema web per la definizione, la somministrazione e la valutazione di test.

Ciascun test gestito dal nostro sistema consisterà in una serie di quesiti a risposta multipla, con una sola risposta esatta e un numero arbitrario di risposte scorrette. Un quesito sarà a sua volta composto da un testo illustrativo (obbligatorio, *opzionalmente* contenente codice HTML di formattazione semplice, come i tag \<b\> e \<i\>) e da una serie opzionale di immagini illustrative (che potrebbero rappresentare, ad esempio, equazioni, grafi, ecc.), mentre le possibili risposte saranno composte da soli blocchi di testo, oltre a un flag che ne indichi l'esattezza.

Il sistema prevederà tre tipi di utenza: il coordinatore, il docente e lo studente.

Di seguito sono illustrati schematicamente i contenuti e le
funzionalità minime che dovrebbero essere inseriti nel sito. Ovviamente, ogni
ulteriore raffinamento o arricchimento di queste specifiche aumenterà il valore
del progetto.
* I docenti potranno inserire nuovi quesiti (o modificare i quesiti già inseriti), associandoli a uno dei settori didattici di riferimento preimpostati nel sistema, ad esempio "Reti di Calcolatori", "Tecnologie del Web" o "Algoritmi". Per ciascun quesito dovranno inoltre fornire una valutazione del livello di difficoltà, in scala 1-5, nell'ambito del settore prescelto, e ovviamente un insieme di risposte, tra cui almeno una dovrà essere indicata come corretta.

* I coordinatori potranno gestire la lista dei settori didattici disponibili, accreditare nuovi docenti (cioè eseguirne la registrazione sul sistema), e creare i test.

* Per creare i test, i coordinatori assegneranno loro un nome, il periodo di erogazione (cioè l'intervallo di giorni all'interno del quale potrà essere sostenuto) e le composizione, secondo una delle seguenti modalità:

  1. indicando una serie di docenti e, per ciascuno di essi, uno dei settori didattici per i quali hanno predisposto dei quesiti, un livello di difficoltà e un numero di quesiti (ad esempio: 5 quesiti di livello 3 sulle Reti di Calcolatori redatti dal prof. X, 12 quesiti di livello 5 sulle Tecnologie del Web redatti dal prof. Y);
  2. indicando solamente una serie di settori didattici con associato un livello di difficoltà e un numero di quesiti (ad esempio 5 quesiti di livello 3 sulle Reti di Calcolatori, 12 quesiti di livello 5 sulle Tecnologie del Web);

  In base alle scelte del coordinatore, il sistema dovrà verificare che un test della composizione data possa essere effettivamente generato (cioè se il numero e la tipologia di quesiti richiesti è effettivamente disponibile.).
* La durata di un test sarà calcolata automaticamente, in base alla sua composizione, secondo la formula ![](Progetti%20IW%202012%20-1_file/image001.gif), dove *T* è l'insieme dei quesiti componenti il test, *L(q)* è il livello di difficoltà del quesito *q* e *K(l)* restituisce il tempo (in minuti) concesso per risolvere un quesito di livello *l* (scelto da voi!).

* La homepage del sito dovrà mostrare tutti i test in programma, evidenziando quelli che si terranno a breve. Ciascun test sarà descritto indicando il numero di quesiti contenuti, con il settore didattico ed eventualmente il nome del docente di riferimento, nonché dalla sua durata complessiva.

* Gli studenti potranno registrarsi nel sistema fornendo le proprie credenziali (tra le quali è richiesto un indirizzo email e un numero di matricola), e poi iscriversi ai test in programma (non sarà ovviamente possibile iscriversi più di una volta allo stesso test, o iscriversi a test che si sono già tenuti).

* In qualunque momento nell'intervallo di validità di un test, uno studente iscritto potrà connettersi, autenticarsi e sostenerlo.

* Nel momento in cui uno studente richiederà di sostenere un test, il sistema ne genererà *un'istanza casuale* nel modo che segue:

  1. nel caso in cui il test sia stato definito come al punto (1), il sistema selezionerà, per ciascuna tupla (*docente* , *settore* , *livello* , *numero* ) presente nella definizione del test stesso, un *numero* di quesiti (scelti a caso) tra quelli inseriti dal *docente* per quello specifico *settore* con il *livello* di difficoltà specificato;
  2. nel caso in cui invece il test sia stato definito come al punto (2), il sistema selezionerà, per ciascuna tupla (*settore* , *livello* , *numero* ) presente nella definizione del test stesso, un *numero* di quesiti (scelti a caso) tra quelli inseriti da tutti i docenti per quello specifico *settore* con il *livello* di difficoltà specificato.

  In entrambi i casi, infine, il sistema selezionerà *casualmente* , tra le risposte possibili di ciascun quesito così prescelto, *tre risposte*, tra cui figuri sempre anche quella corretta.
* Il test verrà presentato allo studente come sequenza di quesiti, suddivisi per settore, con le risposte associate tra cui effettuare una scelta. Una volta avviato il test, lo studente potrà scegliere le risposte e poi sottometterle (tutte insieme) al sistema per la valutazione.

* Se le risposte saranno inviate dopo la durata massima consentita (calcolata come visto sopra), il sistema rifiuterà il test, che non potrà essere più sostenuto. Se invece le risposte saranno fornite nei termini previsti, il sistema mostrerà all'utente un riepilogo delle domande, indicando la sua risposta e quella effettivamente esatta. I quesiti in cui la risposta data risulta scorretta saranno evidenziati. Alla fine del test, verrà riportato il punteggio finale calcolato assegnando un punto a ciascuna risposta esatta, -1 a ciascuna risposta errata e zero a ciascuna risposta non data.

* Il voto dello studente per il particolare test sarà registrato nella base di dati del sistema, insieme al tempo impiegato per risolverlo e alla risposta data a ciascun quesito.

* Il coordinatore potrà consultare in qualsiasi momento l'elenco dei risultati di ciascun test, corredato da qualche statistica significativa (ad esempio media punteggi, tempo medio di risoluzione del test, ecc.). Sarà inoltre possibile consultare voti e statistiche relative a tutti i test sostenuti da un particolare studente.

* *Opzionalmente*, è possibile fare in modo che ciascun docente possa visualizzare delle statistiche sui propri quesiti (ad esempio, numero di volte in cui il quesito è stato utilizzato in un test e numero di persone che hanno scelto la risposta giusta).

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
