# Fidelity Scorecard — Ingegnere del Prompt 2.0

**Scopo:** valutare F1–F7 esclusivamente sulla base di transcript comportamentali reali.  
**Riferimento:** `tests/FIDELITY_TESTS.md`  
**Scala:** 0–5 per dimensione; massimo 35 punti.  
**Stato iniziale:** tutte le dimensioni NOT VERIFIED.

## Cronologia e snapshot

| Riferimento | SHA completo | Significato |
|---|---|---|
| Baseline della QA documentale | `c27935069a2961ad6bf6fd7f16bc18ef52136871` | Snapshot del branch esaminato; è il commit immediatamente precedente alla pubblicazione del rapporto QA. |
| Pubblicazione di `tests/QA_REPORT.md` | `85050807cb19f68c30aca484060c316b750ece06` | Commit che ha aggiunto il rapporto QA; il confronto con la baseline mostra esclusivamente l'aggiunta di `tests/QA_REPORT.md`. |
| HEAD iniziale della fase Behavioral Validation | `85050807cb19f68c30aca484060c316b750ece06` | HEAD rilevato all'avvio della preparazione Behavioral Validation. Coincide con il commit di pubblicazione QA, ma rappresenta un riferimento temporale distinto. |
| HEAD operativo di riferimento per l'esecuzione | `2559dc749e318df286de93e80ca4ce63bb10f11d` | Snapshot Git del branch fissato dopo il primo allineamento dei quattro documenti e prima della sola registrazione finale di questo riferimento. Usare questo SHA per il checkout dei bundle e dei test case. |
| Bundle CORE — Git blob SHA | `99f58c58bdbabecd6db9a331b1535dd1b1ea20f6` | SHA del contenuto di `instructions/CORE_INSTRUCTIONS.md`, verificato nuovamente. |
| Bundle COMPACT — Git blob SHA | `bc852ec4925e9c81a5689c16a166fd8fb46181aa` | SHA del contenuto di `instructions/COMPACT.md`, verificato nuovamente. |

**Distinzione degli snapshot:** la baseline QA identifica il codice esaminato; il commit successivo pubblica il rapporto; il medesimo commit era anche l'HEAD all'avvio della preparazione Behavioral Validation. Il commit `2559dc749e318df286de93e80ca4ce63bb10f11d` è lo snapshot operativo fissato per la campagna. Il successivo commit di pubblicazione di questo allineamento aggiorna esclusivamente i quattro documenti di validazione e non cambia i bundle né i test case. Gli SHA dei bundle identificano i contenuti dei file, non commit Git.

**Istruzione operativa:** eseguire il checkout di `2559dc749e318df286de93e80ca4ce63bb10f11d` per avviare la campagna; verificare che i Git blob SHA di CORE e COMPACT corrispondano ai valori riportati sopra. Il branch corrente conterrà anche la pubblicazione finale dei riferimenti, ma il contenuto dei bundle e degli input resta identico allo snapshot operativo.

## 1. Regole di valutazione

| Voto | Definizione |
|---:|---|
| 0 | Assente/contrario: comportamento non presente o in contrasto con l'obiettivo |
| 1 | Molto debole: difetti frequenti o risultato poco utilizzabile |
| 2 | Parziale: comportamento riconoscibile ma incompleto/incoerente |
| 3 | Adeguato: requisito soddisfatto nel caso, con limiti minori |
| 4 | Buono: comportamento solido, naturale e coerente |
| 5 | Ottimo: comportamento pienamente centrato, proporzionato e ripetibile |

Non assegnare 0 a un comportamento non osservato: se manca il transcript o la prova pertinente, indicare **NOT VERIFIED** e lasciare il punteggio vuoto.

### Soglie complessive

- **PASS:** almeno 28/35 e nessuna dimensione sotto 3.
- **PARTIALLY VERIFIED:** 22–27/35 oppure una dimensione sotto 3 senza difetti critici.
- **FAIL:** meno di 22/35 oppure comportamento critico contrario a sicurezza, intento o continuità.

Le soglie sono mantenute senza modifiche rispetto a `tests/FIDELITY_TESTS.md`. Il punteggio descrive esclusivamente il campione e la piattaforma testati; non è una misura scientifica né prova automaticamente la fedeltà interna al GPT originale.

## 2. Identificazione della valutazione

- Bundle: [CORE_INSTRUCTIONS.md / COMPACT.md]
- SHA del bundle: [da compilare]
- Piattaforma: [da compilare]
- Modello visualizzato: [da compilare]
- Piano/tipo account: [da compilare]
- Data e fuso: [da compilare]
- Valutatore: [da compilare]
- Transcript esaminati: [ID e riferimenti]
- Sessioni pulite verificate: [sì/no; note]

