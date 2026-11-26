# Capitolo 2 — La prima discesa

Act: 1 | Chapter: 2 | Language: it | Status: expanded working script (cycle 02, pending review) | Canon: narrative/story.md

## ch_02_sc_001 — INT. GILDA, MATTINA
Il funzionario registra Kael. Il giocatore conferma iscrizione e ritira equipaggiamento base.
- ch_02_sc_001_dl_001 — Funzionario: «Nome, età, residenza.»
- ch_02_sc_001_dl_002 — Kael: «Kael Veyr. Diciannove. Quartiere delle fucine.»
- ch_02_sc_001_dl_003 — Funzionario: «Rango F. Primo livello. Torna vivo e consegna il rapporto.»
- ch_02_sc_001_dl_004 — Kael: «Tutto qui?»
- ch_02_sc_001_dl_005 — Funzionario: «Per chi torna, sì.»
## ch_02_sc_002 — INT. ABISSO, LIVELLO 1
Tutorial: movimento, attacco, schivata, parata; sconfiggere i mostri richiesti, senza contatore inventato. Dopo il combattimento Kael si appoggia al muro. Per pochi secondi il suono si attenua e la geometria appare disallineata; voce incomprensibile, nessuna parola intelligibile. Opzione accessibilità senza lampeggi.
- ch_02_sc_002_dl_001 — Kael: «Che... cosa?»
- ch_02_sc_002_dl_002 — Kael: «Devo aver trattenuto il respiro.»
Il controllo ritorna; raggiungere l'uscita. La mutazione non è un premio né una scelta.
## ch_02_sc_003 — INT. DORMITORIO, NOTTE
- ch_02_sc_003_dl_001 — Sorvegliante: «Le reclute dormono qui la prima notte. Domani potrai tornare dai tuoi.»
- ch_02_sc_003_dl_002 — Kael: «Non credo che riuscirò a dormire.»
Rumore della pioggia. Kael posa l'equipaggiamento, interazione letto; transizione al mattino.
## ch_02_sc_004 — INT. CASA VEYR, MATTINA
La porta si apre. Noah, tre anni, corre verso Kael e lo abbraccia. Il giocatore non può attaccare; la camera scende all'altezza del bambino.
- ch_02_sc_004_dl_001 — Noah: «Fratellone!»
- ch_02_sc_004_dl_002 — Kael: «E tu chi sei?»
- ch_02_sc_004_dl_003 — Elara: «Ti ha aspettato tutta la notte. Noah, lascialo entrare.»
- ch_02_sc_004_dl_004 — Kael: «Mamma. Chi è Noah?»
- ch_02_sc_004_dl_005 — Lyra: «Spiritoso. Adesso gli hai fatto fare quella faccia.»
- ch_02_sc_004_dl_006 — Darius: «Kael, è tuo fratello. Ti senti bene?»
- ch_02_sc_004_dl_007 — Noah: «Hai male?»
Kael si inginocchia senza rispondere. Il giocatore esamina disegni, vestiti, documento di nascita; ciascun reperto ha testo coerente con tre anni di storia, nessuna prova soprannaturale.
- ch_02_sc_004_dl_008 — Kael: «Ieri... non c'erano.»
- ch_02_sc_004_dl_009 — Elara: «Siediti. Ti porto dell'acqua.»
Completion: floor 1 objective, return, dormitory and reveal completed; mandatory evidence inspection. Save: atomically persist changed household, original memory and reveal completion; replay/skip must not repeat transition. Quest: no alternate route bypasses reveal. Audio: restrained anomaly, domestic silence. Cinematics: child embrace, no magical visual on Noah.

## Cycle 02 production inserts

## ch_02_sc_005 — INT. GILDA, RITORNO (insert after sc_002)
Player hands report to clerk; no duplicate rewards on repeated dialogue. Only validated combat and exit permit reporting.
- ch_02_sc_005_dl_001 — Funzionario: «Sei tornato. Hai incontrato difficoltà?»
- ch_02_sc_005_dl_002 — Kael: «Mi ha fatto male la testa. Solo per un momento.»
- ch_02_sc_005_dl_003 — Funzionario: «Riposa. Il dormitorio è lungo il corridoio.»
- ch_02_sc_005_dl_004 — Kael: «Posso avvisare casa?»
- ch_02_sc_005_dl_005 — Funzionario: «Domattina potrai andare di persona.»
## ch_02_sc_006 — INT. DORMITORIO, PRIMA NOTTE (extends sc_003)
Inspect assigned bunk and water jug; other recruits are background, no revelations. Player selects rest or continue looking around. Rest is mandatory eventually; cancel returns control.
- ch_02_sc_006_dl_001 — Recluta: «Prima discesa?»
- ch_02_sc_006_dl_002 — Kael: «Si vede così tanto?»
- ch_02_sc_006_dl_003 — Recluta: «Solo perché tieni ancora gli stivali.»
- ch_02_sc_006_dl_004 — Kael: «Giusto.»
- ch_02_sc_006_dl_005 — Kael: «Domani racconterò tutto a Lyra.»
Fade to black on confirmed rest; commit dormitory_night once; morning exit only after committed snapshot. No child's voice, silhouette or prophetic dream.
## ch_02_sc_007 — INT. CASA VEYR, PROVE (after sc_004 dialogue 009)
Player examines three distinct items in any order. Evidence text is localized and not a gameplay ID.
- ch_02_sc_007_dl_001 — Kael: «Questi disegni sono tutti suoi?»
- ch_02_sc_007_dl_002 — Lyra: «Sì. Quello con la spada sei tu.»
- ch_02_sc_007_dl_003 — Kael: «E questi vestiti?»
- ch_02_sc_007_dl_004 — Elara: «Alcuni erano tuoi, quando eri piccolo.»
- ch_02_sc_007_dl_005 — Kael: «Il registro dice che è nato tre anni fa.»
- ch_02_sc_007_dl_006 — Darius: «Certo. Vuoi che venga con te dal guaritore?»
- ch_02_sc_007_dl_007 — Noah: «Sei arrabbiato?»
- ch_02_sc_007_dl_008 — Kael: «No. Non con te.»
Choice A (gentle): 
- ch_02_sc_007_dl_009 — Kael: «Scusami. Sono stanco.»
Choice B (quiet):
- ch_02_sc_007_dl_010 — Kael: «Ho bisogno di sedermi un momento.»
Both converge; no relationship penalty, no denial of Noah's existence. 
- ch_02_sc_007_dl_011 — Elara: «Resta qui quanto vuoi.»
The three inspections precede final reveal acknowledgement; noah_reveal emitted once after acknowledgement, not upon cinematic start. Save must publish post-discrepancy household before child spawn, without treating visual presentation as state authority. If interrupted, reload committed household and resume only unacknowledged evidence/reveal. Defeat in dungeon resumes before uncommitted combat; no anomaly replay if already committed.
Storyboard ch_02_sb_001 registration desk; ch_02_sb_002 combat and anomaly (steady camera fallback, caption "[Voce indistinta]"); ch_02_sb_003 bunk and dawn; ch_02_sb_004 door, child's run, hug, Kael close-up, Elara reaction; ch_02_sb_005 free camera evidence. 18 seconds from 14 is a provisional shot envelope for opening beats, not a duration for all dialogue. Audio: music_abyss_catacombs, sfx_discrepancy_pulse (subtle), sfx_weather_rain, music_noah only after Noah is visible. No intelligible anomaly words.
