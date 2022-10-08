---
titolo: TravelWeb
numero: 1
vestione: 1.0
lingua: IT
anno: 2009
materia: IW
mainfile: Progetto_Master.rcp
thisfile: specifica
---

-------
{#specifiche}

Il sito *TravelWeb* rappresenta una semplice agenzia di
viaggi online. Il sito dell'agenzia presenta informazioni turistiche generali
su una serie di *destinazioni* sparse per il mondo, dando anche agli
utenti la possibilità di esprimere i loro pareri su ciascuna di esse. Alle
destinazioni, che sono organizzate in maniera da renderne semplice la ricerca e
la navigazione, sono associate delle *offerte di viaggio*, il vero
prodotto messo in vendita dall'agenzia.

Una *destinazione* può rappresentare qualsiasi sito di
interesse turistico, ad esempio un museo, un parco, una città, una regione, o
addirittura un'intera nazione. Chiaramente, una destinazione potrà includerne
altre più specifiche o essere inclusa a sua volta da altre destinazioni più
generali (ad esempio Italia \> Abruzzo \> L'Aquila \> Basilica di
Collemaggio).

-------
{#operazioni}

- Il sito dovrà prevedere tre tipologie di utenza: amministratori,
  utenti registrati e utenti anonimi. Andranno quindi previste procedure di
  registrazione e login.

- Il sito dovrà collezionare delle statistiche sulle destinazioni
  ricercate e visualizzate (ma non necessariamente acquistate sotto forma di
  offerta di viaggio) dai visitatori del sito. Queste statistiche saranno
  utilizzate, in particolare, per la creazione della homepage, nella quale
  figureranno in evidenza (in maniera da potervi accedere rapidamente) le ultime
  destinazioni consultate nonché quelle più consultate.

- Ad ogni destinazione dovrà essere associata una scheda illustrativa
  contenente (almeno):
   - Una descrizione a turistica della destinazione.
   - Una lista di collegamenti a siti internet di approfondimento.
   - Una galleria di immagini (sulla stessa pagina o su una pagina
  collegata).
   - Una lista dei punti di particolare interesse presenti nell'ambito
  della destinazione (ad esempio monumenti, località da visitare, ecc.). Questa
  lista dovrà necessariamente contenere *almeno* tutte le destinazioni
  presenti nel sito che siano logicamente incluse in quella corrente. Ad esempio,
  se nel sito fossero presenti come destinazioni sia l'Abruzzo che L'Aquila, la
  pagina del primo dovrebbe citare quella della seconda come punto di interesse.
  In questo caso, sarà possibile cliccare sul luogo di interesse per saltare alla
  sua scheda specifica.

- A ciascuna destinazione potranno venire associate delle offerte
  di viaggio ad essa inerenti. Le offerte avranno un periodo di validità, un
  prezzo (per persona), e ovviamente una descrizione. Gli utenti registrati
  potranno comunicare il proprio interesse in un'offerta, venendo inseriti quindi
  in una lista di potenziali adesioni (visibile ai soli amministratori, ad
  esempio per contattare telefonicamente gli interessati).

- Gli utenti registrati avranno la possibilità di pubblicare
  commenti riguardanti le destinazioni, e dare un voto a ciascuna di esse. I
  commenti potranno essere mostrati nella scheda della corrispondente
  destinazione o in una pagina specifica ad essa collegata. Il voto medio
  attribuito dagli utenti (insieme al numero totale di voti pervenuti) sarà invece
  sempre presente sulla scheda.

- Una caratteristica importante di ciascuna destinazione dovrà
  essere la sua *classificazione* . Per classificare le destinazioni
  utilizzeremo una struttura generale a *tag* , dove il *tag* è una
  parola o breve frase dal significato evidente (ad esempio "città", "città
  d'arte", "località balneare", "nazione", "isola", "museo"). Gli amministratori
  e gli utenti registrati sul sito potranno definire dei *tag* assegnandoli
  alle destinazioni. Tuttavia, i *tag* attribuiti dagli amministratori
  saranno prioritari (ad esempio nel processo di ricerca descritto dopo) ed
  evidenziati in maniera diversa nella classificazione di ciascuna destinazione,
  in quanto più "ufficiali". Gli amministratori saranno inoltre gli unici a poter
  cancellare un *tag* da una destinazione.

- Infine, il motore di ricerca costituirà una parte essenziale del
  sito. Dovrà essere possibile effettuare almeno le tipologie di ricerca che
  seguono (ogni altra forma di ricerca realisticamente utile inserita nel sito
  sarà valutata positivamente):
   - Ricerca di destinazioni in base ai *tag* ad esse associati.
   - Ricerca di destinazioni in base al loro nome (o parte di esso).
   - Ricerca di destinazioni in base alla disponibilità di offerte di
  viaggio valide in un determinato periodo e/o con una specifica soglia di prezzo.
   - Ricerca di offerte di viaggio (per qualsiasi destinazione) valide
  in un determinato periodo e/o con una specifica soglia di prezzo.

- Il sito dovrà essere provvisto di un adeguato backoffice,
  accessibile dai soli amministratori, tramite il quale inserire e modificare i
  dati associati alle destinazioni e alle offerte.  