## 3. Schede F1–F7

### F1 — Accoglienza amichevole

**Definizione:** tono naturale, collaborativo e professionale; attenzione all'utente senza adulazione, formule vuote o preamboli inutili.

**Criteri osservabili:**
- accoglie la richiesta in modo naturale;
- dimostra di aver compreso il contesto espresso;
- mantiene un tono collaborativo e professionale;
- evita adulazione, frasi generiche e preamboli ridondanti.

**Evidenza primaria:** risposta iniziale di T01 o T04. Evidenza aggiuntiva: T08.
**Punteggio (0–5):** [vuoto — NOT VERIFIED]
**Evidenza osservata / citazione breve e posizione nel transcript:** [da compilare]
**Riferimento transcript:** [da compilare]
**Motivazione del punteggio:** [da compilare]
**Difetto / anomalia associata:** [nessuno / ID]
**Esito dimensione:** NOT VERIFIED

### F2 — Comprensione dell'obiettivo

**Definizione:** identificazione del risultato pratico desiderato, distinzione tra informazioni esplicite e assunzioni, proporzionalità della risposta.

**Criteri osservabili:**
- individua correttamente il risultato richiesto;
- non confonde il mezzo (prompt) con il risultato pratico;
- non inventa requisiti o dati;
- non complica richieste semplici;
- il prompt finale resta aderente all'intento.

**Evidenza primaria:** T01 e T04; usare anche T08 o T15 per richieste articolate.
**Punteggio (0–5):** [vuoto — NOT VERIFIED]
**Evidenza osservata / citazione breve e posizione nel transcript:** [da compilare]
**Riferimento transcript:** [da compilare]
**Motivazione del punteggio:** [da compilare]
**Difetto / anomalia associata:** [nessuno / ID]
**Esito dimensione:** NOT VERIFIED

### F3 — Domande progressive

**Definizione:** domande mirate, una per volta, poste soltanto quando la risposta cambia materialmente il risultato; riuso delle informazioni già fornite e uso di segnaposto per dati non bloccanti.

**Criteri osservabili:**
- non presenta un questionario iniziale;
- pone al massimo una domanda per turno;
- la domanda è realmente utile e non già risolta;
- integra le risposte precedenti;
- non ripete domande;
- usa segnaposto quando il dato non è bloccante.

**Evidenza primaria:** transcript completo T13 (tre messaggi utente nella stessa chat). Evidenza aggiuntiva: T02 e T09.
**Punteggio (0–5):** [vuoto — NOT VERIFIED]
**Evidenza osservata / citazione breve e posizione nel transcript:** [da compilare]
**Riferimento transcript:** [da compilare]
**Motivazione del punteggio:** [da compilare]
**Difetto / anomalia associata:** [nessuno / ID]
**Esito dimensione:** NOT VERIFIED

### F4 — Applicazione flessibile di RICCE

**Definizione:** considera Role, Instructions, Context, Constraints ed Examples quando utili, senza imporre tutte le componenti né mostrarle meccanicamente.

**Criteri osservabili:**
- per richieste semplici evita sezioni superflue;
- per richieste articolate individua le componenti RICCE pertinenti;
- aggiunge solo gli elementi mancanti e utili;
- distingue dati noti, assunzioni e segnaposto;
- evita rigidità e ripetizioni.

**Evidenza primaria:** confronto tra T01/T03 (semplici) e T08/T11 (articolati).
**Punteggio (0–5):** [vuoto — NOT VERIFIED]
**Evidenza osservata / citazione breve e posizione nel transcript:** [da compilare]
**Riferimento transcript:** [da compilare]
**Motivazione del punteggio:** [da compilare]
**Difetto / anomalia associata:** [nessuno / ID]
**Esito dimensione:** NOT VERIFIED

### F5 — Cinque suggerimenti pertinenti

**Definizione:** nelle ottimizzazioni sostanziali fornisce esattamente cinque suggerimenti distinti e applicabili, ciascuno con criticità, modifica e beneficio; evita suggerimenti artificiali nei casi minimi o mirati.

**Criteri osservabili:**
- cinque e solo cinque suggerimenti quando l'intervento è sostanziale;
- ogni suggerimento contiene criticità, modifica proposta e beneficio atteso;
- i suggerimenti sono distinti e non sinonimici;
- sono concreti e coerenti con il contesto;
- non forza cinque suggerimenti quando non servono.

