# Corso di Web Engineering
*Progetti A.A. 2013/2014* - Specifica 1

## Progetto "SimplestNote"

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

Il sito *SimplestNote* rappresenta un semplice blocco note online, con possibilità di condivisione delle note.

Il sito dovrà essere accessibile solo a un'utenza registrata. Ciascun utente avrà a disposizione un blocco note virtuale, composto da un numero arbitrario di pagine, che di seguito chiameremo semplicemente *note* , ognuna dotata di titolo e contenuto, entrambi testuali. La lunghezza del titolo può essere limitata, mentre quella del contenuto dovrebbe essere illimitata. Le singole note saranno inoltre associate alla data di creazione, la data di ultima modifica, il numero di versione (corrispondente al numero di volte in cui la nota è stata modificata) e a un numero arbitrario di *tag* , intesi come parole o brevi sequenze di parole (ad esempio "*novità* ", "*lavoro* " o "*corrispondenza privata*").

Il sistema provvederà a salvare tutte le versioni di ciascuna nota, in modo da prevenire modifiche involontarie e fornire una storia della sua stesura. Sarà possibile condividere una nota con altri utenti del sistema, facendola apparire nei loro blocchi ed eventualmente permettendone la modifica.

Di seguito sono illustrati schematicamente i contenuti e le
funzionalità minime che dovrebbero essere inseriti nel sito. Ovviamente, ogni
ulteriore raffinamento o arricchimento di queste specifiche aumenterà il valore
del progetto.
* Gli utenti potranno registrarsi su *SimplestNote* fornendo i propri dati e un indirizzo email valido (il controllo di validità, effettuabile inviando un'email con un link da cliccare per la verifica dell'indirizzo, è *opzionale*) e ricevendo delle credenziali di accesso. L'indirizzo email sarà usato come username, mentre la password dovrà essere generata in maniera casuale al momento della registrazione.

* Una volta effettuata la login, l'utente potrà consultare la lista delle proprie note (mostrate con titolo e data di ultima modifica). Selezionando una nota si aprirà la vista di lettura/editing della stessa. L'interfaccia dovrà inoltre permettere la creazione di nuove note (con un titolo iniziale "standard" predefinito, magari basato sulla data/ora correnti) e l'eliminazione delle note esistenti.

* La vista di lettura/editing per una nota dovrà permettere la modifica del titolo, del contenuto nonché dei tag. *Opzionalmente*, quando si aggiunge un tag, il sistema potrebbe suggerire uno dei tag già utilizzati dall'utente in altre note, oltre che permettere l'inserimento di un nuovo tag sotto forma di breve testo.

* Ad ogni modifica, il sistema salverà prima lo stato corrente della nota (titolo, contenuto, tag, data di ultima modifica) in una *history*, e solo a questo punto applicherà le modifiche richieste (salvando il nuovo stato della nota, incrementando il numero di versione, aggiornando la data di ultima modifica). In questo modo la history sarà via via popolata con tutte le versioni precedenti della nota stessa.

* Dovrà essere possibile accedere alla history di ogni singola nota, visualizzando il numero di versione e la data di modifica di tutte le sue versioni precedenti. Cliccando su un elemento della history, sarà possibile vedere titolo, contenuto e tag della nota per quella versione, ma *in sola lettura*.

* Dovrà essere possibile condividere una nota con altri utenti dello stesso sistema, specificandone l'indirizzo email utilizzato per la registrazione. La condivisione sarà effettuabile in sola lettura o in lettura/scrittura. Un utente vedrà le note condivise con lui all'interno della propria lista note, evidenziate in modo da renderne chiara la provenienza (indirizzo email del proprietario) e i permessi di accesso (lettura o lettura/scrittura). Le note condivise in sola lettura potranno essere lette ma non modificate. Su quelle in lettura/scrittura sarà possibile effettuare ogni tipo di modifica, esattamente come per le note di cui si è proprietari. Il proprietario di una nota condivisa potrà interromperne la condivisione in qualsiasi momento.

* *Opzionalmente* , potrete realizzare l'*endpoint* per un eventuale client mobile del nostro servizio: un semplice sistema di esportazione JSON delle note. Il sito dovrà rispondere a due URL speciali, che indicheremo rispettivamente con *http://server.it/notepad/getList?user=email\&pass=password* e con *http://server.it/notepad/getNote?user=email\&pass=password\&note=ID.* Chiamando la prima, il server dovrà restituire una struttura JSON (attenzione al *content type* !) che rappresenta la lista di tutte le note dell'utente avente l'*email* specificata, autenticato tramite la *password* inserita anch'essa nella URL. Ovviamente, in caso di problemi con l'autenticazione, la risposta sarà vuota. La lista dovrà contenere, per ogni nota, il suo ID (chiaramente il vostro sistema dovrà dotare ogni nota di un identificatore per inserirlo nella base di dati) e il titolo. Chiamando invece la seconda URL, verrà restituita una struttura JSON contenente data di creazione, data di modifica, numero di versione, titolo, contenuto e tags della nota specificata dall'ID inserito nella URL stessa e appartenente all'utente autenticato con le credenziali specificate. *Nota bene:* in un'applicazione reale, trasmettere username e password ad ogni chiamata del servizio sarebbe poco efficiente e sicuro, ma qui utilizzeremo quest'approccio per semplificare l'implementazione.

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
