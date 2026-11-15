# Piano di test — Ingegnere del Prompt 2.0

## Obiettivo
Verificare che il Core produca il comportamento previsto nelle tre modalità, applichi RICCE in modo flessibile, mantenga una conversazione utile e consegni prompt completi. I test sono prove comportamentali manuali: non misurano scientificamente un modello.

## Ambito
- Creazione di prompt da richieste semplici e specialistiche.
- Ottimizzazione proporzionata e sostanziale.
- Progettazione di assistenti.
- Chiarimento di ambiguità e gestione delle iterazioni.
- Sicurezza, accuratezza, continuità e portabilità.

## Procedura
1. Usare il testo di `instructions/CORE_INSTRUCTIONS.md` come configurazione.
2. Avviare una nuova conversazione pulita per ogni test, oppure registrare chiaramente lo stato iniziale.
3. Inviare l'input senza aggiungere suggerimenti che anticipino il risultato atteso.
4. Salvare la risposta integrale e annotare piattaforma, modello, piano/account, data e impostazioni rilevanti.
5. Confrontare la risposta con i criteri dello scenario.
6. Assegnare a ogni criterio esito **Sì / Parziale / No** e descrivere le evidenze.
7. Ripetere i casi critici dopo ogni modifica del Core.

## Criteri trasversali
- Identificazione corretta della modalità.
- Aderenza all'intento e uso delle informazioni fornite.
- Chiarimenti non superflui.
- RICCE applicato senza rigidità.
- Output completo e copiabile.
- Cinque suggerimenti soltanto nelle ottimizzazioni sostanziali.
- Punteggi coerenti e motivati quando la valutazione è pertinente.
- Nessun dato, fonte o risultato inventato.
- Nessuna richiesta di segreti.

## Classificazione difetti
- **Bloccante:** risposta contraria all'intento, rischio di sicurezza, invenzione sostanziale o mancata consegna.
- **Maggiore:** modalità errata, requisiti essenziali omessi, prompt incompleto o contraddittorio.
- **Minore:** formulazione poco chiara, struttura ridondante o dettaglio migliorabile.

## Cosa non dimostra la suite
Il superamento dei test non garantisce output corretti per qualsiasi richiesta, lingua, modello o versione. Ogni piattaforma deve essere valutata separatamente e con la propria versione del modello.
