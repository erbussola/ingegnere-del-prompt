# Piano di test — Ingegnere del Prompt 2.0

## Obiettivo
Verificare che il Core produca il comportamento previsto nelle tre modalità, applichi RICCE in modo flessibile, mantenga una conversazione utile e consegni prompt completi. I test sono prove comportamentali: la loro natura deve essere dichiarata e non confusa con un test di piattaforma.

## Ambito
- Creazione di prompt da richieste semplici e specialistiche.
- Ottimizzazione minima, mirata e sostanziale.
- Progettazione di assistenti.
- Dialogo progressivo, domande mirate e gestione delle iterazioni.
- Qualità dei cinque suggerimenti e del sistema di valutazione.
- Lingua, flessibilità settoriale, sicurezza, accuratezza e continuità.

## Tipi di verifica e stati
- **Test definito:** input, comportamento atteso, criteri ed errori sono documentati.
- **Test simulato:** il modello corrente genera una risposta all'input e questa viene valutata contro i criteri. Non equivale a un test su una piattaforma esterna.
- **Test eseguito:** il caso è stato effettivamente inviato al bundle Core in una nuova sessione registrata.
- **Test piattaforma:** il caso è stato eseguito su un account/piattaforma esterna, registrando modello, piano, versione, data ed evidenza.
- **NOT RUN:** non eseguito.
- **NOT VERIFIED:** non esiste evidenza sufficiente per attestare il risultato.
- **PARTIALLY VERIFIED:** una parte è verificata, ma resta almeno una condizione essenziale non controllata.

## Procedura
1. Usare il testo esatto di `instructions/CORE_INSTRUCTIONS.md` come configurazione. Registrare separatamente quando si usa `COMPACT.md` o `UNIVERSAL.md`.
2. Avviare una nuova conversazione pulita per ogni caso, oppure registrare chiaramente il contesto iniziale.
3. Inviare l'input senza suggerire al modello come rispondere.
4. Salvare la risposta integrale e annotare piattaforma, modello/versione, piano/account, data e impostazioni rilevanti.
5. Confrontare la risposta con i criteri dello scenario e assegnare **Sì / Parziale / No** a ogni criterio.
6. Classificare i difetti bloccanti, maggiori o minori e registrare evidenze riproducibili.
7. Ripetere i casi critici dopo ogni modifica del Core.

## Criteri trasversali
- Identificazione corretta della modalità.
- Accoglienza e comprensione del risultato pratico.
- Uso delle informazioni fornite senza ripetere domande.
- Domande progressive, una per turno, soltanto se bloccanti.
- RICCE applicato senza rigidità.
- Output completo, autonomo e copiabile.
- Cinque suggerimenti soltanto nelle ottimizzazioni sostanziali; ciascuno concreto e distinto.
- Punteggi coerenti e motivati, confronto con criteri identici.
- Nessun dato, fonte, policy o risultato inventato.
- Nessuna richiesta o divulgazione di segreti.

## Classificazione difetti
- **Bloccante:** risposta contraria all'intento, rischio di sicurezza, invenzione sostanziale o mancata consegna.
- **Maggiore:** modalità errata, requisiti essenziali omessi, dialogo non progressivo, prompt incompleto o contraddittorio.
- **Minore:** formulazione poco chiara, struttura ridondante o dettaglio migliorabile.

## Casi
La suite è composta da 15 casi in `TEST_CASES.md`. La fedeltà al comportamento atteso del GPT di riferimento è valutata separatamente in `FIDELITY_TESTS.md`.

## Cosa non dimostra la suite
Il superamento dei test non garantisce output corretti per qualsiasi richiesta, lingua, modello o versione. Una simulazione nel modello usato per la QA non dimostra compatibilità con ChatGPT, Copilot, Gemini o Claude; ogni piattaforma deve essere testata separatamente.
