<html><head>
<meta charset="UTF-8"/>
<title>${nomecorso}: Progetti di Fine Corso</title>
<style>${css?no_esc}</style>
</head>

<body>
<section class="intestazione">
<div class="ncorso">Corso di ${nomecorso}</div>
<div class="aa">Progetti A.A. ${anno}/${(anno?number)+1}</div>
<div class="nprogetto">Specifica ${numero!""}</div>
</section>

<section class="specifica">
<h1>Progetto "${titolo}" <span class="versione">Versione ${versione!"1.0"}</span></h1>

## Premessa

I progetti di fine corso si ispirano sempre ad esigenze
reali, e fanno solitamente riferimento a tipologie di sito già presenti sulla
rete. Nello svolgere il progetto, gli studenti dovranno attenersi alla
specifica data in questo documento, ma potranno raffinarla tramite l'interazione
col docente e l'analisi di siti web analoghi. In ogni caso, la realizzazione
finale dovrà essere completamente originale. Le informazioni pubblicate
dovranno essere sempre ben organizzate ed accessibili, date le varie tipologie
di utenza associate alle applicazioni web pubbliche.  

## Specifiche del Sito

<div>${body_specifiche?no_esc}</div>

Di seguito sono illustrati schematicamente i contenuti e le
funzionalità minime che dovrebbero essere inseriti nel sito. Ovviamente, ogni
ulteriore raffinamento o arricchimento di queste specifiche aumenterà il valore
del progetto.

<#if (body_operazioni??)>

<div>${body_operazioni?no_esc}</div>

</#if>

</section>

<#if !(nosvolgimento??)>

<section class="break intestazione">
Indicazioni per lo Sviluppo del Progetto
</section>

<section class="indicazioni">

## Tecnologie da utilizzare

- La struttura base del sito va realizzata in HTML5. La validazione
di tutte le pagine del sito rispetto alla tipologia di HTML prescelta è parte
integrante dello sviluppo e **deve** essere riportata nella documentazione.
- Per la realizzazione del layout devono essere utilizzati il più
possibile i figli di stile CSS. Il layout può liberamente basarsi su quelli
disponibili in rete o utilizzati a lezione. Il grado di **personalizzazione**
del layout sarà comunque tenuto in considerazione in sede di valutazione. **Un
layout responsive non è strettamente richiesto ma fortemente consigliato.**
- Per la programmazione lato *client* il linguaggio richiesto
è JavaScript. Si possono liberamente includere nel progetto librerie sviluppate
da terze parti, a patto che la loro portabilità cross-browser sia adeguata e
che nella relazione siano citate e descritte. È in ogni caso **sconsigliato
l'abuso di tali tecnologie** , soprattutto quando sia possibile sostituirle
con un adeguato uso di HTML, CSS, ecc. **In linea generale, il vostro sito
dovrà essere utilizzabile anche con JavaScript disattivato.** L'uso del sito
senza script potrebbe essere meno "agevole" o permettere di accedere solo alle
funzionalità "vitali", ma non è consentito presentare siti la cui dinamica sia
totalmente basata sull'uso degli script. È tuttavia **ammissibile che gli
script giochino un ruolo più importante nelle funzionalità la cui utenza è
ristretta e predeterminata** (ad esempio nelle funzionalità *back-end*
per gli amministratori, ma non nel *front-end* pubblico del sito o in una
procedura di login).
- Per la programmazione lato *server* è **richiesto** l'uso
di Java (*servlet*), eventualmente associato a qualsiasi DBMS (se necessario)
e a un *template engine* come*Freemarker*. Anche in questo caso è
possibile avvalersi di librerie esterne.
- Il sito, in generale, deve funzionare ed avere un buon *rendering*
sulle versioni più recenti di Edge, Firefox e Chrome, e *possibilmente*
essere compatibile con i browser più datati (in questo caso non c'è bisogno che
tutto funzioni perfettamente, ma almeno che le funzionalità *degradino bene*)
e con le ultime versioni di altri browser, come Opera. Tale compatibilità **deve**
essere esplicitamente dichiarata nella documentazione.  

## Svolgimento e Documentazione del Progetto

Le specifiche fornite potrebbero non risultare esaustive o
completamente definite. Ogni funzionalità aggiunta o raffinata, anche tramite
l'interazione con il committente o con gli utenti finali del sito, sarà
adeguatamente valutata. Tutte le scelte progettuali vanno comunque discusse e
motivate.

Il progetto, svolto secondo le linee guida date dalle
specifiche, dovrà essere consegnato nella forma di un sito web completamente
funzionante, i cui contenuti e le cui caratteristiche saranno valutati in sede
d'esame. Le parti della specifica marcate come *opzionali*, se omesse, non
renderanno il progetto insufficiente ma non gli permetteranno comunque di
raggiungere il massimo dei voti. Nel caso si decida di realizzarle, non sarà
necessario che siano perfette o complete, ma che dimostrino chiaramente il
vostro impegno nell'affrontare una tematica avanzata.

