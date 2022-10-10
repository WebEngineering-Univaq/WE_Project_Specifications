# Corso di Web Engineering
*Progetti A.A. 2015/2016* - Specifica 2

## Progetto "BiblioManager"

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

Il sito *BiblioManager*rappresenta un semplice gestore di catalogo bibliografico online.

Il catalogo conterrà una serie di *pubblicazioni* , ciascuna delle quali caratterizzata da un *titolo* , una lista di *autori* , un *editore* , una serie di *metadati* (vedi dopo) e, opzionalmente, una *descrizione* testuale (sunto del contenuto o presentazione della pubblicazione), un *indice* (composto dai titoli dei vari capitoli/sezioni della pubblicazione, numerati e ordinati) e una serie di *sorgenti* tramite le quali poter accedere alla pubblicazione o a parti di essa. Ciascuna sorgente sarà caratterizzata da un *tipo* , una *URI* , da un *formato* e da una *descrizione*. Esempi di sorgenti valide potrebbero essere i seguenti:

* tipo="immagine", URI="http://server.net/cover.jpg", formato="image/jpeg", descrizione="copertina"

* tipo="download", URI="http://server.net/book.pdf", formato="application/pdf", descrizione="versione elettronica gratuita"

* tipo="acquisto", URI="http://www.amazon.it/xyz", formato="cartaceo, copertina rigida", descrizione="acquista online"

Per quanto riguarda invece i *metadati* , questi saranno costituiti (almeno) dalle seguenti informazioni: codice *ISBN* , numero di *pagine* , *lingua* , *data* di pubblicazione, lista delle *ristampe* (numero e data) e *parole chiave* identificative (zero o più).

Di seguito sono illustrati schematicamente i contenuti e le
funzionalità minime che dovrebbero essere inseriti nel sito. Ovviamente, ogni
ulteriore raffinamento o arricchimento di queste specifiche aumenterà il valore
del progetto.
* Il sistema prevedrà due tipologie di utenza: *attiva* e *passiva* . L'utenza passiva potrà solo consultare il catalogo, quella attiva anche modificarlo. Gli utenti *anonimi* potranno vedere solo la homepage del sito, ma dovranno necessariamente effettuare la login per poter accedere a tutti gli altri contenuti.

* Gli utenti passivi potranno registrarsi nel sito tramite un modulo in cui inseriranno i loro dati anagrafici, un indirizzo email (che verrà usato anche come username) e, ovviamente, la password scelta. Gli utenti attivi potranno "promuovere" qualsiasi utente passivo già registrato rendendolo a sua volta attivo. Il sistema dovrà quindi prevedere un utente attivo iniziale di default preregistrato.

* Nella homepage del sito saranno elencate le ultime pubblicazioni inserite e quelle aggiornate di recente. Sarà inoltre presentata una lista degli utenti attivi più "collaborativi" (cioè quelli che hanno inserito più pubblicazioni) e, cliccando sul loro nome, si potrà visualizzare la lista delle pubblicazioni che hanno inserito (*opzionalmente* formattata come i risultati di ricerca descritti nei punti successivi).

* Gli utenti potranno consultare il catalogo completo tramite una visualizzazione paginata che elenca tutte le pubblicazioni con titolo, autori, editore e anno di pubblicazione. Dovrà essere possibile ordinare questa lista almeno in base a titolo e anno (l'ordinamento per titolo sarà il default) e *opzionalmente* in base a tutte le altre colonne. Selezionando una pubblicazione, verrà visualizzata la sua scheda bibliografica completa.

* Dovrà essere ovviamente presente anche un sistema di ricerca, per permettere agli utenti di trovare le pubblicazioni di loro interesse utilizzando vari criteri, senza necessariamente scorrere la lista completa del punto precedente. Le chiavi di ricerca da supportare *necessariamente* dovranno essere ISBN, titolo, autore, editore, anno di pubblicazione, parole chiave, lingua, presenza di sorgenti di tipo "download" (quindi pubblicazioni gratuite). L'utente dovrà poter specificare uno o più dei suddetti criteri, che verranno considerati in AND. La lista dei risultati ottenuti dalla ricerca avrà la stessa forma e funzionalità della lista completa del catalogo illustrata al punto precedente. Ovviamente, qualsiasi miglioramento a questa funzionalità di ricerca, ad esempio con l'aggiunta di ulteriori criteri, aumenterà il valore del progetto.

* La scheda bibliografica di una pubblicazione dovrà presentare, nella maniera più chiara e meglio organizzata possibile, tutte le informazioni legate ad essa. Se necessario, sarà possibile avvalersi anche di sotto-pagine accessibili dalla scheda bibliografica principale per organizzare meglio tali informazioni. Le sorgenti di tipo immagine, se presenti tra i dati della pubblicazione, dovranno venir usate per creare una galleria di immagini visualizzabili nella scheda bibliografica o in un'opportuna sotto-pagina. In particolare, supporremo che una sorgente di tipo immagine con descrizione "copertina" venga caricata, se disponibile, e mostrata come illustrazione all'inizio della scheda bibliografica, magari accanto al titolo.

* Sarà presente anche una (immancabile) parte social, tramite la quale gli utenti (anche quelli passivi) potranno *consigliare* la lettura di una pubblicazione o inserirne una *recensione* testuale. Il numero di "consigli" dati alla pubblicazione sarà mostrato nella scheda bibliografica insieme alla recensione più recente, e sarà possibile accedere a una sotto-pagina contenente la lista completa (*opzionalmente* paginata) delle recensioni. Queste ultime, tuttavia, non saranno visibili immediatamente dopo il loro inserimento, ma saranno soggette a moderazione, come descritto più avanti.

* Agli utenti attivi verrà data la possibilità di modificare la lista delle pubblicazioni. Dovrete quindi predisporre delle opportune maschere di input tramite le quali inserire, modificare e cancellare ogni dettaglio delle pubblicazioni stesse. In particolare, le funzioni di modifica e cancellazione di una pubblicazione saranno accessibili tramite opportuni link visibili direttamente nella scheda bibliografica quando l'accesso è effettuato da un utente attivo. Allo stesso modo, i link per l'inserimento potranno essere mostrati agli utenti attivi all'inizio della lista/catalogo generale.

* Gli utenti attivi vedranno inoltre, sempre accedendo a una scheda bibliografica, quante nuove recensioni (per quella pubblicazione) sono in attesa di essere approvate. Tali recensioni saranno visibili, nel loro caso, insieme alle recensioni già approvate, ma opportunamente evidenziate come "in attesa di moderazione" e dotate di un link tramite il quale approvarle, rendendole visibili a tutti, o eliminarle definitivamente.

* Per tener traccia delle modifiche effettuate alla bibliografia dai vari utenti attivi, il sistema dovrà mantenere una "storia" di ciascuna scheda bibliografica. Ogni *entry* di tale storia conterrà un *timestamp*, il nome dell'utente e una descrizione della modifica. Potete scegliere voi il dettaglio di questa descrizione: di base, sono accettabili anche descrizioni del tipo "ha modificato la pubblicazione", "ha inserito la pubblicazione", "ha approvato una recensione dell'utente X", ecc. La storia, opportunamente formattata, sarà accessibile a tutti gli utenti attivi sempre a partire dalla corrispondente scheda bibliografica.

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
