---
titolo: Internship tutor
numero: 1
versione 1.0
lingua: IT
anno: 2017
materia: IW
mainfile: Progetto_Master.rcp
thisfile: specifica
---

-------

{#specifiche}

Il sito *Internship tutor* rappresenta un sistema web
per la gestione dell'iter completo dei tirocini universitari. In particolare,
il sistema permetterà alle aziende di registrarsi e, previa approvazione
dell'amministratore, convenzionarsi e pubblicare autonomamente proposte
(dettagliate) di tirocinio. Gli studenti potranno liberamente accedere a tali
proposte, contattare l'azienda, stampare tutta la documentazione necessaria per
l'avvio e la conclusione del tirocinio stesso, e infine fornire il proprio
parere sull'azienda e il tirocinio.

Un'azienda dovrà essere registrata con i seguenti dati:
ragione sociale/nome, indirizzo della sede legale, codice fiscale/partita IVA,
nome e cognome del legale rappresentante, nome, cognome, telefono e indirizzo
email della persona responsabile della convenzione per i tirocini, foro
competente (città alla cui sede giudiziaria le parti dovranno rivolgersi in
caso di disputa legale). Questi dati sono deducibili dallo schema di
convenzione quadro che trovate all'indirizzo
http://www.disim.univaq.it/didattica/risorsa-1632.

Un'offerta di tirocinio dovrà invece specificare
obbligatoriamente il luogo in cui si svolgerà (che può essere anche presso la
sede del tirocinante, nel caso si possa svolgere in remoto), gli orari (se
previsti), il numero di mesi/ore del tirocinio, gli obiettivi (generici), le
modalità (lavoro nel team aziendale, lavoro freelance in remoto, ecc.),
eventuali rimborsi spese o altre facilitazioni previste. Questi dati sono
deducibili dalle prime pagine del progetto formativo che trovate all'indirizzo
http://www.disim.univaq.it/didattica/risorsa-2767.

Lo studente, se interessato a iniziare un tirocinio, dovrà anch'esso
registrarsi (o aggiornare la propria registrazione), inserendo i dati previsti
dalla prima pagina del progetto formativo, cioè nome, data e luogo di nascita,
residenza, codice fiscale, telefono, corso di laurea al quale è iscritto, e
indicando se è portatore di handicap.

All'atto dell'attivazione del tirocinio, lo studente dovrà infine
indicare tutti gli altri dati previsti dalle prime tre pagine del progetto
formativo *che non siano già deducibili dalla registrazione dell'azienda, dai
suoi dati personali, e dall'offerta di tirocinio*.

Alla fine del tirocinio, l'azienda dovrà invece inserire le
informazioni necessarie a completare la penultima pagina del progetto
formativo, quindi le ore di tirocinio effettivamente svolte, la descrizione
dettagliata dell'attività e giudizio finale.

-------

{#operazioni}

- Il sistema dovrà prevedere quattro tipologie di utenza: *anonimo* ,
  *studente, azienda* e *amministratore*.

- Le aziende potranno registrarsi liberamente fornendo i dati
  appena elencati. All'atto della registrazione l'azienda non sarà già visibile
  agli studenti né potrà inserire annunci, ma verrà notificata all'amministratore
  che avrà cura di completare il processo di convenzionamento.

- L'amministratore, a fronte di una richiesta di convenzionamento,
  verificherà (manualmente, quindi deve semplicemente poterli visualizzare) i
  dati inseriti e genererà automaticamente il documento di convenzione quadro (http://www.disim.univaq.it/didattica/risorsa-1632).
  *Suggerimento: potete semplicemente trasformare il documento indicato in un
  template HTML, che riempirete automaticamente con i dati forniti dall'azienda,
  permettendone poi la stampa dal browser. Opzionalmente, potete provare a
  generare un PDF direttamente o convertendo l'HTML generato.* Una volta che
  la convenzione sarà stata firmata e riconsegnata (passo manuale: assumete che
  avvenga), l'amministratore dovrà caricare una scansione della convenzione
  firmata (ad esempio un PDF), associandola ai dati dell'azienda, e *abilitare*
  l'azienda stessa.

- Un'azienda abilitata potrà pubblicare offerte di tirocinio
  direttamente dal web, usando le credenziali fornite durante il processo di
  registrazione, e specificando tutte le informazioni previste.

- Gli studenti potranno inizialmente accedere al sito in maniera
  anonima. In questo modo potranno consultare la lista delle aziende
  convenzionate e la bacheca delle offerte di tirocinio. Su quest'ultima dovrà
  essere possibile eseguire ricerche con criteri quali la città sede del
  tirocinio, la durata minima/massima, parole chiave contenute negli obiettivi,
  ecc.

- Quando uno studente deciderà di aderire a un'offerta, gli verrà
  richiesto di effettuare la login (se già registrato) o registrarsi, fornendo i
  dati descritti nei paragrafi iniziali di questa specifica. Il candidato dovrà
  inoltre specificare il numero di crediti richiesti e i dati (nome ed email) del
  tutore prescelto. A questo punto il sistema invierà una email di richiesta al
  referente per i tirocini dell'azienda (specificato in fase di registrazione) e
  una al tutore designato, contenenti entrambe gli estremi dell'offerta e tutti i
  dati del candidato. *Suggerimento: usate un template per compilare il testo
  di questa mail. Non è necessario che la vostra applicazione effettui veramente
  l'invio, basta che lo simuli, ad esempio scrivendo l'email su un file.*

- Le aziende avranno a disposizione un pannello riepilogativo con
  la lista delle offerte da esse pubblicate. Avranno la possibilità di chiudere
  un avviso (cioè renderlo invisibile agli studenti) e visualizzare la lista
  degli studenti che si sono candidati per ogni specifico avviso.

- Alla fine di una fase di "contrattazione" esterna al nostro sito,
  durante la quale il candidato e l'azienda potranno discutere i dettagli del
  tirocinio, l'azienda potrà bocciare o approvare la candidatura con appositi
  controllo messi a disposizione dalla "lista candidati" appena descritta.

- Nel caso in cui la proposta venga accettata, l'azienda dovrà
  comunicare al sistema anche il periodo di effettuazione del tirocinio, e questo
  genererà automaticamente le prime tre pagine del progetto formativo (http://www.disim.univaq.it/didattica/risorsa-2767),
  permettendone il download sia all'azienda che al tirocinante. *Suggerimento:
  anche qui potete procedere come nel caso della generazione automatica della
  convenzione vista sopra.*Seguirà la solita fase offline, alla fine della
  quale uno dei due soggetti dovrà caricare nel sistema, come al solito, una
  scansione del progetto debitamente firmato e timbrato.

- Arrivati al termine del tirocinio, come definito nel passo
  precedente, all'azienda verrà notificata la necessità di compilare il resoconto
  finale. Come al solito questa procedura sarà effettuata online, e produrrà un
  documento simile alla penultima pagina del progetto formativo, che lo studente
  potrà scaricare, stampare e portare in segreteria.

- *Opzionalmente*, terminato il tirocinio, lo studente avrà la
  possibilità di votare per l'azienda esprimendo una valutazione di gradimento
  nella classica scala 0-5 stelle (che potrà essere in qualche modo associata al
  profilo pubblico dell'azienda)

- *Opzionalmente*, l'amministratore potrà visualizzare alcune
  statistiche interessanti quali i tutori più richiesti, le aziende che ospitano
  più tirocinanti, le aziende con valutazioni migliori/peggiori e così via.  
