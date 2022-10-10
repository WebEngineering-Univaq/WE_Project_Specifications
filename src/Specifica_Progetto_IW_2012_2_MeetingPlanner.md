---
titolo: MeetingPlanner
numero: 2
vestione: 1.0
lingua: IT
anno: 2012
materia: IW
mainfile: Progetto_Master.rcp
thisfile: specifica
---

-------
{#specifiche}

Il sito *MeetingPlanner* rappresenta un semplice sistema per organizzare riunioni.

Il sito sarà accessibile a tre tipologie di utenza: amministratori, organizzatori e partecipanti. I partecipanti, come vedremo, non saranno utenti registrati nel sistema, ma avranno la possibilità di accedere a delle parti specifiche dello stesso *su invito* e per un periodo di tempo limitato.

Il database del sito conterrà informazioni su tutte le riunioni in via di definizione e su quelle fissate in maniera definitiva. Il database, inoltre, conterrà una lista di sale riunioni disponibili. A ciascuna sala andranno associati il nome, l'ubicazione, la capienza e una serie di attrezzature, scelte tra una lista predefinita (ad es. proiettore di lucidi, aria condizionata, impianto microfonico, ecc.).

Gli organizzatori potranno creare
delle richieste di riunione specificando quando e dove la riunione potrebbe
svolgersi e invitando una serie di partecipanti. Questi ultimi riceveranno
l'invito via email e potranno usare il link presente nell'invito stesso per
connettersi e dichiarare la propria disponibilità. L'organizzatore, viste le
preferenze degli invitati, fisserà quindi la riunione definitiva e il sistema
provvederà a darne segnalazione a tutti i partecipanti.

-------
{#operazioni}

- La homepage del sito non dovrà presentare informazioni
  particolari: è sufficiente che permetta il login dell'amministratore e degli
  organizzatori registrati. Il resto del sito non deve essere accessibile agli
  utenti anonimi.
- La definizione di nuovi amministratori e organizzatori sarà di
  esclusiva competenza degli amministratori (andrà quindi previsto un
  amministratore predefinito per inizializzare il sistema).
- Gli amministratori potranno definire e modificare le sale
  riunioni disponibili, con le caratteristiche viste sopra.
- Un organizzatore potrà creare degli *inviti a riunione*
  specificando una descrizione della riunione stessa e indicando la lista dei
  partecipanti, con nome, cognome e indirizzo email. Dovranno essere inoltre allegate
  all'invito una serie di date, intervalli orari e corrispondenti luoghi
  ammissibili per la riunione, ad esempio "3/4/2014
  dalle 15 alle 18 in sala riunioni 2, oppure 7/6/2015
  dalle 9.30 alle 13.30 in via Garibaldi 12".
- L'organizzatore potrà chiedere al sistema di verificare la disponibilità,
  in una certa data/ora, di una sala riunioni dotata delle attrezzature desiderate.
  In questo caso il sistema, in base ai dati in suo possesso, indicherà
  all'organizzatore se e quali sale riunioni libere abbiano le caratteristiche
  richieste (compresa una capienza compatibile col numero di partecipanti
  invitati). L'organizzatore potrà quindi scegliere una delle proposte del
  sistema come luogo per la riunione nella data/ora corrispondente. In ogni caso,
  l'organizzatore non sarà vincolato, nella scelta del luogo della riunione, a
  specificare una delle sale riunioni gestite da sistema, ma potrà liberamente
  indicare qualsiasi altro luogo o indirizzo.
- Agli inviti a riunione potranno essere opzionalmente allegati uno
  o più file in formato testo o PDF, che l'organizzatore potrà caricare nel
  sistema.
- Dopo aver completato la definizione di un invito a riunione,
  l'organizzatore potrà chiedere al sistema di inviare per email gli inviti così
  definiti a tutti i partecipanti. *Suggerimento*: nella versione
  "giocattolo" di questa applicazione, potrete non realizzare veramente l'invio
  delle email e, ad esempio, stamparne solo il testo a video.
- Le email inviate ai potenziali partecipanti dovranno contenere la
  descrizione della riunione, il nome del suo organizzatore e un link da cliccare
  per esprimere la propria disponibilità alla partecipazione. Questo link,
  generato automaticamente, dovrà contenere i dati (ad esempio come parametri di
  una *query string* ) necessari al sistema per riconoscere la riunione in
  oggetto e l'utente invitato. *Suggerimento*: invece di includere
  direttamente dati come l'ID della riunione o il nome dell'invitato all'interno
  del link, rendendolo così molto fragile e soggetto a contraffazioni o
  manipolazioni, è più opportuno inserirvi una stringa alfanumerica univoca
  generata casualmente (del tipo http://\<URL_base_della_web_application\>/invite?ticket=AJCH5E35NCH36I45GS),
  alla quale nel database del sito vengano associate tutte le informazioni
  necessarie.
- All'utente invitato a una riunione, accedendo al sistema tramite
  il link inviatogli, verrà presentato un prospetto di tutte le combinazioni di
  data/ora/luogo possibili. L'utente potrà quindi spuntare le proposte per le
  quali si dichiara disponibile ed opzionalmente lasciare una nota testuale. L'utente
  potrà, inoltre, scaricare e consultare i documenti eventualmente allegati
  all'invito a riunione. Una volta espresse le proprie preferenze, l'utente non
  avrà più modo di modificarle, e il link usato per accedere al sistema non sarà più
  valido.
- L'organizzatore, in ogni momento, potrà controllare quali
  invitati hanno risposto e come. Il sistema, inoltre, calcolerà e mostrerà
  all'organizzatore le combinazioni di data/ora/luogo che sono compatibili con
  tutte le disponibilità comunicate dai partecipanti (se possibile) o con la
  maggioranza di essi.
- L'organizzatore potrà, infine, scegliere una data definitiva tra
  quelle proposte, fissando la riunione i cui dettagli verranno registrati nel
  sistema (questo sarà molto utile nel caso in cui il luogo scelto sia una delle
  sale riunioni, perché in questo modo il sistema potrà sapere che la sala
  rimarrà occupata in quel periodo di tempo)
- Nel momento in cui una riunione verrà definitivamente fissata, il
  sistema invierà una email di conferma a tutti i partecipanti che si erano
  dichiarati disponibili per la data/ora/luogo prescelti, e una email di scuse a
  tutti quelli che non potranno partecipare.  
