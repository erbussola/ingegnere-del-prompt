# Deployment — Google Gemini

## Stato della piattaforma al 15 novembre 2026
Google sta sostituendo i **Gems** con le **skills** in Gemini Apps, con date diverse in base al tipo di account:
- **Account Google personali (18+):** dal 17 novembre 2026 i Gems diventano di sola lettura; dal 17 dicembre 2026 vengono rimossi da Gemini Apps.
- **Google Workspace business, enterprise e non profit:** transizione prevista a marzo 2027.
- **Google Workspace for Education:** transizione prevista a giugno 2027.

Google dichiara che i Gems esistenti e i file supportati saranno convertiti automaticamente in skills. Le skills sono istruzioni riutilizzabili che possono essere richiamate nelle chat; Gemini può anche applicarle automaticamente quando pertinenti. Funzionalità e rollout possono comunque variare in base all'account.

## Configurazione raccomandata
1. Verifica nella Gemini app se il tuo account mostra Skills o Gems.
2. Se è disponibile la creazione di una skill, crea una skill **Ingegnere del Prompt** e trasferisci il Core da `instructions/CORE_INSTRUCTIONS.md` nel campo istruzioni.
3. Se il tuo account mostra ancora Gems e consente di crearli, puoi usare il flusso documentato: Gems > New Gem > nome e istruzioni > eventuali fonti > Save. Per account personali 18+, tieni presente la transizione del 17 novembre e la rimozione del 17 dicembre 2026.
4. Aggiungi file di supporto solo se la funzione è disponibile e autorizzata.
5. Testa la skill/Gem con i casi di `tests/TEST_CASES.md`.

## Modalità universale
Se Skills/Gems non sono disponibili, apri una chat standard e incolla `instructions/CORE_INSTRUCTIONS.md` come primo messaggio. È il fallback raccomandato e non dipende dal rollout.

## Materiali utili
Core, RICCE, valutazione, template ed esempi. Aggiungi documenti aggiornati solo dopo aver verificato che la piattaforma li abbia acquisiti.

## Fonti ufficiali
- Transizione Gems → skills e calendario per tipo di account: https://support.google.com/gemini/answer/18560919
- Uso e creazione Gems: https://support.google.com/gemini/answer/15146780

Verifica fonti: 15 novembre 2026. Le date riportate sono quelle pubblicate da Google e possono essere aggiornate dal provider.
