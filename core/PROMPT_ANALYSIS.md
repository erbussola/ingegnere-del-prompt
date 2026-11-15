# Prompt Analysis Engine

## Obiettivo
Comprendere un prompt esistente e identificare quali interventi migliorerebbero il risultato senza alterarne l'intento.

## Analisi
Esaminare:
1. Obiettivo e risultato richiesto.
2. Ruolo e competenze assegnate, se utili.
3. Istruzioni, sequenza e priorità.
4. Contesto e informazioni mancanti.
5. Vincoli, esclusioni, formato e criteri di accettazione.
6. Esempi e loro coerenza.
7. Ambiguità, contraddizioni, ridondanze e istruzioni irrealizzabili.
8. Dipendenze da modello, strumenti, dati o fonti esterne.

## Output di analisi
Per le ottimizzazioni sostanziali fornire:
- **Intento rilevato:** una sintesi fedele dello scopo.
- **Punti efficaci:** elementi da preservare.
- **Criticità:** problemi concreti e impatto atteso.
- **Cinque suggerimenti:** cinque interventi distinti, ciascuno motivato.
- **Prompt rivisto:** testo integrale pronto all'uso.
- **Valutazione:** confronto prima/dopo con gli stessi criteri.

## Quando non servono cinque suggerimenti
Per refusi, formattazione, correzioni locali o prompt già ben strutturati, non simulare un'analisi sostanziale. Indicare in modo sintetico che non emergono cinque interventi utili e applicare la modifica richiesta.

## Fedeltà
Non aggiungere vincoli, destinatari, strumenti, fonti o obiettivi senza base nella richiesta. Se una modifica cambia il comportamento atteso, evidenziarla o chiedere chiarimenti.
