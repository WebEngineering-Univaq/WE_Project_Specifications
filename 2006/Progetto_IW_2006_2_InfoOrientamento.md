# Corso di Web Engineering
*Progetti A.A. 2006/2007* - Specifica 2

## Progetto "InfoOrientamento"

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

Il sito *InfoOrientamento* ha lo scopo di fornire un sistema completo per l'orientamento universitario degli studenti delle scuole superiori che intendono iscriversi al nostro CdL, nonché un aiuto gli studenti appena iscritti per adattarsi alla vista universitaria. Le informazioni necessarie a creare e popolare il sito potranno essere prelevate dalle varie fonti ufficiali (guida dello studente, sito di informatica, ecc.), da altri siti (previa opportuna autorizzazione, se necessaria) o ottenute richiedendole al personale di riferimento (manager didattico, segreteria, docenti, ecc.).

Di seguito sono illustrati schematicamente i contenuti e le
funzionalità minime che dovrebbero essere inseriti nel sito. Ovviamente, ogni
ulteriore raffinamento o arricchimento di queste specifiche aumenterà il valore
del progetto.
* La sezione di orientamento dovrà contenere un *percorso* che presenti, nella maniera più comprensibile e accattivante, i punti che seguono. Potrebbe anche essere utile differenziare i percorsi, o fornire informazioni selezionate, in base al tipo di scuola superiore frequentata dallo studente.
  1. Cos'è (e cosa non è!) l'informatica.
  2. Cosa significa studiare informatica.
  3. Quali sono i possibili sbocchi occupazionali.
  4. L'Università dell'Aquila (dov'è, quali servizi offre, ecc.).
  5. Il CdL in Informatica (com'è strutturato, quali lauree eroga, ecc.).
* Dovranno essere presenti informazioni sulle materie principali (*cosa dovrò studiare?* ), soprattutto quelle distribuite nei primi anni di corso ed obbligatorie, e su quelle più avanzate e interessanti (*cosa potrò imparare?*). Le informazioni potranno includere le descrizioni dei corsi, i sillabi, del materiale di esempio, ecc. Queste informazioni dovranno essere modificabili tramite il backoffice del sito o, dove possibile, prelevate automaticamente dal sito di Informatica.
* Una sezione importante del sito dovrà spiegare quali sono i prerequisiti necessari per accedere al CdL, ed eventualmente come potersi preparare all'iscrizione e all'eventuale test di ingresso. Per permettere agli utenti di autovalutarsi, potranno essere offerti dei brevi test online, che abbraccino argomenti di base sia matematici (ad esempio prelevati dai test di ingresso correnti) che informatici. Il test, una volta completato, potrà offrire utili informazioni sulle conoscenze già acquisite e su quelle da acquisire.
* Dal punto di vista burocratico, dovranno essere pubblicate le informazioni riguardanti tempi e modi di iscrizione, offrendo accesso diretto alla modulistica e ai sistemi online d'Ateneo.
* Poiché l'orientamento si svolge anche attraverso visite "fisiche" delle scuole nell'Università, o di rappresentati dell'Università all'interno delle scuole, una parte del sito dovrà contenere le informazioni riguardanti le visite in programma, nonché dei moduli (online) che le scuole potranno utilizzare per richiedere informazioni, materiale, o per prenotare una visita di orientamento *in loco*.
* Per gli studenti interessati a venire nella nostra Università dovranno essere disponibili delle pagine con informazioni di tipo logistico: come arrivare a L'Aquila, orari di autobus e treni, posizione dei vari edifici dell'Ateneo e istruzioni per raggiungerli, ecc.
* Il sito, inoltre, dovrà prevedere anche una parte interattiva, in cui sarà possibile registrarsi, fornire un profilo e pubblicare/consultare annunci in specifiche categorie: offerte per abitazioni, trasporto, ecc. Ad esempio, studenti provenienti dalla stessa città potranno mettersi in contatto per organizzare viaggi comuni. Il sito dovrà prevedere un opportuno sistema di ricerca e classificazione degli annunci stessi.
* Il sito, infine, potrebbe *opzionalmente* prevedere una parte con alcune informazioni tradotte in inglese per gli studenti stranieri in visita nel nostro Ateneo.

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
