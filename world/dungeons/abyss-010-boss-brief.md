# Piano 10 | Boss dell'Anticamera delle radici

| Campo | Proposta |
| --- | --- |
| Piano e ID creatura | `abyss_010` · `boss_abyss_10` |
| Nome visualizzato IT / EN | **Chela delle Radici** / **Rootclaw** |
| Ruolo | Caposaldo delle Catacombe. Mette alla prova lettura della direzione, uso dei fianchi e recupero dopo un colpo evitato. |
| Stato | Brief di design da revisionare. Metriche iniziali per il graybox, da riscontrare in UE 5.6. |

L'Anticamera delle radici conserva il cortile con Strisciante e Tenaglia in nicchie separate, il checkpoint sul pianerottolo e l'arena senza nemici comuni. La creatura riprende la chela asimmetrica della Tenaglia come segnale di direzione e ha sagoma, rig e set di mosse propri. Radici e pietra descrivono l'ambiente e la superficie delle placche. [Piano delle Catacombe](abyss-catacombs-plan.md) · [Bestiario](../../art/creatures/first-descent-bestiary.md) · [Mappatura proposta](https://github.com/eidolon-game/eidolon-game/blob/82c869f35e384c2b1462274e45612f928ea9e57e/Source/Eidolon/Dungeons/Data/boss_floor_mapping.json)

## Mosse e contrattacco

Gli intervalli sono valori iniziali in secondi da provare con il personaggio del progetto. Preparazione, danno e recupero usano eventi dell'animazione condivisi tra combat, effetti e audio.

| Mossa | Preparazione e finestra attiva | Risposta e recupero |
| --- | --- | --- |
| Spazzata della chela | Solleva la chela grande dal lato del colpo. Fissa asse e verso dopo circa 0,55 s. Dopo altri 0,35 s, la chela segue un arco frontale per circa 0,25 s. | Esci dall'arco verso il lato leggero o arretra oltre la portata. La chela rimane a terra per circa 1,1 s e lascia esposta la cerniera del fianco. L'animazione e il volume di danno devono concordare in ogni posa. |
| Affondo corto | Ritrae mandibola e appendice piccola per circa 0,75 s. Blocca il punto d'impatto nell'ultimo terzo della preparazione. Il colpo avanza lungo l'asse, con attività iniziale di 0,18 s. | Spostati lateralmente e sfrutta circa 0,75 s di recupero. Il boss usa l'affondo quando il bersaglio si ferma nella corsia frontale. |
| Passo di corsia | Dalla seconda fase, evidenzia con la testa e gli arti il punto di arrivo, poi si sposta in una corsia adiacente lungo il raccordo. Il segnale dura almeno 1,2 s. Dopo il passo, resta fermo circa 0,8 s prima di poter preparare un nuovo attacco. | Muoviti sul raccordo libero o resta fuori dalla sagoma d'arrivo. Il passo non infligge danni. Se la sagoma d'arrivo è occupata, l'IA ferma il movimento e rivaluta la posizione dopo il recupero, lasciando libera la via d'uscita. |

**Sequenza al 50%.** Al primo attraversamento del 50% di salute con il boss ancora vivo, memorizza la richiesta di transizione. Completa il recupero della mossa corrente, interrompi la selezione di attacchi e segnala il primo passo di corsia con una posa più lunga e un colpo secco della chela. La seconda fase comincia al termine del passo e rende disponibile la stessa riposizione tra i normali attacchi. La transizione avviene una volta per tentativo, senza ripristinare salute o imporre uno stacco di camera. Se un colpo è letale, risolvi direttamente la sconfitta. Alla ripartenza dal checkpoint ricostruisci il boss all'inizio della prima fase. Mantieni invece la sconfitta già confermata e l'uscita aperta dopo la sua registrazione.

## Arena, camera e sicurezza delle corsie

- Blocca uno spazio iniziale di **2000 × 2400 cm** da verificare con camera e navigazione. Riserva tre corsie longitudinali da almeno **600 cm** di larghezza utile ciascuna, collegate da aree di cambio corsia larghe almeno **300 cm** alle due estremità e a metà. Incassa radici, pilastri, battute del cancello e stipiti oltre queste larghezze. Segnala le corsie con la posa delle lastre e con fonti di luce costanti.
- Lascia una corsia laterale raggiungibile dal giocatore prima dell'attività di ogni colpo. Prova l'arco della spazzata dal centro, vicino ai due bordi e con il boss in ciascuna corsia. Se una posa chiude entrambi i raccordi, l'IA deve riposizionarsi prima di iniziare quella mossa. Il boss non attraversa l'ingresso o l'uscita e non inizia un passo mentre un colpo è attivo.
- Mantieni l'aggancio al corpo durante la transizione. L'aggancio non deve ricentrare di colpo sul punto di arrivo; se il personaggio è contro la parete, la camera si retrae senza attraversare la mesh e conserva in quadro chela, traiettoria e fuga più vicina. Verifica visuale con e senza aggancio, anche nei raccordi e subito dopo l'ingresso. Fornisci segnali di posa e bordo del colpo indipendenti da audio, colore e vibrazione. Offri un'opzione senza scuotimento.
- Il cancello verso la Foresta Sepolta si apre dopo la conferma persistente della sconfitta. Fallimento di spawn e interruzione del caricamento devono consentire il retry dal pianerottolo. L'ingresso in arena e la riapertura dopo ricarica richiedono clearance e collisione verificate con il pawn.

## Consegna degli asset

| Disciplina | Consegna richiesta |
| --- | --- |
| Concept e mesh | Tre viste ortogonali, confronto di scala con Kael e Tenaglia, silhouette della chela e della cerniera leggibile con luce radente. Mesh grigia prima dei dettagli, origine a terra, unità UE in cm, LOD e UV verificabili. Ingombro proposto in posa neutra **440 × 320 × 260 cm**, da provare nelle corsie con gli arti in movimento. |
| Rig e animazione | Catene indipendenti per chela, appendice leggera, mandibola e arti. Clip separate per attesa, svolta, due direzioni della spazzata, affondo, recuperi, passo laterale, transizione e morte. Marcare fissaggio bersaglio, attività, recupero e fine spostamento. Verificare il movimento in entrambe le direzioni. |
| Collisione e combat | Volumi distinti per corpo, chela, affondo e cerniera esposta. La protezione della cerniera segue la posa e la finestra della mossa; i volumi offensivi si disattivano al termine o all'interruzione valida. Tracciare il bordo del colpo tra i frame per evitare salti del volume durante lo swing. |
| Materiali, effetti e audio | Materiale pietra ossea del roster come base, placche stratificate e cerniera leggibile anche senza effetto. Effetti sul contatto col pavimento, segnale discreto del cambio corsia, suoni distinti di preparazione, impatto e recupero. Registra sorgenti, licenze e prove di importazione. |

## Criteri di accettazione

1. Schiva e contrattacca da centro e corsie laterali con tastiera/mouse e controller. Evidenza richiesta di un percorso libero durante ogni finestra attiva, anche con audio e scuotimento disattivati.
2. Supera il 50% durante preparazione, colpo e recupero. Verifica una sola transizione al termine della mossa. Prova il colpo letale da sopra il 50%, un punto d'arrivo occupato e una partenza con camera contro il muro.
3. Sopprimi lo spawn, ritenta dal checkpoint, poi sconfiggi il boss e ricarica. Verifica uscita chiusa fino alla registrazione della sconfitta, apertura persistente e accesso al piano 11 una sola volta per completamento.

Registra l'identità della build, il log e l'esito di ogni prova. Le prove richiedono mappa, asset importati e runtime UE 5.6.
