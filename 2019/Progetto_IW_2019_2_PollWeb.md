# Corso di Web Engineering
*Progetti A.A. 2019/2020* - Specifica 2

## Progetto "PollWeb"

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

Il sito *PollWeb* rappresenta un semplice sistema per la realizzazione di sondaggi online. Ciascun sondaggio avrà un utente *responsabile*, un titolo, un testo di apertura e uno di chiusura, e sarà composto da una serie di domande. Ciascuna domanda, a sua volta, potrà essere di una delle seguenti tipologie:

1. *Testo breve*: una riga di testo;
2. *Testo lungo*: più righe di testo;
3. *Numero*: solo numeri;
4. *Data*: solo date, opzionalmente con ora associata;
5. *Scelta singola*: vengono presentate una serie di opzioni e l'utente deve sceglierne esattamente una;
6. *Scelta multipla*: vengono presentate una serie di opzioni e l'utente può sceglierne una o più.

Tutti i tipi di domanda appena elencati avranno degli attributi comuni: *codice* (usato per identificare univocamente la domanda), *testo* (il testo della domanda, *opzionalmente* in HTML), *nota* (una nota esplicativa che potrebbe apparire dopo il quesito per guidarne la compilazione), *obbligatoria* (se impostato, indica che l'utente deve necessariamente rispondere alla domanda, o scegliere (almeno) una delle risposte nel caso delle domande a scelta multipla). Altri attributi specifici potranno essere aggiunti a ciascun tipo di domanda per definirla meglio, ad esempio

* Lunghezza minima e massima di un campo di testo;
* *Valore* *minimo e massimo* per i campi numerici (e magari anche per quelli data);
* *Espressione regolare* che deve fare match con un campo di testo;
* Numero minimo e/o massimo di opzioni selezionabili per le scelte multiple.

Questi attributi sono tutti *opzionali*, ma più ne gestirete più realistico diverrà il vostro progetto.

\*Suggerimento:\*una parte molto importante di questo progetto sarà, chiaramente, la definizione e la realizzazione di una struttura dati che possa modellare i sondaggi aggregando domande che a loro volta possano essere definite, ciascuna con le proprie caratteristiche, nella maniera più efficiente possibile, e associate alle risposte in maniera altrettanto efficace.

Di seguito sono illustrati schematicamente i contenuti e le
funzionalità minime che dovrebbero essere inseriti nel sito. Ovviamente, ogni
ulteriore raffinamento o arricchimento di queste specifiche aumenterà il valore
del progetto.
* Il sistema dovrà prevedere tre tipologie di utenza: *partecipante* , *responsabile* e *amministratore*. Le tipologie sono a cascata, quindi, ad esempio, un responsabile potrà essere anche un partecipante. I dati associati a ciascun utente dovranno includere almeno un indirizzo email valido.

* *L'amministratore* è unico e lo supporremo preregistrato nel sistema. I responsabili dovranno essere registrati dagli amministratori. Per i partecipanti vedremo più avanti la procedura di registrazione nel sistema.

* Ciascun utente *responsabile* potrà creare nuovi sondaggi, a cui verrà associato. Nel creare un sondaggio, andranno forniti tutti i campi testuali (vedi sopra), dopodiché si passerà alla definizione delle domande, come descritto nei punti seguenti.

* Per comporre il sondaggio, il responsabile inserirà le singole domande una alla volta, in sequenza. Deve essere possibile rivedere la sequenza dei quesiti già inseriti in una schermata riassuntiva, nella quale siano anche presentate le caratteristiche più importanti di ciascun quesito.

* Le domande già inserite nella sequenza del sondaggio devono poter essere modificate, cancellate o riordinate (spostandole più in alto o più in basso nella sequenza).

* Ogni tipo di domanda avrà una schermata di input (inserimento/modifica) propria, anche se ovviamente le varie schermate dovrebbero mantenere una certa uniformità, almeno per gli elementi comuni a tutte le tipologie.

* Il sondaggio potrà essere *riservato* o *pubblico* . Nel primo caso (sondaggio *riservato* ), il responsabile dovrà inserire manualmente nel sistema i dati (nome, email, password) dei partecipanti che potranno accedere al sondaggio. *Opzionalmente* , questi dati potrebbero essere anche importati da un file CSV. *Nota bene: ogni sondaggio avrà il suo insieme di partecipanti, quindi gli utenti inseriti in un sondaggio non potranno accedere ad altri sondaggi, a meno che non siano registrati (replicandone i dati) anche in questi ultimi.* Nel caso invece il sondaggio sia *pubblico*, chiunque potrà accedervi, cioè non sarà prevista una procedura di autenticazione.

* Una volta soddisfatto della definizione del sondaggio, il responsabile potrà *attivarlo* , rendendolo compilabile al pubblico. All'atto dell'attivazione, gli verrà presentata la URL che i partecipanti potranno utilizzare per accedere alla compilazione del sondaggio. *Opzionalmente*, nel caso di sondaggi riservati, all'attivazione il sistema potrebbe inviare un'email di invito, completa di URL di accesso e credenziali, a tutti i partecipanti registrati.

* Accedendo alla URL del sondaggio (quella presentata al responsabile al momento della sua attivazione), ai partecipanti dei sondaggi *riservati* verrà richiesto di autenticarsi, per poi passare alla compilazione. Per i sondaggi *pubblici* , invece, si passerà direttamente alla compilazione. *Nota bene: nei sondaggi riservati, ciascun utente potrà partecipare solo una volta, quindi dopo una compilazione conclusasi con successo, la sua utenza verrà disabilitata.*

* La compilazione del sondaggio si svolgerà mostrando all'utente tutti i quesiti in esso definiti, nella sequenza impostata. Scegliete la tecnica di input più consona a ciascun tipo di quesito. *Opzionalmente*, potrete anche presentare il sondaggio paginato, un certo numero di quesiti per volta.

* Una volta inviate le risposte al sondaggio, il server effettuerà tutti i dovuti controlli sulla validità e sui vincoli impostati sui singoli quesiti, e in caso di successo registrerà le risposte. In caso di errore, l'utente verrà invitato a ripetere la compilazione.

* Il responsabile potrà in ogni momento *chiudere* il sondaggio, inibendone l'accesso ai partecipanti.

* Il responsabile potrà *esportare i dati* delle risposte in formato CSV e/o in altri formati utili. Potete scegliere il formato dei dati in maniera da rendere questo file il più chiaro e informativo possibile. *Opzionalmente*, il responsabile potrà anche visualizzare le singole risposte pervenute direttamente via web (in sola lettura ovviamente).

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
