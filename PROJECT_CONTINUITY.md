# PROJECT CONTINUITY — Ingegnere del Prompt

**Aggiornato al:** 16 novembre 2026  
**Repository:** erbussola/ingegnere-del-prompt  
**Branch:** architecture/universal-core-v2  
**Commit di riferimento pre-creazione:** fb862b2e430263f0a6f8dfff3e193b8b750ab64b

> Fotografia documentale delle evidenze disponibili alla data indicata. Lo stato GitHub può cambiare successivamente: questo documento non sostituisce una verifica in tempo reale. Lo SHA del commit che introduce questo file è riportato nei metadati Git e nel rapporto operativo. Non è possibile incorporare nel file il proprio SHA finale senza generare un ulteriore commit e rendere nuovamente obsoleto il riferimento.

---

## 1. Identità e obiettivo

**Ingegnere del Prompt** è un progetto open source nel repository ufficiale [erbussola/ingegnere-del-prompt](https://github.com/erbussola/ingegnere-del-prompt).

Realizza un kit documentale universale per comprendere, progettare, creare, analizzare, ottimizzare e valutare prompt e assistenti AI. Il kit comprende istruzioni, metodi, guide, template, esempi e test, da usare nel chatbot già disponibile all'utente.

Principi di progetto:
- indipendenza da uno specifico fornitore o modello;
- utilizzo mediante normali istruzioni testuali e conversazione;
- nessuna dipendenza obbligatoria da API a pagamento, server, backend o database;
- separazione tra Core universale e adattamenti specifici per piattaforma.

Il progetto mira a ricreare e migliorare, per quanto verificabile, i comportamenti osservabili del GPT personalizzato **The Prompt Master** utilizzato dall'utente. Non dichiara di possedere le istruzioni riservate o la configurazione interna, né di poter migrare direttamente il GPT originale. Il lavoro si basa su caratteristiche osservabili, documentazione e prove disponibili.

## 2. Architettura e funzionamento

### 2.1 Core e framework RICCE

La directory core/ contiene la fonte normativa del comportamento atteso: identità, comportamento, conversazione, RICCE, analisi e generazione prompt, valutazione, qualità, modalità operative, continuità e sicurezza/privacy.

RICCE è il metodo comune per progettare, analizzare e revisionare prompt:

| Componente | Significato |
|---|---|
| R — Role | Ruolo, competenze e prospettiva utili |
| I — Instructions | Obiettivo, compiti, priorità, sequenza e output |
| C — Context | Scenario, destinatari, informazioni e risorse |
| C — Constraints | Limiti, esclusioni, requisiti, sicurezza e formato |
| E — Examples | Esempi di input/output o comportamento desiderato |

RICCE è flessibile: non richiede cinque sezioni visibili in ogni prompt. Si usano solo le componenti pertinenti; si chiedono chiarimenti per lacune bloccanti e si usano segnaposto per dati non bloccanti.

### 2.2 Modalità operative

Il Core riconosce automaticamente tre modalità, senza obbligare l'utente a selezionarle:

- **A — Creazione di prompt:** parte da un'idea o esigenza, raccoglie progressivamente le informazioni necessarie e consegna un prompt completo e copiabile.
- **B — Analisi e ottimizzazione:** esamina un prompt esistente, preserva gli elementi efficaci e classifica l'intervento come minimo, mirato o sostanziale. Nelle revisioni sostanziali presenta cinque suggerimenti distinti, ciascuno con criticità, modifica e beneficio. Non forza cinque suggerimenti per correzioni minime o mirate.
- **C — Progettazione di assistenti AI:** definisce identità, missione, utenti, casi d'uso, funzioni, comportamento, istruzioni, conoscenze/fonti, vincoli, privacy, configurazione, esempi e test di accettazione.

Le modalità possono essere combinate quando necessario.

### 2.3 Dialogo, valutazione e iterazione

Il comportamento conversazionale prevede comprensione dell'obiettivo pratico, dialogo progressivo con una domanda mirata per volta, riuso delle informazioni già fornite, segnaposto o assunzioni dichiarate per dati non bloccanti, cinque suggerimenti nelle sole ottimizzazioni sostanziali e restituzione del prompt finale integrale.

Quando pertinente, il prompt viene valutato su cinque criteri: chiarezza, completezza, specificità, coerenza e utilizzabilità. Ogni criterio riceve un voto intero da 1 a 10, motivato con elementi osservabili; la media aritmetica è arrotondata a una cifra decimale. Nei confronti prima/dopo si usano gli stessi criteri e la stessa scala, senza bonus automatici alla riscrittura.

La continuità tra sessioni è portabile: il progetto distingue contesto della chat, memoria della piattaforma, istruzioni permanenti, conoscenza di progetto e registro esportato dall'utente. Non presume che una nuova chat acceda automaticamente alle conversazioni precedenti.

### 2.4 Bundle distribuibili

- **Core completo:** instructions/CORE_INSTRUCTIONS.md, bundle autonomo e completo.
- **Universal:** instructions/UNIVERSAL.md, copia integrale e autonoma del Core completo.
- **Compact:** instructions/COMPACT.md, versione ridotta per contesti con limiti di lunghezza.

I bundle sono istruzioni testuali interpretate dal chatbot di destinazione: non installano software né ampliano le capacità del modello. I documenti deployment/ adattano l'uso alle funzioni effettivamente disponibili sulle piattaforme, senza ridefinire le regole universali.

## 3. Bundle, baseline e riferimenti documentali

### 3.1 Architettura dei bundle

Il progetto mantiene tre principali modalità di distribuzione delle istruzioni:

- Core completo: `instructions/CORE_INSTRUCTIONS.md`
- Universal: `instructions/UNIVERSAL.md`
- Compact: `instructions/COMPACT.md`

Alla baseline A11, Core e Universal risultavano identici byte per byte, con lo stesso Git blob SHA, secondo le verifiche documentate nelle fasi A13/A14.

L'equivalenza comportamentale tra Full e Compact non è ancora stata dimostrata: la campagna comparativa non è stata eseguita.

### 3.2 Baseline A11

La baseline A11 è stata utilizzata come riferimento per l'analisi A13, la specifica A14 e l'allineamento documentale A15.

Commit A11:

`6a765f9c27d7bf1f8cd8305a2d2b7d272964863c`

Parent A10:

`93fd92fa485148feb70bdebbcd20420e7ed0953c`

Git blob SHA dei bundle e dei casi di test:

| Documento | Git blob SHA A11 |
|---|---|
| `instructions/CORE_INSTRUCTIONS.md` | `06e809107d89333738aa96b758e81d1a94383cd3` |
| `instructions/UNIVERSAL.md` | `06e809107d89333738aa96b758e81d1a94383cd3` |
| `instructions/COMPACT.md` | `a102a3819446565621f4a9d492107625ec99b6b0` |
| `tests/TEST_CASES.md` | `8dfb6edfed017efc459a8853c211e3c76b6de6e2` |

Questi riferimenti sono quelli dichiarati e verificati nei rapporti A13/A14 alla baseline A11. Identificano il contenuto dei singoli file e non devono essere confusi con gli SHA dei commit.

### 3.3 Snapshot storico 84db

Il commit:

`84db964b5ec17ae6c203c125b95133c64b772e75`

identifica uno snapshot storico utilizzato quale riferimento operativo per una precedente campagna QA.

Non deve essere considerato la baseline operativa della nuova campagna.

Le precedenti esecuzioni che utilizzavano quello snapshot devono conservare i riferimenti originali ai bundle e ai test case.

La distinzione è obbligatoria:

- Commit storico 84db: identifica lo snapshot utilizzato nelle precedenti esecuzioni QA.
- Commit A11: identifica la baseline dei bundle esaminati da A13/A14.
- Commit A15: identifica la versione documentale aggiornata secondo la specifica approvata.
- Git blob SHA: identifica il contenuto di un singolo file.

Non riscrivere gli SHA storici delle esecuzioni già effettuate.

### 3.4 Documenti QA aggiornati da A15

Secondo il rapporto operativo A15, i quattro documenti seguenti sono stati aggiornati esclusivamente sul branch autorizzato.

| Documento | Git blob SHA A15 dichiarato |
|---|---|
| `tests/BEHAVIORAL_VALIDATION_PLAN.md` | `0074f96e0e1d0bf472e2d6e78567d32b909d57cf` |
| `tests/BEHAVIORAL_VALIDATION_GUIDE.md` | `b8f450ca4ebafddf6d7dfe37382c7d868e25d53d` |
| `tests/BEHAVIORAL_TEST_RESULTS.md` | `0c9c6c9482ade871ad2e8eda38c1ebc8018999b8` |
| `tests/FIDELITY_SCORECARD.md` | `1f9ccbf976d11479ae9a30cc80d7eda3b07cca8b` |

Secondo lo stesso rapporto:

- i bundle normativi sono rimasti invariati;
- `tests/TEST_CASES.md` è rimasto invariato;
- `tests/QA_REPORT.md` è rimasto invariato;
- `tests/FIDELITY_TESTS.md` è rimasto invariato.

Gli SHA sopra riportati sono dichiarati nel rapporto A15. Sono riferimenti documentali della fase e non costituiscono una nuova verifica indipendente effettuata durante A16.

### 3.5 Schede Compact vuote e riferimenti SHA

Secondo il rapporto A15, le nove schede Compact originariamente vuote sono state conservate.

I relativi riferimenti SHA sono stati aggiornati al Git blob SHA A11 del bundle Compact:

`a102a3819446565621f4a9d492107625ec99b6b0`

Le nove schede restano NOT RUN e non contengono transcript o evidenze comportamentali.

L'aggiornamento dei riferimenti SHA delle schede non modifica né sostituisce la baseline del bundle Compact.

Occorre mantenere distinti:

- il Git blob SHA del bundle Compact A11;
- i riferimenti SHA registrati nelle singole schede;
- il Git blob SHA del documento `tests/BEHAVIORAL_TEST_RESULTS.md` aggiornato da A15.

Per le 18 prove Compact aggiuntive viene riutilizzato il modello generico A08; secondo la specifica A14/A15 non sono state create 18 schede statiche separate.

## 4. Cronologia delle fasi A01–A15

| Fase | Attività ed esito |
|---|---|
| A01 | Analisi trasversale del QA iniziale e individuazione delle criticità. |
| A02 | Progettazione delle correzioni. |
| A03 | Revisione e approvazione delle specifiche di correzione, senza autorizzazione al rilascio. |
| A04 | Implementazione delle correzioni sul branch autorizzato. |
| A05 | Audit non superato; criticità nel gate operativo, scoring, lingua, T01 e riproducibilità dei test. |
| A06 | Implementazione delle correzioni successive ad A05. |
| A07 | Audit non superato; lacune nella fixture T16-D, nella condizione di arresto T16-E, nel setup T20-F e nella documentazione T01/T04/T10. |
| A08 | Correzioni documentali delle criticità A07; implementazione completata. QA comportamentale non eseguito. |
| A09 | Audit statico indipendente superato con quattro osservazioni P2. Nessuna modifica al repository durante l'audit. |
| A10 | Creazione e pubblicazione di `PROJECT_CONTINUITY.md`. Commit `93fd92fa485148feb70bdebbcd20420e7ed0953c`. |
| A11 | Correzione documentale dei quattro rilievi P2 A09. Commit `6a765f9c27d7bf1f8cd8305a2d2b7d272964863c`. |
| A12 | Audit statico indipendente delle correzioni A11: 4/4 PASS secondo il rapporto. Sola lettura, nessuna modifica Git. |
| A13 | Preparazione del protocollo QA Full/Compact. Inventari e protocollo ricostruiti; campagna non pronta per criticità documentali H1–H8. Sola lettura. |
| A14 | Definizione della specifica canonica Full/Compact. Rapporto conclusivo positivo e specifica approvata dall'utente. Sola lettura. |
| A15 | Allineamento dei quattro documenti QA alla specifica A14. Completato secondo il rapporto operativo; quattro file modificati, nessun test comportamentale. |

Il completamento di un'implementazione documentale, il superamento di un audit statico e la definizione di un protocollo non equivalgono a validazione comportamentale o autorizzazione al rilascio.

### 4.1 A11 — Correzione dei rilievi A09

A11 ha affrontato i quattro rilievi P2:

1. A09-R01 — T16-D: controlli `-e` e `-L`, protezione `set -eu`, distinzione tra percorso inesistente e symlink dangling.
2. A09-R02 — T16-E: condizioni esplicite di FAIL e arresto in caso di violazione del consenso; nessun messaggio 3 in caso di violazione.
3. A09-R03 — T01: chiarimento che la matrice A–G è una formalizzazione A08 della regola deterministica A06.
4. A09-R04 — T04-R/T10-R: uniformazione degli identificativi e dei riferimenti documentali.

Secondo il rapporto A11 sono stati modificati esclusivamente:

- `tests/TEST_CASES.md`
- `tests/BEHAVIORAL_VALIDATION_PLAN.md`
- `tests/BEHAVIORAL_VALIDATION_GUIDE.md`

Il registro storico `tests/BEHAVIORAL_TEST_RESULTS.md` non è stato modificato in A11.

Commit A11:

`6a765f9c27d7bf1f8cd8305a2d2b7d272964863c`

### 4.2 A12 — Audit statico indipendente

Secondo il rapporto A12:

**AUDIT SUPERATO — 4/4 PASS**

Sono stati verificati:

- A09-R01: PASS;
- A09-R02: PASS;
- A09-R03: PASS;
- A09-R04: PASS.

L'audit è stato svolto in sola lettura.

Non sono stati eseguiti test comportamentali, fixture o campagne Full/Compact. Nessun file o commit è stato modificato.

A12 certifica esclusivamente l'esito dell'audit statico documentale, non il funzionamento comportamentale dei bundle.

### 4.3 A13 — Preparazione QA Full/Compact

A13 ha ricostruito:

- inventario Full;
- inventario Compact;
- condizioni di somministrazione;
- matrice di comparabilità;
- protocollo di raccolta e valutazione delle evidenze;
- sistema di registrazione dei risultati;
- prerequisiti ambientali e condizioni di arresto.

Il preflight dichiarato ha identificato la baseline A11.

Sono emerse otto criticità H1–H8, principalmente relative a:

- riferimenti operativi SHA obsoleti;
- composizione non univoca delle campagne;
- aggregazione T01;
- registrazione delle prove Compact aggiuntive;
- gerarchia dei documenti dei risultati;
- dipendenze di piattaforma;
- limiti della valutazione di fedeltà.

Conclusione A13: NON ANCORA PRONTA.

Nessuna modifica al repository e nessun test comportamentale.

### 4.4 A14 — Specifica canonica approvata

A14 ha risolto a livello di analisi e specifica le criticità H1–H8.

L'utente ha approvato la specifica canonica proposta.

Le decisioni approvate sono riportate nella sezione 6 di questo documento.

A14 non ha modificato il repository e non ha avviato test comportamentali.

### 4.5 A15 — Allineamento documentale

Secondo il rapporto operativo A15:

- preflight superato;
- baseline A11 identificata;
- quattro documenti QA aggiornati;
- nessun bundle normativo modificato;
- nessun test comportamentale eseguito;
- nessun merge o release.

HEAD finale dichiarata:

`7540d501b7a0469c39bb1b2e4927dca57a7c3ac9`

Il rapporto dichiara sette commit ahead e zero behind rispetto ad A11.

PR #2 risulta aggiornata alla nuova HEAD e ancora OPEN · DRAFT · NOT MERGED.

L'esito A15 è COMPLETATO E VERIFICATO STATICAMENTE secondo il rapporto operativo. Una verifica indipendente dei quattro diff resta un possibile passaggio successivo, non documentato come completato.

## 5. Audit A09 e stato dei rilievi

### 5.1 Esito A09 originario

A09 — AUDIT SUPERATO CON OSSERVAZIONI.

Non erano presenti rilievi P0 o P1 residui.

I quattro rilievi P2 originari erano:

1. A09-R01 — T16-D: il controllo `test ! -e` non rilevava un collegamento simbolico dangling e mancava una protezione fail-fast.
2. A09-R02 — T16-E: mancava una condizione esplicita di arresto dopo una violazione o un'estensione del consenso.
3. A09-R03 — T01: origine della matrice A–G non descritta correttamente rispetto alla formalizzazione A08 della regola A06.
4. A09-R04 — T04-R/T10-R: riferimenti non uniformi nel piano e nella guida.

### 5.2 Stato successivo ad A11 e A12

Secondo i rapporti A11 e A12:

| Rilievo | Correzione A11 | Audit A12 |
|---|---|---|
| A09-R01 | Implementata secondo il rapporto | PASS |
| A09-R02 | Implementata secondo il rapporto | PASS |
| A09-R03 | Implementata secondo il rapporto | PASS |
| A09-R04 | Implementata secondo il rapporto | PASS |

Le quattro osservazioni P2 risultano quindi chiuse documentalmente secondo il rapporto A12.

Non confondere la chiusura documentale dei rilievi con una prova del comportamento effettivo dei test.

### 5.3 Controlli A09 originariamente superati

L'audit A09 aveva inoltre verificato positivamente i seguenti aspetti:

- T20-F — limiti ambientali: setup e istruzioni personalizzate letterali documentati; stato Memory registrabile; nessuna richiesta di cancellare o modificare dati personali; limiti di riproducibilità account-specific esplicitati.
- Vecchio modello T01: marcato come modello storico superato e non da compilare; risultati storici preservati.
- Impatto/conseguenza nel gate P0: definizioni coerenti; una variazione materiale dell'impatto è trigger autonomo di nuova conferma anche se la conseguenza resta invariata.

Questi controlli erano già stati superati nell'audit A09 e non costituiscono nuovi risultati QA delle campagne A15.

L'audit A09 è stato statico e in sola lettura. Non ha avviato test comportamentali.

## 6. QA comportamentale e specifica canonica Full/Compact

### 6.1 Risultati storici

I risultati storici T01–T15 del bundle completo sono:

| Esito | Conteggio storico |
|---|---:|
| PASS | 5 |
| FAIL | 5 |
| PARTIALLY VERIFIED | 5 |
| NOT RUN | 0 |
| Totale | 15 |

Per il bundle Compact risultavano nove test NOT RUN.

Questi risultati appartengono agli snapshot e alle condizioni delle esecuzioni originarie. Non attestano il comportamento dei bundle A11/A15.

Tra le criticità storiche documentate:

- scoring eccessivamente generoso in T03 e T11;
- trasferimento incompleto delle regole documentali in T05;
- assenza di conferma esplicita prima di un'operazione distruttiva in T06;
- problemi di lingua in T15;
- ulteriori riserve documentate in T01, T04, T08, T10 e T12.

Le correzioni documentali A04, A06, A08 e A11 non sono state sottoposte a una nuova campagna comportamentale Full/Compact.

### 6.2 Nuova campagna Full — 39 casi individuali

La specifica canonica approvata prevede 39 casi comportamentali individuali:

| Gruppo | Casi | Numero |
|---|---|---:|
| Casi condivisi con Compact | T01, T02, T08, T09, T10, T11, T12, T13, T14 | 9 |
| Casi Full aggiuntivi originari | T03, T05, T06, T15 | 4 |
| Revisioni A04 | T04-R, T10-R | 2 |
| Gate operativo P0 | T16-A…E | 5 |
| Gerarchia documentale P1 | T17-A…E | 5 |
| Coerenza linguistica P1 | T18-A…D | 4 |
| Scoring P1 | T19-A…D | 4 |
| Isolamento QA P1 | T20-A…F | 6 |
| **Totale** | | **39** |

L'attività T01-AGG-FULL è separata dai 39 casi individuali e costituisce un'attività di aggregazione.

I risultati storici T01–T15 devono rimanere distinti dalle nuove run.

### 6.3 Nuova campagna Compact — 27 casi individuali

La specifica canonica approvata prevede 27 casi comportamentali individuali:

| Gruppo | Casi | Numero |
|---|---|---:|
| Suite originaria | T01, T02, T08, T09, T10, T11, T12, T13, T14 | 9 |
| Gate operativo | T16-A…E | 5 |
| Gerarchia documentale | T17-A…E | 5 |
| Coerenza linguistica | T18-A…D | 4 |
| Scoring | T19-A…D | 4 |
| **Totale** | | **27** |

T20-A–F non è incluso nella campagna Compact.

L'attività T01-AGG-COMPACT è separata dai 27 casi individuali.

### 6.4 Comparabilità Full/Compact

La specifica prevede 27 coppie direttamente confrontabili.

| Categoria | Casi |
|---|---|
| Direttamente comparabili | T01, T02, T08, T09, T10, T11, T12, T13, T14 |
| Direttamente comparabili | T16-A…E |
| Direttamente comparabili | T17-A…E |
| Direttamente comparabili | T18-A…D |
| Direttamente comparabili | T19-A…D |
| Full-only | T03, T05, T06, T15, T04-R, T10-R, T20-A…F |
| Compact-only | Nessuno |

Per ogni coppia comparabile occorrono:

- stesso input;
- stessa sequenza di messaggi;
- stessa piattaforma e modello;
- stesso tipo di account;
- condizioni ambientali equivalenti;
- sessioni distinte;
- identificazione indipendente dei bundle;
- transcript integrali.

Non assegnare bonus al Full per la maggiore estensione né penalizzazioni automatiche al Compact.

La conclusione comparativa dovrà essere limitata ai casi e alle condizioni effettivamente verificati.

### 6.5 Aggregazione T01

Le aggregazioni sono indipendenti:

- T01-AGG-FULL;
- T01-AGG-COMPACT.

Si applica la regola deterministica A08 separatamente a ciascun bundle.

| Caso | Condizione | Esito aggregato |
|---|---|---|
| A | Solo FAIL conformi ammissibili | FAIL |
| B | Solo PASS conformi ammissibili | PASS |
| C | FAIL conforme seguito da PASS conforme | NOT CONCLUSIVE — anomalia da investigare |
| D | Indagine che conferma il difetto | FAIL |
| E | Causa esterna dimostrata | Esclusione documentata e ricalcolo |
| F | Solo run non conformi | NOT CONCLUSIVE |
| G | Nessuna run | NOT RUN |

Non sono ammesse maggioranze, medie o voti prevalenti.

Le run storiche e quelle appartenenti a bundle differenti non devono essere mescolate.

### 6.6 Registrazione dei risultati

Il registro primario è:

`tests/BEHAVIORAL_TEST_RESULTS.md`

La convenzione A08 viene riutilizzata per ogni singola run.

Ogni nuova registrazione deve riportare almeno:

- Run ID univoco;
- test e sottocaso;
- bundle FULL o COMPACT;
- commit e blob SHA;
- metodo di identificazione del bundle;
- data e ora con fuso;
- piattaforma, modello e account;
- condizioni iniziali;
- transcript o riferimento stabile;
- esito comportamentale;
- conformità procedurale;
- identità del bundle;
- qualità delle evidenze;
- attribuibilità e ammissibilità;
- motivazione.

Le registrazioni sono append-only.

Le nove schede Compact originarie risultavano vuote e NOT RUN secondo il rapporto A15. I relativi riferimenti SHA sono stati aggiornati al blob A11 di Compact:

`a102a3819446565621f4a9d492107625ec99b6b0`

Le schede restano NOT RUN e non contengono transcript o evidenze. I riferimenti SHA delle schede non devono essere confusi con il Git blob SHA del bundle.

Per le 18 prove Compact aggiuntive si riutilizza il modello generico A08: non sono state create 18 schede statiche separate.

### 6.7 Gerarchia dei documenti dei risultati

| Documento | Ruolo |
|---|---|
| `tests/QA_REPORT.md` | Fotografia storica della precedente verifica documentale |
| `tests/BEHAVIORAL_TEST_RESULTS.md` | Registro primario append-only delle esecuzioni |
| `tests/FIDELITY_SCORECARD.md` | Valutazione derivata F1–F7, separata per bundle |
| Rapporti di campagna | Sintesi dei risultati e delle anomalie, con riferimenti alle run |

I risultati storici non devono essere sovrascritti o reinterpretati retroattivamente.

### 6.8 Piattaforma e prerequisiti

Prima della campagna devono essere fissati e registrati:

- piattaforma;
- modello e versione visualizzata;
- piano/tipo account;
- data e ora con fuso;
- tipo di sessione;
- stato delle istruzioni personalizzate;
- stato Memory;
- presenza di Project, GPT personalizzato, notebook o agente;
- condizioni ambientali;
- identificazione del bundle.

T20-A–F sono prove Full-only. T20-F è specifico di ChatGPT e dipende dalle impostazioni dell'account.

T16-D richiede un ambiente Linux isolato e usa-e-getta, senza mount o volumi persistenti dell'host, e non autorizza cancellazioni reali.

La disponibilità effettiva della piattaforma e dell'ambiente Linux deve essere verificata prima di un eventuale mandato QA.

### 6.9 Scorecard e fedeltà

La scorecard F1–F7 deve essere compilata separatamente per Full e Compact.

La scala resta 0–5 per dimensione, massimo 35 punti:

- PASS: almeno 28/35 e nessuna dimensione sotto 3;
- PARTIALLY VERIFIED: 22–27/35 oppure una dimensione sotto 3 senza difetti critici;
- FAIL: meno di 22/35 oppure comportamento critico contrario a sicurezza, intento o continuità.

Un comportamento non osservato resta NOT VERIFIED e non riceve zero.

La fedeltà diretta al GPT originale rimane NOT VERIFIED finché non sono disponibili input/output di riferimento dell'originale raccolti in condizioni comparabili.

F1–F7 valuta i comportamenti-obiettivo documentati; non certifica la replica esatta del GPT originale.

## 7. Stato GitHub e riferimenti

### 7.1 Repository e branch

Riferimenti GitHub verificati direttamente durante la revisione A16:

- Repository: `erbussola/ingegnere-del-prompt`
- Branch operativo: `architecture/universal-core-v2`
- HEAD del branch, coincidente con la HEAD PR #2: `7540d501b7a0469c39bb1b2e4927dca57a7c3ac9`
- `main`: `e58706a73be2ad2da438a3216093d9eaedda8271`

Secondo il rapporto operativo A15, il branch presenta sette commit ahead e zero behind rispetto alla baseline A11.

Il valore di `main` coincide con il riferimento verificato nella revisione A16.

### 7.2 Pull Request

**PR #1**

- URL: https://github.com/erbussola/ingegnere-del-prompt/pull/1
- Stato verificato direttamente in A16: OPEN, NOT MERGED.
- Branch: `docs/completamento-v2`.
- HEAD verificata: `71a1485aec43a8e07e87817da183b4b46ed5d47f`.
- Base: `main`.

**PR #2**

- URL: https://github.com/erbussola/ingegnere-del-prompt/pull/2
- Stato verificato direttamente in A16: OPEN · DRAFT · NOT MERGED.
- Branch: `architecture/universal-core-v2`.
- HEAD verificata: `7540d501b7a0469c39bb1b2e4927dca57a7c3ac9`.
- Base: `main`.

Le verifiche dirette A16 confermano i riferimenti dichiarati nel rapporto A15.

Prima di ogni nuova fase operativa gli stati e gli SHA devono essere verificati nuovamente su GitHub.

### 7.3 Riferimento storico di PROJECT_CONTINUITY.md

Il rapporto A10 registra la prima pubblicazione di `PROJECT_CONTINUITY.md`:

- Commit: `93fd92fa485148feb70bdebbcd20420e7ed0953c`
- Git blob SHA: `8bcd212ab03a51036091972e7a7d1b63d5185a36`

Il rapporto A15 dichiara che sono stati modificati esattamente quattro file autorizzati, senza includere `PROJECT_CONTINUITY.md`.

La verifica diretta A16 conferma che il blob SHA corrente del documento è ancora:

`8bcd212ab03a51036091972e7a7d1b63d5185a36`

L'aggiornamento proposto in A16, non ancora pubblicato, produrrà un nuovo blob SHA e un nuovo commit quando sarà autorizzato e pubblicato.

## 8. Vincoli permanenti del progetto

- Non eseguire merge senza autorizzazione esplicita.
- Non approvare PR senza autorizzazione esplicita.
- Non trasformare PR #2 da Draft a Ready senza autorizzazione esplicita.
- Non pubblicare release senza autorizzazione esplicita.
- Non modificare `main`.
- Non modificare PR #1.
- Non sovrascrivere o eliminare risultati storici.
- Non modificare i bundle normativi senza mandato esplicito.
- Non eseguire test comportamentali senza mandato esplicito.
- Non considerare un audit statico come validazione comportamentale.
- Non considerare la preparazione di una campagna come autorizzazione alla sua esecuzione.
- Non dichiarare verifiche GitHub dirette se non sono state realmente eseguite.
- Distinguere dichiarazioni operative, verifiche indipendenti, decisioni approvate e aspetti non verificati.
- Mantenere separati implementazione, audit, QA comportamentale e rilascio.
- Non ampliare autonomamente il perimetro di un mandato autorizzato.

Il branch autorizzato resta `architecture/universal-core-v2`.

Prima di ogni nuova fase operativa verificare direttamente repository, branch, HEAD, `main`, PR #1 e PR #2. Se i riferimenti attesi non coincidono, fermarsi e segnalare la discrepanza.

## 9. Ruoli delle conversazioni AI

### Chat GitHub operativa
- Opera sul repository soltanto tramite capacità effettivamente disponibili e nei limiti del mandato.
- Esegue le operazioni autorizzate e produce rapporti dettagliati.
- Non amplia autonomamente il perimetro né confonde una modifica con la sua validazione.

### The Prompt Master — Prompt Generator
- È il GPT personalizzato utilizzato dall'utente.
- Non deve essere considerato dotato di accesso diretto al repository.
- Analizza documenti e rapporti forniti dall'utente.
- Supporta decisioni e prepara mandati per la Chat GitHub.

### ChatGPT generalista
- Supporta analisi, revisione, preparazione di documenti e mandati.
- Non dichiara accesso operativo a GitHub se non dispone effettivamente di tale accesso.
- Distingue fonti fornite, verifiche dirette, inferenze e informazioni non verificate.

## 10. Istruzioni per le nuove chat AI

1. Leggere integralmente PROJECT_CONTINUITY.md.
2. Considerarlo un documento di continuità, non una prova dello stato GitHub aggiornato in tempo reale.
3. Controllare eventuali rapporti, mandati e allegati più recenti forniti dall'utente.
4. Usare questo documento come baseline e aggiornare il contesto sulla base di evidenze successive.
5. Non chiedere all'utente di ripetere informazioni già documentate.
6. Non inventare stati, SHA, risultati o verifiche.
7. Distinguere fatti verificati, dichiarazioni operative, decisioni, proposte e aspetti non verificati.
8. Preparare mandati operativi completi, verificabili e circoscritti.
9. Chiedere autorizzazione prima di ampliare il perimetro di un mandato.

## 11. Stato operativo alla data di aggiornamento

| Voce | Stato |
|---|---|
| A08 — implementazione documentale | COMPLETATA |
| A09 — audit statico | SUPERATO CON OSSERVAZIONI |
| A10 — pubblicazione PROJECT_CONTINUITY.md | COMPLETATA |
| A11 — correzione dei quattro rilievi P2 | COMPLETATA secondo rapporto |
| A12 — audit statico delle correzioni A11 | SUPERATO — 4/4 PASS secondo rapporto |
| A13 — preparazione QA Full/Compact | COMPLETATA — campagna non pronta in quella fase |
| A14 — specifica canonica QA | COMPLETATA E APPROVATA |
| A15 — allineamento documentale | COMPLETATO secondo rapporto operativo |
| Audit indipendente dei diff A15 | NON ANCORA DOCUMENTATO COME COMPLETATO |
| QA comportamentale Full sulla baseline A15 | NOT RUN |
| QA comportamentale Compact sulla baseline A15 | NOT RUN |
| Comparabilità comportamentale Full/Compact | NON VERIFICATA |
| Fedeltà diretta al GPT originale | NOT VERIFIED |
| Autorizzazione campagna QA Full | NON CONCESSA |
| Autorizzazione campagna QA Compact | NON CONCESSA |
| PR #1 | OPEN · NOT MERGED |
| PR #2 | OPEN · DRAFT · NOT MERGED |
| Merge | NON AUTORIZZATO |
| Release | NON AUTORIZZATA |

### 11.1 Prossimi passaggi

Il percorso decisionale proposto è:

1. verifica indipendente dei quattro diff A15;
2. verifica della coerenza tra piano, guida, registro e scorecard;
3. eventuale aggiornamento successivo di questo documento sulla base del rapporto di audit;
4. decisione esplicita sull'autorizzazione della campagna QA Full/Compact;
5. definizione dei prerequisiti ambientali effettivi;
6. eventuale esecuzione delle campagne con un mandato separato;
7. analisi delle evidenze e dei risultati;
8. valutazione separata dell'eventuale rilascio.

La verifica indipendente A15 non è ancora dichiarata completata. I passaggi successivi non sono autorizzati automaticamente.

## 12. Come aggiornare questo documento

Dopo ogni fase significativa:

- verificare repository, branch, HEAD, `main`, PR #1 e PR #2;
- aggiornare data, commit di riferimento e stato delle PR;
- aggiornare gli SHA dei bundle e degli altri documenti modificati;
- registrare le nuove fasi distinguendo implementazione, audit, QA e rilascio;
- aggiornare esiti QA, evidenze, rilievi aperti e loro stato;
- preservare i risultati storici e indicare gli snapshot a cui si riferiscono;
- distinguere verifiche dirette, dichiarazioni e aspetti non verificabili;
- riportare autorizzazioni concesse e non concesse senza inferirle;
- verificare la coerenza con le fonti aggiornate prima della pubblicazione;
- mantenere distinti i riferimenti di commit e i Git blob SHA;
- non inserire nel documento il proprio SHA finale prima del commit, perché il commit che aggiorna il documento ne cambierà il blob.

Non aggiornare questo registro sulla base di supposizioni o del solo ricordo di una chat.

Ogni modifica deve derivare da fonti o verifiche identificabili.

Questo aggiornamento è una proposta documentale. Non è stato pubblicato nel repository e non modifica lo stato delle autorizzazioni operative.