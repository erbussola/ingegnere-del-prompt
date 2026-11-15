# Prompt Evaluation Engine

## Scopo
Valutare la qualità strutturale e la praticità di un prompt. Il punteggio è un giudizio qualitativo guidato da criteri espliciti, non una misura scientifica né una previsione certa del comportamento del modello.

## Scala
Usare voti interi da 1 a 10 per ciascun criterio:
- 1–2: insufficiente rispetto allo scopo;
- 3–4: debole, con lacune importanti;
- 5–6: adeguato ma incompleto;
- 7–8: buono e utilizzabile;
- 9–10: molto solido, senza lacune rilevanti per lo scopo.

## Criteri
1. **Chiarezza:** obiettivo e istruzioni sono comprensibili e non ambigui?
2. **Completezza:** contiene le informazioni indispensabili?
3. **Specificità:** definisce ambito, destinatari, risultato e criteri pertinenti?
4. **Coerenza:** le istruzioni sono compatibili e prive di conflitti?
5. **Utilizzabilità:** è autonomo, copiabile e pratico nel contesto previsto?

## Calcolo
Media aritmetica dei cinque voti, arrotondata a una cifra decimale:
`(Chiarezza + Completezza + Specificità + Coerenza + Utilizzabilità) / 5`.

## Presentazione e coerenza
- Motivare sinteticamente ogni criterio con elementi osservabili.
- Se si confrontano versione iniziale e finale, usare gli stessi criteri e la stessa scala.
- Non alzare il punteggio per rendere più gradevole la riscrittura.
- Un voto 9–10 richiede l'assenza di lacune rilevanti rispetto allo scopo, non la sola buona scrittura.
- Se il prompt è molto breve, valutarlo rispetto al compito e non penalizzarlo per sezioni RICCE non necessarie.
- Se la modifica è minima, non forzare un miglioramento numerico.

## Limiti
Un prompt con punteggio elevato può comunque produrre risposte errate. Valutare l'output effettivo richiede test sul modello e sul contesto di destinazione.

## Motivazioni verificabili e confronto

Per ciascuno dei cinque criteri fornire una motivazione breve, specifica e basata su elementi osservabili del prompt rispetto allo scopo. Evitare formule generiche.

Nel confronto iniziale/finale applicare gli stessi criteri e la stessa scala, riportare voti e medie, spiegare le differenze effettive, consentire che il voto aumenti, resti invariato o diminuisca e non attribuire un bonus automatico alla riscrittura. Ogni voto 9–10 richiede una motivazione specifica sull'assenza di lacune rilevanti. Mantenere le motivazioni proporzionate senza costruire giustificazioni artificiali per voti invariati.
