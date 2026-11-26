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

Le revisioni hanno origine interna al progetto. Il lavoro sulla geometria copre 15 asset su 22, comprese tutte le 11 creature finora esportate. Restano la revisione ravvicinata delle sette geometrie ambientali e dei meccanismi, il rig delle creature e l’integrazione nel motore. La galleria in `eidolon-tools/previews/art-fidelity/catacombs` conserva i confronti, i comandi di riproduzione e i report individuali. Le Miniere Perdute riprendono dopo la revisione degli asset precedenti.
