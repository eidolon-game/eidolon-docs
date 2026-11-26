# Chapter 6 and Ending IV | Capitolo 6 e Finale IV

Status / Stato — Production proposal pending director and QA review. Data and saves are unchanged by this proposal. / Proposta di produzione in attesa di revisione del direttore e del QA. La proposta non modifica dati o salvataggi.

## Chapter 6 | Capitolo 6

**IT.** Il capitolo 6 rimane nella sequenza dei 26 capitoli. Il racconto di Edran e la consegna del diario avvengono nella missione secondaria. Il passaggio al capitolo 7 deve consentire di proseguire verso la seconda cinta senza aver concluso la missione, nel rispetto del requisito canonico dei cento Giganti. Il diario viene consegnato una volta sola. La chiusura della missione facoltativa registra `edran_diary` e assegna `lost_memories` con una transazione persistente e ripetibile senza duplicati. Consenti di ritrovare Edran prima della scelta finale anche a chi ha superato il capitolo 6.

**EN.** Chapter 6 stays in the 26-chapter sequence. Edran tells his story and hands over the diary in the side quest. The transition to chapter 7 must let players continue to the second wall without completing the quest, subject to the canonical requirement of defeating one hundred Giants. Edran hands over the diary once. Completing the optional quest records `edran_diary` and grants `lost_memories` in a persistent, idempotent transaction. Keep Edran accessible before the ending choice for players who moved past chapter 6.

The experimental manifest lists meeting Edran and recovering the diary as the chapter objective, includes the handover in chapter dialogue, and also exposes recovery through a chapter-6-only interaction. The proposal moves the handover dialogue to the optional quest when the quest system can persist it. / Il manifest sperimentale elenca l'incontro e il recupero del diario come obiettivo del capitolo, include la consegna nel dialogo e offre anche un recupero limitato al capitolo 6. La proposta sposta il dialogo di consegna nella missione facoltativa quando il sistema missioni potrà salvarne lo stato. [Canon / Canone](../narrative/story.md#capitolo-6--la-famiglia-dimenticata) · [Experimental data](https://github.com/eidolon-game/eidolon-game/blob/06bc2fc0bc2254453813a44559617e2bf8dd9e05/Content/Eidolon/Data/campaign.json#L99-L117) · [Recovery interaction](https://github.com/eidolon-game/eidolon-game/blob/06bc2fc0bc2254453813a44559617e2bf8dd9e05/Source/Eidolon/EidolonGameMode.cpp#L214-L233)

## Ending IV | Finale IV

**IT.** Mantieni `freedom` e il controllo congiunto dei tre requisiti dopo lo scontro finale. `lost_memories` rappresenta il recupero di memorie nelle missioni designate; il diario di Edran è la fonte provvisoria del graybox. `eidolon_aid` richiede il completamento di una missione facoltativa di aiuto agli Eidolon; l'interazione generica con gli abitanti dimenticati del capitolo 20 è provvisoria. `origin_truth` si acquisisce dopo la rivelazione di Elyria del capitolo 24. I tre flag riassumono il progresso; il set definitivo delle missioni e i criteri per le memorie restano soggetti a revisione narrativa. Conserva le condizioni dei finali I–III.

**EN.** Keep `freedom` and require all three conditions after the final encounter. `lost_memories` represents recovering memories in designated quests; Edran's diary is the provisional graybox source. `eidolon_aid` requires completing an optional quest to help the Eidolon; the generic chapter 20 interaction with forgotten residents is provisional. Award `origin_truth` after Elyria's revelation in chapter 24. The three flags summarize progress; the final quest list and memory criteria await narrative review. Preserve the conditions for endings I–III. [Canon / Canone](../narrative/story.md#finale-iv--il-mondo-senza-padroni) · [Chapter 24 / Capitolo 24](../narrative/story.md#capitolo-24--la-verità-sulla-creazione) · [Experimental completion gate](https://github.com/eidolon-game/eidolon-game/blob/06bc2fc0bc2254453813a44559617e2bf8dd9e05/Source/Eidolon/EidolonCampaignSubsystem.cpp#L169-L179)

## Compatibility and acceptance | Compatibilità e accettazione

**IT.** Mantieni ID, chiavi e flag già presenti nei salvataggi sperimentali. Evita di ricalcolare un flag già guadagnato usando una nuova lista di missioni. Adotta i nuovi produttori dei flag solo dopo il collaudo della persistenza e della ripresa a metà missione.

**EN.** Preserve IDs, keys and flags already present in experimental saves. Keep an earned flag valid when the quest list changes. Switch to the new flag producers after persistence and mid-quest recovery checks pass.

| Check / Verifica | Expected behavior / Esito atteso |
| --- | --- |
| Skip chapter 6 side quest / Salta la missione secondaria | Chapter 7 remains reachable; no memory credit. / Il capitolo 7 rimane raggiungibile; nessuna memoria accreditata. |
| Return to Edran and reload / Torna da Edran e ricarica | One diary, one quest completion and one reward. / Un diario, un completamento e una ricompensa. |
| Help the Eidolon and reload / Aiuta gli Eidolon e ricarica | The quest completion and credit persist together. / Completamento e credito restano salvati insieme. |
| Omit each flag in turn / Ometti ciascun flag a turno | Ending IV stays locked; endings I–III remain selectable after the final encounter. / Il finale IV resta bloccato; i finali I–III restano disponibili dopo lo scontro finale. |
| Earn all flags / Ottieni tutti i flag | Ending IV becomes selectable after the final encounter. / Il finale IV diventa selezionabile dopo lo scontro finale. |

Runtime checks pending UE 5.6. / Verifiche runtime in attesa di UE 5.6.
