# Checklist di rilascio

## Core e istruzioni
- [ ] Tutti i moduli Core sono coerenti tra loro.
- [ ] Il bundle completo include le regole operative essenziali.
- [ ] `UNIVERSAL.md` è identico a `CORE_INSTRUCTIONS.md`.
- [ ] Il bundle compatto conserva le tre modalità, RICCE, qualità, privacy e continuità essenziali.
- [ ] Nessuna regola fondamentale è duplicata nei deployment con significato diverso.

## Documentazione
- [ ] README e guide hanno link relativi validi.
- [ ] Tutti i deployment citano fonti ufficiali e data di verifica.
- [ ] Requisiti e limiti dei piani sono descritti correttamente.
- [ ] La licenza locale corrisponde al Legal Code ufficiale; link canonico presente.
- [ ] Materiali di terzi, privacy e sicurezza sono delimitati.
- [ ] Non sono presenti credenziali, segreti o dati personali.

## Test comportamentali
- [ ] Sono eseguiti i casi pertinenti di `tests/TEST_CASES.md`.
- [ ] Sono valutate le sette dimensioni di `tests/FIDELITY_TESTS.md`.
- [ ] Risultati, prompt, piattaforma, modello, piano e data sono registrati.
- [ ] I difetti bloccanti e maggiori sono risolti o documentati.

## Test multipiattaforma
- [ ] I test sono eseguiti su account reali per ogni piattaforma dichiarata compatibile.
- [ ] I test su CORE, COMPACT e UNIVERSAL sono distinti e registrati.
- [ ] La matrice distingue capacità documentate, simulazioni e prove esterne.
- [ ] Non viene dichiarata compatibilità empirica senza evidenze.

## Repository
- [ ] Changelog aggiornato.
- [ ] Branch e PR corretti.
- [ ] Nessuna modifica accidentale a `main`.
- [ ] Review e merge lasciati al maintainer secondo le autorizzazioni.
