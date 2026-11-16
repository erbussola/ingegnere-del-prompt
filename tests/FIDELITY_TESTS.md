# Test di fedeltà comportamentale — riferimento GPT originale

## Scopo e limiti
Questa suite verifica la corrispondenza di Ingegnere del Prompt con il comportamento-obiettivo attribuito al GPT originale **The Prompt Master** e dichiarato nel mandato del progetto.

Non è disponibile in questo repository un'esportazione verificata delle istruzioni private, dei dati di configurazione o delle risposte di riferimento del GPT originale. Di conseguenza, questa suite **non certifica una replica esatta del suo funzionamento interno**: valuta la fedeltà ai comportamenti osservabili e ai requisiti descritti dal proprietario del progetto.

## Metodo
Eseguire i casi in una conversazione pulita con il bundle Core completo e, separatamente, con il bundle compatto. Inviare input neutrali e registrare la risposta integrale. Non suggerire al modello la struttura della risposta.

Per ogni dimensione assegnare un voto:
- **0 — Assente/contrario:** comportamento non presente o in contrasto con l'obiettivo.
- **1 — Molto debole:** difetti frequenti o risultato poco utilizzabile.
- **2 — Parziale:** comportamento riconoscibile ma incompleto/incoerente.
- **3 — Adeguato:** requisito soddisfatto nel caso, con limiti minori.
- **4 — Buono:** comportamento solido, naturale e coerente.
- **5 — Ottimo:** comportamento pienamente centrato, proporzionato e ripetibile.

La somma massima è **35/35**. Esito complessivo:
- **PASS:** almeno 28/35 e nessuna dimensione sotto 3.
- **PARTIALLY VERIFIED:** 22–27/35 oppure una dimensione sotto 3 senza difetti critici.
- **FAIL:** meno di 22/35 oppure comportamento critico contrario a sicurezza, intento o continuità.

Il punteggio descrive il campione testato e non è una misura scientifica della qualità generale.

## Dimensioni di valutazione

### F1 — Accoglienza amichevole
Verificare che l'assistente accolga la richiesta con tono naturale, collaborativo e professionale, dimostrando attenzione senza adulazione, formule vuote o preamboli inutili.

**Evidenza richiesta:** risposta iniziale del caso, con indicazione dell'obiettivo compreso.

### F2 — Comprensione della richiesta
Verificare che identifichi il risultato pratico desiderato, distingua richiesta esplicita e assunzioni e non trasformi un bisogno semplice in un processo eccessivo.

**Evidenza richiesta:** sintesi dell'obiettivo e aderenza del prompt finale.

### F3 — Qualità delle domande
Verificare che le domande siano progressive, mirate e poste una alla volta; che riutilizzi le risposte già fornite; che chieda solo informazioni che cambiano materialmente il risultato; che usi segnaposto quando opportuno.

**Evidenza richiesta:** transcript di almeno due turni di chiarimento (T13).

### F4 — Applicazione di RICCE
Verificare che Role, Instructions, Context, Constraints ed Examples siano considerati quando utili, senza imporre tutte le componenti né mostrarle meccanicamente nei prompt semplici.

**Evidenza richiesta:** confronto tra un caso semplice (T01/T03) e uno articolato (T08/T11).

### F5 — Qualità dei cinque suggerimenti
Verificare che nelle ottimizzazioni sostanziali siano forniti esattamente cinque suggerimenti distinti e applicabili. Ogni suggerimento deve esprimere criticità, modifica e beneficio. Nei casi minimi o mirati non devono essere inventati cinque interventi.

**Evidenza richiesta:** risposta T14 (oppure T11) e risposta T03.

### F6 — Qualità dei prompt prodotti
Verificare che il prompt sia completo, autonomo, copiabile, specifico quanto serve, coerente con i vincoli e utilizzabile in un modello di destinazione. Deve distinguere dati noti da segnaposto e non inventare capacità.

**Evidenza richiesta:** prompt finale da T04, T05, T06, T07 o T15.

### F7 — Perfezionamento iterativo
Verificare che recepisca modifiche successive, mantenga obiettivo e vincoli già approvati, non ripeta le domande e restituisca ogni volta il prompt integrale aggiornato.

**Evidenza richiesta:** transcript T10 con prima e seconda versione.

## Casi di riferimento
- **Accoglienza e comprensione:** T01, T04.
- **Domande progressive:** T09 e T13.
- **RICCE flessibile:** T01, T03 e T08.
- **Cinque suggerimenti:** T11 e T14; controllo di proporzionalità T03.
- **Qualità del prompt:** T04–T08 e T15.
- **Iterazione:** T10.

## Scheda di registrazione

| Dimensione | Voto 0–5 | Evidenza / motivazione |
|---|---:|---|
| F1 — Accoglienza | [ ] | [ ] |
| F2 — Comprensione | [ ] | [ ] |
| F3 — Domande | [ ] | [ ] |
| F4 — RICCE | [ ] | [ ] |
| F5 — Suggerimenti | [ ] | [ ] |
| F6 — Prompt finale | [ ] | [ ] |
| F7 — Iterazione | [ ] | [ ] |
| **Totale / 35** | **[ ]** | **[ ]** |
| **Esito** | **[PASS / PARTIALLY VERIFIED / FAIL]** | **[ ]** |

## Confronto con il GPT di riferimento
Un confronto diretto richiede:
1. accesso autorizzato al GPT originale;
2. stessi input e contesto iniziale;
3. risposte integrali raccolte da entrambi;
4. valutazione cieca, quando possibile, con la stessa rubrica;
5. annotazione di modello, data, impostazioni e differenze.

In assenza di tali evidenze, riportare **NOT VERIFIED** per il confronto diretto. Non dedurre il funzionamento interno del GPT originale dalle sole descrizioni del progetto.
