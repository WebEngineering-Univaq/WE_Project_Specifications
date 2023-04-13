---
titolo: Web of Forms
numero: 2
lingua: IT
anno: 2022
materia: IW
versione: 2.0
mainfile: Progetto_Master.rcp
thisfile: specifica
---

-------

{#specifiche}

Il sito *Web of Forms* rappresenta un pratico sistema
per generare moduli formattati (lettere tipo, modulistica pubblica, ecc.) senza
usare un word processor. L'idea è quella di sfruttare le potenzialità di HTML e
dei template, che abbiamo imparato a usare per la generazione delle pagine web,
anche per generare moduli stampabili o comunque esportabili in formati
documentali comuni come il PDF. A questo scopo, daremo la possibilità agli
utenti-autori di creare dei template per dei documenti tipo *(suggerimento:
se partite da qualche documento già in vostro possesso nel formato di un word
processor, potete usare la comune funzione "salva come HTML" per generare un
draft iniziale del template)* e definire nome e tipo dei campi-placeholder
in essi contenuti. Gli altri utenti del sito potranno quindi compilare tali
campi e visualizzare (come HTML) o scaricare (come PDF) il documento formattato
risultante. In particolare, il sistema dovrà gestire (con gli opportuni
controlli) l'input di campi testo, numeri, e valori testuali scelti da un
elenco. Per semplicità, omettiamo le tabelle (ad esempio le righe di una
fattura), ma se provate a realizzarle sarà un grande valore aggiunto al
realismo del vostro progetto! *Suggerimento: studiate bene come combinare un
data model con un template caricato come stringa dal database nel vostro
template engine, e come farne scrivere l'output su una seconda stringa. Per la
conversione HTML-PDF, utilizzate il convertitore fornito da iText (https://itextpdf.com/en/products/itext-7/convert-html-css-to-pdf-pdfhtml,
https://itextpdf.com/en/blog/technical-notes/pdfhtml-configuration-options).*

-------

{#operazioni}

- Gli utenti potranno registrarsi nel sistema fornendo un nickname
  e un indirizzo email.

- Gli utenti, una volta autenticati, potranno caricare un template
  in tre fasi: 1) fornire il suo nome e la descrizione, 2) caricare il template
  HTML (caricamento di file e/o immissione diretta in un campo di testo), 3)
  fornire nome, tipo, testo descrittivo e nome interno (quello usato nel template
  e da inserire nel data model) per ciascuno dei campi previsti dal template.

- Un nuovo template sarà accessibile solo agli utenti
  amministratori (che supporremo semplicemente utenti con dei privilegi speciali)
  finchè uno di questi, provatolo, lo renderà pubblico.

- Gli autori di un template potranno eliminarlo o modificarlo in
  ogni momento. Il sistema dovrà tenere traccia della data di ultima modifica e
  di un contatore di versione da incrementare ad ogni modifica. Questa
  informazione dovrà essere chiaramente presentata agli utenti, in modo che
  sappiano se e quando il template è cambiato.

- Il processo di compilazione del modulo da parte degli utenti (*anche
  anonimi*) sarà il seguente:

   1. Gli utenti potranno scegliere un modulo da una lista. *Opzionalmente, per aiutare
gli utenti nella scelta, potreste fornire un'anteprima del modulo compilandolo
"al volo" con dati casuali associati a tutti i campi.*

   2. Una volta selezionato un modulo, il sistema dovrà generare e presentare all'utente
un opportuno form in cui inserire i valori di tutti i campi richiesti dal
modulo stesso. *In questa fase dovrete cercare di assistere il più possibile gli
utenti nella compilazione. Cercate quindi di usare i controlli giusti per ogni
tipo di campo e prevedete sempre la validazione, anche lato client.*

   3. Una volta inviati (e validati sul server) i valori dei campi, il server li
   combinerà con il template fornendo quindi all'utente una versione HTML finale
   del modulo compilato.

   4. Dopo aver esaminato il risultato, l'utente potrà scegliere di tornare indietro (al
   passo 2 per cambiare i valori dei campi o al passo 1 per scegliere un altro template),
   oppure scaricare il modello compilato sia in formato HTML (lo stesso
   visualizzato) che in formato PDF (convertito dall'HTML come spiegato sopra).
   
- L'utente dovrebbe inoltre essere in grado di scaricare, al passo
  3, un file in formato JSON contenente la definizione del modulo compilato, cioè
  nome del template e lista dei campi con relativi valori. Il sistema dovrebbe
  prevedere una modalità in cui, caricando questo file al passo 1, si possa
  passare direttamente all'anteprima finale (passo 4), con la possibilità di
  tornare indietro e correggere le scelte, come già illustrato.

- Infine, gli utenti registrati dovranno essere in grado di inviare
  un feedback agli autori dei modelli sotto forma di messaggi testuali che
  potranno poi venir consultati dagli autori stessi, una volta autenticati, in
  un'apposita area personale.  
