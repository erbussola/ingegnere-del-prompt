# Contribuire

Ingegnere del Prompt è un progetto documentale aperto alla community. Sono benvenuti miglioramenti del Core, nuove guide, template, esempi, traduzioni e test.

## Prima di proporre una modifica
- Cerca nei file e nelle Issue per evitare duplicati.
- Per modifiche sostanziali descrivi problema, obiettivo e impatto.
- Per guide di piattaforma usa documentazione ufficiale aggiornata e indica la data di verifica.
- Per nuovi comportamenti del Core aggiungi o aggiorna i test pertinenti.

## Regole architetturali
- I principi comportamentali devono risiedere in `core/`.
- `instructions/CORE_INSTRUCTIONS.md` e `instructions/COMPACT.md` sono bundle distribuibili: devono riflettere i moduli Core.
- I file `deployment/` descrivono solo configurazione, limiti e adattamenti piattaforma; non devono creare regole comportamentali divergenti.
- Framework, template ed esempi supportano il Core e non lo sostituiscono.
- Evita duplicazioni non necessarie e mantieni i collegamenti relativi aggiornati.

## Pull Request
1. Usa un branch dedicato e descrivi la motivazione.
2. Mantieni le modifiche circoscritte, ma aggiorna tutti i documenti dipendenti.
3. Aggiungi casi di test quando cambia il comportamento.
4. Verifica Markdown, link, lingua, licenze e assenza di dati riservati.
5. Compila il modello PR.

## Licenze e attribuzione
Contribuisci solo con contenuti originali o materiali che hai il diritto di condividere. I contributi accettati destinati ai contenuti del progetto devono essere compatibili con CC BY-SA 4.0, salvo accordo scritto diverso prima dell'accettazione. Conserva l'attribuzione e segnala le fonti di terzi. L'eventuale codice software futuro richiede una valutazione di licenza separata.

## Sicurezza
Non inserire password, token, chiavi API, dati personali o informazioni riservate in issue, esempi o file pubblici. Per segnalazioni sensibili non pubblicare dettagli sfruttabili.
