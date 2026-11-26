# Revisione del dettaglio degli asset di EIDOLON

La revisione parte dai 22 GLB originali delle Catacombe, di Valdris e della Foresta Sepolta. Le versioni iniziali esportavano le normali geometriche e i valori dei materiali. Le texture procedurali osservabili in Blender restavano nella scena sorgente. Dieci asset avevano almeno una mesh priva di UV.

## Direzione artistica

- La forma deve reggere una vista ravvicinata. Corteccia e radici seguono la crescita delle fibre. Le scaglie si spezzano con spessore e bordi irregolari. Pietra stratificata, giunture, tendini e parti usurate si distinguono nella sagoma e nelle ombre.
- Associa il dettaglio al materiale e all’uso. La rugosità varia tra il bordo affilato di una lama, l’ossidazione del ferro e la superficie tesa fra le piastre. Mantieni leggibili il punto debole e la direzione di un attacco con la stessa illuminazione.
- Porta nel GLB le mappe di colore, rugosità, metallicità e normali tangenti. Verifica le UV e reimporta il GLB prima del render di revisione. Conserva dimensioni, perni e gruppi mobili. Controlla il passaggio effettivo nei portali e attorno agli oggetti.
- Presenta una vista d’insieme e un dettaglio. Per valutare le superfici, usa luce e camera equivalenti. In Unreal 5.6 verifica il rig, la silhouette in movimento, gli LOD, la collisione e il costo in luce neutra e in scena.

## Stato della revisione

| Gruppo | Intervento | Verifica |
| --- | --- | --- |
| Tutti i 22 asset | Primo passaggio sulle superfici. Mappe originali a 1024 px, UV aggiunte alle primitive che le richiedevano. Geometria e trasformazioni di partenza preservate. | Catalogo, file incorporati, hash e reimportazione Blender. |
| Predatore delle Radici | Placche di corteccia con spessore, fibre orientate, testa e arti rielaborati. | Reimportazione, scala e confronto in Blender con luce e camera equivalenti. |
| Groviglio della faglia | Strati fratturati, fenditure geometriche e radici scanalate. | Reimportazione, perni, ingombro, mappe e render ravvicinato. |
| Catacomb Crawler | Piastre scheggiate, cresta asimmetrica e fibre tra le articolazioni. | Reimportazione e render del corpo. |
| Zecca d’ossario, Mantide d’architrave, Ariete midollare e Tenaglia della volta | Placche aperte lungo i bordi, fibre nei punti di flessione, profili asimmetrici e faccette degli occhi. | Reimportazione con verifica di ingombri, appoggio al suolo, UV e tangenti. Confronti a luce e camera equivalenti. |
| Missina del turibolo, Sanguisuga della malta, Millepiedi a sonaglio e Chela delle Radici | Pieghe di bocca e branchie, uncini consumati, segmenti dorsali rimodellati e fratture stratificate della corazza. | Stesse verifiche geometriche e materiali. Viste intere e ravvicinate del GLB reimportato. |
| Arco di radici e Belvedere della vena | Fibre, scaglie, superfici di cava, usura sul piano di camminamento. | Reimportazione e controllo geometrico di passaggio per entrambi. |
| Spada da recluta e urna funeraria | Rifacimento di bordi, ferri e finiture di contatto, con coperchio dell’urna separato. | Reimportazione, dimensioni, perno e dettagli ravvicinati. |
| Belvedere della Radura obliqua e scala delle Terrazze dei rami | Strati e scagliature nell’ardesia. Venature incise nei montanti, nei pioli e nel legno dell’argano. | 35 verifiche di appoggio sulla terrazza. Undici pioli a larghezza intera e rotazione di 30° della scala con asse fisso. |
| Presa del Bacino delle felci e perno del tronco cavo | Muratura sfogliata, corrosione superficiale del ferro e del bronzo, rilievo della corteccia. | Rotazione di 90° della ruota con la presa fissa. Trenta posizioni del perno lungo 58 cm di estrazione. |
| Saracinesca del Canale delle radichette, passerella dei Tronchi sospesi e chiavistello della Doppia radura | Scheggiature della pietra, fibre delle travi e delle radici, usura del ferro e dell’impugnatura. | 56 raggi nel varco aperto, 57 punti sugli appoggi del ponte e 19 pose di rotazione, due scatti e 38 pose di transito del chiavistello. |

Le revisioni hanno origine interna al progetto. Il passaggio sulle superfici e sulla geometria copre tutti i 22 GLB iniziali. Le gallerie in `eidolon-tools/previews/art-fidelity` conservano confronti, comandi di riproduzione e report individuali. Restano il rig delle creature, l’ottimizzazione degli asset e i collaudi visivi e di gioco in Unreal. La produzione delle Miniere Perdute segue la stessa verifica di modelli e materiali.
