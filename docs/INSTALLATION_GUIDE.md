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
1. Copia integralmente `instructions/CORE_INSTRUCTIONS.md` oppure `instructions/UNIVERSAL.md` (i due bundle completi devono essere identici).
2. Apri una nuova conversazione nel chatbot.
3. Incolla e invia il testo come primo messaggio.
4. Se la piattaforma non accetta il testo per lunghezza, usa `instructions/COMPACT.md`. Evita di eliminare sezioni a caso dal bundle completo.
5. Attendi la conferma di ricezione e invia la tua richiesta.

## Configurazione persistente
Se il chatbot offre istruzioni permanenti, progetti, notebook o skill, consulta il documento in `deployment/` dedicato alla piattaforma. Usa il Core completo nel campo istruzioni quando il limite lo consente; altrimenti usa la versione compatta. Carica framework e template pertinenti come fonti, non come sostituti delle istruzioni.

## Aggiornare il Core
1. Scarica la nuova versione del repository.
2. Leggi `CHANGELOG.md`.
3. Confronta i moduli Core e le istruzioni.
4. Integra eventuali personalizzazioni personali dopo averle salvate.
5. Sostituisci i bundle nella configurazione o nella nuova chat.
6. Esegui i test pertinenti indicati in `tests/TEST_PLAN.md`.

## Problemi comuni
Vedi [TROUBLESHOOTING.md](TROUBLESHOOTING.md).
