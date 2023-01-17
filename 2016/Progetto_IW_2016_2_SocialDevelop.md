# Corso di Web Engineering
*Progetti A.A. 2016/2017* - Specifica 2

## Progetto "SocialDevelop"

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

Il sito *SocialDevelop* rappresenta uno strumento di supporto allo sviluppo di software in maniera collaborativa. Mentre altri siti, come GitHub, si concentrano sulla scrittura vera e propria del codice e sul suo *versioning*, il nostro sistema si pone un obiettivo più a monte, cioè quello di pubblicizzare le idee di sviluppo e individuare gli sviluppatori freelance più adatti per entrare in ciascun progetto, creando anche un sistema di "referenze".

*Grazie a Konstantinos, Svetoslav, Petyo e Danail per avermi suggerito questa idea*

La struttura del sito sarà simile a quella di un forum, ma invece dei *thread* (discussioni) su *SocialDevelop* verranno creati dei *progetti* . Ciascun progetto avrà un *coordinatore* e sarà associato a dei *task*, cioè attività da realizzare per completarlo.

Un *task* sarà corredato da una *descrizione* testuale, dal *numero di collaboratori* che dovranno lavorarci, e da un *intervallo temporale* fissato per il suo completamento. Ogni *task* , inoltre, avrà un *tipo* (molto generico e scelto da una lista predefinita, come "sviluppo", "grafica", "documentazione", ecc.) e un elenco di capacità (che chiameremo *skill* ) richieste a chi ci lavorerà, ognuna con un *livello* minimo di competenza (diciamo da 1 a 10, ad esempio "Programmazione C++" livello 8, oppure "Responsive design" livello 5, ecc.). Gli *skill* andranno scelti anch'essi da una lista predefinita, specifica per il tipo di *task* . Infine, un *task* potrà essere *aperto* o *chiuso* . Un *task* chiuso non accetta ulteriori collaboratori, a meno che questi non vengano aggiunti direttamente dal coordinatore. A *task* aperto, invece, potranno essere inviate domande di collaborazione, come descritto più avanti. Un *task* sarà considerato chiuso se ha già il numero richiesto di collaboratori o se è stato chiuso esplicitamente dal coordinatore. Negli altri casi, sarà aperto.

All'interno di un progetto, infine, potranno essere postati messaggi (annunci, richieste, discussioni interne) sia pubblici, cioè visibili da ogni utente, sia privati, cioè visibili solo dagli iscritti al progetto.

Il sito avrà un amministratore al quale spetterà solo il compito di inserire/modificare la lista dei tipi di *task* e la lista di *skill* associati ad ogni tipo (*opzionalmente* , è possibile associare uno *skill* anche a più di un tipo). Per questi ultimi, sarebbe *opzionalmente* utile dare una struttura gerarchica (ad esempio "Design interfacce Swing" potrebbe essere un "figlio" di "Programmazione Java"), per meglio organizzarne la ricerca. Uno *skill* , come già descritto, è una competenza, generica o molto specifica, che potrà poi essere associata ai *task* e anche ai profili utente, come vedremo.

Gli utenti del sito, che chiameremo *sviluppatori* (in senso lato, potrebbero anche essere dei grafici) dovranno inizialmente registrarsi fornendo, oltre ai loro dati anagrafici e di contatto, anche il loro curriculum in forma testuale oppure come PDF da caricare nel sistema. Gli sviluppatori dovranno inoltre elencare i loro *skill* , scelti dalla lista globale di *skill* presenti nel sistema, indicando per ciascuno il livello di competenza raggiunto (con la stessa scala usata per gli *skill* associati ai *task* , come specificato sopra). Ad esempio, uno sviluppatore potrebbe dichiarare un livello 7 nello *skill* "Programmazione Java".

Di seguito sono illustrati schematicamente i contenuti e le
funzionalità minime che dovrebbero essere inseriti nel sito. Ovviamente, ogni
ulteriore raffinamento o arricchimento di queste specifiche aumenterà il valore
del progetto.
* Tutti gli utenti, anche*anonimi,* potranno navigare nella lista dei progetti, visualizzare i relativi *task* (sia in una lista compatta che in una visualizzazione di dettaglio) e leggere i soli messaggi pubblici postati nei progetti stessi.

* Tutti gli utenti, anche anonimi, avranno la possibilità di effettuare ricerche su *SocialDevelop* secondo due modalità:

  1. ricerca di sviluppatori: si potranno indicare una serie di *skill* (sempre prelevate dalla lista globale del sistema) e *opzionalmente* un livello minimo di competenza per ciascuna di esse. Il sistema restituirà quindi la lista dei profili degli sviluppatori aventi tutte quelle *skill*, con un livello di competenza maggiore o uguale a quello richiesto, se specificato;
  2. ricerca di progetti: si potranno inserire delle parole chiave e il sistema restituirà la lista dei progetti presenti su *SocialDevelop* aventi quelle parole nel nome o nella descrizione.
* Gli utenti anonimi potranno registrarsi divenendo così utenti registrati o *sviluppatori* . Nel processo di registrazione lo sviluppatore dovrà fornire i propri dati anagrafici, di contatto nonché il proprio curriculum e le proprie *skill*, come già descritto in questa specifica.

