---
titolo: SondaggiOnLine
numero: 2
vestione: 1.0
lingua: IT
anno: 2011
materia: IW
mainfile: Progetto_Master.rcp
thisfile: specifica
---

-------

{#specifiche}

Il sito Sondaggi*OnLine* rappresenta un semplice
sistema per condurre sondaggi tramite web.

Ciascun sondaggio, definibile dall'amministratore del
sistema, avrà un titolo e una descrizione testuale, e sarà costituito da una
sequenza arbitraria di quesiti. Un quesito sarà caratterizzato da un testo
descrittivo, e potrà prevedere quattro tipologie di risposta:

1) un
   numero (che potrebbe ad esempio rappresentare un "livello")
   all'interno da un determinato intervallo (ad esempio "indicare la qualità
   del prodotto, da 0 (orribile) a 10 (meraviglioso)");

2) una
   risposta singola, scelta tra una serie di possibili risposte predefinite (ad
   esempio: "quale di questi cibi ti piace di più? (selezionare una sola
   risposta): a. il gelato, b. la pizza");

3) più
   risposte selezionate tra una serie di possibili risposte predefinite (ad
   esempio: "quale di questi cibi ti piace? (selezionare una o più risposte):
   a. il gelato, b. la pizza"),

4) una
   risposta testuale libera, con una lunghezza massima (in caratteri, ad esempio
   "inserire un commento, max 500 caratteri" ).

Supporremo che il sistema disponga di una base di dati
precostituita composta da dati anagrafici e indirizzi email della popolazione
che può essere sottoposta a sondaggio. I soggetti selezionati per la
compilazione di un particolare sondaggio potranno accedere al questionario
tramite un link specifico, che sarà inviato loro per email. Questo link sarà
generato automaticamente e conterrà una chiave (ad esempio una serie di numeri
casuali) univoca che il sistema dovrà identificare come l'associazione tra il
soggetto e il sondaggio (ad esempio
http://mioserver.com/poll?accesskey=JD83MG92Y6MSK4). Cliccando sul link, quindi,
verrà automaticamente mostrato nel browser il sondaggio "intestato"
al soggetto corrispondente.

-------

{#operazioni}

- La homepage del sito non dovrà presentare informazioni
  particolari: è sufficiente che permetta il login dell'amministratore. Il resto
  del sito deve essere inaccessibile agli utenti anonimi.

- L'amministratore potrà definire i sondaggi e modificarli, ma solo
  se non sono già in fase di compilazione. Ciascun quesito dovrà avere la
  struttura descritta in precedenza, e potrà essere indicato come obbligatorio o
  opzionale. I quesiti saranno suddivisi in gruppi, ciascuno dei quali avrà una
  sua descrizione testuale introduttiva.

- Dovrà essere possibile definire semplici regole di correlazione
  tra quesiti, nel seguente modo. Per ciascuna risposta di un quesito a risposta
  singola (tipo 2), sarà possibile specificare una sequenza di quesiti (tra
  quelli già inseriti nello stesso sondaggio) che devono essere compilati solo
  nel caso in cui quella risposta sia scelta (ad esempio, il campo di input "Nazione
  di nascita" è obbligatorio, ma deve essere compilato solo se si risponde "No"
  alla domanda "Siete italiani?").

- Quando l'amministratore del sistema deciderà di attivare un dato
  sondaggio, dovrà anche indicare la dimensione del campione a cui sottoporlo, il
  sesso (maschile, femminile o entrambi) e l'intervallo di età. Verrà inoltre
  fissato un intervallo di date all'interno del quale il sondaggio dovrà essere
  compilato. Il sistema selezionerà quindi casualmente dalla sua base di dati il
  numero richiesto di soggetti aventi le caratteristiche specificate e invierà
  loro un'email (*potete simulare questo invio, non è necessario che lo
  facciate veramente!*) indicando il titolo del sondaggio, la sua descrizione,
  le date in cui potrà essere compilato e fornendo il link per la sua compilazione,
  generato come descritto sopra.

- All'utente, che accederà al sito tramite il link in suo possesso,
  il sondaggio andrà presentato opportunamente formattato, *opzionalmente*
  prevedendone la suddivisione su più pagine. Sarà necessario scegliere i
  controlli HTML più opportuni per garantire l'input richiesto dal tipo di
  quesito, cercando di minimizzare le possibilità di errore. E' possibile
  prevedere controlli avanzati lato client, ma gli stessi controlli dovranno
  essere sempre ripetuti sul server. Per quel che riguarda le regole di
  correlazione tra quesiti discusse sopra, queste dovranno almeno essere
  utilizzate per generare automaticamente opportuni avvertimenti testuali (ad
  esempio, "se rispondete Y a questa domanda, allora non dovrete rispondere
  alla domanda N").

- Una volta terminata la compilazione, l'utente invierà le sue
  risposte al sistema. Quest'ultimo non permetterà di proseguire con la
  sottomissione del modulo nel caso in cui si verifichino errori: ad esempio, input
  non corretto rispetto ai vincoli imposti dal quesito, quesito obbligatorio
  senza risposta, ecc. Il server dovrà anche implementare le verifiche corrispondenti
  alle regole di correlazione, ad esempio ignorando il valore di una risposta
  (quindi omettendo anche gli altri controlli su di essa: obbligatorietà, ecc.)
  se una regola la disabilita (con riferimento all'esempio fatto in precedenza,
  il sistema non controllerà che il campo "Nazione di nascita" sia stato
  compilato, sebbene obbligatorio, e non ne salverà il valore nel caso in cui si
  sia risposto "Sì" alla domanda "Siete italiani?").

- Nel caso in cui le risposte fornite dall'utente siano coerenti
  con le regole di compilazione, il sistema provvederà a registrarle e a
  disabilitare l'accesso al sondaggio tramite il link originariamente fornito
  all'utente, in modo che non possa più compilarlo.

- L'amministratore potrà, in ogni momento, leggere una serie di
  statistiche ricavate da ciascun sondaggio. E' possibile inserire ogni tipo di
  statistica sensata, ma le seguenti dovranno necessariamente essere realizzate:

(a) numero e percentuale
(rispetto al campione) di utenti che hanno risposto al sondaggio;

(b) per le domande a
risposta multipla (tipo 2 e 3), e per quelle a risposta numerica (tipo 1),
distribuzione percentuale delle risposte degli utenti rispetto a ciascuna delle
opzioni proposte;

(c) per le domande a
risposta testuale libera (tipo 4), lunghezza media delle stesse;

(d) per ogni domanda
non obbligatoria, percentuale degli utenti che hanno deciso di rispondere.  
