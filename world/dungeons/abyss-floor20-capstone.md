# Piano 20 · Il Groviglio della faglia | Riftroot Tangle

`boss_abyss_20` è il caposaldo dell'arena **Radici nella faglia** (`abyss_020`). Una creatura dell'Abisso si muove trascinando blocchi di roccia stretti tra fasci di radici. Ha quattro punti d'appoggio bassi, una cavità centrale che si apre dopo lo sforzo e una sagoma irregolare che si riconosce contro la parete. L'ingombro di riferimento è 420 × 500 × 310 cm in posizione neutra. Il modello resta un prototipo. Nel bestiario di produzione appartiene ai mostri dell'Abisso. [Piano della Foresta Sepolta](abyss-buried-forest-plan.md) · [Mappatura proposta](https://github.com/eidolon-game/eidolon-game/blob/82c869f35e384c2b1462274e45612f928ea9e57e/Source/Eidolon/Dungeons/Data/boss_floor_mapping.json)

## Arena e ancore

Misure iniziali per il graybox. Coordinate locali in centimetri, Z riferito al piano calpestabile. Il rettangolo di verifica è largo 2400 cm e lungo 2800 cm, con X positivo verso le Miniere e Y tra −1200 e +1200. World assegna un solo transform al piano e alle ancore. Le chiavi sotto sono proposte, da registrare dopo la verifica dei riferimenti.

| Ancora | Posizione iniziale | Uso |
| --- | --- | --- |
| `abyss_020_entry` | (200, 0, 0) | Arrivo dalla rampa del Belvedere della vena. Fa intravedere la faglia lasciando il giocatore in copertura. |
| `abyss_020_checkpoint` | (500, 0, 0) | Area di sosta fuori portata. Collisione e camera permettono una ripartenza orientata verso la soglia. |
| `abyss_020_arena_trigger` | (850, 0, 0) | Attraversamento che attiva l'incontro. Se lo spawn fallisce, mantiene disponibile il percorso al checkpoint. |
| `abyss_020_boss_spawn` | (1550, 0, 0) | Area centrale liscia. Distanza e orientamento lasciano al giocatore il tempo di leggere il primo segnale. |
| `abyss_020_flank_left`, `abyss_020_flank_right` | (1550, −900, 0), (1550, +900, 0) | Piazzole collegate alle estremità da raccordi larghi almeno 300 cm. Conservare almeno 400 cm di larghezza libera lungo ciascun fianco. |
| `abyss_020_exit_gate` | (2450, 0, 0) | Varco con collisione propria. Sul lato interno lascia spazio per girarsi e raggiungere entrambi i fianchi. |
| `abyss_020_exit` | (2700, 0, 0) | Attivazione della discesa al piano 21. La destinazione ha un'ancora indipendente con appoggio e via di ritorno verificati. |

## Combattimento e accessibilità

Il Groviglio combatte dalla fascia centrale. I raccordi laterali restano accessibili con camera libera o agganciata. I primi cicli alternano due mosse singole; ogni finestra attiva ha un verso leggibile e almeno una via d'uscita raggiungibile a piedi. Tempi e sagome sono valori di partenza, da tarare con il pawn.

| Mossa | Segnale e attività | Opportunità |
| --- | --- | --- |
| **Cuneo di roccia** | Solleva un blocco e porta due appoggi all'indietro. Fissa l'asse dopo circa 0,65 s; batte al suolo circa 0,4 s dopo. Una lingua di detriti segue una fascia rettilinea davanti al boss. Il bordo compare prima dell'impatto e termina dove finisce il volume di danno. | Esci lateralmente dalla fascia. Il blocco resta a terra per circa 1,2 s e scopre la cavità verso il lato opposto alla zampa sollevata. |
| **Richiamo delle radici** | Le radici del fianco scelto si tendono verso due punti visibili. Il braccio della creatura si piega sullo stesso lato. Dopo almeno 1 s le radici rientrano lungo il fianco scelto; la fascia centrale arretrata e il fianco opposto restano liberi. | Allontanati dal fianco segnalato lungo il raccordo vicino. Durante il rientro, colpisci la cavità da dietro la spalla. Nessuna presa trascina il giocatore. |
| **Scorrimento di faglia** | Sotto il 45% di salute, alla prima pausa tra due mosse, il Groviglio espelle un blocco decorativo nella parete e avanza fino alla piazzola centrale successiva. Appoggia i quattro arti uno alla volta e indica l'arrivo con la testa per almeno 1,4 s. Lo spostamento avviene una sola volta e non causa danni. | Usa uno dei fianchi. Se la piazzola è occupata, arresta lo spostamento e mantieni la pausa prima del prossimo attacco. Un colpo letale risolve subito la sconfitta. Dopo la pausa, le due mosse riprendono dalla nuova posizione senza attivarsi insieme. |

