# Corso di Web Engineering
*Progetti A.A. 2022/2023* - Specifica 2

## Progetto "Web of Forms"

> Versione 2.0

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

Il sito *Web of Forms* rappresenta un pratico sistema per generare moduli formattati (lettere tipo, modulistica pubblica, ecc.) senza usare un word processor. L'idea è quella di sfruttare le potenzialità di HTML e dei template, che abbiamo imparato a usare per la generazione delle pagine web, anche per generare moduli stampabili o comunque esportabili in formati documentali comuni come il PDF. A questo scopo, daremo la possibilità agli utenti-autori di creare dei template per dei documenti tipo *(suggerimento: se partite da qualche documento già in vostro possesso nel formato di un word processor, potete usare la comune funzione "salva come HTML" per generare un draft iniziale del template)* e definire nome e tipo dei campi-placeholder in essi contenuti. Gli altri utenti del sito potranno quindi compilare tali campi e visualizzare (come HTML) o scaricare (come PDF) il documento formattato risultante. In particolare, il sistema dovrà gestire (con gli opportuni controlli) l'input di campi testo, numeri, e valori testuali scelti da un elenco. Per semplicità, omettiamo le tabelle (ad esempio le righe di una fattura), ma se provate a realizzarle sarà un grande valore aggiunto al realismo del vostro progetto! *Suggerimento: studiate bene come combinare un data model con un template caricato come stringa dal database nel vostro template engine, e come farne scrivere l'output su una seconda stringa. Per la conversione HTML-PDF, utilizzate il convertitore fornito da iText (https://itextpdf.com/en/products/itext-7/convert-html-css-to-pdf-pdfhtml, https://itextpdf.com/en/blog/technical-notes/pdfhtml-configuration-options).*

Di seguito sono illustrati schematicamente i contenuti e le
funzionalità minime che dovrebbero essere inseriti nel sito. Ovviamente, ogni
ulteriore raffinamento o arricchimento di queste specifiche aumenterà il valore
del progetto.
* Gli utenti potranno registrarsi nel sistema fornendo un nickname e un indirizzo email.

* Gli utenti, una volta autenticati, potranno caricare un template in tre fasi: 1) fornire il suo nome e la descrizione, 2) caricare il template HTML (caricamento di file e/o immissione diretta in un campo di testo), 3) fornire nome, tipo, testo descrittivo e nome interno (quello usato nel template e da inserire nel data model) per ciascuno dei campi previsti dal template.

* Un nuovo template sarà accessibile solo agli utenti amministratori (che supporremo semplicemente utenti con dei privilegi speciali) finchè uno di questi, provatolo, lo renderà pubblico.

* Gli autori di un template potranno eliminarlo o modificarlo in ogni momento. Il sistema dovrà tenere traccia della data di ultima modifica e di un contatore di versione da incrementare ad ogni modifica. Questa informazione dovrà essere chiaramente presentata agli utenti, in modo che sappiano se e quando il template è cambiato.

* Il processo di compilazione del modulo da parte degli utenti (*anche anonimi*) sarà il seguente:

  1. Gli utenti potranno scegliere un modulo da una lista. *Opzionalmente, per aiutare gli utenti nella scelta, potreste fornire un'anteprima del modulo compilandolo "al volo" con dati casuali associati a tutti i campi.*

  2. Una volta selezionato un modulo, il sistema dovrà generare e presentare all'utente un opportuno form in cui inserire i valori di tutti i campi richiesti dal modulo stesso. *In questa fase dovrete cercare di assistere il più possibile gli utenti nella compilazione. Cercate quindi di usare i controlli giusti per ogni tipo di campo e prevedete sempre la validazione, anche lato client.*

  3. Una volta inviati (e validati sul server) i valori dei campi, il server li combinerà con il template fornendo quindi all'utente una versione HTML finale del modulo compilato.

  4. Dopo aver esaminato il risultato, l'utente potrà scegliere di tornare indietro (al passo 2 per cambiare i valori dei campi o al passo 1 per scegliere un altro template), oppure scaricare il modello compilato sia in formato HTML (lo stesso visualizzato) che in formato PDF (convertito dall'HTML come spiegato sopra).

* L'utente dovrebbe inoltre essere in grado di scaricare, al passo 3, un file in formato JSON contenente la definizione del modulo compilato, cioè nome del template e lista dei campi con relativi valori. Il sistema dovrebbe prevedere una modalità in cui, caricando questo file al passo 1, si possa passare direttamente all'anteprima finale (passo 4), con la possibilità di tornare indietro e correggere le scelte, come già illustrato.

* Infine, gli utenti registrati dovranno essere in grado di inviare un feedback agli autori dei modelli sotto forma di messaggi testuali che potranno poi venir consultati dagli autori stessi, una volta autenticati, in un'apposita area personale.

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
