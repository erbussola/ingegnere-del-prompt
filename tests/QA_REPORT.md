# QA Report — Ingegnere del Prompt 2.0

**Data verifica:** 15 novembre 2026  
**Branch verificato:** `architecture/universal-core-v2`  
**Pull Request:** [#2 — Universal Core 2.0](https://github.com/erbussola/ingegnere-del-prompt/pull/2)  
**Base:** `main` — invariato  
**Esito generale:** **PARTIALLY VERIFIED — NON PRONTO PER IL RILASCIO**

---

## 1. Sintesi esecutiva

La verifica approfondita conferma che la PR #2 ha una struttura documentale coerente con l'obiettivo del Core universale e che il contenuto è migliorato rispetto alla prima fase. I moduli descrivono un comportamento conversazionale progressivo, tre modalità operative, RICCE flessibile, cinque suggerimenti per ottimizzazioni sostanziali, iterazione e valutazione qualitativa.

I bundle completo e universale sono identici byte per byte. Il bundle compatto riporta le funzioni principali. I 15 casi di test e la rubrica di fedeltà sono definiti. Sono state verificate le procedure e le limitazioni di piattaforma sulle fonti ufficiali disponibili e corretti alcuni limiti non precisi.

Tuttavia, **non è stata eseguita una campagna di test comportamentali in sessioni pulite con il bundle caricato**, né sono stati eseguiti test su account reali di ChatGPT, Copilot Notebooks, Gemini e Claude. Non è stato possibile confrontare direttamente il comportamento con il GPT originale perché non è disponibile un dataset di risposte di riferimento né l'accesso alla sua configurazione originale. La sola ispezione dei file e la simulazione ragionata non sono sufficienti a certificare la qualità operativa.

La PR #2 deve quindi restare in draft. La versione 2.0 non va dichiarata pronta.

### Stato sintetico

| Area | Stato | Motivazione |
|---|---|---|
| Struttura modulare del Core | **PASS** | 11 moduli presenti con responsabilità riconoscibili |
| Coerenza normativa tra moduli | **PARTIALLY VERIFIED** | nessuna contraddizione critica individuata nella revisione; manca validazione esecutiva |
| Bundle completo | **PASS** | autonomo, senza dipendenze obbligatorie da altri file |
| Bundle universale | **PASS** | identico al bundle completo |
| Bundle compatto | **PARTIALLY VERIFIED** | copre funzioni essenziali; non testato per equivalente comportamento |
| Modalità A/B/C | **PASS** documentale | flussi e output attesi espliciti |
| Valutazione 1–10 | **PASS** documentale | criteri, media, motivazioni e confronto definiti |
| Test comportamentali | **NOT RUN** | i casi sono definiti ma non eseguiti in sessioni isolate con il bundle |
| Simulazione nel modello corrente | **NOT RUN come suite riproducibile** | la QA è stata condotta per ispezione e verifica di coerenza, non con transcript strutturati per ogni T01–T15 |
| Fedeltà al GPT originale | **NOT VERIFIED** | assente un riferimento empirico confrontabile |
| Deployment e fonti ufficiali | **PARTIALLY VERIFIED** | procedure e limiti documentati; account/tenant reali non provati |
| Link relativi nei documenti principali | **PASS** | nessun riferimento interno mancante rilevato nei file controllati |
| Legal Code CC BY-SA 4.0 | **PARTIALLY VERIFIED** | §8(c) corretto; trascrizione locale presente, ma non è stato eseguito un confronto completo byte-per-byte con il testo ufficiale |
| CI / GitHub Actions | **NOT VERIFIED** | nessuno status check e nessuna workflow run restituiti per l'head |
| Prontezza al rilascio | **FAIL** | mancano prove comportamentali e multipiattaforma fondamentali |

---

## 2. Stato del Core

### 2.1 Moduli esaminati

Sono stati esaminati tutti gli 11 moduli previsti:

1. `core/IDENTITY.md`
2. `core/BEHAVIORAL_ENGINE.md`
3. `core/CONVERSATION_ENGINE.md`
4. `core/RICCE_ENGINE.md`
5. `core/PROMPT_ANALYSIS.md`
6. `core/PROMPT_GENERATION.md`
7. `core/PROMPT_EVALUATION.md`
8. `core/QUALITY_ENGINE.md`
9. `core/OPERATING_MODES.md`
10. `core/CONTINUITY_ENGINE.md`
11. `core/SECURITY_AND_PRIVACY.md`

### 2.2 Valutazione

| Controllo | Stato | Osservazioni |
|---|---|---|
| Identità e missione | **PASS** | universale, non legata al provider o al settore |
| Comportamento | **PASS** | accoglienza, comprensione, proporzionalità e dialogo espliciti |
| Conversazione | **PASS** | ciclo operativo, domande progressive e criteri di arresto |
| RICCE | **PASS** | componenti operative e applicazione flessibile |
| Analisi prompt | **PASS** | classificazione minima, mirata, sostanziale |
| Generazione prompt | **PASS** | procedura operativa e gestione lacune |
| Valutazione | **PASS** | scala intera 1–10, cinque criteri, media a una cifra decimale |
| Qualità | **PASS** | gate di controllo e classificazione esiti |
| Modalità operative | **PASS** | A/B/C e combinazioni |
| Continuità | **PASS** | contesto chat, memoria piattaforma, istruzioni e registro portabile distinti |
| Sicurezza/privacy | **PASS** | segreti, minimizzazione, fonti e materiali esterni |

### 2.3 Coerenza e responsabilità

Le responsabilità sono ragionevolmente separate: Identity definisce missione e confini; Behavioral e Conversation definiscono il dialogo; RICCE definisce il metodo; Analysis e Generation gestiscono i due processi principali; Evaluation e Quality verificano il risultato; Operating Modes instrada il comportamento; Continuity e Security coprono aspetti trasversali.

Non è stata rilevata una contraddizione normativa critica tra i moduli esaminati. Esiste una duplicazione intenzionale tra Behavioral Engine, Conversation Engine e bundle, necessaria per rendere il comportamento distribuibile. La duplicazione è gestibile soltanto con un processo di aggiornamento simultaneo dei bundle quando cambia il Core.

**Limite:** la coerenza documentale non dimostra che il modello esegua correttamente il ciclo operativo. Stato finale: **PARTIALLY VERIFIED** per la qualità complessiva del Core.

---

## 3. Stato delle istruzioni distribuibili

### 3.1 Risultato statico

| File | Dimensione rilevata | Stato |
|---|---:|---|
| `instructions/CORE_INSTRUCTIONS.md` | circa 11 KB | **PASS** |
| `instructions/UNIVERSAL.md` | circa 11 KB | **PASS** |
| `instructions/COMPACT.md` | circa 3,3 KB | **PARTIALLY VERIFIED** |

Verifica oggettiva: `CORE_INSTRUCTIONS.md` e `UNIVERSAL.md` hanno lo stesso SHA Git, pertanto sono identici byte per byte.

### 3.2 Completezza e autonomia

Il bundle completo include identità, comportamento, RICCE, riconoscimento automatico delle tre modalità, cinque suggerimenti, valutazione, qualità, sicurezza, iterazione, continuità e portabilità. Non richiede che il chatbot apra altri file o segua link esterni.

Il bundle universale è una copia autonoma del completo e la procedura di avvio specifica che va incollato come primo messaggio.

Il bundle compatto conserva i punti essenziali: dialogo progressivo, RICCE, tre modalità, cinque suggerimenti condizionati, valutazione, sicurezza e continuità. Non è stata però misurata la perdita qualitativa rispetto al completo in un test comparativo.

### 3.3 Problema residuo

**NOT RUN:** non è stata eseguita una prova reale di installazione dei tre bundle in sessioni pulite, verificando lunghezza accettata, acquisizione, persistenza nel contesto e comportamento risultante. L'autonomia testuale è verificata; l'utilizzabilità pratica è solo parzialmente verificata.

---

## 4. Stato delle modalità operative

| Modalità | Stato documentale | Verifica comportamentale |
|---|---|---|
| A — Creazione | **PASS** | **NOT RUN** |
| B — Ottimizzazione | **PASS** | **NOT RUN** |
| C — Progettazione assistenti | **PASS** | **NOT RUN** |

La classificazione automatica è definita senza richiedere all'utente di scegliere A/B/C. La complessità è gestita in modo proporzionato. L'ottimizzazione distingue interventi minimi, mirati e sostanziali, evitando suggerimenti artificiali.

La progettazione di assistenti include utenti, missione, casi d'uso, funzioni, conoscenze, privacy, configurazione e test.

**Problema aperto:** non ci sono ancora transcript di test che dimostrino la corretta classificazione automatica su richieste ambigue o miste.

---

## 5. Stato del sistema di valutazione

<badge color="success">PASS — documentazione</badge>

I cinque criteri sono definiti:
1. Chiarezza.
2. Completezza.
3. Specificità.
4. Coerenza.
5. Utilizzabilità.

La procedura prevede voti interi 1–10, media aritmetica e arrotondamento a una cifra decimale. Ogni voto deve essere motivato con elementi osservabili. Il confronto prima/dopo deve utilizzare la stessa rubrica. È espressamente vietato gonfiare i punteggi.

**NOT RUN:** non è stata misurata la coerenza dei punteggi su un campione di prompt valutato ripetutamente. Il metodo è documentato, non ancora calibrato empiricamente.

---

## 6. Stato delle piattaforme

Le procedure sono state confrontate con la documentazione ufficiale consultata il 15 novembre 2026. La verifica riguarda la documentazione pubblicata, non l'esperienza concreta di un account.

| Piattaforma | Stato documentale | Test reale |
|---|---|---|
| Universal Chat | **PARTIALLY VERIFIED** | **NOT RUN** |
| ChatGPT Projects | **PASS** sulle capacità documentate | **NOT RUN** |
| Microsoft Copilot Notebooks | **PARTIALLY VERIFIED** | **NOT RUN** |
| Gemini Skills | **PARTIALLY VERIFIED** | **NOT RUN** |
| Claude Projects | **PARTIALLY VERIFIED** | **NOT RUN** |

### ChatGPT

La guida distingue correttamente Projects e Custom Instructions. Projects sono disponibili agli utenti autenticati secondo piano/workspace; limiti file documentati: Free 5, Go/Plus 25, Edu/Pro/Business/Enterprise 40. Le Custom Instructions hanno limiti diversi per piano: Free/Go 1.500 caratteri e piani superiori 5.000 caratteri per i campi di testo estesi. La guida è stata corretta in questa QA.

Fonti: [Projects](https://help.openai.com/en/articles/10169521-projects-in-chatgpt), [Custom Instructions](https://help.openai.com/en/articles/8096356-chatgpt-custom-instructions).

### Microsoft Copilot Notebooks

La guida chiarisce che un Notebook non è un GPT personalizzato globale. Microsoft documenta istruzioni per singolo Notebook e differenze tra Copilot Chat (fino a 50 fonti) e Microsoft 365 Copilot Work/School (fino a 300), oltre a differenze di tipologie di fonte e strumenti.

Il deployment resta dipendente da licenza, tenant, servizi SharePoint/OneDrive e rollout. La procedura è documentata, ma non testata su un tenant.

Fonti: [Istruzioni per Notebook](https://support.microsoft.com/en-us/microsoft-365-copilot/provide-custom-instructions-for-your-microsoft-365-copilot-notebook), [Licenze e limiti](https://support.microsoft.com/en-us/microsoft-365-copilot/copilot-notebooks-licensing).

### Gemini

La guida distingue account personali maggiorenni e Workspace. Al 15 novembre 2026, Google indica il 17 novembre 2026 come data da cui i Gems personali diventano read-only e il 17 dicembre 2026 come data di rimozione; Workspace business/enterprise/non profit segue nel marzo 2027 ed Education nel giugno 2027. Skills sono disponibili nelle chat per account personali 18+ e hanno limiti di file e di funzionalità.

Fonti: [Transizione Gems → Skills](https://support.google.com/gemini/answer/18560919).

### Claude

Projects è disponibile anche per account Free fino a cinque progetti. La knowledge base con RAG avanzato è disponibile nei piani a pagamento. Le istruzioni di progetto sono indicate dalla documentazione di personalizzazione come funzione soggetta al piano: la guida è stata corretta per non dare per scontato che l'account Free possa impostarle.

Fonti: [Projects](https://support.claude.com/en/articles/9517075-what-are-projects), [Personalizzazione](https://support.claude.com/en/articles/10185728-understanding-claude-s-personalization-features).

**Conclusione piattaforme:** capacità documentate **PARTIALLY VERIFIED**; compatibilità comportamentale su account reali **NOT VERIFIED**.

---

## 7. Stato dei test

### Suite definita

La suite `tests/TEST_CASES.md` contiene **15 casi**:
- T01 creazione semplice;
- T02 ottimizzazione incompleta;
- T03 prompt già strutturato;
- T04 marketing;
- T05 analisi documentale;
- T06 programmazione;
- T07 generazione immagini;
- T08 progettazione assistente;
- T09 richiesta ambigua;
- T10 iterazione;
- T11 cinque suggerimenti e valutazione;
- T12 privacy e segreti;
- T13 dialogo progressivo;
- T14 qualità dei cinque suggerimenti;
- T15 lingua e indipendenza dal settore.

La qualità dei casi è **PASS** a livello di definizione: ciascuno contiene input, comportamento atteso, criteri ed errori da evitare. La suite copre i principali requisiti del Core.

### Test simulati

Non è stata eseguita una campagna riproducibile con 15 transcript indipendenti nel modello corrente. Non è quindi corretto riportare un numero di test simulati superati. La revisione di coerenza dei casi rispetto al Core è stata effettuata; non equivale a simulazione o test esecutivo.

### Test effettivamente eseguiti

- **Test strutturali sul repository:** eseguiti.
- **Test di uguaglianza Core/Universal:** eseguito e superato (SHA identico).
- **Controllo presenza e struttura dei 15 test case:** eseguito.
- **Controllo documentale dei deployment e delle fonti:** eseguito.
- **Esecuzione dei casi T01–T15 in sessioni pulite con bundle:** **NOT RUN**.
- **Esecuzione su account reali esterni:** **NOT RUN**.

---

## 8. Fedeltà comportamentale al GPT originale

Il file `tests/FIDELITY_TESTS.md` definisce sette dimensioni, scala 0–5 e soglie su 35 punti:

| Dimensione | Obiettivo | Stato |
|---|---|---|
| F1 Accoglienza amichevole | tono naturale, professionale, collaborativo | **NOT RUN** |
| F2 Comprensione | identificazione del risultato pratico | **NOT RUN** |
| F3 Domande | progressione, una per volta, dati bloccanti | **NOT RUN** |
| F4 RICCE | flessibilità senza rigidità | **NOT RUN** |
| F5 Suggerimenti | cinque interventi distinti e proporzionati | **NOT RUN** |
| F6 Prompt finali | completezza e copiabilità | **NOT RUN** |
| F7 Iterazione | conservazione delle parti approvate | **NOT RUN** |

### Confronto diretto con il GPT originale

**NOT VERIFIED.** Non è disponibile un transcript di riferimento, un export autorizzato delle istruzioni private o una serie di input/output raccolta dal GPT originale. Il progetto può essere valutato contro i comportamenti descritti dal proprietario, ma non può certificare la replica esatta del GPT originale.

Per completare la verifica servono:
1. accesso autorizzato al GPT originale;
2. stessi input e contesto iniziale;
3. risposte integrali raccolte da entrambi;
4. valutazione con la stessa rubrica, preferibilmente cieca;
5. registrazione di modello, data, impostazioni e differenze.

Non è assegnato un punteggio F1–F7, perché non esistono evidenze esecutive adeguate.

---

## 9. Controllo documentale

### Ambito ispezionato

Sono stati verificati i file del repository relativi a:
- Core e moduli normativi;
- bundle e README delle istruzioni;
- guide di deployment;
- framework e template;
- esempi;
- test;
- documentazione e knowledge base;
- README, changelog, licenza, contributi e codice di condotta;
- template Issue e Pull Request.

### Risultati

| Controllo | Stato | Note |
|---|---|---|
| README | **PASS** | architettura, modalità e stato QA descritti |
| CHANGELOG | **PASS** | aggiornato durante QA |
| FAQ | **PASS** | limiti piattaforma e costi chiariti |
| Guide | **PARTIALLY VERIFIED** | corrette sulle fonti ufficiali; account non provati |
| CONTRIBUTING | **PASS** | regole architetturali e licenze esplicite |
| CODE_OF_CONDUCT | **PASS** | comportamenti e segnalazioni descritti |
| LICENSE.md | **PASS** documentale | riferimento al file legale e alla fonte canonica |
| LICENSE-CC-BY-SA-4.0.txt | **PARTIALLY VERIFIED** | §8(c) confrontato e corretto; non eseguito diff completo byte-per-byte |
| Collegamenti interni | **PASS** nei documenti principali controllati | nessun link interno mancante rilevato |
| Duplicazioni | **PARTIALLY VERIFIED** | bundle duplicati intenzionalmente; richiedono sincronizzazione futura |
| CI / Actions | **NOT VERIFIED** | nessuno status check o workflow run visibile sull'head |

Il file `docs/RECOVERY_FROM_PR1.md` è stato aggiornato da 12 a 15 casi per allinearlo alla suite corrente.

---

## 10. Problemi individuati

### Correzioni effettuate

1. Corretto il limite delle Custom Instructions ChatGPT: non è unico per tutti i piani.
2. Aggiornata la matrice piattaforme e la FAQ con il limite corretto.
3. Esplicitate differenze Copilot Chat / Microsoft 365 Copilot nei tipi di fonti e nei limiti.
4. Chiarita la differenza tra accesso a Claude Projects sul piano Free e disponibilità delle istruzioni persistenti di progetto.
5. Aggiornati README, CHANGELOG e FAQ per riflettere le correzioni QA.
6. Aggiornata la nota di recupero PR #1 per riportare 15 test e la rubrica di fedeltà.
7. Verificata l'identità dei bundle completo e universale.
8. Verificati i link relativi nei documenti principali controllati.
9. Verificata la formulazione ufficiale del §8(c) del Legal Code CC BY-SA 4.0 rispetto alla copia locale.

### Problemi ancora aperti

| Problema | Gravità | Stato |
|---|---|---|
| Test T01–T15 non eseguiti con bundle in sessioni pulite | Bloccante per rilascio | **NOT RUN** |
| Test su ChatGPT, Copilot, Gemini, Claude non eseguiti su account reali | Bloccante per compatibilità dichiarata | **NOT RUN** |
| Rubrica F1–F7 non compilata con transcript reali | Bloccante per fedeltà comportamentale | **NOT RUN** |
| Confronto diretto col GPT originale non disponibile | Maggiore | **NOT VERIFIED** |
| Diff completo del Legal Code locale non eseguito | Minore | **PARTIALLY VERIFIED** |
| CI / Actions senza evidenze | Minore/da verificare | **NOT VERIFIED** |
| Bundle completo/compatto duplicano regole normative | Rischio manutentivo | Da gestire con test automatico di coerenza |

---

## 11. Valutazione complessiva

Il progetto ha raggiunto un livello documentale e architetturale solido. Il Core è sufficientemente definito per avviare una campagna di test, le istruzioni sono autonome e le guide piattaforma distinguono meglio capacità, licenze e limiti.

La qualità operativa resta però **non verificata**. La suite di test è un piano di verifica, non evidenza del suo superamento. La compatibilità delle piattaforme non può essere dedotta dalla presenza di istruzioni personalizzate. La fedeltà al GPT originale non può essere dichiarata senza il confronto diretto.

**Valutazione QA: PARTIALLY VERIFIED.**

### Raccomandazione

**NO-GO per il rilascio 2.0.**  
**GO per la fase successiva di test comportamentali controllati.**

La PR #2 deve rimanere in draft fino a:
1. esecuzione T01–T15 con il bundle completo in sessioni pulite;
2. esecuzione dei casi essenziali con il bundle compatto;
3. compilazione dei sette punteggi F1–F7 con transcript;
4. prove reali sulle piattaforme dichiarate;
5. registrazione di modello, piano, data e risultati;
6. risoluzione dei difetti bloccanti e maggiori;
7. confronto diretto con il GPT originale, se l'accesso viene reso disponibile, oppure dichiarazione esplicita che la fedeltà è valutata solo rispetto al comportamento-obiettivo descritto.

---

## 12. Stato repository e Pull Request

Al momento della chiusura di questa QA:
- Branch: `architecture/universal-core-v2`.
- PR #2: aperta, draft, non unita.
- `main`: invariato; il branch è avanti rispetto a `main` e non indietro.
- PR #1: aperta, non unita, branch originale preservato.
- Nessuna review o approvazione è stata inviata.
- Nessun merge è stato effettuato.
- Nessun file è stato rimosso dalla PR #2 durante questa QA.

La PR #2 deve rimanere draft.

---

## 13. Checklist per la prossima esecuzione

- [ ] Eseguire T01–T15 con `CORE_INSTRUCTIONS.md` in sessioni pulite.
- [ ] Ripetere i test chiave con `COMPACT.md`.
- [ ] Registrare transcript integrali, modello e data.
- [ ] Compilare F1–F7 in `FIDELITY_TESTS.md`.
- [ ] Eseguire almeno un ciclo di confronto su ciascuna piattaforma.
- [ ] Verificare eventuali limitazioni specifiche di piano e tenant.
- [ ] Eseguire un confronto completo del Legal Code locale rispetto al plain text canonico.
- [ ] Verificare eventuali controlli CI disponibili.
- [ ] Aggiornare la raccomandazione di rilascio solo dopo evidenze riproducibili.

## Addendum A04 — stato dopo implementazione documentale

**Mandato:** A04 — implementazione controllata della specifica A03.  
**QA comportamentale:** NON ESEGUITO durante l'implementazione.  
**Equivalenza Compact:** NON VERIFICATA.  
**Rilascio:** NON AUTORIZZATO.

Questo addendum non riscrive gli esiti storici del rapporto. Le modifiche documentali non costituiscono prova comportamentale. La nuova campagna è descritta nel piano e nella guida; le nuove run sono registrate append-only in BEHAVIORAL_TEST_RESULTS.md. Applicare scheda ambientale, quattro assi indipendenti e aggregazione T01. Tutti i test nuovi richiedono sessioni conformi e transcript integrali. Non dichiarare risolti difetti sulla sola base delle modifiche documentali.
