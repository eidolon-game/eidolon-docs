# Tronchi sospesi e Doppia radura

Brief di implementazione per `abyss_017` e `abyss_018`. Dal Canale delle radichette, Kael raggiunge due attraversamenti divisi da un'isola e poi due radure contigue. Il piano 17 separa le minacce nello spazio; il 18 coordina i loro attacchi nel tempo. Gli incontri usano `abyss_forest_stalker` e possono essere affrontati senza ucciderlo. Identificatori e dimensioni restano proposte per il graybox. [Piano della Foresta Sepolta](abyss-buried-forest-plan.md) · [Canone dell'Abisso](../../narrative/story.md#atto-ii--i-cento-livelli-dellabisso) · [Piani 15–16](abyss-hollow-trunk-rootlet-canal.md)

## Piano 17 · Tronchi sospesi

Il primo attraversamento è un tronco fisso dall'ingresso all'isola. Dal centro dell'isola, una passerella girevole collega a scelta una rientranza laterale o l'approdo di uscita. Entrambi gli approdi consentono di tornare all'isola dalla stessa passerella. Il comando resta sull'isola e la rotazione avviene soltanto a passerella vuota. Il checkpoint è sulla sponda iniziale. Prova larghezze utili iniziali di 220 cm per il tronco e 250 cm per la passerella, con parapetti al di fuori della fascia utile. Riserva sull'isola almeno 650 × 650 cm calpestabili per comando, inversione e camera.

| Ancora proposta | Posizionamento e uso |
| --- | --- |
| `abyss_017_entry_checkpoint` | Sponda stabile, rivolta ai due attraversamenti. Il caricamento lascia il pawn fuori dal volume di attivazione del primo Stalker. |
| `abyss_017_near_stalker_spawn`, `abyss_017_near_stalker_landing` | Primo settore presso il tronco fisso. L'ancora di atterraggio controlla il tratto a riva, con una rientranza laterale utile prima del colpo. |
| `abyss_017_island`, `abyss_017_bridge_control` | Nucleo sicuro dell'isola, fuori dalla rotazione e dalla portata offensiva di entrambe le minacce. Il comando è visibile da entrambi gli approdi. |
| `abyss_017_bridge_pivot`, `abyss_017_bridge_side_dock`, `abyss_017_bridge_far_dock` | Perno e due approdi con pose discrete. Per ciascuna posa, verifica che la passerella si allinei alla quota dell'approdo e che la collisione sia continua. |
| `abyss_017_far_stalker_spawn`, `abyss_017_far_stalker_landing` | Secondo settore oltre l'isola. Il balzo termina sulla sponda, fuori da passerella e isola. Riserva una nicchia all'approdo per uscire dal bersaglio del balzo. |
| `abyss_017_exit` | Sponda lontana, oltre il secondo impatto e raggiungibile da un percorso laterale. Viaggio consentito dopo l'allineamento confermato alla sponda di uscita. |

Il primo Stalker minaccia l'avvicinamento al tronco fisso, il secondo l'approdo dopo la passerella. Entrambi hanno visuale, appigli e collisioni confinati al proprio settore. L'isola interrompe l'inseguimento e offre riparo anche se entrambe le creature sono attive. In graybox, misura i volumi di balzo dilatati del raggio del pawn e verifica che siano disgiunti e non tocchino l'isola. Le creature possono ritirarsi o essere sconfitte. Per evitare lo scontro, lascia che fissino l'atterraggio nella rispettiva zona a riva e attraversa durante il recupero. La rientranza all'approdo lontano resta raggiungibile senza esporsi di nuovo alla traiettoria.

Interazione proposta `abyss_017_bridge_align`. Valida l'origine, la posa richiesta e l'assenza di pawn od ostacoli sul piano rotante. Mentre il movimento è in corso, il blocco d'accesso sull'isola impedisce di salire nella zona di rotazione e il controllo del personaggio resta attivo. Dopo l'allineamento confermato, riapri solo il collegamento alla sponda selezionata. Se la posa iniziale è verso la rientranza, il primo allineamento confermato verso l'uscita soddisfa il requisito di progressione. Un'eventuale rotazione successiva mantiene la posa effettiva distinta dal fatto che il primo allineamento sia avvenuto. Impedisci il viaggio dal lato di uscita se il collegamento e l'arrivo del pawn non sono validi.

## Piano 18 · Doppia radura

Due camere legate da un arco largo almeno 500 cm e da una fascia laterale continua, inizialmente larga 350 cm. Uno Stalker emerge a terra nella prima radura. Il secondo scende da un appiglio nella seconda. La paratia è visibile entrando e il chiavistello si raggiunge sul fianco protetto della seconda radura. Una rientranza presso il comando offre ritirata verso l'arco e resta agibile con la paratia chiusa.

| Ancora proposta | Posizionamento e uso |
| --- | --- |
| `abyss_018_entry_checkpoint` | Ripresa in sicurezza prima della prima radura. |
| `abyss_018_ground_stalker_spawn`, `abyss_018_ground_stalker_landing` | Primo Stalker a terra, con settore di attacco nella prima camera. |
| `abyss_018_high_stalker_perch`, `abyss_018_high_stalker_landing` | Secondo Stalker sopra la seconda camera. L'appiglio presenta la creatura contro uno sfondo leggibile e l'atterraggio rimane lontano dalla paratia. |
| `abyss_018_side_refuge`, `abyss_018_arch` | Riserva laterale e collegamento largo tra le camere. Larghezza e camera devono permettere di girarsi e vedere l'atterraggio. |
| `abyss_018_latch`, `abyss_018_gate`, `abyss_018_exit` | Un comando con due scatti leggibili, un varco con collisione separata e l'uscita verso il Belvedere della vena. |

Gestisci un solo attacco che restringe lo spazio alla volta. Acquisisci la finestra condivisa prima della preparazione e rilasciala dopo il recupero, l'annullamento valido o la sconfitta. Il secondo Stalker può attendere sull'appiglio mentre il primo attacca. Annuncia distintamente la sua discesa e mantieni percorribile almeno un collegamento laterale durante l'intera finestra. Una creatura incapace di raggiungere l'ancora di atterraggio rilascia la finestra e torna alla pattuglia. Il giocatore può usare il riparo e aspettare tra i due attacchi per manovrare.

| Interazione proposta | Requisito e risultato confermato |
| --- | --- |
| `abyss_018_latch_first_set` | Kael è al comando, nella portata prevista, con chiavistello a riposo. Il primo scatto inserisce il fermo e accende l'indicatore meccanico. La paratia resta chiusa. |
| `abyss_018_latch_second_set` | Il primo scatto risulta confermato e Kael è al comando. Il secondo scatto libera la paratia. Una perdita di controllo prima del commit permette di ritrovare il primo scatto dopo la ritirata. |

## Salvataggio, rollback e aggiramenti

- **Ponte.** Valida la revisione della posa prima di accettare un cambio. Per un retry della stessa manovra conserva l'identità della richiesta; una rotazione deliberata successiva usa una nuova revisione. Prima del commit, visualizza la manovra senza rendere percorribile il nuovo approdo. Se la scrittura viene rifiutata, riporta ponte e collisione all'ultima posa confermata, sblocca il comando e mantieni libero il tronco fisso. Dopo una risposta persa, leggi lo stato autorevole e ripristina la posa registrata prima di accettare un nuovo cambio.
- **Chiavistello.** Usa una ricevuta distinta per ogni scatto, collegando il secondo alla revisione confermata del primo. Ricevuta e stato vengono salvati insieme. Il rifiuto del primo lascia lo stato a riposo. Il rifiuto del secondo mantiene il fermo del primo inserito e la paratia chiusa. Ripetizioni della stessa richiesta ripresentano l'esito senza ripetere il progresso. Respingi il secondo scatto prima del primo, anche se arrivano insieme.
- **Ripresa.** Dopo ricarica, posa, collisioni e segnali derivano dallo stato confermato. Ripristina il checkpoint solo dopo una lettura valida. Se la lettura fallisce, consenti un nuovo tentativo senza azzerare i progressi. Se lo spawn di uno Stalker opzionale fallisce, conserva il percorso degli obiettivi ambientali e ritenta soltanto dallo slot del suo settore. Durante la transizione al piano successivo, aggiorna il piano solo dopo aver verificato appoggio e controllo alla destinazione.
- **Bypass previsto.** Aggirare o aspettare le creature è valido su entrambi i piani. Prova bordi, tronchi decorativi e collisione della paratia per assicurare che il personaggio raggiunga la nuova uscita tramite l'allineamento del ponte o i due scatti. Le rientranze di fuga devono permettere un rientro al comando senza sconfitta o ricarica forzata.

## Segnali IT/EN

| Contesto | IT | EN |
| --- | --- | --- |
| Osservazione di Kael all'isola | «Qui posso fermarmi.» | “I can stop here.” |
| Comando del ponte | Allinea la passerella | Align the bridge |
| Rotazione interdetta | Libera la passerella | Clear the bridge |
| Obiettivo alla paratia | Solleva il chiavistello | Raise the latch |
| Primo scatto confermato | Fermo inserito | Catch engaged |
| Azione residua | Libera la paratia | Release the gate |
| Rifiuto della manovra | Riprova la manovra | Try the mechanism again |

## Collaudo UE 5.6

1. Percorri entrambi i rami del ponte e torna all'isola da entrambi gli approdi. Lascia vive le due creature e verifica che l'isola non venga raggiunta da un balzo. Prova rotazione a passerella occupata, rifiuto del commit e perdita della risposta. Dopo ricarica, un solo approdo deve risultare collegato nella posa salvata.
2. Attraversa la Doppia radura lasciando vivi gli Stalker. Introduci respawn e annullamento di un attacco e verifica che la finestra venga rilasciata una sola volta. Nega il primo scatto e prova il secondo in anticipo. Conferma il primo, interrompi il secondo e ricarica. Verifica un solo primo scatto persistente e la paratia ancora chiusa. Ripeti con risposta persa dopo il secondo per verificare la ricostruzione aperta.
3. Esegui entrambi i passaggi con tastiera e controller, audio disattivato e camera agganciata e libera. Verifica visibilità dei segnali, collisioni ai bordi pavimento, recovery dello spawn e nuovo viaggio dopo caricamento fallito. Registra build, percorso, log ed esiti. Prove runtime da eseguire.
