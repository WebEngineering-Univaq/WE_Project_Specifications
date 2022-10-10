# Corso di Web Engineering
*Progetti A.A. 2007/2008* - Specifica 1

## Progetto "WebMovie"

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

Il sito *WebMovie* costituisce un sistema web completo per la gestione di un catalogo cinematografico online. Sarà possibile effettuare ricerche, consultare le informazioni sui film e le schede degli attori/personaggi, acquistare copie di un film, vendere le proprie copie usate, ecc.

Di seguito sono illustrati schematicamente i contenuti e le
funzionalità minime che dovrebbero essere inseriti nel sito. Ovviamente, ogni
ulteriore raffinamento o arricchimento di queste specifiche aumenterà il valore
del progetto.
* Il sito disporrà di schede informative complete per ogni film, contenenti almeno: titolo, anno di realizzazione, regista, personaggi e relativi attori, genere (drammatico, commedia, horror, ecc.), paese di realizzazione. Inoltre,
  1. Ogni scheda potrà prevedere l'accesso a un'opportuna galleria di immagini associate al film, se disponibili.
  2. Ogni scheda dovrà prevedere l'accesso a una serie di risorse di approfondimento, costituite da link ad altri siti web o da materiale locale (ad es. trailer scaricabili in formato elettronico).
  3. Ogni scheda dovrà prevedere un'area in cui i visitatori potranno lasciare i loro commenti sul film. I commenti saranno mostrati sulla pagina insieme a un modulo per aggiungere il proprio.
* Il sito disporrà inoltre di schede informative su ogni persona (regista o attore) presente nei film. Le schede in questo caso comprenderanno una biografia e la lista dei film diretti o interpretati.
* Ovviamente, ovunque possibile i nomi delle persone e i titoli dei film dovranno essere cliccabili, in modo da poter navigare tra le schede in maniera ipertestuale.
* Il sito dovrà prevedere i seguenti sistemi di ricerca per i film:
  1. Ricerca libera, tramite stringhe da individuare all'interno delle informazioni testuali contenute nelle schede dei film.
  2. Ricerca per attore o regista.
  3. Ricerca per anno.
  4. Ricerca per genere.
* I risultati delle ricerche dovranno essere presentati tramite una lista contenente schede sintetiche su ciascun film individuato. Cliccando su un film, si accederà alla sua scheda completa.
* Dovrà essere possibile raffinare la propria ricerca, cioè effettuare una nuova ricerca sui soli risultati della ricerca precedente.
* Oltre alle funzioni di ricerca, sarà possibile "sfogliare" il catalogo dei film con diverse modalità:
  1. Consultazione per titolo. Il catalogo mostrerà i titoli, ordinati alfabeticamente, di tutti i film. Cliccando su un titolo, si potrà visualizzare la relativa scheda.
  2. Consultazione per attore o regista. Il catalogo mostrerà i nomi, ordinati alfabeticamente, di tutte le persone catalogate nel sistema. Cliccando su un nome, si potrà visualizzare la relativa scheda.
* Una volta individuata la scheda di un film d'interesse sarà possibile accedere a un mercato virtuale *molto semplificato* , con le seguenti funzioni:
  1. Acquisto di una nuova copia del film con carta di credito. L'utente dovrà specificare il formato (DVD, VHS, ecc.) richiesto, i propri dati e quelli della propria carta di credito. La richiesta di acquisto verrà inserita nel database del sito e l'utente riceverà una email di conferma.
  2. Inserimento di un annuncio per la vendita di una copia personale usata del film. Gli annunci, corredati di indirizzo email di contatto e di informazioni base sulla copia in vendita (anno di acquisto, formato, condizioni, ecc.) saranno pubblicati su un'opportuna pagina collegata alla scheda del film.
* Il sito dovrà inoltre essere dotato di un opportuno *backoffice* che permetta di inserire e modificare tutte le informazioni associate alle schede di film e persone.

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
