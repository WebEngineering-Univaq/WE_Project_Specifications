# Corso di Web Engineering
*Progetti A.A. 2009/2010* - Specifica 1

## Progetto "TravelWeb"

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

Il sito *TravelWeb* rappresenta una semplice agenzia di viaggi online. Il sito dell'agenzia presenta informazioni turistiche generali su una serie di *destinazioni* sparse per il mondo, dando anche agli utenti la possibilità di esprimere i loro pareri su ciascuna di esse. Alle destinazioni, che sono organizzate in maniera da renderne semplice la ricerca e la navigazione, sono associate delle *offerte di viaggio*, il vero prodotto messo in vendita dall'agenzia.

Una *destinazione* può rappresentare qualsiasi sito di interesse turistico, ad esempio un museo, un parco, una città, una regione, o addirittura un'intera nazione. Chiaramente, una destinazione potrà includerne altre più specifiche o essere inclusa a sua volta da altre destinazioni più generali (ad esempio Italia \> Abruzzo \> L'Aquila \> Basilica di Collemaggio).

Di seguito sono illustrati schematicamente i contenuti e le
funzionalità minime che dovrebbero essere inseriti nel sito. Ovviamente, ogni
ulteriore raffinamento o arricchimento di queste specifiche aumenterà il valore
del progetto.
* Il sito dovrà prevedere tre tipologie di utenza: amministratori, utenti registrati e utenti anonimi. Andranno quindi previste procedure di registrazione e login.

* Il sito dovrà collezionare delle statistiche sulle destinazioni ricercate e visualizzate (ma non necessariamente acquistate sotto forma di offerta di viaggio) dai visitatori del sito. Queste statistiche saranno utilizzate, in particolare, per la creazione della homepage, nella quale figureranno in evidenza (in maniera da potervi accedere rapidamente) le ultime destinazioni consultate nonché quelle più consultate.

* Ad ogni destinazione dovrà essere associata una scheda illustrativa contenente (almeno):

  * Una descrizione a turistica della destinazione.
  * Una lista di collegamenti a siti internet di approfondimento.
  * Una galleria di immagini (sulla stessa pagina o su una pagina collegata).
  * Una lista dei punti di particolare interesse presenti nell'ambito della destinazione (ad esempio monumenti, località da visitare, ecc.). Questa lista dovrà necessariamente contenere *almeno* tutte le destinazioni presenti nel sito che siano logicamente incluse in quella corrente. Ad esempio, se nel sito fossero presenti come destinazioni sia l'Abruzzo che L'Aquila, la pagina del primo dovrebbe citare quella della seconda come punto di interesse. In questo caso, sarà possibile cliccare sul luogo di interesse per saltare alla sua scheda specifica.
* A ciascuna destinazione potranno venire associate delle offerte di viaggio ad essa inerenti. Le offerte avranno un periodo di validità, un prezzo (per persona), e ovviamente una descrizione. Gli utenti registrati potranno comunicare il proprio interesse in un'offerta, venendo inseriti quindi in una lista di potenziali adesioni (visibile ai soli amministratori, ad esempio per contattare telefonicamente gli interessati).

* Gli utenti registrati avranno la possibilità di pubblicare commenti riguardanti le destinazioni, e dare un voto a ciascuna di esse. I commenti potranno essere mostrati nella scheda della corrispondente destinazione o in una pagina specifica ad essa collegata. Il voto medio attribuito dagli utenti (insieme al numero totale di voti pervenuti) sarà invece sempre presente sulla scheda.

* Una caratteristica importante di ciascuna destinazione dovrà essere la sua *classificazione* . Per classificare le destinazioni utilizzeremo una struttura generale a *tag* , dove il *tag* è una parola o breve frase dal significato evidente (ad esempio "città", "città d'arte", "località balneare", "nazione", "isola", "museo"). Gli amministratori e gli utenti registrati sul sito potranno definire dei *tag* assegnandoli alle destinazioni. Tuttavia, i *tag* attribuiti dagli amministratori saranno prioritari (ad esempio nel processo di ricerca descritto dopo) ed evidenziati in maniera diversa nella classificazione di ciascuna destinazione, in quanto più "ufficiali". Gli amministratori saranno inoltre gli unici a poter cancellare un *tag* da una destinazione.

* Infine, il motore di ricerca costituirà una parte essenziale del sito. Dovrà essere possibile effettuare almeno le tipologie di ricerca che seguono (ogni altra forma di ricerca realisticamente utile inserita nel sito sarà valutata positivamente):

  * Ricerca di destinazioni in base ai *tag* ad esse associati.
  * Ricerca di destinazioni in base al loro nome (o parte di esso).
  * Ricerca di destinazioni in base alla disponibilità di offerte di viaggio valide in un determinato periodo e/o con una specifica soglia di prezzo.
  * Ricerca di offerte di viaggio (per qualsiasi destinazione) valide in un determinato periodo e/o con una specifica soglia di prezzo.
* Il sito dovrà essere provvisto di un adeguato backoffice, accessibile dai soli amministratori, tramite il quale inserire e modificare i dati associati alle destinazioni e alle offerte.

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
