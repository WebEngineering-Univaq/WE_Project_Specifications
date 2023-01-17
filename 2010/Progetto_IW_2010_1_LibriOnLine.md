# Corso di Web Engineering
*Progetti A.A. 2010/2011* - Specifica 1

## Progetto "LibriOnLine"

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

Il sito *LibriOnLine* rappresenta una semplice interfaccia web per la gestione di una biblioteca.

La base di dati del sito conterrà informazioni riguardanti i volumi gestiti dalla biblioteca, gli utenti e i prestiti. In particolare, per ogni libro avremo il codice ISBN, il titolo, la lingua, l'editore, l'anno di pubblicazione, i nomi di tutti gli autori e, opzionalmente, una recensione o breve descrizione (come quella che spesso appare sulla copertina posteriore del libro o sul risvolto interno della sovracopertina). Una serie di *tag,* cioè parole o frasi brevi (ad. es. "botanica", "informatica", "programmazione","novità", ecc.), saranno associati a ciascun volume e potranno essere, ad esempio, estratte dal titolo del libro stesso o/e decise dai bibliotecari. Ogni libro avrà una durata massima di prestito (*default* un mese) e potrà essere presente in biblioteca anche in più copie. Infine, alcuni libri potranno essere contrassegnati "di libera lettura" ed accessibili direttamente online, sotto forma di file di testo o PDF scaricabili. Per ogni libro il sito dovrà generare una pagina descrittiva che contenga, opportunamente organizzate, tutte le informazioni di cui sopra.

Il sito dovrà prevedere tre tipologie di utenza: *bibliotecari* , utenti *registrati* e utenti *anonimi* . Andranno quindi previste opportune procedure di login. **Supporremo che** **solo i bibliotecari possano aggiungere nuovi utenti (compresi altri bibliotecari) nel sistema** (che sarà inizializzato con un singolo bibliotecario di default), ad esempio registrando un utente quando questo deposita le proprie credenziali presso la biblioteca. Ogni utente registrato avrà un profilo contenente i suoi dati anagrafici, l'indirizzo email e un numero di telefono.

Di seguito sono illustrati schematicamente i contenuti e le
funzionalità minime che dovrebbero essere inseriti nel sito. Ovviamente, ogni
ulteriore raffinamento o arricchimento di queste specifiche aumenterà il valore
del progetto.
* Tutti gli utenti dovranno poter ricercare i libri in base a: (1) il titolo o parte di esso, (2) i *tag* associati, (3) uno o più degli autori, (4) il codice ISBN. La completezza e la versatilità della funzione di ricerca, essenziale per un sito come questo, è lasciata all'iniziativa dei realizzatori. I risultati della ricerca dovranno essere presentati elencando i libri trovati, ciascuno con titolo, autori, editore e anno. Cliccando su ciascun libro si aprirà la corrispondente pagina di dettaglio.

* Nella pagina di dettaglio di un libro dovrà essere possibile cliccare sul nome di un autore avviando automaticamente una ricerca di tutti i libri da lui scritti (la sua bibliografia completa).

* Nella pagina di dettaglio di un libro, e in generale ovunque compaiano dei *tag*, dovrà essere possibile cliccare su uno di essi avviando automaticamente una ricerca di tutti i libri associati.

* A partire dalla pagina di dettaglio di un libro gli utenti dovranno poter conoscere il numero di copie presenti nella biblioteca e il numero di quelle attualmente libere (non in prestito). *Opzionalmente*, è possibile indicare all'utente, nel caso in cui tutte le copie siano in prestito, la data presunta di restituzione della prima copia, calcolata sulla base della sua data di prestito e della durata massima prevista.

* I bibliotecari, dopo aver cercato e individuato un particolare libro (usando le funzioni appena elencate), potranno registrarne il prestito a nome di uno degli utenti noti al sistema.

* Gli utenti registrati potranno visualizzare la lista dei volumi che hanno in prestito e le relative date di riconsegna. I libri la cui data di riconsegna è stata superata dovranno essere opportunamente evidenziati. Gli utenti potranno inoltre visionare lo storico dei volumi già presi in prestito e restituiti.

* I bibliotecari potranno, a partire dalla pagina di dettaglio di un libro, verificare i dati di tutti i prestiti, presenti o passati, relativi ad esso. Inoltre, i bibliotecari potranno visualizzare una lista (eventualmente paginata) di tutti i libri in prestito, tra cui saranno evidenziati quelli la cui data di riconsegna è stata superata.

* La homepage del sito dovrà mostrare alcune informazioni a carattere generale, ad esempio i libri maggiormente prestati e gli ultimi aggiunti alla biblioteca. Per gli utenti registrati, la homepage potrà anche segnalare i libri da riconsegnare a breve.

* Il sito dovrà essere provvisto di un adeguato *backoffice*, accessibile ai soli bibliotecari, tramite il quale inserire e modificare tutti i dati associati ai libri.

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
