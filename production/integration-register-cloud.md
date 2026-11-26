# Registro di integrazione Cloud

Rilevazione del 26 novembre 2026. Il [registro del ciclo 02](integration-register-cycle02.md) conserva le decisioni sui contratti; valgono i blocchi di revisione già registrati.

Le pagine PR di GitHub riportano **53 PR aperte**, 21 Game, 18 Docs e 14 Tools, e zero chiuse. I riferimenti Git nativi riportano gli stessi 53 head e 53 merge di prova. L’API GitHub è bloccata dal proxy. Le pagine web e i riferimenti Git sono stati consultati in sola lettura.

Per ogni PR, la merge base e il diff sono calcolati rispetto al tip ufficiale di `integration/studio`. Git ricostruisce un merge virtuale isolato per ciascuna candidata. Un merge pulito certifica la compatibilità testuale del singolo confronto. Le revisioni dei diff, le interazioni tra PR, la build UE e le approvazioni restano requisiti per l’integrazione delle 47 PR con modifiche nuove.

In Game, le PR #4, #5 e #6 appartengono già alla cronologia della base sperimentale. Anche Game #21, Docs #15 e Tools #12 sono già presenti nel rispettivo branch di integrazione. Evitare una seconda applicazione di questi sei contributi.

## eidolon-game

