# Guida all'installazione e configurazione

## Requisiti
Un chatbot che accetti testo e il contenuto del bundle. Non sono necessari codice, Git, API, server o database.

## Scaricare il progetto
1. Apri il repository GitHub.
2. Seleziona **Code > Download ZIP**.
3. Estrai l'archivio.
4. Apri la directory `instructions/`.

In alternativa, apri il singolo file sul repository e copia il contenuto.

## Installazione universale
1. Copia `instructions/CORE_INSTRUCTIONS.md`.
2. Apri una nuova conversazione nel chatbot.
3. Incolla e invia il testo come primo messaggio.
4. Se la piattaforma rifiuta il testo per lunghezza, usa `instructions/COMPACT.md` oppure invia il Core in parti numerate, chiedendo di attendere «FINE».
5. Dopo la conferma, invia la tua richiesta.

## Configurazione persistente
Se il chatbot offre istruzioni permanenti, progetti, notebook o skill, consulta il documento in `deployment/` dedicato alla piattaforma. Usa il Core completo nel campo istruzioni se il limite lo consente; altrimenti usa la versione compatta. Carica i framework e i template pertinenti come fonti, non come sostituti delle istruzioni.

## Aggiornare il Core
1. Scarica la nuova versione del repository.
2. Leggi `CHANGELOG.md`.
3. Confronta i moduli Core e le istruzioni.
4. Integra eventuali personalizzazioni personali dopo averle salvate.
5. Sostituisci il bundle nella configurazione o nella nuova chat.
6. Esegui i test essenziali indicati in `tests/TEST_PLAN.md`.

## Problemi comuni
Vedi [TROUBLESHOOTING.md](TROUBLESHOOTING.md).
