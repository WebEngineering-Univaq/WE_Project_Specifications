---
titolo: ContentManager
numero: 1
vestione: 1.0
lingua: IT
anno: 2012
materia: IW
mainfile: Progetto_Master.rcp
thisfile: specifica
---

-------

{#specifiche}

Il sito *ContentManager* rappresenta un semplice
sistema web per la creazione di mini-siti web statici senza l'ausilio di
programmazione o stesura di codice HTML/CSS.

Ciascun mini-sito sarà identificato dalla username del suo
realizzatore e avrà una struttura ad albero corrispondente alla struttura
logica di navigazione del sito stesso, con una pagina HTML associata ad ogni
nodo. Alla radice corrisponderà sempre la homepage del sito. Ad esempio:

Homepage  
   \> About  
   \> Interests  
   \> Ski  
   \> Photography  
   \> Links  
   \> Contacts  

Tutte le pagine del mini-sito saranno identificate da un codice
numerico, condivideranno la stessa intestazione e lo stesso piè di pagina e
verranno visualizzate usando lo stesso foglio di stile.

Intestazione, piè di pagina e "corpo" delle pagine HTML del
sito saranno inseriti nel database, mentre i fogli di stile saranno conservati
nel file system. Il sistema disporrà di un insieme predefinito di fogli di
stile, ciascuno associato a un nome e a una descrizione, le cui regole dovranno
definire l'aspetto di tutti i principali elementi HTML (titoli, paragrafi,
tabelle, liste, ecc.).

L'utente potrà richiedere la homepage del sito dell'utente *pippo* usandounaURL del tipo http://\<URL_base_della_web_application\>/site?user=\<username\>, mentre qualsiasi altra pagina con identificatore *X* dello stesso sito
corrisponderà alla URL http://\<URL_base_della_web_application\>/site?user=*pippo* \&page=*X*

Per rispondere a queste URL, il sistema dovrà comporre
dinamicamente la pagina web finale inserendo nel suo *body* quattro parti:
l'intestazione comune a tutto il mini-sito, seguita dal contenuto della pagina
richiesta, da un menu di navigazione (che potrà apparire in qualsiasi punto
della pagina), e infine dal piè di pagina comune. Nella *head* della pagina
così generata dovrà anche essere inserito un riferimento al foglio di stile
scelto dall'utente.

Il menu di navigazione dovrà essere creato automaticamente
in base alla struttura ad albero del sito, e conterrà almeno un link alla
pagina padre di quella corrente (se non ci si trova nella homepage) e i link a
tutte le pagine figlie dirette di quella corrente. Ad esempio, il menu nella
pagina *Interests* della struttura vista prima dovrebbe contenere *Homepage* ,
*Ski* e *Photography*.

L'utente potrà anche caricare nel suo spazio web delle
immagini, seguendo un'apposita procedura, e fino a una dimensione massima
preimpostata (cioè finché la somma delle dimensioni delle immagini caricate è
al di sotto di un certo limite). A ogni immagine sarà associato un
identificatore numerico *Y* , in modo tale che la si possa recuperare (ad
esempio all'interno di una pagina del mini-sito, con un tag img) usando una URL
del tipo http://\<URL_base_della_web_application\>/image?user=*pippo* \&image=*Y.
Suggerimento*: per creare una servlet che "scarica" un'immagine, come quella
appena richiesta, e per capire come caricare un binario sul server, si vedano
gli esempi sviluppati a lezione. Le immagini potranno essere conservate in
directory separate per ciascun utente oppure nella stessa directory,
ridenominandole in modo che i nomi non siano in conflitto. L'importante è che
si possa poi mappare ciascun identificatore numerico sul file che gli
corrisponde nel file system.

-------
{#operazioni}

- Gli utenti che vogliono creare il proprio sito personale potranno
  registrarsi su *ContentManager* fornendo i propri dati e un indirizzo
  email valido (il controllo di validità, effettuabile inviando una email con un
  link da cliccare per la verifica dell'indirizzo, è *opzionale*) e
  ricevendo delle credenziali di accesso. Il sistema inizializzerà inoltre lo
  spazio web dell'utente creando la homepage (radice dell'albero di navigazione),
  contenente inizialmente un testo predefinito, e generando un'intestazione/piè
  di pagina di default per il mini-sito (magari contenenti il nome dell'utente,
  la data di creazione, ecc.).
- Accedendo al proprio spazio web, un utente registrato potrà
  vedere l'albero delle pagine già create. modificare ciascuna pagina,
  eliminarla o creare nuove pagine a qualsiasi livello dell'albero. All'atto
  della creazione di una nuova pagina, dopo aver specificato in che punto
  dell'albero dovrà apparire, l'utente potrà scegliere se iniziare con una pagina
  vuota o con una *pagina modello* già predisposta (vedi dopo).
- *Opzionalmente*, potrà anche essere offerta all'utente la
  possibilità di spostare un sottoalbero (cioè una pagina e tutte quelle da essa
  discendenti) in una posizione diversa dell'albero.
- L'utente registrato potrà inoltre modificare l'intestazione e il
  piè di pagina del suo mini-sito.
- L'editing delle pagine e dell'intestazione/piè di pagina dovrà
  essere effettuato tramite un editor WYSIWYG per HTML come ckeditor (http://ckeditor.com/)
  o tinymce (http://www.tinymce.com/).
- L'utente registrato potrà visualizzare la lista di tutte le
  immagini che ha caricato sul sito, eliminarle o aggiungerne di nuove. Nella
  lista dovrà essere in evidenza il link (costruito come visto sopra) da
  utilizzare per incorporare o scaricare l'immagine stessa.
- L'utente registrato potrà visualizzare la lista dei fogli di
  stile predefiniti nel sistema e scegliere quello da applicare al proprio sito.
- Infine, gli utenti più "prodighi" potranno rendere pubbliche una
  o più pagine da loro realizzate marcandole come *pagine modello*, in modo
  che altri utenti possano usarle come base per le pagine del proprio mini-sito,
  come descritto sopra.
- Nella homepage dell'applicazione saranno presentati, oltre ai
  controlli per registrarsi e fare login, i nomi degli ultimi mini-siti creati,
  in modo che tutti gli utenti, anche anonimi, possano accedere alla homepage dei
  mini-siti di proprio interesse e poi navigarvi usandone il menu o gli eventuali
  link interni.  