Tip ufficiale `82dc0451c7f00ea090249fa4dfb22e7941da0ac7`. Git espone 23 branch, inclusi `main`, `develop` e `integration/studio`. [PR aperte](https://github.com/eidolon-game/eidolon-game/pulls) · [Branch](https://github.com/eidolon-game/eidolon-game/branches)

| PR | Branch e head | Commit nuovi | File | Esito rispetto a studio |
| --- | --- | ---: | ---: | --- |
| [#4](https://github.com/eidolon-game/eidolon-game/pull/4) | `feature/third-person-prototype` [`8c1d809ff293`](https://github.com/eidolon-game/eidolon-game/commit/8c1d809ff29383601aa899469e9de7e454f426c7) | 0 | 0 | Già in cronologia |
| [#5](https://github.com/eidolon-game/eidolon-game/pull/5) | `feature/arena-demo` [`4269d0d1c885`](https://github.com/eidolon-game/eidolon-game/commit/4269d0d1c88560062c59f490a5555b0437a06e19) | 0 | 0 | Già in cronologia |
| [#6](https://github.com/eidolon-game/eidolon-game/pull/6) | `feature/campaign-foundation` [`fc9cf93c896f`](https://github.com/eidolon-game/eidolon-game/commit/fc9cf93c896f3338356fc584b72f773a3d281181) | 0 | 0 | Già in cronologia |
| [#7](https://github.com/eidolon-game/eidolon-game/pull/7) | `feature/core-architecture` [`ffeab7af44d9`](https://github.com/eidolon-game/eidolon-game/commit/ffeab7af44d90287ead740c1f6ad7d8f8dc28d4d) | 42 | 42 | Merge virtuale pulito. Sospesa per autorità e attivazione del contratto Core |
| [#8](https://github.com/eidolon-game/eidolon-game/pull/8) | `feature/combat-system` [`c759d155964f`](https://github.com/eidolon-game/eidolon-game/commit/c759d155964f6f778c68c39f11efd3308bc367ae) | 23 | 12 | Merge virtuale pulito. Sospesa per contratto eventi e portata del combattimento |
| [#9](https://github.com/eidolon-game/eidolon-game/pull/9) | `feature/npc-ai-companions` [`6c7db9f11d73`](https://github.com/eidolon-game/eidolon-game/commit/6c7db9f11d732fdc701227ec0bbb6687c536d428) | 18 | 13 | Merge virtuale pulito. Revisione pendente |
| [#10](https://github.com/eidolon-game/eidolon-game/pull/10) | `feature/rpg-economy` [`1967b9521e15`](https://github.com/eidolon-game/eidolon-game/commit/1967b9521e15fc51dee7e8919684a78024a457d5) | 8 | 6 | Merge virtuale pulito. Revisione pendente |
| [#11](https://github.com/eidolon-game/eidolon-game/pull/11) | `feature/ui-ux` [`4c2321c931b6`](https://github.com/eidolon-game/eidolon-game/commit/4c2321c931b650c96c67f1a8f5c79d39ea76df57) | 8 | 8 | Merge virtuale pulito. Revisione pendente |
| [#12](https://github.com/eidolon-game/eidolon-game/pull/12) | `feature/discrepancy-save-system` [`04edc1858a3f`](https://github.com/eidolon-game/eidolon-game/commit/04edc1858a3f02d6f283646e1b85d4874c807724) | 23 | 17 | Merge virtuale pulito. Sospesa per atomicità del cursore e recupero salvataggio |
| [#13](https://github.com/eidolon-game/eidolon-game/pull/13) | `feature/character-art` [`1f18a0899199`](https://github.com/eidolon-game/eidolon-game/commit/1f18a0899199e45f8471ea06bddd41aeebbd2550) | 2 | 2 | Merge virtuale pulito. Revisione pendente |
| [#14](https://github.com/eidolon-game/eidolon-game/pull/14) | `feature/creature-art` [`cd4e399597eb`](https://github.com/eidolon-game/eidolon-game/commit/cd4e399597ebb576f09625d5c702e732197f970c) | 3 | 3 | Merge virtuale pulito. Revisione pendente |
| [#15](https://github.com/eidolon-game/eidolon-game/pull/15) | `feature/environment-art` [`cb7c289f09ca`](https://github.com/eidolon-game/eidolon-game/commit/cb7c289f09ca0a9a4eb6206e4671412a2c2d3efc) | 5 | 4 | Merge virtuale pulito. Revisione pendente |
| [#16](https://github.com/eidolon-game/eidolon-game/pull/16) | `feature/dungeons-level-design` [`82c869f35e38`](https://github.com/eidolon-game/eidolon-game/commit/82c869f35e384c2b1462274e45612f928ea9e57e) | 11 | 9 | Merge virtuale pulito. Revisione pendente |
| [#17](https://github.com/eidolon-game/eidolon-game/pull/17) | `feature/animation-cinematics` [`e008eeacc8b7`](https://github.com/eidolon-game/eidolon-game/commit/e008eeacc8b7ad051cbb8b4e7a890eff87340def) | 5 | 5 | Merge virtuale pulito. Revisione pendente |
| [#18](https://github.com/eidolon-game/eidolon-game/pull/18) | `feature/open-world` [`17621e8b0bf6`](https://github.com/eidolon-game/eidolon-game/commit/17621e8b0bf69e8b4105167eee7a7345dd4854b2) | 4 | 4 | Merge virtuale pulito. Revisione pendente |
| [#19](https://github.com/eidolon-game/eidolon-game/pull/19) | `feature/audio-design` [`7bc72d38d580`](https://github.com/eidolon-game/eidolon-game/commit/7bc72d38d58025ef3ed0cd853d1f3889da6c7aaa) | 4 | 4 | Merge virtuale pulito. Revisione pendente |
| [#20](https://github.com/eidolon-game/eidolon-game/pull/20) | `feature/qa-automation` [`b76eaf00d34c`](https://github.com/eidolon-game/eidolon-game/commit/b76eaf00d34ceb8ad52500b764b619eb532f74d9) | 3 | 2 | Merge virtuale pulito. Revisione pendente |
| [#21](https://github.com/eidolon-game/eidolon-game/pull/21) | `Tip studio` [`82dc0451c7f0`](https://github.com/eidolon-game/eidolon-game/commit/82dc0451c7f00ea090249fa4dfb22e7941da0ac7) | 0 | 0 | Già in cronologia |
| [#22](https://github.com/eidolon-game/eidolon-game/pull/22) | `feature/weapons-equipment-art` [`453294297bfd`](https://github.com/eidolon-game/eidolon-game/commit/453294297bfd646a831ae6365e98e3a8ca62c1d4) | 7 | 6 | Merge virtuale pulito. Revisione pendente |
| [#23](https://github.com/eidolon-game/eidolon-game/pull/23) | `feature/quest-dialogue` [`8fbdaeab26a5`](https://github.com/eidolon-game/eidolon-game/commit/8fbdaeab26a53cefab3a84ca8db98ca7067ea782) | 5 | 4 | Merge virtuale pulito. Sospesa per convalida del bersaglio e persistenza delle quest |
| [#24](https://github.com/eidolon-game/eidolon-game/pull/24) | `feature/build-engineering` [`cab784eed385`](https://github.com/eidolon-game/eidolon-game/commit/cab784eed3856c764a85161ef30e317471024c9b) | 10 | 7 | Merge virtuale pulito. Candidata Build, revisione workflow pendente |

### Issue aperte (7)

- Pin UE5 version and verify initial build [#1](https://github.com/eidolon-game/eidolon-game/issues/1)
- Implement third-person character and input prototype [#2](https://github.com/eidolon-game/eidolon-game/issues/2)
- Configure repository protection and security [#3](https://github.com/eidolon-game/eidolon-game/issues/3)
- [QA-020-01][Critical] Failed spawn permits dungeon progression [#25](https://github.com/eidolon-game/eidolon-game/issues/25)
- [QA-020-02][High] Boss reach boundary exceeds player attack reach [#26](https://github.com/eidolon-game/eidolon-game/issues/26)
- [QA-020-03][Critical] Checkpoint load failure resets in-memory campaign [#27](https://github.com/eidolon-game/eidolon-game/issues/27)
- [QA-020-04][High] Interaction advances dialogue without NPC proximity [#28](https://github.com/eidolon-game/eidolon-game/issues/28)

### GitHub Actions

Workflow presenti su studio: `.github/workflows/validate.yml`.
Ultimo run visibile: completed successfully: Run 368 of EIDOLON CI. feat(environment): initial art direction and modular kit foundation. [Run](https://github.com/eidolon-game/eidolon-game/actions/runs/45864583498)
Elenco pubblico consultato: 25 run visibili nella prima pagina. [Actions](https://github.com/eidolon-game/eidolon-game/actions)
Il workflow studio verifica il sorgente. Sul runner Windows ospitato, il probe termina senza packaging quando Unreal Engine è assente. Un run verde da solo non dimostra la produzione di un binario.

## eidolon-docs

Tip ufficiale `de96384c68a9758321e43a21de5183cd3a79432e`. Git espone 20 branch, inclusi `main`, `develop` e `integration/studio`. [PR aperte](https://github.com/eidolon-game/eidolon-docs/pulls) · [Branch](https://github.com/eidolon-game/eidolon-docs/branches)

| PR | Branch e head | Commit nuovi | File | Esito rispetto a studio |
| --- | --- | ---: | ---: | --- |
| [#2](https://github.com/eidolon-game/eidolon-docs/pull/2) | `feature/core-architecture` [`bb9fdcf16031`](https://github.com/eidolon-game/eidolon-docs/commit/bb9fdcf1603189d134b4e40f9878b776997964e7) | 3 | 3 | Merge virtuale pulito. Revisione pendente |
| [#3](https://github.com/eidolon-game/eidolon-docs/pull/3) | `feature/rpg-economy` [`148c578d30d2`](https://github.com/eidolon-game/eidolon-docs/commit/148c578d30d2eb3fa7ba1f861b3c494c087ae64c) | 3 | 2 | Merge virtuale pulito. Revisione pendente |
| [#4](https://github.com/eidolon-game/eidolon-docs/pull/4) | `feature/ui-ux` [`733621817966`](https://github.com/eidolon-game/eidolon-docs/commit/7336218179662676ec6c78fc7e405e306cbbfaac) | 2 | 2 | Merge virtuale pulito. Revisione pendente |
| [#5](https://github.com/eidolon-game/eidolon-docs/pull/5) | `feature/world-bible` [`e3360990547d`](https://github.com/eidolon-game/eidolon-docs/commit/e3360990547db4aa43ee88010df7dbb08794bb9e) | 20 | 18 | Merge virtuale pulito. Revisione pendente |
| [#6](https://github.com/eidolon-game/eidolon-docs/pull/6) | `feature/character-art` [`b4ac0c84b212`](https://github.com/eidolon-game/eidolon-docs/commit/b4ac0c84b21258187e9362615108b997e9fa23ce) | 6 | 6 | Merge virtuale pulito. Revisione pendente |
| [#7](https://github.com/eidolon-game/eidolon-docs/pull/7) | `feature/creature-art` [`478ccf94def4`](https://github.com/eidolon-game/eidolon-docs/commit/478ccf94def449a20f326badad3a83faa1392347) | 4 | 3 | Merge virtuale pulito. Revisione pendente |
| [#8](https://github.com/eidolon-game/eidolon-docs/pull/8) | `feature/environment-art` [`ad840f02aa4d`](https://github.com/eidolon-game/eidolon-docs/commit/ad840f02aa4d1cec9b09e54d11cb2d716b99ec1c) | 7 | 6 | Merge virtuale pulito. Revisione pendente |
| [#9](https://github.com/eidolon-game/eidolon-docs/pull/9) | `feature/asset-pipeline` [`6bf6567794f5`](https://github.com/eidolon-game/eidolon-docs/commit/6bf6567794f5b260a779d7a098db517502f7b833) | 2 | 2 | Merge virtuale pulito. Revisione pendente |
| [#10](https://github.com/eidolon-game/eidolon-docs/pull/10) | `feature/dungeons-level-design` [`e8464c99131f`](https://github.com/eidolon-game/eidolon-docs/commit/e8464c99131f78b2284c9baf623bba3478e7b5b5) | 4 | 3 | Merge virtuale pulito. Revisione pendente |
| [#11](https://github.com/eidolon-game/eidolon-docs/pull/11) | `feature/animation-cinematics` [`2ab9a19f3fe8`](https://github.com/eidolon-game/eidolon-docs/commit/2ab9a19f3fe86b9ce3223a1b3d6a4702b6851aa1) | 5 | 5 | Merge virtuale pulito. Revisione pendente |
| [#12](https://github.com/eidolon-game/eidolon-docs/pull/12) | `feature/open-world` [`4b28f49ede8a`](https://github.com/eidolon-game/eidolon-docs/commit/4b28f49ede8a927c386fe9c73e415db2fe5e904f) | 2 | 2 | Merge virtuale pulito. Revisione pendente |
| [#13](https://github.com/eidolon-game/eidolon-docs/pull/13) | `feature/audio-design` [`f1003cc26eca`](https://github.com/eidolon-game/eidolon-docs/commit/f1003cc26ecad50623b1ff2807bf67514f9f2dcf) | 6 | 6 | Merge virtuale pulito. Revisione pendente |
| [#14](https://github.com/eidolon-game/eidolon-docs/pull/14) | `feature/qa-automation` [`98e0aab7a370`](https://github.com/eidolon-game/eidolon-docs/commit/98e0aab7a370578903f559a5cc767bd26fbc14c1) | 3 | 2 | Merge virtuale pulito. Revisione pendente |
| [#15](https://github.com/eidolon-game/eidolon-docs/pull/15) | `Tip studio` [`de96384c68a9`](https://github.com/eidolon-game/eidolon-docs/commit/de96384c68a9758321e43a21de5183cd3a79432e) | 0 | 0 | Già in cronologia |
| [#16](https://github.com/eidolon-game/eidolon-docs/pull/16) | `feature/weapons-equipment-art` [`2f06b82234d5`](https://github.com/eidolon-game/eidolon-docs/commit/2f06b82234d58900979b60e99b19463b8ea29b2a) | 2 | 2 | Merge virtuale pulito. Revisione pendente |
| [#17](https://github.com/eidolon-game/eidolon-docs/pull/17) | `feature/quest-dialogue` [`7b98d914f8f3`](https://github.com/eidolon-game/eidolon-docs/commit/7b98d914f8f3dd6c6e389a1bdf59e25fac0733ea) | 2 | 1 | Merge virtuale pulito. Revisione pendente |
| [#18](https://github.com/eidolon-game/eidolon-docs/pull/18) | `feature/build-engineering` [`f0a4e22d3eb6`](https://github.com/eidolon-game/eidolon-docs/commit/f0a4e22d3eb679c4abc180dc289b4176e48f4465) | 4 | 1 | Merge virtuale pulito. Revisione pendente |
| [#19](https://github.com/eidolon-game/eidolon-docs/pull/19) | `feature/main-screenplay` [`69bef36e5bb8`](https://github.com/eidolon-game/eidolon-docs/commit/69bef36e5bb87971191aebdeea9aecb17656cfc2) | 40 | 32 | Merge virtuale pulito. Revisione pendente |

### Issue aperte (1)

- Expand GDD and first descent vertical slice [#1](https://github.com/eidolon-game/eidolon-docs/issues/1)

### GitHub Actions

Il tip studio non contiene workflow.
La pagina pubblica non mostra run. [Actions](https://github.com/eidolon-game/eidolon-docs/actions)

## eidolon-tools

Tip ufficiale `b0b03fccc9dc76cc0334e08ba75d9e24e3578315`. Git espone 16 branch, inclusi `main`, `develop` e `integration/studio`. [PR aperte](https://github.com/eidolon-game/eidolon-tools/pulls) · [Branch](https://github.com/eidolon-game/eidolon-tools/branches)

| PR | Branch e head | Commit nuovi | File | Esito rispetto a studio |
| --- | --- | ---: | ---: | --- |
| [#2](https://github.com/eidolon-game/eidolon-tools/pull/2) | `feature/rpg-economy` [`3514388b2961`](https://github.com/eidolon-game/eidolon-tools/commit/3514388b2961c80fca7936ed1d01757fb51dee07) | 5 | 4 | Merge virtuale pulito. Revisione pendente |
| [#3](https://github.com/eidolon-game/eidolon-tools/pull/3) | `feature/character-art` [`5ddf7fd0de44`](https://github.com/eidolon-game/eidolon-tools/commit/5ddf7fd0de44ea2ea5bb477f502f156844b57ab4) | 4 | 4 | Merge virtuale pulito. Revisione pendente |
| [#4](https://github.com/eidolon-game/eidolon-tools/pull/4) | `feature/creature-art` [`fc0f7db547d8`](https://github.com/eidolon-game/eidolon-tools/commit/fc0f7db547d8e58646ba2d382db8379439d05cfa) | 5 | 3 | Merge virtuale pulito. Revisione pendente |
| [#5](https://github.com/eidolon-game/eidolon-tools/pull/5) | `feature/environment-art` [`31edb07e086f`](https://github.com/eidolon-game/eidolon-tools/commit/31edb07e086fd7ca18e1d6ac344083bae986bdbb) | 11 | 10 | Merge virtuale pulito. Revisione pendente |
| [#6](https://github.com/eidolon-game/eidolon-tools/pull/6) | `feature/asset-pipeline` [`8daebceb7667`](https://github.com/eidolon-game/eidolon-tools/commit/8daebceb7667808737930eb925878445d80d4371) | 10 | 7 | Merge virtuale pulito. Revisione pendente |
| [#7](https://github.com/eidolon-game/eidolon-tools/pull/7) | `feature/dungeons-level-design` [`abbf2ec75125`](https://github.com/eidolon-game/eidolon-tools/commit/abbf2ec75125eb74250d5079a15d64dd3177d1f8) | 7 | 6 | Merge virtuale pulito. Revisione pendente |
| [#8](https://github.com/eidolon-game/eidolon-tools/pull/8) | `feature/animation-cinematics` [`a5dd119934fc`](https://github.com/eidolon-game/eidolon-tools/commit/a5dd119934fc2fdff32ccfe864671915ecec0c43) | 4 | 4 | Merge virtuale pulito. Revisione pendente |
| [#9](https://github.com/eidolon-game/eidolon-tools/pull/9) | `feature/open-world` [`05a608f7fdbf`](https://github.com/eidolon-game/eidolon-tools/commit/05a608f7fdbf5dc726f32cd4ce9ed0071b2d107a) | 3 | 3 | Merge virtuale pulito. Revisione pendente |
| [#10](https://github.com/eidolon-game/eidolon-tools/pull/10) | `feature/audio-design` [`4418ef821521`](https://github.com/eidolon-game/eidolon-tools/commit/4418ef821521f47d2d36f26954f0e4313abd8cba) | 8 | 8 | Merge virtuale pulito. Revisione pendente |
| [#11](https://github.com/eidolon-game/eidolon-tools/pull/11) | `feature/qa-automation` [`f2f98266889e`](https://github.com/eidolon-game/eidolon-tools/commit/f2f98266889eba22c1a667e0ffd671ba2f7da1e1) | 8 | 6 | Merge virtuale pulito. Revisione pendente |
| [#12](https://github.com/eidolon-game/eidolon-tools/pull/12) | `Tip studio` [`b0b03fccc9dc`](https://github.com/eidolon-game/eidolon-tools/commit/b0b03fccc9dc76cc0334e08ba75d9e24e3578315) | 0 | 0 | Già in cronologia |
| [#14](https://github.com/eidolon-game/eidolon-tools/pull/14) | `feature/weapons-equipment-art` [`1338649c5e0b`](https://github.com/eidolon-game/eidolon-tools/commit/1338649c5e0b8e410296849b20954766ee3e0595) | 2 | 2 | Merge virtuale pulito. Revisione pendente |
| [#15](https://github.com/eidolon-game/eidolon-tools/pull/15) | `feature/quest-dialogue` [`bd285e74f10a`](https://github.com/eidolon-game/eidolon-tools/commit/bd285e74f10a664f2e03f471b7f09ff3e44fa92b) | 3 | 2 | Merge virtuale pulito. Revisione pendente |
| [#16](https://github.com/eidolon-game/eidolon-tools/pull/16) | `feature/build-engineering` [`42858e4ecfd8`](https://github.com/eidolon-game/eidolon-tools/commit/42858e4ecfd846801a6d7232eccd5b1bb53eae50) | 9 | 5 | Merge virtuale pulito. Revisione pendente |

### Issue aperte (2)

- Test project layout validator [#1](https://github.com/eidolon-game/eidolon-tools/issues/1)
- Build 19: coordinate Blender CI download failure and registry tests [#13](https://github.com/eidolon-game/eidolon-tools/issues/13)

### GitHub Actions

Il tip studio non contiene workflow.
Ultimo run visibile: failed: Run 6 of Department 18 calibration reproduction. ci: department 19 build engineering foundation. [Run](https://github.com/eidolon-game/eidolon-tools/actions/runs/45864189224)
Elenco pubblico consultato: 24 run visibili nella prima pagina. [Actions](https://github.com/eidolon-game/eidolon-tools/actions)
La cronologia pubblica include il workflow Build tools validation dal ramo di build engineering.
