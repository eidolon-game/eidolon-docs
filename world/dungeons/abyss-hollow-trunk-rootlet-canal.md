# Piastre nel tronco e Canale delle radichette

Brief per `abyss_015` e `abyss_016`. Dopo lo scarico del Bacino delle felci, Kael segue l'acqua residua attorno a un tronco cavo e poi nel canale sotto la galleria. I due piani riusano `abyss_forest_stalker`. La tenuta del perno e lo sblocco del contrappeso sono obiettivi ambientali; il giocatore può completarli lasciando viva la creatura. Misure e chiavi sono proposte per il graybox. [Piano della Foresta Sepolta](abyss-buried-forest-plan.md) · [Piani 13–14](abyss-branch-terraces-fern-basin.md)

## Piano 15 · Piastre nel tronco

| Spazio | Layout e comportamento |
| --- | --- |
| Ingresso e nicchia | Un pianerottolo al sicuro ospita il checkpoint e la nicchia con il perno. Il tronco divide il percorso e si vede la passerella ancora sollevata dall'altra parte. La luce che filtra dal vetro opaco cade su entrambi gli imbocchi e offre un riferimento anche tornando indietro. |
| Sentiero corto | Tratto diretto lungo il tronco, largo almeno 300 cm al netto di radici e piastre. Attraversa un punto della pattuglia a vista sul tratto d'arrivo. Una piazzola permette di lasciare il perno e spostarsi oltre il segnale del balzo. Il giocatore può passare mentre lo Stalker riprende la pattuglia. |
| Sentiero lungo | Anello esterno con ripari di roccia e due rientranze da almeno 350 × 350 cm. Lo Stalker vi transita a intervalli leggibili. Alterna tratti con visuale sull'animale e pieghe che interrompono l'aggro; nessuna rientranza deve diventare un vicolo cieco durante il balzo. |
| Ricongiungimento | Entrambi i percorsi arrivano sul lato di montaggio. Lascia almeno 400 × 400 cm per allineare il perno, allontanarsi e aggirare la creatura senza scavalcare il meccanismo. La passerella apre un percorso continuo verso il piano 16. |

**Movimentazione.** Lo stesso perno si può agganciare, trascinare e lasciare su entrambi i sentieri. Il trascinamento consente movimento a piedi e cambio di direzione, mentre schivata e interruzione volontaria rilasciano il perno. La posa a terra non blocca il pawn o la navmesh. Verifica svolte, pendenze e raggio di aggancio con la sagoma effettiva del perno. Se il perno resta fuori dalla superficie valida o incastrato oltre una breve finestra di recupero, riportalo alla nicchia e segnala il ripristino. Anche un comando esplicito presso la nicchia può recuperarlo prima del montaggio. Elimina qualsiasi copia transitoria quando lo riporti all'ancora.

| Chiave proposta | Uso |
| --- | --- |
| `abyss_015_pin_pickup` | Aggancio contestuale al perno disponibile. Stato transitorio nel tentativo. |
| `abyss_015_pin_reset` | Recupero del perno smarrito alla nicchia, consentito fino al montaggio confermato. |
| `abyss_015_pin_seat` | Esito durevole di inserimento nell'alloggio. Valida piano, identità del perno, allineamento e distanza del pawn. A conferma ottenuta, il perno risulta montato e la passerella si abbassa. |

## Piano 16 · Canale delle radichette

| Spazio | Layout e comportamento |
| --- | --- |
| Nicchia di servizio | Dal checkpoint si vede la saracinesca e si distinguono i due percorsi tramite altezza, profilo della luce e suono dell'acqua. Ancorare l'ingresso del canale vicino alla nicchia. Una piazzola senza ostilità immediata consente di scegliere la via. |
| Galleria superiore | Passaggio alto alla luce irregolare. Lo Stalker presidia l'imbocco, con una spalla laterale abbastanza larga da interrompere l'inseguimento. Una rientranza prima della saracinesca invita a chiamare l'attenzione, poi a cambiare lato usando una delle due aperture. |
| Canale basso | Passaggio percorribile a piedi con acqua bassa. Parti da 250 cm di larghezza e 320 cm di altezza utile sul percorso del pawn; le due aperture laterali che deve attraversare lo Stalker si dimensionano separatamente in base alla sua sagoma in movimento. Dai a entrambe un appoggio asciutto per virare e camera libera all'uscita. Il canale continua sotto la galleria fino allo sbocco oltre la saracinesca. |
| Lato interno | Lo sbocco raggiunge una piazzola protetta da una piega della roccia. Qui Kael libera il contrappeso dal lato interno, alzando la saracinesca e aprendo il passaggio verso il piano 17. Conserva un raccordo percorribile verso il canale con saracinesca ancora chiusa. |

