# Capitolo 4 — Il centesimo livello

Act: 2 | Chapter: 4 | Language: it | Status: first draft (partial) | Canon: narrative/story.md

## ch_04_sc_001 — Catacombe–Santuario del Silenzio
Durante la discesa attraverso i dieci biomi, il giocatore supera i checkpoint dei livelli 10, 20, 30, 40, 50, 60, 70, 80 e 90. I marchi sui mostri e i meccanismi di contenimento diventano visibili senza spiegazione. Al 70 si osserva la statua; al 90 un mostro morente parla.
- ch_04_sc_001_dl_001 — Selene: «Questa incisione è identica a quella sulla porta della Gilda.»
- ch_04_sc_001_dl_002 — Kael: «Forse qualcuno è arrivato qui prima di noi.»
- ch_04_sc_001_dl_003 — Mostro: «Ricorda.»
- ch_04_sc_001_dl_004 — Kael: «Aspetta! Hai detto qualcosa?»

## ch_04_sc_002 — Cuore dell'Abisso, livello 100
Combattere il Custode imprigionato nella struttura. Dopo la vittoria, esaminare la porta con il simbolo dell'Egida, chiusa dall'esterno.
- ch_04_sc_002_dl_001 — Riven: «È finita. Possiamo tornare.»
- ch_04_sc_002_dl_002 — Kael: «Guarda i cardini. Qualcuno l'ha chiusa dall'altra parte.»
- ch_04_sc_002_dl_003 — Riven: «Allora chiediamolo a chi ha la chiave.»

## ch_04_sc_003 — Valdris, ufficio del Maestro
Aldren consegna il Sigillo dell'Egida e spiega il vero scopo del dungeon e l'esistenza della seconda cinta. Kael riceve la prova dei cento Giganti.
- ch_04_sc_003_dl_001 — Aldren: «L'Abisso è opera nostra. Non potrebbe riversarsi sulla città.»
- ch_04_sc_003_dl_002 — Kael: «Ci avete insegnato il contrario.»
- ch_04_sc_003_dl_003 — Aldren: «Vi abbiamo insegnato a combattere. Ora saprai perché.»
- ch_04_sc_003_dl_004 — Kael: «E se il dungeon cambiasse i ricordi?»
- ch_04_sc_003_dl_005 — Aldren: «Non tutti i ricordi meritano di essere recuperati, ragazzo.»

Completion: Abyss floor 100, Custodian defeated, door inspected, Sigil granted; unlock first wall only. All ten biome encounter scripts still require expansion.
Dependencies: Quest maps gates and validated events; Save persists completion idempotently; Cinematics stages reveal and control handoff; Audio records dialogue and environment cues. Detailed encounter and alternative dialogue passes pending.

## Cycle 02 production insert

## ch_04_sc_004 — Livello 90, dopo il combattimento (prima di sc_002)
Il giocatore può avvicinarsi alla creatura morente o mantenere la distanza; la battuta «Ricorda» di sc_001 viene riprodotta in entrambi i casi, una sola volta. Nessun riferimento a un Custode parlante.
- ch_04_sc_004_dl_001 — Selene: «L'hai sentito anche tu?»
- ch_04_sc_004_dl_002 — Kael: «Sì. Ma non so che cosa volesse dire.»
- ch_04_sc_004_dl_003 — Riven: «Non restiamo qui. Qualunque cosa fosse, abbiamo ancora dieci livelli davanti.»
Choice: annotate the word immediately or defer journal access; the mandatory discovery persists regardless. At level 100 the Custodian is a separate encounter, not the speaker. Quest 08: legacy mq_04_line_1 speaker must be corrected to the floor-90 monster; no shared file change.
