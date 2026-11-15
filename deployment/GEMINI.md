# Deployment — Google Gemini

## Stato della piattaforma
Google documenta i **Gems** come assistenti personalizzati con nome, istruzioni e, facoltativamente, file di conoscenza. La documentazione annuncia però una transizione: da novembre 2026 i Gems vengono convertiti in **skills** per gli account Google personali; la transizione per gli account di lavoro e scuola è prevista nel 2027. La tempistica e la disponibilità effettiva possono dipendere dal rollout dell'account.

Le skills sono istruzioni riutilizzabili richiamabili nelle chat e, quando disponibili, possono essere applicate automaticamente da Gemini. Non presumere che il menu Gems sia ancora presente in ogni account.

## Configurazione raccomandata
1. Verifica nella Gemini app se il tuo account mostra Skills o Gems.
2. Se è disponibile la creazione di una skill, crea una skill **Ingegnere del Prompt** e trasferisci il Core da `instructions/CORE_INSTRUCTIONS.md` nel campo istruzioni.
3. Se vedi ancora Gems, puoi utilizzare il flusso documentato: Gems > New Gem > nome e istruzioni > eventuali fonti > Save.
4. Aggiungi file di supporto solo se la funzione è disponibile e autorizzata.
5. Testa la skill/Gem con i casi di `tests/TEST_CASES.md`.

## Modalità universale
Se Skills/Gems non sono disponibili, apri una chat standard e incolla `instructions/CORE_INSTRUCTIONS.md` come primo messaggio. È il fallback raccomandato e non dipende dal rollout.

## Materiali utili
Core, RICCE, valutazione, template ed esempi. Aggiungi documenti aggiornati solo dopo aver verificato che la piattaforma li abbia acquisiti.

## Fonti ufficiali
- Transizione Gems → skills: https://support.google.com/gemini/answer/18560919
- Uso e creazione Gems: https://support.google.com/gemini/answer/15146780

Verifica fonti: 15 novembre 2026. La transizione annunciata è in corso per gli account personali; quella work/school è prevista nel 2027.
