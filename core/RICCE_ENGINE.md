# RICCE Engine

## Funzione
RICCE è il framework operativo centrale per progettare e revisionare prompt. Le cinque componenti sono una guida di analisi, non una struttura obbligatoria da mostrare in ogni output.

| Elemento | Significato | Domanda guida |
|---|---|---|
| R | Role | Quale ruolo/prospettiva è realmente utile? |
| I | Instructions | Quali attività, priorità e risultati sono richiesti? |
| C | Context | Quali scenario, destinatari e informazioni servono? |
| C | Constraints | Quali limiti, esclusioni, standard e formati vincolano il lavoro? |
| E | Examples | Quali esempi riducono ambiguità o definiscono lo standard atteso? |

## Applicazione
1. Individua gli elementi già presenti nella richiesta.
2. Seleziona solo le componenti utili al risultato.
3. Rileva lacune e contraddizioni.
4. Chiedi chiarimenti solo per le lacune bloccanti.
5. Inserisci segnaposto per i dati che l'utente potrà completare in seguito.
6. Rimuovi sezioni che aggiungerebbero solo lunghezza.
7. Controlla che il prompt finale sia autonomo.

## Regole per componente
- **Role:** descrivere competenze e prospettiva funzionali; evitare titoli altisonanti privi di utilità.
- **Instructions:** usare verbi operativi, ordinare le attività, esplicitare il risultato atteso.
- **Context:** distinguere dati disponibili, fonte e assunzioni; non inventare il contesto.
- **Constraints:** precisare limiti, esclusioni, priorità, sicurezza e formato, evitando vincoli impossibili o conflittuali.
- **Examples:** includere esempi quando spiegano meglio di una regola astratta tono, schema, casi limite o qualità.

## Principio
La qualità è data dalla pertinenza delle componenti, non dalla presenza formale di tutte e cinque. Un prompt semplice può essere completo senza sezioni RICCE visibili.
