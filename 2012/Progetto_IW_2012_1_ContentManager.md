# Corso di Web Engineering
*Progetti A.A. 2012/2013* - Specifica 1

## Progetto "ContentManager"

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

Il sito *ContentManager* rappresenta un semplice sistema web per la creazione di mini-siti web statici senza l'ausilio di programmazione o stesura di codice HTML/CSS.

Ciascun mini-sito sarà identificato dalla username del suo realizzatore e avrà una struttura ad albero corrispondente alla struttura logica di navigazione del sito stesso, con una pagina HTML associata ad ogni nodo. Alla radice corrisponderà sempre la homepage del sito. Ad esempio:

Homepage  
\> About  
\> Interests  
\> Ski  
\> Photography  
\> Links  
\> Contacts

Tutte le pagine del mini-sito saranno identificate da un codice numerico, condivideranno la stessa intestazione e lo stesso piè di pagina e verranno visualizzate usando lo stesso foglio di stile.

Intestazione, piè di pagina e "corpo" delle pagine HTML del sito saranno inseriti nel database, mentre i fogli di stile saranno conservati nel file system. Il sistema disporrà di un insieme predefinito di fogli di stile, ciascuno associato a un nome e a una descrizione, le cui regole dovranno definire l'aspetto di tutti i principali elementi HTML (titoli, paragrafi, tabelle, liste, ecc.).

L'utente potrà richiedere la homepage del sito dell'utente *pippo* usandounaURL del tipo http://\<URL_base_della_web_application\>/site?user=\<username\>, mentre qualsiasi altra pagina con identificatore *X* dello stesso sito corrisponderà alla URL http://\<URL_base_della_web_application\>/site?user=*pippo* \&page=*X*

Per rispondere a queste URL, il sistema dovrà comporre dinamicamente la pagina web finale inserendo nel suo *body* quattro parti: l'intestazione comune a tutto il mini-sito, seguita dal contenuto della pagina richiesta, da un menu di navigazione (che potrà apparire in qualsiasi punto della pagina), e infine dal piè di pagina comune. Nella *head* della pagina così generata dovrà anche essere inserito un riferimento al foglio di stile scelto dall'utente.

Il menu di navigazione dovrà essere creato automaticamente in base alla struttura ad albero del sito, e conterrà almeno un link alla pagina padre di quella corrente (se non ci si trova nella homepage) e i link a tutte le pagine figlie dirette di quella corrente. Ad esempio, il menu nella pagina *Interests* della struttura vista prima dovrebbe contenere *Homepage* , *Ski* e *Photography*.

L'utente potrà anche caricare nel suo spazio web delle immagini, seguendo un'apposita procedura, e fino a una dimensione massima preimpostata (cioè finché la somma delle dimensioni delle immagini caricate è al di sotto di un certo limite). A ogni immagine sarà associato un identificatore numerico *Y* , in modo tale che la si possa recuperare (ad esempio all'interno di una pagina del mini-sito, con un tag img) usando una URL del tipo http://\<URL_base_della_web_application\>/image?user=*pippo* \&image=*Y. Suggerimento*: per creare una servlet che "scarica" un'immagine, come quella appena richiesta, e per capire come caricare un binario sul server, si vedano gli esempi sviluppati a lezione. Le immagini potranno essere conservate in directory separate per ciascun utente oppure nella stessa directory, ridenominandole in modo che i nomi non siano in conflitto. L'importante è che si possa poi mappare ciascun identificatore numerico sul file che gli corrisponde nel file system.

Di seguito sono illustrati schematicamente i contenuti e le
funzionalità minime che dovrebbero essere inseriti nel sito. Ovviamente, ogni
ulteriore raffinamento o arricchimento di queste specifiche aumenterà il valore
del progetto.
* Gli utenti che vogliono creare il proprio sito personale potranno registrarsi su *ContentManager* fornendo i propri dati e un indirizzo email valido (il controllo di validità, effettuabile inviando una email con un link da cliccare per la verifica dell'indirizzo, è *opzionale*) e ricevendo delle credenziali di accesso. Il sistema inizializzerà inoltre lo spazio web dell'utente creando la homepage (radice dell'albero di navigazione), contenente inizialmente un testo predefinito, e generando un'intestazione/piè di pagina di default per il mini-sito (magari contenenti il nome dell'utente, la data di creazione, ecc.).
* Accedendo al proprio spazio web, un utente registrato potrà vedere l'albero delle pagine già create. modificare ciascuna pagina, eliminarla o creare nuove pagine a qualsiasi livello dell'albero. All'atto della creazione di una nuova pagina, dopo aver specificato in che punto dell'albero dovrà apparire, l'utente potrà scegliere se iniziare con una pagina vuota o con una *pagina modello* già predisposta (vedi dopo).
* *Opzionalmente*, potrà anche essere offerta all'utente la possibilità di spostare un sottoalbero (cioè una pagina e tutte quelle da essa discendenti) in una posizione diversa dell'albero.
* L'utente registrato potrà inoltre modificare l'intestazione e il piè di pagina del suo mini-sito.
* L'editing delle pagine e dell'intestazione/piè di pagina dovrà essere effettuato tramite un editor WYSIWYG per HTML come ckeditor (http://ckeditor.com/) o tinymce (http://www.tinymce.com/).
* L'utente registrato potrà visualizzare la lista di tutte le immagini che ha caricato sul sito, eliminarle o aggiungerne di nuove. Nella lista dovrà essere in evidenza il link (costruito come visto sopra) da utilizzare per incorporare o scaricare l'immagine stessa.
* L'utente registrato potrà visualizzare la lista dei fogli di stile predefiniti nel sistema e scegliere quello da applicare al proprio sito.
* Infine, gli utenti più "prodighi" potranno rendere pubbliche una o più pagine da loro realizzate marcandole come *pagine modello*, in modo che altri utenti possano usarle come base per le pagine del proprio mini-sito, come descritto sopra.
* Nella homepage dell'applicazione saranno presentati, oltre ai controlli per registrarsi e fare login, i nomi degli ultimi mini-siti creati, in modo che tutti gli utenti, anche anonimi, possano accedere alla homepage dei mini-siti di proprio interesse e poi navigarvi usandone il menu o gli eventuali link interni.

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