**Approcci.** Il giocatore può scendere subito nel canale mentre lo Stalker guarda la galleria, percorrerlo fino allo sbocco e raggiungere il contrappeso. In alternativa, attira lo Stalker da una delle aperture, attraversa verso l'altra quando il balzo ha già fissato la direzione e raggiungi lo sbocco dal lato libero. Posizionare appigli e destinazioni del balzo fuori dalle bocche strette, dal contrappeso e dall'arrivo del giocatore. Lo Stalker può cambiare percorso lungo le aperture abilitate, con un rientro alla pattuglia se il collegamento è indisponibile. Per entrambe le vie, prova l'inserimento di una piazzola oltre la lunghezza del corpo a ogni cambio di quota e conserva una via di ritorno quando il mostro occupa il ramo opposto.

| Chiave proposta | Uso |
| --- | --- |
| `abyss_016_counterweight_release` | Esito durevole di sblocco. Valida il piano, il lato interno e la distanza dal comando. A conferma ottenuta, saracinesca e uscita assumono lo stato aperto. |

## Stato intermedio, ricevute e ripresa

- Usa una sola identità di ricevuta per lo stesso esito durevole del piano. Valida ogni nuova richiesta al momento dell'interazione. Se arriva lo stesso esito già registrato, ripresenta lo stato confermato. Una richiesta con dati incompatibili viene rifiutata senza sovrascrivere l'esito.
- Muovi la maniglia localmente durante l'interazione e applica apertura e collisione solo dopo il commit congiunto di ricevuta e obiettivo. Sul 15 conserva il perno disponibile presso l'alloggio in attesa di risposta; sul 16 lascia agibile il raccordo interno. Se il commit fallisce, ripristina il controllo e lascia il varco chiuso, con la manovra ritentabile. Se manca soltanto la risposta, leggi lo stato autorevole prima di inviare un nuovo tentativo.
- Al checkpoint prima di `abyss_015_pin_seat` confermato, il perno torna alla nicchia e la passerella è sollevata. Dopo la conferma ricostruisci perno unico nell'alloggio e passerella aperta. Sul 16 ripristina il contrappeso e la saracinesca in base alla conferma. Prima dello sblocco il canale rimane percorribile per un nuovo tentativo.
- Se la lettura del checkpoint fallisce, conserva l'ultima revisione valida e offri un retry senza azzerare lo stato. Verifica l'appoggio del pawn prima di riprendere. Se il caricamento del piano seguente fallisce, conserva le manovre confermate e rendi ripetibile l'uscita. Registra l'avanzamento dopo la verifica dell'arrivo.

## Segnali IT/EN

| Contesto | IT | EN |
| --- | --- | --- |
| Obiettivo del 15 | Porta il perno alla passerella | Bring the pin to the bridge |
| Azione di presa | Trascina il perno | Drag the pin |
| Perno smarrito e ripristinato | Il perno è tornato nella nicchia | The pin is back in the alcove |
| Azione all'alloggio | Inserisci il perno | Fit the pin |
| Osservazione di Kael nella nicchia del 16 | «Il canale passa sotto la galleria.» | “The channel runs beneath the gallery.” |
| Obiettivo del 16 | Raggiungi il retro della saracinesca | Get behind the gate |
| Azione sul lato interno | Libera il contrappeso | Release the counterweight |
| Manovra rifiutata | Riprova la manovra | Try the mechanism again |

## Verifiche UE 5.6

1. Completa il 15 su entrambi i sentieri con lo Stalker vivo. Prova spigoli, rilascio con schivata, incastro del perno e recupero dalla nicchia. Verifica unicità dell'oggetto dopo il ripristino e dopo il montaggio.
2. Completa il 16 aggirando la galleria e attirando la creatura da ciascuna apertura. Verifica che raggiungere il comando dalla parte esterna non funzioni, che il giocatore possa tornare dal lato interno a varco chiuso e che nessun attacco obblighi a un salto sul fondo del canale.
3. Per i due esiti durevoli induci rifiuto prima del commit e perdita della risposta dopo il commit. Ricarica prima e dopo, ripeti la richiesta e confronta progressione, oggetti, collisioni e animazione. Simula anche il fallimento del caricamento al piano seguente.
4. Ripeti con tastiera e controller, camera libera e agganciata e audio disattivato. Registra build, percorso ed esito. Le prove in engine sono da eseguire.
