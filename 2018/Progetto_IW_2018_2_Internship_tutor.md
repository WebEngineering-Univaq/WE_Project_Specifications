# Corso di Web Engineering
*Progetti A.A. 2018/2019* - Specifica 2

## Progetto "Internship tutor"

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

Il sito *Internship tutor* rappresenta un sistema web per la gestione dell'iter completo dei tirocini universitari. In particolare, il sistema permetterà alle aziende di registrarsi e, previa approvazione dell'amministratore, convenzionarsi e pubblicare autonomamente proposte (dettagliate) di tirocinio. Gli studenti potranno liberamente accedere a tali proposte, contattare l'azienda, stampare tutta la documentazione necessaria per l'avvio e la conclusione del tirocinio stesso, e infine fornire il proprio parere sull'azienda e il tirocinio.

Un'azienda dovrà essere registrata con i seguenti dati: ragione sociale/nome, indirizzo della sede legale, codice fiscale/partita IVA, nome e cognome del legale rappresentante, nome, cognome, telefono e indirizzo email della persona responsabile della convenzione per i tirocini, foro competente (città alla cui sede giudiziaria le parti dovranno rivolgersi in caso di disputa legale). Questi dati sono deducibili dallo schema di convenzione quadro che trovate all'indirizzo http://www.disim.univaq.it/didattica/risorsa-1632.

Un'offerta di tirocinio dovrà invece specificare obbligatoriamente il luogo in cui si svolgerà (che può essere anche presso la sede del tirocinante, nel caso si possa svolgere in remoto), gli orari (se previsti), il numero di mesi/ore del tirocinio, gli obiettivi (generici), le modalità (lavoro nel team aziendale, lavoro freelance in remoto, ecc.), eventuali rimborsi spese o altre facilitazioni previste. Questi dati sono deducibili dalle prime pagine del progetto formativo che trovate all'indirizzo http://www.disim.univaq.it/didattica/risorsa-2767.

Lo studente, se interessato a iniziare un tirocinio, dovrà anch'esso registrarsi (o aggiornare la propria registrazione), inserendo i dati previsti dalla prima pagina del progetto formativo, cioè nome, data e luogo di nascita, residenza, codice fiscale, telefono, corso di laurea al quale è iscritto, e indicando se è portatore di handicap.

All'atto dell'attivazione del tirocinio, lo studente dovrà infine indicare tutti gli altri dati previsti dalle prime tre pagine del progetto formativo *che non siano già deducibili dalla registrazione dell'azienda, dai suoi dati personali, e dall'offerta di tirocinio*.

Alla fine del tirocinio, l'azienda dovrà invece inserire le informazioni necessarie a completare la penultima pagina del progetto formativo, quindi le ore di tirocinio effettivamente svolte, la descrizione dettagliata dell'attività e giudizio finale.

Di seguito sono illustrati schematicamente i contenuti e le
funzionalità minime che dovrebbero essere inseriti nel sito. Ovviamente, ogni
ulteriore raffinamento o arricchimento di queste specifiche aumenterà il valore
del progetto.
* Il sistema dovrà prevedere quattro tipologie di utenza: *anonimo* , *studente, azienda* e *amministratore*.

* Le aziende potranno registrarsi liberamente fornendo i dati appena elencati. All'atto della registrazione l'azienda non sarà già visibile agli studenti né potrà inserire annunci, ma verrà notificata all'amministratore che avrà cura di completare il processo di convenzionamento.

* L'amministratore, a fronte di una richiesta di convenzionamento, verificherà (manualmente, quindi deve semplicemente poterli visualizzare) i dati inseriti e genererà automaticamente il documento di convenzione quadro (http://www.disim.univaq.it/didattica/risorsa-1632). *Suggerimento: potete semplicemente trasformare il documento indicato in un template HTML, che riempirete automaticamente con i dati forniti dall'azienda, permettendone poi la stampa dal browser. Opzionalmente, potete provare a generare un PDF direttamente o convertendo l'HTML generato.* Una volta che la convenzione sarà stata firmata e riconsegnata (passo manuale: assumete che avvenga), l'amministratore dovrà caricare una scansione della convenzione firmata (ad esempio un PDF), associandola ai dati dell'azienda, e *abilitare* l'azienda stessa.

* Un'azienda abilitata potrà pubblicare offerte di tirocinio direttamente dal web, usando le credenziali fornite durante il processo di registrazione, e specificando tutte le informazioni previste.

* Gli studenti potranno inizialmente accedere al sito in maniera anonima. In questo modo potranno consultare la lista delle aziende convenzionate e la bacheca delle offerte di tirocinio. Su quest'ultima dovrà essere possibile eseguire ricerche con criteri quali la città sede del tirocinio, la durata minima/massima, parole chiave contenute negli obiettivi, ecc.

* Quando uno studente deciderà di aderire a un'offerta, gli verrà richiesto di effettuare la login (se già registrato) o registrarsi, fornendo i dati descritti nei paragrafi iniziali di questa specifica. Il candidato dovrà inoltre specificare il numero di crediti richiesti e i dati (nome ed email) del tutore prescelto. A questo punto il sistema invierà una email di richiesta al referente per i tirocini dell'azienda (specificato in fase di registrazione) e una al tutore designato, contenenti entrambe gli estremi dell'offerta e tutti i dati del candidato. *Suggerimento: usate un template per compilare il testo di questa mail. Non è necessario che la vostra applicazione effettui veramente l'invio, basta che lo simuli, ad esempio scrivendo l'email su un file.*

* Le aziende avranno a disposizione un pannello riepilogativo con la lista delle offerte da esse pubblicate. Avranno la possibilità di chiudere un avviso (cioè renderlo invisibile agli studenti) e visualizzare la lista degli studenti che si sono candidati per ogni specifico avviso.

* Alla fine di una fase di "contrattazione" esterna al nostro sito, durante la quale il candidato e l'azienda potranno discutere i dettagli del tirocinio, l'azienda potrà bocciare o approvare la candidatura con appositi controllo messi a disposizione dalla "lista candidati" appena descritta.

* Nel caso in cui la proposta venga accettata, l'azienda dovrà comunicare al sistema anche il periodo di effettuazione del tirocinio, e questo genererà automaticamente le prime tre pagine del progetto formativo (http://www.disim.univaq.it/didattica/risorsa-2767), permettendone il download sia all'azienda che al tirocinante. \*Suggerimento: anche qui potete procedere come nel caso della generazione automatica della convenzione vista sopra.\*Seguirà la solita fase offline, alla fine della quale uno dei due soggetti dovrà caricare nel sistema, come al solito, una scansione del progetto debitamente firmato e timbrato.

* Arrivati al termine del tirocinio, come definito nel passo precedente, all'azienda verrà notificata la necessità di compilare il resoconto finale. Come al solito questa procedura sarà effettuata online, e produrrà un documento simile alla penultima pagina del progetto formativo, che lo studente potrà scaricare, stampare e portare in segreteria.

* *Opzionalmente*, terminato il tirocinio, lo studente avrà la possibilità di votare per l'azienda esprimendo una valutazione di gradimento nella classica scala 0-5 stelle (che potrà essere in qualche modo associata al profilo pubblico dell'azienda)

* *Opzionalmente*, l'amministratore potrà visualizzare alcune statistiche interessanti quali i tutori più richiesti, le aziende che ospitano più tirocinanti, le aziende con valutazioni migliori/peggiori e così via.

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
