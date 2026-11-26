# Risk register
| ID | Risk | Severity | Mitigation / owner |
|---|---|---|---|
|R01|No UE on hosted runner|Critical|19: licensed isolated runner; no false packaging success|
|R02|Uncompiled C++/UHT defects|High|01/20: compile gate and independent review|
|R03|Concurrent edits to shared legacy files|High|00: ownership, pinned heads, isolated PRs|
|R04|Narrative drift or unreachable ending|High|07/08/09/20: canonical graph and exhaustive tests|
|R05|Graybox mistaken for final art|High|10–18: rendered evidence and import checks|
|R06|Public repo exposes restricted assets/SDK|High|18/19: provenance, private licensed storage when authorized|
|R07|Persistent runner executes untrusted PR|Critical|19: private isolated runner only; no secrets on public PR|
|R08|AAA scope exceeds resources|High|00: milestone evidence and vertical slice before scale|
|R09|Console access unavailable|High|19: authorized platform tools/certification only|
|R10|Save corruption or duplicate rewards|High|06/08/20: transactional state, recovery tests|

Cycle 02: Blender download risk mitigated for calibration SHA only; production batch and import remain unverified. R01 remains critical. New critical risks: failed spawn bypass (#25), checkpoint loss (#27); high: reach mismatch (#26), dialogue bypass (#28). Owners 01/02/06/08/17; independent QA 20.
