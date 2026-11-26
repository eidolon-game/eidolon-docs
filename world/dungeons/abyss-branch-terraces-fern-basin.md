# Terrazze dei rami e Bacino delle felci

Brief per i piani `abyss_013` e `abyss_014`. Dopo la pausa della Radura obliqua, la stessa creatura torna su due terreni diversi: alle Terrazze il giocatore legge il balzo dall'alto; nel Bacino legge il movimento lungo la riva. Entrambi i piani consentono di proseguire lasciando vivo `abyss_forest_stalker`. Misure e chiavi d'interazione sono proposte da verificare nel graybox UE 5.6. [Piano della Foresta Sepolta](abyss-buried-forest-plan.md)

## Piano 13 · Terrazze dei rami

| Spazio | Layout e vincolo |
| --- | --- |
| Arrivo | Pianerottolo largo di fronte a due percorsi leggibili. La rampa lunga si vede già dall'ingresso e una radice sporgente segnala il passaggio rapido. Metti il checkpoint fuori dal raggio massimo dell'incontro. |
| Terrazza bassa | Parti da una piazzola di 1000 × 800 cm. Riserva 250 cm liberi sul lato opposto al tronco oltre le pose estreme del mostro. Il bordo vicino al dirupo ha una barriera bassa continua che lascia visibile l'atterraggio. |
| Tronco e appigli | Lo Stalker sale solo su attacchi posati sul tronco inclinato. Ogni appiglio collega una piazzola valida a terra e un'ancora di atterraggio con collisione verificata. Se l'ancora non è percorribile, la creatura resta a terra e riprende la pattuglia. |
| Bivio e ricongiungimento | Il percorso breve passa per la piazzola bassa: attira il balzo, spostati oltre il bordo del colpo e passa durante il recupero. La rampa esterna mantiene visuale sulla creatura e arriva alla stessa terrazza alta; aggiungi una rientranza all'ultimo tornante per fermarsi e leggere l'aggro. Nessun salto obbligatorio su entrambe le vie. |
| Scala e discesa | La terrazza alta ospita lo scrocco. Interagire dal lato di arrivo abbassa la scala tra le terrazze e libera il percorso verso il piano 14. La scala permette di tornare al bivio. Lascia una piazzola tra scrocco e uscita affinché la camera possa riallinearsi. |

Prima del balzo lo Stalker si raccoglie sulle zampe e indica il punto di atterraggio con sguardo e bordo a terra. Il punto si fissa prima che lasci l'appiglio. La rampa lunga resta al di fuori del volume d'impatto in tutti gli stati, anche se la creatura segue il giocatore a terra. Dopo l'atterraggio una via laterale rimane libera e la camera mantiene visibili lo Stalker e almeno una via di fuga. Consenti l'apertura dello scrocco durante l'aggro; la sconfitta della creatura non fa parte del requisito.

## Piano 14 · Bacino delle felci

| Spazio | Layout e vincolo |
| --- | --- |
| Arrivo | Fascia asciutta con checkpoint e vista sulle due prese. Muri bassi e felci suggeriscono una traversata breve e un percorso di servizio rialzato lungo il perimetro. Il canale d'uscita è visibile dall'arrivo. |
| Riva e passerelle | Parti da passerelle con 200 cm di larghezza utile e piazzole asciutte di 350 × 350 cm ai comandi. Interrompi la linea tra le due piazzole con un setto di roccia basso. Una via di ritorno collega entrambe all'arrivo anche quando la creatura occupa la riva. |
| Presa alta e presa bassa | Monta due volantini separati. La presa alta usa la passerella dal lato dell'ingresso, la bassa una rampa accessibile dalla passerella opposta o dal percorso di servizio. Entrambi gli ordini devono essere percorribili anche dopo lo scarico parziale. |
| Canale d'uscita | Un livello d'acqua iniziale e uno intermedio mostrano lo stato delle prese; in entrambi un accesso fisico chiuso blocca il canale. Con entrambe le prese confermate l'acqua scende sotto il gradino d'uscita e il passaggio verso il piano 15 si apre. |

