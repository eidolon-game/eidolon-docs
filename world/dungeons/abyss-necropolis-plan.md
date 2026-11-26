# La Necropoli | Piani 51–60 dell'Abisso

Proposta di level design per la fascia canonica tra **Le Terre di Cristallo** e **Le Fucine Infernali**. Il percorso passa da camere funerarie raccolte a cortili di pietra, balconate di ossari e una soglia da cui proviene la prima corrente d'aria calda. L'architettura suggerisce percorsi di servizio e spazi per la sosta. Nomi di culture, scritture, identità dei costruttori e spiegazioni sulla Gilda restano riservati alla narrazione approvata. Salva per i piani canonici la statua del 70, «Ricorda» del 90 e lo scontro del 100 con il Custode. [Canone dell'Abisso](../../narrative/story.md#atto-ii--i-cento-livelli-dellabisso) · [Terre di Cristallo](abyss-crystal-lands-plan.md) · [Binding 90–100](abyss-catacombs-plan.md#collegamenti-canonici-a-lunga-distanza)

## Origine e continuità degli asset

Gli elementi di scavo del piano precedente servono solo alla soglia. Per la Necropoli, produrre moduli originali per loculi, sarcofagi, archi d'ossario, lastre e cancelli con geometria separata per collisioni e movimento. Le forme e i segni decorativi sono proposte originali del progetto, senza iscrizioni decodificabili o identità associate. Per ciascun asset registrare autore, sorgente, diritti di utilizzo, unità, pivot, stato d'importazione e approvazione di art e narrativa. Riferimenti di ricerca e prototipi richiedono verifica dei diritti prima di un uso negli asset; il presente brief non certifica asset di produzione. [Registro degli asset](../../production/asset-register.md)

Riusa `abyss_necropolis_sentinel` (Ossuary Sentinel) dal roster proposto. È un bipede arcuato di circa 400 cm, con difesa frontale, fendente e giunzione dorsale vulnerabile. Prova una posa di guardia leggibile da lontano e un sollevamento netto prima del colpo. Ai piani 51–59 gli incontri sono facoltativi: le vie di fuga, gli scrocchi e i percorsi laterali rimangono accessibili con il nemico vivo, anche dopo un tentativo di manovra interrotto. [Bestiario proposto](https://github.com/eidolon-game/eidolon-docs/blob/478ccf94def449a20f326badad3a83faa1392347/art/creatures/bestiary.json#L222-L264)

## Progressione

| Piano | Architettura e incontro | Manovra e percorso |
| --- | --- | --- |
| `abyss_051` · Vestibolo dei loculi | Soglia asciutta da Le Terre di Cristallo e due camere a gomito. Il primo Sentinel presidia la seconda e mostra la guardia prima del fendente. | Raggiungi la leva dietro la seconda camera. Una fascia di nicchie protette a lato consente di leggere il colpo e aggirare il Sentinel senza affrontarlo. |
| `abyss_052` · Corte delle stele | Cortile rettangolare attraversato da file di stele basse. Il Sentinel attraversa il centro lungo un asse leggibile dalla camera. | Ruota il supporto di una lastra per trasformarla in passerella sopra il fossato. In alternativa, raggiungi l'approdo tramite un percorso in leggero pendio. L'uscita è raggiungibile in entrambe le pose. |
| `abyss_053` · Anello dei sarcofagi | Sala anulare con due gallerie radiali e depositi al centro. Il Sentinel pattuglia solo il ramo esterno vicino all'ingresso. | Ruota due chiusure a feritoia in qualunque ordine. Ogni chiusura confermata resta inserita e lascia l'altra accessibile, anche tornando dal ramo interno. |
| `abyss_054` · Galleria dei basamenti | Tre basamenti bassi e un corridoio di servizio allineato al pendio. Il Sentinel protegge il passo diretto attraverso la sala. | Trasporta un fermo da un ripiano alla soglia; entrambe le vie sono abbastanza ampie per girarsi con il fermo. Se smarrito torna all'ancora finché la posa non è confermata. |
| `abyss_055` · Balconata delle volte | Sosta tranquilla. Dalla balconata si vedono le volte sovrapposte e le due rampe di servizio. Il percorso principale è asciutto e senza ostilità. | Segui la rampa fino al piano inferiore. Una nicchia panoramica ritorna sullo stesso percorso e non richiede comandi o oggetti. |
| `abyss_056` · Cappelle accostate | Tre cappelle laterali sfalsate rispetto alla navata. Il Sentinel non può colpire attraverso i muretti divisi in settori. | Apri, dal riparo, una delle due griglie a battente. Ciascuna apre un percorso diverso verso lo stesso pianerottolo. Conserva una via di ritorno verso il comando. |
| `abyss_057` · Ponte dei pilastri | Galleria alta con pilastri ravvicinati, ponticello e ripiano inferiore raggiungibile da una rampa. Un Sentinel presidia il lato lontano. | Blocca il contrappeso dal ripiano, poi alza il ponte da una nicchia asciutta. Il primo esito rimane salvato se il giocatore viene interrotto prima della seconda manovra. |
| `abyss_058` · Camera delle grate | Camera a due quote con corridoi laterali e tre archi. Due Sentinel occupano settori distinti; un solo fendente restringe lo spazio alla volta. | Individua il corridoio dietro la grata e sgancia il braccio dal lato interno. Non richiedere salti di precisione e lascia percorribile il ritorno a grata chiusa. |
| `abyss_059` · Soglia dell'aria calda | Percorso quieto. Una spaccatura lascia passare aria calda, mentre l'ultimo portico ripara il pianerottolo prima dell'arena. Le pose solide rendono leggibile il cambio di bioma senza effetti invadenti. | Raggiungi il checkpoint del 60. Un affaccio facoltativo mostra il varco verso Le Fucine Infernali e torna al percorso senza attivare l'incontro. |
| `abyss_060` · Cortile dell'ultima lastra | Arena con tre corsie, due ripari bassi e nessun nemico comune. Proposta per `boss_abyss_60`: **Lastrarca / Slabarch**, mostro dell'Abisso. | Una volta approvato l'incontro, registra la sconfitta del relativo slot e apri la discesa alle Fucine Infernali (`abyss_061`). Collauda il collegamento geometrico separatamente dal combattimento. |

## Lastrarca / Slabarch · caposaldo proposto

Bipede basso, con spalle arcuate e due grandi lastre mobili incassate ai fianchi. Le lastre fanno parte della sagoma e non hanno iscrizioni. **Appoggio di lastra** mostra il lato scelto prima di far scendere una lastra in una sola corsia. La battuta è breve, un percorso laterale resta libero e il recupero espone l'articolazione. **Fendente a volta** fissa l'asse dopo una torsione leggibile e spazza la fascia frontale. L'inerzia apre la giunzione dorsale. La preparazione indica direzione e ampiezza prima del colpo mediante la posa e un bordo stabile, con audio e colore facoltativi. Conserva almeno una via raggiungibile a piedi. Le lastre si ritraggono alla fine di ogni mossa e non modificano stabilmente navigazione o varchi. Se nessuna via sicura è praticabile, l'IA rinvia la mossa. [Mappatura boss proposta](https://github.com/eidolon-game/eidolon-game/blob/82c869f35e384c2b1462274e45612f928ea9e57e/Source/Eidolon/Dungeons/Data/boss_floor_mapping.json)

## Recupero e cambio piano

- Usa due ancore proposte, `abyss_051_arrival` e `abyss_051_arrival_recovery`, sullo stesso pianerottolo fuori dall'incontro. Prima di consolidare il cambio di piano, controlla appoggio, clearance e presa di controllo. Se entrambe le ancore falliscono o il caricamento viene interrotto, torna allo stato valido del 50 mantenendo aperto il varco già confermato. Applica lo stesso criterio al viaggio 60→61 e alla ripresa al 60.
- Registra manovre e ricevute insieme sotto la chiave di piano. In caso di scrittura rifiutata, ripristina collisione, indicatore e posa precedente. Conserva il primo esito se fallisce il secondo. Se la risposta si perde, leggi lo stato autorevole prima di ritentare con la stessa identità. Un oggetto proposto e ancora privo di posa confermata torna all'ancora con la ricarica.
- Se lo spawn di un nemico facoltativo fallisce, lascia agibili le manovre previste. Se fallisce lo spawn del caposaldo, conserva il varco chiuso e rendi ritentabile lo stesso slot dal checkpoint. Il varco si apre dopo la sconfitta registrata; un errore di caricamento del 61 non la annulla. Il piano 61 inizia con un pianerottolo asciutto e fuori dall'esposizione a calore o incontri.
- Verifica leggibilità con audio disattivato e senza distinzione dei colori. Ogni comando è raggiungibile con una sola interazione contestuale, senza combinazioni simultanee, tempi stretti o mira fine. Prova andata e ritorno con tastiera e controller e camera agganciata o libera.

## Comandi proposti IT/EN

| Uso | IT | EN |
| --- | --- | --- |
| Chiusure del 53 | Chiudi le due feritoie | Close both shutters |
| Fermo del 54 | Prendi il fermo | Take the locking pin |
| Griglie del 56 | Apri la griglia | Open the grille |
| Primo esito del 57 | Contrappeso bloccato | Counterweight locked |
| Seconda manovra del 57 | Alza il ponte | Raise the bridge |
| Comando interno del 58 | Sgancia il braccio | Release the arm |
| Scrittura rifiutata | Riprova la manovra | Try the mechanism again |
| Viaggio interrotto | Riprova la discesa | Retry the descent |

## Collaudo UE 5.6

Completa 51–59 lasciando vivi i Sentinel. Prova entrambi i percorsi al 52, l'ordine inverso al 53, reset del fermo al 54, entrambe le griglie al 56, rifiuto della seconda manovra al 57 e ritorno dal lato interno al 58. Prova rifiuto e perdita di risposta per il caposaldo, ricarica dopo sconfitta e retry verso il 61 con varco aperto. Registra build, percorso, stato finale e log. Prove runtime da eseguire.
