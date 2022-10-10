---
titolo: CourseWeb
numero: 1
lingua: IT
anno: 2016
materia: IW
mainfile: Progetto_Master.rcp
thisfile: specifica
---

-------

{#specifiche}

*Dopo un decennio passato a cercare di inventarsi il modo
migliore per organizzare online le informazioni sugli insegnamenti
universitari, incrociando i desiderata di studenti, docenti, personale
amministrativo e delle varie normative al riguardo, il vostro docente ha
(momentaneamente) esaurito le idee, e quindi ha deciso di chiedere a voi di
realizzare il vostro "sito della didattica ideale", nella speranza di trovare
nuova ispirazione* *J*

Il sito *CourseWeb* rappresenta un catalogo di corsi
universitari online, semplificato ma rispondente ai principali requisiti di
trasparenza e completezza necessari per questo tipo di sito.

Per prima cosa, il sito dovrà supportare la **pubblicazione
bilingue** (italiano e inglese) di tutti i contenuti, requisito necessario
per l'internazionalizzazione. Dovrete quindi avere, per ogni vista, almeno due
template (uno in italiano e uno in inglese), progettare un sistema per inserire
le informazioni in entrambe le lingue nel back-office e uno per selezionare
quale lingua visualizzare nel front-office (*opzionalmente*, in assenza
del contenuto in una lingua, verrà sempre utilizzata l'altra lingua a
disposizione).

Ciascun corso dovrà essere necessariamente associato alle
informazioni che seguono. Qualunque altro extra, derivante dalla vostra
esperienza diretta, sarà apprezzato e magari di ispirazione per il futuro.

- Dati di base: nome, codice, settore scientifico-disciplinare
(SSD, ad esempio INF/01), lingua, semestre
- Lista docenti titolari
- Descrizione del corso: prerequisiti, obiettivi di apprendimento,
modalità d'esame, modalità di insegnamento, sillabo/programma analitico
(suddiviso per punti, in generale un punto per ciascun credito)
- Libri di testo (autore, titolo, volume, anno, editore, link web
se disponibile)
- Relazioni con altri insegnamenti: corsi propedeutici, corsi
mutuati, moduli (nel caso di corsi integrati)
- Collegamenti esterni (link): homepage del corso, risorse esterne,
forum/eLearning
- Note (ogni dettaglio per il quale non è prevista una voce
specifica)

*Opzionalmente* , gli *obiettivi di
apprendimento* citati nella lista possono essere strutturati secondo i
cosiddetti *descrittori di Dublino*, richiesti dai processi di
standardizzazione europei. I descrittori richiedono che gli obiettivi del corso
siano descritti sulla base dei risultati raggiunti in cinque aree: *Knowledge*
(quali conoscenze sono acquisite con il corso?), *Application* (come e
dove sono applicabili le conoscenze derivanti dal corso?), *Evaluation*
(se e in che modo le conoscenze acquisite possono aiutare nel valutare,
giudicare, comparare...?), *Communication* (se e in che modo gli studenti
possono trasmettere la conoscenza acquisita?), *Lifelong learning skills*
(il corso fornisce strumenti per continuare ad apprendere determinati
argomenti?).

Infine, anche le informazioni che seguono,
pur necessarie in un sistema realistico, nel nostro progetto saranno *opzionali*:
più ne aggiungete, più il vostro progetto avrà valore.

- Informazioni sull'erogazione: lista dei corsi di
laurea/curriculum per il quale il corso è fruibile, con indicazione del suo
valore in crediti (CFU) e della rispettiva tipologia (A, B, C, D, F)
- Materiale: una lista di elementi (con nome, descrizione e
dimensioni) scaricabili dal sito (come i PDF)

Per poter creare una "guida virtuale" sarà necessario che **il
sistema raccolga tutte queste informazioni anno per anno** . Ciò significa che
dovrete **predisporre un sistema col quale i dati appena esposti siano
associati a un anno accademico**, e che ne possano quindi esistere diverse
copie, per differenti anni accademici.

-------
{#operazioni}

- Il sistema dovrà prevedere tre tipologie di utenza: *anonimo* ,
  *docente* e *amministratore*. Solo gli amministratori potranno
  registrare nuovi utenti e assegnare loro un tipo.

- Tutti gli utenti, anche*anonimi,* potranno visualizzare la
  lista completa dei corsi, eventualmente filtrata per nome (anche parziale),
  codice, SSD, semestre, docente, lingua e corsi di laurea per i quali è
  disponibile (se avete inserito anche quest'ultima informazione). Cliccando su
  un corso si visualizzerà la sua scheda completa.

- Ovviamente, la scheda del corso andrà curata nei minimi dettagli,
  per rendere più chiara possibile la presentazione delle informazioni a esso
  relative. È possibile suddividere la scheda su più pagine, ricordando però che
  le informazioni essenziali devono essere raggiungibili con un numero basso di
  click.

- Gli amministratori del sito saranno gli unici a poter creare i
  corsi (inserendo almeno le informazioni essenziali: nome e codice) e assegnare
  loro i titolari.

- I docenti potranno inserire e modificare tutte le informazioni
  inerenti i soli corsi loro assegnati, mentre ovviamente gli amministratori
  potranno intervenire su tutti i corsi.

- Il back-office per i docenti dovrà essere ugualmente molto curato
  e intuitivo, considerato che anche l'utenza di questo lato del sistema sarà
  ampia e variegata. Sarà utile predisporre help contestuali che chiariscano il
  significato dei vari campi da valorizzare, ed eventualmente suddividere la
  compilazione della scheda di un corso in segmenti logici, stile *wizard*.
  Ove possibile (ad esempio nella selezione dei corsi in relazione, delle lingue,
  dei semestri, dei SSD, delle tipologie di credito, ecc.) si prevedano sempre campi
  con compilazione assistita o guidata.

- Il sito disporrà di un *log* in cui dovranno essere annotate
  tutte le operazioni svolte tramite il back-office (ad esempio "l'utente X ha
  modificato le informazioni del corso Y": decidete voi quale livello di
  dettaglio raggiungere in queste *entry*).

- Infine, per realizzare la "guida virtuale" introdotta più in
  alto, quello che ci si aspetta dal sito è che:
   1. le informazioni presentate nella scheda di ciascun corso siano, di default, quelle riferite all'ultimo anno accademico (che deve essere evidenziato nella scheda) per il quale il corso è stato aggiornato.
   2. all'utente sia offerta la possibilità di visionare la scheda di un corso relativa a uno degli altri anni accademici per i quali le informazioni sono disponibili (ad esempio tramite dei controlli sulla scheda del corso, oppure con opportuni filtri sull'elenco corsi generale)
   3. nel back office, le informazioni inserite o modificate dai docenti siano sempre quelle relative all'anno accademico corrente. Quando un docente cerca di modificare le informazioni di un corso e queste non sono già presenti per l'anno accademico corrente, verranno automaticamente copiate, come base, quelle dell'anno più prossimo, se presenti. *Opzionalmente*, gli amministratori potranno modificare anche le informazioni relative ad altri anni accademici.
