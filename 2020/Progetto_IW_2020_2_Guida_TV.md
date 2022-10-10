# Corso di Web Engineering
*Progetti A.A. 2020/2021* - Specifica 2

## Progetto "Guida TV"

> Versione 1.5

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

Il sito "Guida TV" rappresenta una guida online ai programmi televisivi. Il sito gestirà il palinsesto di un certo numero di canali televisivi, per ognuno dei quali sarà disponibile l'elenco dei programmi per ogni giorno. Verranno pubblicati i programmi dei sette giorni successivi a quello corrente (ovviamente potranno essercene anche meno, in base ai dati forniti dai vari editori), mentre per i programmi dei giorni passati, anch'essi disponibili, è possibile prevedere un limite oltre il quale tali informazioni saranno cancellate dal database, per evitare inutile carico.

Di ogni programma avremo l'ora di inizio e fine, il nome, una breve descrizione e il genere (i generi dovrebbero essere prelevati da una lista predefinita). Se il programma rappresenta un episodio di una serie, avremo anche il numero di stagione e il numero di episodio nella stagione. Potrà essere presente anche un link a una scheda di approfondimento (non necessariamente interna al sito stesso: pensate alle pagine della Wikipedia, ad esempio) nonché un'immagine. Quest'ultima potrà essere interna al sito o collegata tramite un link esterno.

Sarà possibile consultare il palinsesto di ogni canale (programmi di un certo giorno) ed effettuare ricerche per titolo e/o genere, eventualmente ristrette a uno specifico canale. L'intervallo temporale di tali ricerche potrà essere altresì specificato dall'utente.

*Suggerimento: considerate che molto spesso nei palinsesti figurano più volte gli stessi programmi, oppure episodi di una stessa serie. Nel progettare il modello dati, e quindi anche le operazioni che lo riguardano, provate a ottimizzarne al meglio la struttura in base a questa considerazione. Ad esempio, se un film viene replicato in due giorni diversi, il database non dovrebbe contenerne due volte tutte le informazioni di base (titolo, descrizione, link...): solo i dati di messa in onda (canale, ora, ecc.), che sono gli unici a cambiare, dovrebbero esistere in due versioni diverse.*

Sul sito sarà possibile registrarsi inserendo la propria email e una password. Gli utenti registrati, una volta eseguita la login, potranno specificare le modalità di ricezione di una email giornaliera con gli ultimi aggiornamenti al palinsesto. La mail potrà contenere i programmi del giorno per alcuni canali selezionati, eventualmente solo per certe fasce orarie (mattino/pomeriggio/sera/notte) e/o i risultati di una ricerca salvata (del tipo appena descritto), per essere aggiornati, ad esempio, sul momento in cui nel palinsesto appare un programma che si vuole seguire. *Nota: l'applicazione realizzata per il progetto non dovrà necessariamente inviare queste email, ma dovrete comunque realizzare tutto il codice per crearne il contenuto, riversandolo poi, in fase di demo, su un file esterno.*

Nota bene: trattandosi di un sito che verrà sicuramente usato molto in mobilità, si curi particolarmente l'aspetto della *responsiveness*.

Di seguito sono illustrati schematicamente i contenuti e le
funzionalità minime che dovrebbero essere inseriti nel sito. Ovviamente, ogni
ulteriore raffinamento o arricchimento di queste specifiche aumenterà il valore
del progetto.
* La homepage mostrerà la lista dei canali a disposizione, nonché le trasmissioni correntemente in onda su ciascuno di essi.

* Dalla homepage si potrà accedere a una seconda vista simile a quella della homepage stessa, in cui sono elencati tutti i canali con associati, però, i programmi del loro palinsesto giornaliero *relativi a una specifica fascia oraria* (mattina/pomeriggio/sera/notte).

* In qualsiasi vista, cliccando su un canale, sarà possibile visualizzare il suo palinsesto completo per la giornata attuale. In questa vista, quella classica da "guida tv", saranno mostrati tutti i programmi (ordinati!) con l'ora di inizio, quella di fine, il genere e il titolo. Se disponibile, a fianco di un programma potrà essere mostrata la relativa immagine opportunamente scalata.

* In qualsiasi vista, cliccando su un programma si accederà alla scheda con i dettagli: immagine a dimensione maggiore (se disponibile), descrizione, link di approfondimento.

* Se il programma è parte di una serie, nella sua scheda di dettaglio dovrà essere possibile visualizzare data/ora e canale di trasmissione di tutti i relativi episodi nell'ultimo mese.

* La funzionalità di ricerca, accessibile in ogni punto del sito, dovrà permettere di specificare uno o più dei seguenti criteri, combinati in AND: (parte del) titolo, genere, ora di inizio massima e minima, canali, intervallo temporale (date). I risultati di ricerca saranno mostrati in maniera simile alla vista della guida TV, ma in questo caso ordinati per data, ora di inizio e canale.

* Un utente potrà registrarsi fornendo una email valida e una password a sua scelta. L'email dovrà essere confermata cliccando su un link inviato allo stesso indirizzo. *Nota: scrivete il codice necessario a generare il link di convalida e gestirne il click, ma in sede di demo potrete semplicemente far stampare il link da qualche parte e immetterlo nel browser, senza bisogno di inviare veramente delle email.*

* Nel proprio profilo l'utente potrà abilitare l'email giornaliera di informazioni, descritta più in alto, specificando eventualmente una lista di canali e una o più fasce orarie di interesse.

* L'utente autenticato, inoltre, una volta eseguita una ricerca come visto sopra, avrà a disposizione un bottone per salvarne i criteri, in modo che possano essere usati per generare ulteriori informazioni da inserire nella sua mail giornaliera, come già illustrato.

* Ovviamente, l'utente registrato potrà in ogni momento disabilitare l'invio dei risultati di una ricerca e/o del palinsesto giornaliero.

* L'amministratore del sito, che immagineremo unico e preregistrato nel sistema, potrà inserire, modificare o cancellare i canali e i relativi palinsesti, cioè i programmi e le informazioni sulla loro messa in onda.

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