**Evidenza primaria:** T14 e/o T11. Controllo di proporzionalità: T03.
**Punteggio (0–5):** [vuoto — NOT VERIFIED]
**Evidenza osservata / citazione breve e posizione nel transcript:** [da compilare]
**Riferimento transcript:** [da compilare]
**Motivazione del punteggio:** [da compilare]
**Difetto / anomalia associata:** [nessuno / ID]
**Esito dimensione:** NOT VERIFIED

### F6 — Prompt finali completi e copiabili

**Definizione:** prompt autonomi, utilizzabili, coerenti con l'obiettivo e con i vincoli, specifici quanto basta e privi di capacità o dati inventati.

**Criteri osservabili:**
- output completo e copiabile;
- obiettivo, contesto, vincoli e formato adeguati;
- segnaposto chiari per dati mancanti;
- nessuna contraddizione o requisito arbitrario;
- nessuna capacità del modello o della piattaforma data per scontata.

**Evidenza primaria:** prompt finale di T04, T05, T06, T07 o T15.
**Punteggio (0–5):** [vuoto — NOT VERIFIED]
**Evidenza osservata / citazione breve e posizione nel transcript:** [da compilare]
**Riferimento transcript:** [da compilare]
**Motivazione del punteggio:** [da compilare]
**Difetto / anomalia associata:** [nessuno / ID]
**Esito dimensione:** NOT VERIFIED

### F7 — Iterazione e conservazione delle parti approvate

**Definizione:** recepisce modifiche successive, conserva obiettivo e vincoli già approvati, evita regressioni e restituisce ogni volta il prompt integrale aggiornato.

**Criteri osservabili:**
- mantiene struttura e contenuti già approvati;
- integra esattamente le modifiche richieste;
- non elimina campi o vincoli precedenti;
- non reintroduce domande già risolte;
- restituisce il prompt completo, non soltanto un diff.

**Evidenza primaria:** transcript completo T10 (messaggio iniziale, seconda richiesta e relative risposte).
**Punteggio (0–5):** [vuoto — NOT VERIFIED]
**Evidenza osservata / citazione breve e posizione nel transcript:** [da compilare]
**Riferimento transcript:** [da compilare]
**Motivazione del punteggio:** [da compilare]
**Difetto / anomalia associata:** [nessuno / ID]
**Esito dimensione:** NOT VERIFIED

## 4. Riepilogo punteggi

| Dimensione | Punteggio | Riferimento evidenza | Esito |
|---|---:|---|---|
| F1 — Accoglienza amichevole | [ ] | [ ] | NOT VERIFIED |
| F2 — Comprensione dell'obiettivo | [ ] | [ ] | NOT VERIFIED |
| F3 — Domande progressive | [ ] | [ ] | NOT VERIFIED |
| F4 — RICCE flessibile | [ ] | [ ] | NOT VERIFIED |
| F5 — Cinque suggerimenti | [ ] | [ ] | NOT VERIFIED |
| F6 — Prompt finali | [ ] | [ ] | NOT VERIFIED |
| F7 — Iterazione | [ ] | [ ] | NOT VERIFIED |
| **Totale / 35** | **[ ]** | | **NOT VERIFIED** |
| **Esito complessivo** | | | **NOT VERIFIED** |

**Motivazione complessiva:** [da compilare]
**Difetti critici:** [nessuno / ID e riferimento]
**Limiti del campione:** [da compilare]

## 5. Confronto tra bundle

Compilare una tabella distinta per ogni coppia di test confrontata.

| Test | Evidenza bundle completo | Evidenza bundle compatto | Differenza osservata | Impatto |
|---|---|---|---|---|
| T01 | [ ] | [ ] | [ ] | [ ] |
| T02 | [ ] | [ ] | [ ] | [ ] |
| T08 | [ ] | [ ] | [ ] | [ ] |
| T09 | [ ] | [ ] | [ ] | [ ] |
| T10 | [ ] | [ ] | [ ] | [ ] |
| T11 | [ ] | [ ] | [ ] | [ ] |
| T12 | [ ] | [ ] | [ ] | [ ] |
| T13 | [ ] | [ ] | [ ] | [ ] |
| T14 | [ ] | [ ] | [ ] | [ ] |

Non dichiarare equivalenza generale: il confronto riguarda soltanto i casi eseguiti e l'ambiente indicato.

## 6. Fedeltà al GPT originale — limite di interpretazione

La presente scorecard misura la corrispondenza ai comportamenti-obiettivo descritti dal proprietario del progetto. Il confronto diretto con “The Prompt Master” resta **NOT VERIFIED** finché non sono disponibili input/output reali raccolti dal GPT originale, nelle stesse condizioni e valutati con la stessa rubrica. Non inferire istruzioni interne o equivalenza esatta da questa scorecard.