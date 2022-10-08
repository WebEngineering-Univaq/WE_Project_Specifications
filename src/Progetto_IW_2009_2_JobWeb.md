---
titolo: JobWeb
numero: 2
vestione: 1.0
lingua: IT
anno: 2009
materia: IW
mainfile: Progetto_Master.rcp
thisfile: specifica
---

-------
{#specifiche}

Il sito *JobWeb* rappresenta un semplice portale per lo
scambio di proposte e offerte di lavoro. Su questo sito i candidati potranno
pubblicare e aggiornare il proprio curriculum e indicare le proprie preferenze
in ambito lavorativo, mentre le aziende potranno ricercare un profilo adatto ai
loro interessi. Tuttavia, solo le aziende accreditate potranno visionare
completamente i curriculum dei candidati e contattarli.

L'oggetto fondamentale da memorizzare nel sito sarà quindi
il *curriculum* . La forma e i contenuti di un curriculum professionale
possono essere dedotti cercando e visionando alcuni tra i molti esempi
disponibili online (ad esempio, http://europass.cedefop.europa.eu/europass/home/hornav/Downloads/EuropassCV/CVTemplate.csp).
In generale, comunque, è necessario che siano presenti almeno le sezioni
seguenti:

- Anagrafica (nome, cognome, data di nascita, ecc.; non dimenticate
  i contatti: email, telefono, posta...). Dovrà essere prevista anche la
  pubblicazione di una foto.

- Istruzione (titoli di studio maturati, con data, istituzione
  erogante ed eventuale voto).

- Esperienze lavorative (datore di lavoro, incarico e periodo di
  ogni esperienza).

- Capacità/conoscenze (ad esempio, descrizione delle proprie
  conoscenze tecniche), all'interno delle quali ha particolare rilievo la lista
  delle lingue scritte e/o parlate.

-------
{#operazioni}

- Il sito dovrà prevedere tre tipologie di utenza: amministratori,
  utenti registrati e utenti anonimi. Gli utenti registrati dovranno essere a
  loro volta distinti in *candidati* (in cerca di lavoro) e *aziende*
  (in cerca di personale). Andranno quindi previste procedure di registrazione e
  login.

- Ogni candidato registrato potrà inserire e modificare in ogni
  momento il proprio curriculum. L'inserimento dovrà essere curato in maniera da
  risultare semplice e, ove possibile, assistito (ad esempio prevedendo un aiuto
  alla compilazione di ciascuna voce e validando il più possibile ogni input),
  per venire incontro alle esigenze di ogni tipo di utente, anche poco avvezzo
  all'uso dei supporti elettronici.

- Ogni utente che abbia pubblicato il proprio curriculum potrà
  specificare anche una serie di informazioni riguardanti le proprie preferenze
  in ambito lavorativo. In particolare, dovrà essere possibile specificare:
   - Il tipo di impiego ricercato (ad esempio *part time*, a
  tempo indeterminato, di livello dirigenziale, ecc.; è possibile proporre una
  lista da cui spuntare una o più caratteristiche) e in che ambito/settore (ed
  esempio nel settore dell'informatica: anche qui è possibile prevedere una lista
  a scelta multipla).
   - La provincia/regione preferita per l'impiego.
   - La propria disponibilità a viaggiare in Italia o all'estero.
   - La propria disponibilità a soggiornare per brevi o lunghi periodi all'estero.

- Il sito dovrà prevedere due formati di visualizzazione per i   curriculum:
   - La prima visualizzazione, detta *pubblica*, mostrerà solo
  alcune parti selezionate del curriculum, escludendo tutti i dati sensibili. In
  particolare, nella parte anagrafica verranno mostrati solo l'età e il sesso (i
  curriculum saranno anonimi in questa modalità!), mentre nella sezione
  istruzione verranno omessi tutti i dettagli sui titoli di studio tranne la
  denominazione del titolo stesso e la data di acquisizione. Le esperienze
  lavorative e la sezione capacità/conoscenze saranno invece riportate per
  intero.
   - La seconda visualizzazione, detta *completa*, conterrà
  invece tutti i dettagli del curriculum inserito dall'utente.

- In entrambi i casi, al curriculum sarà accodata una piccola
  scheda contenente le preferenze espresse dalla persona per l'eventuale impiego.
  Andrà curato molto l'aspetto visivo, perché la presentazione sia di facile
  lettura e simile a quella usata nei modelli di curriculum elettronici o
  cartacei reperibili in rete.

- Tutti gli utenti (anonimi o registrati) potranno condurre
  ricerche sui curriculum presenti nel sito in base ai seguenti criteri: età e
  sesso del candidato, titoli di studio (ad esempio per ricercare solo laureati o
  laureati in una particolare disciplina), lingue conosciute e preferenze
  lavorative (soprattutto luogo di lavoro e tipo di inquadramento). L'organizzazione
  della ricerca e le modalità per combinare i criteri suddetti sono a completa
  discrezione degli sviluppatori del sito, e la capacità di generare un sistema
  di ricerca efficace sarà valutata positivamente.

- I risultati delle ricerche saranno presentati in formato completo
  solo agli utenti registrati come aziende, mentre appariranno in formato
  pubblico (anonimo) a tutte le altre tipologie di utente (anonimi o registrati
  come candidati).

- Le aziende registrate avranno anche la possibilità di indicare
  dei criteri di ricerca "predefiniti", sempre costruiti in base alle modalità di
  ricerca realizzate nel sito, e salvarli nel proprio profilo (ad esempio,
  un'azienda potrebbe specificare e salvare una ricerca in cui si richiedono solo
  laureati in informatica disposti a lavorare nel Lazio). I risultati relativi
  potranno essere richiamati automaticamente (senza bisogno, cioè, di reimpostare
  ogni volta manualmente la ricerca) su un'apposita pagina. Il sistema terrà inoltre
  traccia della data in cui tale pagina è stata letta per l'ultima volta dall'utente-azienda,
  e lo avvertirà (ad esempio evidenziando il link relativo) nel caso in cui i
  risultati della ricerca siano cambiati rispetto all'ultima visita (*suggerimento:
  per realizzare questa funzionalità, sarà sufficiente confrontare le date di
  modifica di tutti i curriculum selezionati dalla ricerca con la data
  dell'ultimo accesso alla pagina*).  