* Il profilo di ogni sviluppatore mostrerà, oltre alle informazioni inserite in fase di registrazione, anche una lista di referenze automatiche generate sulla base dei progetti in cui ha lavorato o sta lavorando. Per ciascuna collaborazione verrà indicato il *task* su cui lo sviluppatore ha lavorato e la valutazione (quando il *task* è terminato) data dal coordinatore del progetto, del quale sarà presente anche il nome e l'indirizzo email, per approfondire la referenza.

* Gli sviluppatori iscritti a un progetto potranno leggere tutti i messaggi, sia pubblici che privati, inerenti il progetto stesso, e postarne di nuovi.

* Ogni sviluppatore potrà creare nuovi progetti, divenendone il *coordinatore* , e popolarli con i relativi *task* . La definizione di un progetto, dei suoi *task* e delle *skill* richieste dovrà seguire la struttura precedentemente illustrata in questa specifica. Il coordinatore di un progetto potrà inoltre, in qualsiasi momento, modificare il progetto, ad esempio cambiando le date o le *skill* associate a un *task*, variando il numero di collaboratori richiesti, ecc.

* Il coordinatore di un progetto, una volta definito completamente un *task* , potrà visualizzare la lista degli sviluppatori potenzialmente adatti a quel *task* (cioè con *skill*corrispondenti) ottenuta automaticamente sfruttando in maniera opportuna la funzione di ricerca (1) già illustrata.

* Il coordinatore di un progetto potrà inviare a qualsiasi sviluppatore una proposta di collaborazione su un particolare *task* . La proposta sarà inserita in un apposito "*pannello degli inviti* " visibile al coordinatore che riporterà, per ciascuna proposta, il *task* associato, lo sviluppatore contattato, la data di invio della proposta e il suo stato ("in attesa", "accettata" o "rifiutata"). Il coordinatore potrà annullare una proposta di collaborazione in qualsiasi momento.

* Gli sviluppatori disporranno di un proprio "*pannello delle proposte* " che elencherà tutte le proposte di collaborazione inviate dai coordinatori di progetto come appena descritto. Per ciascuna proposta dovrà essere possibile navigare sul relativo progetto e *task* (per visualizzarne i dettagli), accettarla o declinarla. Le offerte non valutate (cioè non accettate o declinate) saranno automaticamente considerate declinate dopo un certo periodo di tempo. Se uno sviluppatore accetta un'offerta di collaborazione il sistema, oltre a cambiare lo stato della relativa proposta nel "*pannello degli inviti* " del coordinatore e nel "*pannello delle proposte* " dello sviluppatore, iscriverà automaticamente lo sviluppatore al progetto e al *task* assegnatogli e diminuirà di conseguenza il conteggio degli sviluppatori richiesti per quel *task*.

* Gli sviluppatori avranno a disposizione anche un "*pannello delle offerte* " che riporterà una selezione automatica delle possibilità di collaborazione coerenti con le loro *skill* . In altre parole, il sistema ricercherà e mostrerà automaticamente (usando un sistema di ricerca simile a quello (1)) i *task aperti* aventi *skill* compatibili con quelli dello sviluppatore. Selezionata un'offerta, lo sviluppatore potrà inviare una domanda di adesione al coordinatore del relativo progetto. Nel pannello, lo stato dell'offerta cambierà da "disponibile" a "adesione richiesta". In base alla successiva decisione del coordinatore, lo stato potrà poi divenire "accolta" o "rigettata". Una domanda di adesione potrà essere ritirata in qualsiasi momento.

* I coordinatori di un progetto avranno a disposizione un *"pannello delle domande"* di collaborazione che elencherà le domande ricevute come descritto al punto precedente, con lo sviluppatore e il *task* associati. Da qui potranno navigare per analizzare nel dettaglio il profilo del candidato e potranno poi accogliere o rigettare la domanda. Se accettata, la domanda provocherà in cambio di stato nel "*pannello delle domande* " del coordinatore e nel "*pannello delle offerte* " del candidato, nonché l'iscrizione immediata del candidato al progetto/*task*, come già descritto.

* *Opzionalmente*, potrete fare in modo che ogni aggiornamento di stato nei pannelli "inviti", "offerte" e "domande" appena descritti generi anche un'email di notifica inviata al rispettivo utente. Ad esempio, un coordinatore riceverà una notifica quando una sua offerta viene accettata o rigettata, o quando uno sviluppatore fa domanda di adesione a un suo progetto, mentre uno sviluppatore riceverà una notifica del risultato di una sua domanda di adesione.

* Il coordinatore di un progetto potrà in qualsiasi momento escludere uno sviluppatore da un *task* (nel caso non lavori come richiesto), de-iscrivendolo ed eventualmente riaprendo il corrispondente *task* a nuove domande di collaborazione (in pratica, aumentando di uno il numero di persone richieste dal *task*).

* Alla conclusione di un *task*, il coordinatore di un progetto avrà la possibilità di valutare (su una scala 1-5) tutti gli sviluppatori che vi hanno collaborato. Questa valutazione, come già illustrato, comparirà nel profilo degli sviluppatori.

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