La documentazione (**in formato elettronico**) che
accompagna il progetto **deve** contenere almeno le seguenti informazioni:
- Indicazione delle dipendenze software (di quali librerie avete
bisogno dal lato server e client?).
- Indicazione delle funzionalità realizzate e di quelle
eventualmente non realizzate. Descrizione dettagliata delle eventuali
funzionalità extra o opzionali inserite nel progetto.
- Diagramma che illustra la struttura e la navigabilità del sito.
- Schema relazionale della base di dati (se presente).
- Descrizione analitica del layout del sito, con indicazione delle
sue principali componenti statiche/dinamiche.
- Descrizione delle eventuali tecnologie avanzate (linguaggi,
framework, plugin, librerie, ...) utilizzate, del motivo per cui sono state
adottate e del contributo effettivo che hanno dato alla realizzazione del
progetto.
- Descrizione di *eventuali* problemi riscontrati nella
fruizione del sito su browser differenti, lista dei browser compatibili.
- Screenshot delle pagine più importanti del sito (*opzionale*).

Nel caso di gruppi di lavoro composti da più componenti, *il
contributo effettivo offerto da ciascun componente* alla realizzazione
finale **deve** essere descritto nella documentazione (indicando, ad
esempio, chi si è dedicato prevalentemente alla programmazione server, chi ha
realizzato il layout, chi ha programmato lato client, ecc.). In sede di esame,
i responsabili potranno essere chiamati a riferire sugli aspetti loro delegati.  

## Valutazione del Progetto

Nel valutare il progetto consegnato saranno prese in
considerazione le seguenti caratteristiche (in ordine di importanza):
1. Rispetto delle specifiche.
2. Correttezza tecnica.
3. Chiarezza e correttezza organizzativa dei contenuti.
4. Accessibilità e conformità agli standard.
5. Uso appropriato di contenuti statici e dinamici.
6. Qualità del design.
7. Adeguatezza della documentazione.

A questa valutazione si aggiungerà quella generale derivata
dalla discussione del progetto in sede d'esame.  

## Ulteriori Informazioni

Questa specifica è disponibile in formato PDF sulla pagina
web del corso di Web Engineering, all'indirizzo http://people.disim.univaq.it/dellapenna.
Ulteriori informazioni e chiarimenti sulle specifiche possono essere richiesti
direttamente via email all'indirizzo giuseppe.dellapenna@univaq.it.

Si ricorda che i progetti vanno svolti in *piccoli* gruppi (tre persone è il numero consigliato). 
Eccezioni a questa regola andranno concordate direttamente col docente.

An English translation of this project specification is also available on the teacher's website (http://people.disim.univaq.it/dellapenna). To access it, open the didactic page for this course, select "English version", and go to the projects listing at the page bottom. If the translation is not there, ask the teacher to publish it :smile:

</section>

</#if>


<#if (scheda??)>

<section class="break intestazione">
Scheda Sintetica
</section>

<section class="scheda">

La scheda sintetica va compilata ed inviata al docente, in
forma elettronica, *prima* di sostenere l'esame. Una sua copia va inoltre
allegata alla documentazione del progetto.

**Nome del progetto:**   &nbsp;
{.linetocompile}

**Autori:**

<table>
<thead>
<tr><th style="width:20%">Nome</th><th style="width:20%">Cognome</th><th style="width:10%">Matricola</th><th>Ruolo nello sviluppo del progetto</th></tr>
</thead>
<tbody>
<tr><td> </td><td> </td><td> </td><td> </td></tr>
<tr><td> </td><td> </td><td> </td><td> </td></tr>
<tr><td> </td><td> </td><td> </td><td> </td></tr>
<tr><td> </td><td> </td><td> </td><td> </td></tr>
<tr><td> </td><td> </td><td> </td><td> </td></tr>
</tbody>
</table>

**Tecnologie/Librerie/Framework utilizzati lato client**  (ad es. HTML5, CSS 2/3, Javascript, JQuery, Bootstrap):    &nbsp;
{.linetocompile}

&nbsp;
{.linetocompile}

&nbsp;
{.linetocompile}

**Tecnologie/Librerie/Framework utilizzati lato server:** (ad es. JSP, MySQL, JPA, template engines)  &nbsp;
{.linetocompile}

&nbsp;
{.linetocompile}

&nbsp;
{.linetocompile}

**Compatibilità** :  

| **Browser**                    | **Versione** | **Compatibile** | **Degradante** | **Non compatibile** | **Non provato** |
|--------------------------------|--------------|-----------------|----------------|---------------------|-----------------|
| **Internet Explorer**/**Edge** |              |                 |                |                     |                 |
| **Mozilla Firefox**            |              |                 |                |                     |                 |
| **Google Chrome**              |              |                 |                |                     |                 |
| **Opera**                      |              |                 |                |                     |                 |
| **Safari**                     |              |                 |                |                     |                 |
| &nbsp;                               |              |                 |                |                     |                 |
| &nbsp;                               |              |                 |                |                     |                 |

**Data di consegna del progetto:**  &nbsp;
{.linetocompile}

</section>

</#if>


</body>
</html>