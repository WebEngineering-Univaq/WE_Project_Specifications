# Corso di Web Engineering
*Progetti A.A. 2009/2010* - Specifica 2

## Progetto "JobWeb"

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

Il sito *JobWeb* rappresenta un semplice portale per lo scambio di proposte e offerte di lavoro. Su questo sito i candidati potranno pubblicare e aggiornare il proprio curriculum e indicare le proprie preferenze in ambito lavorativo, mentre le aziende potranno ricercare un profilo adatto ai loro interessi. Tuttavia, solo le aziende accreditate potranno visionare completamente i curriculum dei candidati e contattarli.

L'oggetto fondamentale da memorizzare nel sito sarà quindi il *curriculum* . La forma e i contenuti di un curriculum professionale possono essere dedotti cercando e visionando alcuni tra i molti esempi disponibili online (ad esempio, http://europass.cedefop.europa.eu/europass/home/hornav/Downloads/EuropassCV/CVTemplate.csp). In generale, comunque, è necessario che siano presenti almeno le sezioni seguenti:

* Anagrafica (nome, cognome, data di nascita, ecc.; non dimenticate i contatti: email, telefono, posta...). Dovrà essere prevista anche la pubblicazione di una foto.

* Istruzione (titoli di studio maturati, con data, istituzione erogante ed eventuale voto).

* Esperienze lavorative (datore di lavoro, incarico e periodo di ogni esperienza).

* Capacità/conoscenze (ad esempio, descrizione delle proprie conoscenze tecniche), all'interno delle quali ha particolare rilievo la lista delle lingue scritte e/o parlate.

Di seguito sono illustrati schematicamente i contenuti e le
funzionalità minime che dovrebbero essere inseriti nel sito. Ovviamente, ogni
ulteriore raffinamento o arricchimento di queste specifiche aumenterà il valore
del progetto.
* Il sito dovrà prevedere tre tipologie di utenza: amministratori, utenti registrati e utenti anonimi. Gli utenti registrati dovranno essere a loro volta distinti in *candidati* (in cerca di lavoro) e *aziende* (in cerca di personale). Andranno quindi previste procedure di registrazione e login.

* Ogni candidato registrato potrà inserire e modificare in ogni momento il proprio curriculum. L'inserimento dovrà essere curato in maniera da risultare semplice e, ove possibile, assistito (ad esempio prevedendo un aiuto alla compilazione di ciascuna voce e validando il più possibile ogni input), per venire incontro alle esigenze di ogni tipo di utente, anche poco avvezzo all'uso dei supporti elettronici.

* Ogni utente che abbia pubblicato il proprio curriculum potrà specificare anche una serie di informazioni riguardanti le proprie preferenze in ambito lavorativo. In particolare, dovrà essere possibile specificare:

  * Il tipo di impiego ricercato (ad esempio *part time*, a tempo indeterminato, di livello dirigenziale, ecc.; è possibile proporre una lista da cui spuntare una o più caratteristiche) e in che ambito/settore (ed esempio nel settore dell'informatica: anche qui è possibile prevedere una lista a scelta multipla).
  * La provincia/regione preferita per l'impiego.
  * La propria disponibilità a viaggiare in Italia o all'estero.
  * La propria disponibilità a soggiornare per brevi o lunghi periodi all'estero.
* Il sito dovrà prevedere due formati di visualizzazione per i curriculum:

  * La prima visualizzazione, detta *pubblica*, mostrerà solo alcune parti selezionate del curriculum, escludendo tutti i dati sensibili. In particolare, nella parte anagrafica verranno mostrati solo l'età e il sesso (i curriculum saranno anonimi in questa modalità!), mentre nella sezione istruzione verranno omessi tutti i dettagli sui titoli di studio tranne la denominazione del titolo stesso e la data di acquisizione. Le esperienze lavorative e la sezione capacità/conoscenze saranno invece riportate per intero.
  * La seconda visualizzazione, detta *completa*, conterrà invece tutti i dettagli del curriculum inserito dall'utente.
* In entrambi i casi, al curriculum sarà accodata una piccola scheda contenente le preferenze espresse dalla persona per l'eventuale impiego. Andrà curato molto l'aspetto visivo, perché la presentazione sia di facile lettura e simile a quella usata nei modelli di curriculum elettronici o cartacei reperibili in rete.

* Tutti gli utenti (anonimi o registrati) potranno condurre ricerche sui curriculum presenti nel sito in base ai seguenti criteri: età e sesso del candidato, titoli di studio (ad esempio per ricercare solo laureati o laureati in una particolare disciplina), lingue conosciute e preferenze lavorative (soprattutto luogo di lavoro e tipo di inquadramento). L'organizzazione della ricerca e le modalità per combinare i criteri suddetti sono a completa discrezione degli sviluppatori del sito, e la capacità di generare un sistema di ricerca efficace sarà valutata positivamente.

* I risultati delle ricerche saranno presentati in formato completo solo agli utenti registrati come aziende, mentre appariranno in formato pubblico (anonimo) a tutte le altre tipologie di utente (anonimi o registrati come candidati).

* Le aziende registrate avranno anche la possibilità di indicare dei criteri di ricerca "predefiniti", sempre costruiti in base alle modalità di ricerca realizzate nel sito, e salvarli nel proprio profilo (ad esempio, un'azienda potrebbe specificare e salvare una ricerca in cui si richiedono solo laureati in informatica disposti a lavorare nel Lazio). I risultati relativi potranno essere richiamati automaticamente (senza bisogno, cioè, di reimpostare ogni volta manualmente la ricerca) su un'apposita pagina. Il sistema terrà inoltre traccia della data in cui tale pagina è stata letta per l'ultima volta dall'utente-azienda, e lo avvertirà (ad esempio evidenziando il link relativo) nel caso in cui i risultati della ricerca siano cambiati rispetto all'ultima visita (*suggerimento: per realizzare questa funzionalità, sarà sufficiente confrontare le date di modifica di tutti i curriculum selezionati dalla ricerca con la data dell'ultimo accesso alla pagina*).

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
