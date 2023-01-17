# Corso di Web Engineering
*Progetti A.A. 2020/2021* - Specifica 1

## Progetto "Collectors Site"

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

Il sito *Collectors Site* rappresenta un punto di incontro per i collezionisti di dischi (anche se lo stesso tipo di sito potrebbe adattarsi quasi a qualunque tipo di collezione, useremo i dischi come caso di studio in modo da poter aggiungere più dettagli alla specifica).

Gli utenti di questo sito, o *collezionisti* , una volta registrati potranno inserire tutti i dati relativi alle proprie *collezioni* di dischi(dovete prevedere che ogni collezionista possa creare più collezioni, ciascuna con un nome distinto). Per ogni *disco* in una collezione, dovranno essere specificati gli autori, il titolo, l'anno di uscita, l'etichetta (casa editrice), il genere (scelto da una lista predefinita di generi musicali), lo stato (di conservazione dell'oggetto, scelto da una lista predefinita), il formato (vinile, CD, digitale,...), il numero di *barcode*, se disponibile (i codici a barre garantiscono l'identificazione univoca dell'elemento), e poi ovviamente la lista delle tracce, ciascuna con titolo, durata, ed eventuali informazioni su compositore ed esecutore (cantante, musicista), se diverso da quelli dell'intero disco. Infine, ogni disco può essere associato a una o più immagini (copertina, retro, eventuali facciate interne o libretti, ecc.). Insomma, cercate di essere il più realistici possibile.

Per ogni disco, il collezionista potrà inoltre indicare l'eventuale numero di *doppioni* a sua disposizione (spesso si hanno più copie dello stesso disco, magari a seguito di scambi, e magari anche perché se ne prevede la rivendita).

I collezionisti potranno decidere di *condividere* la propria collezione con specifici utenti o in maniera pubblica. Ogni collezionista avrà quindi a disposizione un pannello con una lista delle collezioni condivise specificamente con lui, che potrà visualizzare liberamente.

Il sito disporrà di una funzionalità di ricerca avanzata (per artista, titolo, collezionista, ecc.), utilizzabile anche dagli utenti anonimi, che prenderà in considerazione tutte le collezioni pubbliche e, per un utente che abbia eseguito l'accesso, anche la collezione personale e tutte le collezioni condivise con lui (*suggerimento: potete eseguire la stessa ricerca su ogni collezione accessibile dall'utente e poi fondere i risultati*).

È importante che, nel sistema, gli stessi dischi, anche se appartenenti a collezioni e collezionisti diversi, siano messi in relazione, in modo da poterli raggruppare se necessario, proprio per rispondere più facilmente a interrogazioni del tipo "chi ha questo disco?". A questo scopo, cercate sempre, quando viene immesso un nuovo disco, di "suggerire" al collezionista di importare (come valori iniziali) i dati dello stesso disco, se già presente nel sistema in altre collezioni. Così facendo, internamente creerete una connessione tra i dischi "uguali", anche se poi il collezionista sarà libero di editare i dati della propria copia. Inoltre, sarebbe opportuno inserire l'autocompletamento ovunque possibile, usando come origine i dati dello stesso campo già presenti nella base di dati: ad esempio, inserendo il nome di un cantante, il sistema dovrebbe suggerire il completamento usando i nomi dei cantanti già inseriti. Questo accorgimento non ha solo lo scopo di velocizzare l'input, ma è utile anche per evitare che nella base di dati lo stesso oggetto (in questo caso, un cantante) sia inserito più volte con piccole variazioni di scrittura (ad esempio spazi, apostrofi, ecc.).

Di seguito sono illustrati schematicamente i contenuti e le
funzionalità minime che dovrebbero essere inseriti nel sito. Ovviamente, ogni
ulteriore raffinamento o arricchimento di queste specifiche aumenterà il valore
del progetto.
* I collezionisti potranno registrarsi nel sistema fornendo un nickname e un indirizzo email. Non è richiesto, anche se possibile, inserire il proprio nome e cognome.

* Ogni collezionista avrà un profilo pubblico, visibile anche agli utenti anonimi, contenente i dati personali inseriti e la lista delle sole collezioni pubbliche.

* I collezionisti, una volta autenticati, potranno gestire le proprie collezioni, e in particolare creare o cancellare una collezione e inserire/cancellare/modificare i singoli dischi contenuti nella collezione, con le caratteristiche descritte precedentemente nella specifica.

* Il sito dovrà prevedere (almeno) due viste sulle collezioni: lista dell'intera collezione e dettaglio disco contenuto nella collezione. In entrambi i casi, dovrete decidere quali informazioni mostrare e come organizzarle. Ovviamente la vista sulla collezione e sui relativi contenuti sarà accessibile al proprietario e a tutti coloro che posseggano diritti di accesso alla collezione stessa (nel caso di collezioni pubbliche o condivise).

* Un'importante elemento del sito sarà la funzionalità di ricerca. Dovrà essere possibile effettuare ricerche in base a nomi di autori/compositori/interpreti, in base a titoli e in base al nickname dei collezionisti. I risultati potranno essere di tipo diverso in base agli elementi trovati: singoli dischi, intere collezioni, profili di collezionisti. Si potrà decidere di includere nella ricerca solo le proprie collezioni (se si è autenticati) o anche quelle condivise/pubbliche.

* Ogni collezionista avrà a disposizione un pannello con la lista delle collezioni condivise con lui, dalle quali accedere in maniera diretta alla vista della relativa collezione.

* Ogni collezionista potrà decidere se rendere ciascuna propria collezione privata (default), pubblica o condividerla con altri specifici utenti. Quando si condivide la collezione con un utente, questo riceverà una email di notifica (*suggerimento: potete simulare l'invio, non è necessario usare realmente la posta elettronica*).

* Il sito dovrà fornire una serie di statistiche, pubbliche o personali (per collezionista). Siete liberi di individuare quelle più interessanti. Suggerimenti possono essere il numero dischi per autore, per genere, ecc. (in una collezione, per il collezionista, o in tutto il sistema, come statistica globale)

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