Lo Stalker pattuglia la riva asciutta e balza verso le piazzole di atterraggio previste. Onde e felci piegate rinforzano la direzione annunciata dalla posa; il bordo del colpo rimane leggibile anche senza riflessi. Per evitare il combattimento, raggiungi le piazzole attraverso il percorso rialzato oppure usa il recupero dopo il balzo. Il percorso rialzato aggira l'incontro e riconduce ai due comandi. Entrambe le prese restano necessarie su ciascuna strada. Un comando in corso si può interrompere senza modificare lo stato; la presa confermata resta aperta, anche se il tentativo sull'altra fallisce.

## Interazioni, ricevute e ricarica

- Proporre gli ID `abyss_013_stair_release`, `abyss_014_drain_upper` e `abyss_014_drain_lower` nel catalogo del piano. Associare ogni interazione alla propria ancora e verificare identità, piano, distanza e raggiungibilità prima di richiedere il salvataggio. Una richiesta ripetuta per lo stesso esito usa la stessa identità di ricevuta. Una richiesta incompatibile con una ricevuta esistente è rifiutata.
- Save registra ricevuta ed esito insieme. L'animazione può mostrare la manovra in corso; apertura definitiva, collisione, acqua e indicatori di obiettivo riflettono soltanto l'esito confermato. Per il Bacino deriva il livello dell'acqua e l'accesso al canale dalle due prese registrate, senza un terzo salvataggio indipendente.
- Se la ricevuta tarda, mostra lo stato in corso e lascia spazio per arretrare. Se la richiesta fallisce, mantieni la scala o la presa nello stato precedente, conserva l'eventuale altra presa già confermata e riabilita l'interazione. Se la risposta si perde, leggi lo stato autorevole prima di ritentare; una ricevuta già confermata ripristina la vista senza ripetere gli effetti. Non consumare oggetti o assegnare ricompense per i tentativi.
- Al rientro da checkpoint ricostruisci la scala e le prese dallo stato durevole e riposiziona lo Stalker sulla pattuglia nelle condizioni previste dal sistema di salvataggio. Una ricarica fallita deve rendere ripetibile il recupero del checkpoint senza azzerare i progressi. Conferma la presenza a pavimento e il controllo del personaggio dopo ogni ripresa. Un'uscita anticipata o un caricamento fallito non avanzano il piano.

## Segnali in gioco

Testo breve per indicatori e sottotitoli ambientali. Il tono descrive ciò che Kael vede o fa, senza anticipare le spiegazioni sulla Gilda.

| Contesto | IT | EN |
| --- | --- | --- |
| Bivio delle Terrazze, osservazione facoltativa di Kael | «Da lassù mi vede. La rampa passa più larga.» | “It can see me from up there. The ramp gives me more room.” |
| Azione sulla terrazza alta | Abbassa la scala | Lower the ladder |
| Arrivo al Bacino, obiettivo | Apri le due prese di drenaggio | Open both drains |
| Indicatore dopo la prima presa | Una presa è aperta | One drain is open |
| Conferma del drenaggio | Il canale è libero | The channel is clear |
| Conferma in attesa | Salvataggio in corso | Saving |
| Manovra rifiutata con stato ancora chiuso | Riprova la manovra | Try the mechanism again |

## Collaudo mirato

1. Attraversa la via breve e la rampa lunga del 13 lasciando vivo lo Stalker. Testa lo scrocco da entrambi i lati, il balzo verso un'ancora occupata, il tentativo di saltare il blocco e la ricarica dopo l'abbassamento della scala.
2. Apri prima la presa alta e poi la bassa al 14; ripeti in ordine opposto. Verifica il percorso rialzato lasciando vivo lo Stalker, la condizione intermedia e la tenuta del passaggio chiuso in immersione e dalla riva.
3. Per ciascun ID d'interazione induci rifiuto prima del salvataggio e perdita della risposta dopo il salvataggio. Riprova e ricarica. Verifica un solo esito durevole, collisione allineata alla grafica e avanzamento soltanto dopo l'uscita valida.
4. Esegui i percorsi con tastiera e controller, senza audio, agli angoli della camera più stretti. Verifica che un giocatore riesca a distinguere percorso facoltativo, obiettivo obbligatorio e segnale del balzo senza affidarsi al colore.

Prove runtime da eseguire in UE 5.6.
