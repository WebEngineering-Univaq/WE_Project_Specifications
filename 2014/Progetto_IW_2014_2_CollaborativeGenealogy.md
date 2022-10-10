# Corso di Web Engineering
*Progetti A.A. 2014/2015* - Specifica 2

## Progetto "CollaborativeGenealogy"

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

Il sito *CollaborativeGenealogy* rappresentaun metodo sociale per costruire il proprio albero genealogico contribuendo contemporaneamente al completamento di quello degli altri utenti.

Il sito dovrà essere accessibile solo a un'utenza registrata. Ciascun utente dovrà fornire (e non potrà più aggiornare) i propri dati anagrafici completi, comprensivi di data e luogo di nascita, e un indirizzo email, all'atto della registrazione. L'utente potrà poi fornire i propri contatti (indirizzo, numeri di telefono, ecc.) e, *opzionalmente*, tenere aggiornata anche una propria biografia testuale e caricare una foto da utilizzare per il suo profilo. L'aspetto "sociale" del sistema risiede nel modo in cui vengono costruiti gli alberi genealogici.

Di seguito sono illustrati schematicamente i contenuti e le
funzionalità minime che dovrebbero essere inseriti nel sito. Ovviamente, ogni
ulteriore raffinamento o arricchimento di queste specifiche aumenterà il valore
del progetto.
* Gli utenti anonimi, cioè che accedono al sito senza fare login, vedranno una semplice pagina di presentazione, un modulo di login/registrazione e uno di ricerca. La ricerca sarà effettuata solo su nome e cognome degli utenti registrati e i risultati mostreranno solo il nome completo degli utenti e il numero di "parenti" nel loro albero genealogico. In questo modo l'utente anonimo potrà "testare" l'utilità del servizio, pur senza violare la privacy degli utenti registrati, e decidere di iscriversi per poter usare il sistema nella sua totalità.

* Un utente registrato potrà eseguire ricerche nel sistema sulla base di vari parametri, tra cui i più importanti sono nome e cognome (trovare persone con il proprio cognome è un buon punto di partenza per ricercare una possibile parentela!), data e luogo di nascita. Dovrà essere data all'utente la massima libertà nel combinare questi parametri per effettuare ricerche "mirate". I risultati della ricerca conterranno, in questo caso, nome, cognome, data e luogo di nascita.

* Per creare il proprio albero genealogico, l'utente avrà tre modalità. *Nota bene:* per semplificare il sistema, l'utente potrà aggiungere di volta in volta solo parenti diretti, cioè *padre* , *madre,* *figli* e*fratelli*, di persone già nel suo albero genealogico. Quindi, per inserire il suo nonno materno, dovrà prima inserire sua madre e poi il padre di quest'ultima.

  1. Dopo aver effettuato una ricerca, individuando dei possibili parenti, l'utente avrà la possibilità di aggiungerli al proprio albero genealogico.
  2. Se un parente non è già presente nel sistema, ma è noto all'utente, questo potrà creare il suo profilo di base (nome, cognome, email, data e luogo di nascita) e aggiungerlo contestualmente al proprio albero genealogico.
  3. Infine, per gestire parenti non raggiungibili (o defunti) l'utente potrà creare un profilo base come specificato sopra ma *senza un indirizzo email* e aggiungerlo al proprio albero genealogico, ma in questo caso la relazione parentela sarà sempre mostrata dal sistema con la segnalazione "*non verificato*" a fianco.
* In tutti i casi, l'utente dovrà poter specificare il componente del suo albero genealogico con cui la persona trovata è legata e il relativo grado di parentela (*padre* , *madre* , *figlio, fratello*).

* Nei casi 1 e 2, cioè quando si aggiunge un parente già registrato o lo si specifica manualmente, il possibile nuovo parente dovrà approvare la parentela dichiarata, prima che l'inserimento sia considerato definitivo. Finché non lo farà, ovviamente, la parentela non sarà considerata effettiva e non sarà mostrata nella genealogia dell'utente. Una volta approvata la parentela, i due utenti diverranno ufficialmente "parenti" e ciascuno potrà vedere tutti i dati e navigare nell'albero genealogico dell'altro.

* Il potenziale parente riceverà una notifica per email *(Suggerimento: non c'è bisogno che inviate delle vere email, per questo prototipo basterà che mostriate il testo che vorreste inviare...)* con i dati della persona "proponente" e il tipo di parentela proposta, che potrà approvare o rifiutare. Per gli utenti già registrati (aggiunti come al punto 1), sarà possibile fare login nel loro account ed effettuare questa scelta. Gli utenti non registrati (aggiunto come al punto 2) riceveranno nell'email di notifica un invito a registrarsi nel sistema e approvare la parentela.

* Il sistema dovrà infine permettere a ciascun utente registrato di "navigare" nel proprio albero genealogico, mostrando per prime le parentele dirette e permettendo di espandere passo dopo passo i "parenti dei parenti", e così via. Questa navigazione comprenderà sia la parte di albero da lui direttamente costruita, sia i sotto-alberi costruiti dai suoi parenti anch'essi registrati nel sistema. Un sistema di *breadcrumbs,* il classico percorso di navigazione a segmenti, permetterà in questo caso di ricostruire il rapporto di parentela del parente attualmente selezionato. Ad esempio: sulla pagina principale del mio profilo, clicco su mio padre "Tizio". La pagina mi mostrerà allora il percorso attuale "Io \> Tizio (padre)", i dati di Tizio e tutti i parenti a lui direttamente legati. Cliccando su suo padre "Caio" passerò alla sua pagina il cui percorso sarà "Io \> Tizio (padre) \> Caio (padre)" e così via. *Opzionalmente*, potreste cercare di calcolare il rapporto di parentela complessivo del parente selezionato in base al percorso seguito: in questo caso, ad esempio, la pagina potrebbe mostrare "Caio è il tuo nonno paterno".

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