Il riposizionamento sposta il punto di partenza degli attacchi. La caduta del blocco rimane fuori dalla superficie percorribile. Verifica la posa e la sagoma del colpo con audio disattivato, profilo senza scuotimento e impostazioni daltonismo. Evita lampi, cambio forzato di camera e particelle opache davanti al boss. Usa suoni distinti per blocco sollevato e radici tese. Le indicazioni IT/EN di prima lettura possono restare «Esci dalla linea» / “Step out of its path” e «Spostati sull'altro fianco» / “Move to the other flank”.

## Stato, ripresa e ingresso alle Miniere

1. Attiva un solo slot di spawn su attraversamento valido della soglia. Se fallisce, mantieni il progresso incompleto e il varco a valle chiuso, ripristina il ritorno al checkpoint e consenti un retry che riusa lo stesso slot. Uccidere un altro mostro non soddisfa la condizione.
2. Registra con Save un solo esito di sconfitta per l'incontro validato del piano 20. A conferma ottenuta, apri il varco, elimina gli elementi offensivi e aggiorna il percorso. Se la scrittura fallisce, conserva la scena in uno stato sicuro e riutilizza la stessa identità di ricevuta per il retry. Se la risposta si perde, leggi l'esito autorevole prima di applicare nuovamente la presentazione o iniziare un altro tentativo.
3. Prima della sconfitta confermata, la ripresa dal checkpoint ricostruisce il tentativo dall'inizio. Dopo la conferma, la ripresa ricostruisce l'arena libera e il varco aperto. Una lettura del checkpoint fallita offre il recupero ripetibile senza azzerare l'esito. Eventuali avanzamenti di rango restano di competenza del sistema di progressione. [Ranghi del canone](../../narrative/story.md#sistema-dei-ranghi-degli-avventurieri)
4. Oltre il varco, una breve discesa sostituisce le radici con tagli di cava e conduce a un pianerottolo asciutto del piano 21. Prima del viaggio verifica destinazione, superficie d'appoggio e orientamento verso le Miniere Perdute. Se il caricamento fallisce, conserva la sconfitta e il varco aperto sul piano 20. Il tentativo successivo riparte dal varco o dal checkpoint coerente con l'esito registrato. Registra l'arrivo al 21 solo dopo aver verificato presa di controllo e appoggio nel livello di destinazione. [Fasce dell'Abisso](../../narrative/story.md#atto-ii--i-cento-livelli-dellabisso)

## Collaudo UE 5.6

- Verifica spostamento e fuga da centro, fianchi e pareti durante ciascuna mossa. Prova tastiera e controller, camera agganciata e libera, audio e scuotimento disattivati. Misura il bordo dei volumi contro la posa durante preparazione, attività e recupero.
- Supera il 45% durante ciascuna fase di una mossa. Prova destinazione occupata e danno letale che supera la soglia. Verifica una sola transizione per tentativo.
- Simula mancato spawn, rifiuto della ricevuta e perdita di risposta dopo la scrittura. Ricarica prima e dopo la conferma della sconfitta; verifica stato della creatura, collisione del varco e assenza di ricompense duplicate. Verifica arrivo al piano 21 dopo fallimento e retry del caricamento.

Il graybox usa `abyss_020_encounter` per avviare lo scontro, `abyss_020_boss_advance` a (2050, 0, 0) per lo scorrimento, `abyss_020_riftroot_gate` a X 2600 e l'uscita a X 2820. La rampa successiva resta in attesa della mappa delle Miniere Perdute. Importazione degli asset e prove runtime UE 5.6 da eseguire.
