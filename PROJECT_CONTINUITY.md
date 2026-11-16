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

## 3. Architettura documentale e SHA storici

| Area | Percorsi e ruolo |
|---|---|
| Istruzioni normative e moduli Core | core/, instructions/ — fonte normativa e bundle distribuibili |
| Documentazione generale | README.md, docs/ — orientamento, architettura, brief, guide, FAQ e troubleshooting |
| Deployment | deployment/ — adattamenti e istruzioni per piattaforme |
| Framework | framework/ — RICCE, valutazione, checklist e continuità |
| Test e validazione | tests/ — casi, piano, guida, scorecard e risultati |
| Risultati storici | tests/QA_REPORT.md, tests/BEHAVIORAL_TEST_RESULTS.md, tests/FIDELITY_SCORECARD.md |
| Procedure operative | docs/RELEASE_CHECKLIST.md, docs/RECOVERY_FROM_PR1.md e .github/ |

Gli SHA seguenti sono Git blob SHA verificati al riferimento A08/A09. Sono riferimenti storici e vanno aggiornati dopo modifiche successive:

| File | Git blob SHA storico |
|---|---|
| instructions/CORE_INSTRUCTIONS.md | 06e809107d89333738aa96b758e81d1a94383cd3 |
| instructions/UNIVERSAL.md | 06e809107d89333738aa96b758e81d1a94383cd3 |
| instructions/COMPACT.md | a102a3819446565621f4a9d492107625ec99b6b0 |

Al riferimento verificato, Core e Universal erano identici byte per byte, come attestato dallo stesso Git blob SHA. Non è stata dimostrata l'equivalenza comportamentale di Compact rispetto al bundle completo: la validazione comparativa Full/Compact non è stata completata.

## 4. Cronologia delle fasi A01–A09

| Fase | Attività ed esito |
|---|---|
| **A01** | Analisi trasversale del QA iniziale e individuazione delle criticità. |
| **A02** | Progettazione delle correzioni. |
| **A03** | Revisione e approvazione delle specifiche di correzione, senza autorizzazione al rilascio. |
| **A04** | Implementazione delle correzioni sul branch autorizzato. |
| **A05** | Audit non superato; criticità nel gate operativo, scoring, lingua, T01 e riproducibilità dei test. |
| **A06** | Implementazione delle correzioni successive ad A05. |
| **A07** | Audit non superato; lacune nella fixture T16-D, nella condizione di arresto T16-E, nel setup T20-F e nella documentazione T01/T04/T10. |
| **A08** | Correzioni documentali delle criticità A07; implementazione completata. QA comportamentale non eseguito. |
| **A09** | Audit statico indipendente superato con osservazioni P2; nessuna modifica al repository durante l'audit. |

Riferimento Git verificato per A08 e utilizzato come baseline dell'audit A09: fb862b2e430263f0a6f8dfff3e193b8b750ab64b.

Il completamento di un'implementazione non equivale a validazione comportamentale, approvazione o autorizzazione al rilascio.

## 5. Audit A09 e rilievi residui

**A09 — AUDIT SUPERATO CON OSSERVAZIONI.** Non sono rimasti rilievi P0 o P1. Quattro rilievi P2 non risultavano ancora implementati:

1. **A09-R01 — T16-D, fixture:** il controllo test ! -e non rileva un collegamento simbolico dangling e manca una protezione fail-fast. Correzione proposta: set -eu e controllo del percorso sia con -e sia con -L.
2. **A09-R02 — T16-E, consenso:** manca una condizione di arresto esplicita dopo il consenso iniziale se viene rilevata un'esecuzione non autorizzata o un'estensione del consenso ad altre risorse. Correzione proposta: interrompere, registrare FAIL e non inviare il messaggio 3.
3. **A09-R03 — T01, matrice A–G:** descrivere la matrice come formalizzazione A08 dei casi derivati dalla regola deterministica A06, non come denominazione già presente nel testo A06.
4. **A09-R04 — T04-R/T10-R:** restano riferimenti non uniformi nel piano e nella guida. Uniformare identificativi, riferimenti descrittivi e lista Full.

Le correzioni richiedono un mandato successivo dedicato. Non sono incluse nell'implementazione A08 e non devono essere considerate già eseguite.

### 5.1 Controlli A09 superati

- **T20-F:** setup e istruzioni personalizzate letterali documentati; stato Memory registrabile; nessuna richiesta di cancellare o modificare dati personali; limiti di riproducibilità account-specific esplicitati.
- **Vecchio modello T01:** marcato come modello storico superato e non da compilare; risultati storici preservati.
- **Impatto/conseguenza nel gate P0:** definizioni coerenti; una variazione materiale dell'impatto è trigger autonomo di nuova conferma anche se la conseguenza resta invariata.

L'audit A09 è stato statico e in sola lettura. Non ha avviato test comportamentali.

## 6. Stato del QA comportamentale

### 6.1 Risultati storici del bundle completo

I risultati storici T01–T15 del bundle completo, come riportati nel mandato A10 e nella documentazione QA:

| Esito | Conteggio storico |
|---|---:|
| PASS | 5 |
| FAIL | 5 |
| PARTIALLY VERIFIED | 5 |
| NOT RUN | 0 |
| **Totale** | **15** |

Per il bundle Compact risultavano **nove test NOT RUN**.

Sono risultati storici: non costituiscono una nuova campagna e non attestano il comportamento dell'attuale snapshot A08. Tra le criticità storiche documentate:
- scoring eccessivamente generoso in T03 e T11;
- trasferimento incompleto delle regole documentali in T05;
- assenza di conferma esplicita prima di un'operazione distruttiva in T06;
- problemi di lingua in T15;
- ulteriori riserve documentate in T01, T04, T08, T10 e T12.

Le correzioni A04, A06 e A08 non sono state sottoposte a una nuova campagna comportamentale Full/Compact. I risultati storici non provano il comportamento delle versioni corrette.

## 7. Stato GitHub e riferimenti verificati

Verifiche GitHub dirette eseguite il 16 novembre 2026 prima della creazione del presente documento:

- Repository: erbussola/ingegnere-del-prompt
- Branch di lavoro: architecture/universal-core-v2
- HEAD pre-creazione: fb862b2e430263f0a6f8dfff3e193b8b750ab64b
- main: e58706a73be2ad2da438a3216093d9eaedda8271

**PR #1**
- URL: https://github.com/erbussola/ingegnere-del-prompt/pull/1
- Stato verificato: OPEN, NOT MERGED.
- HEAD: 71a1485aec43a8e07e87817da183b4b46ed5d47f.

**PR #2**
- URL: https://github.com/erbussola/ingegnere-del-prompt/pull/2
- Stato verificato prima della creazione: OPEN · DRAFT · NOT MERGED.
- Branch: architecture/universal-core-v2.
- HEAD A08/A09: fb862b2e430263f0a6f8dfff3e193b8b750ab64b.
- Base: main.

La creazione di questo documento aggiunge un commit al branch e aggiorna la HEAD della PR #2. Il nuovo commit e la nuova HEAD devono essere letti dai metadati GitHub e registrati nel rapporto conclusivo. main e PR #1 non devono essere modificati.

## 8. Vincoli permanenti del progetto

- Non eseguire merge senza autorizzazione esplicita.
- Non approvare PR senza autorizzazione esplicita.
- Non trasformare PR #2 da Draft a Ready senza autorizzazione esplicita.
- Non pubblicare release senza autorizzazione esplicita.
- Non modificare main.
- Non modificare PR #1.
- Non sovrascrivere o eliminare risultati storici.
- Non dichiarare verifiche GitHub dirette se non sono state realmente eseguite.
- Distinguere dichiarazioni di una chat operativa da verifiche indipendenti.
- Non eseguire test comportamentali senza mandato esplicito.
- Mantenere separati implementazione, audit, QA comportamentale e rilascio.
- Non ampliare autonomamente il perimetro di un mandato autorizzato.

Il branch autorizzato è architecture/universal-core-v2. Prima di ogni nuova fase operativa verificare direttamente repository, branch, HEAD, main, PR #1 e PR #2. Se i riferimenti attesi non coincidono, fermarsi e segnalare la discrepanza.

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
| A08 — implementazione documentale | **COMPLETATA** |
| A09 — audit statico | **SUPERATO CON OSSERVAZIONI** |
| QA comportamentale Full dopo le correzioni A04/A06/A08 | **NOT RUN** |
| QA comportamentale Compact dopo le correzioni A04/A06/A08 | **NOT RUN** |
| Conformità procedurale | **NON ANCORA VALUTATA** |
| Autorizzazione campagna QA | **NON CONCESSA** |
| Autorizzazione rilascio | **NOT AUTHORIZED** |
| PR #2 | **OPEN · DRAFT · NOT MERGED** |

Il percorso decisionale successivo, non ancora autorizzato, prevede:

1. eventuale correzione delle osservazioni A09 mediante mandato dedicato;
2. eventuale audit delle correzioni;
3. decisione esplicita sull'avvio della campagna QA Full e Compact;
4. analisi dei risultati;
5. valutazione separata dell'eventuale rilascio.

Nessuno di questi passaggi è autorizzato dal presente documento.

## 12. Come aggiornare questo documento

Dopo ogni fase significativa:
- verificare repository, branch, HEAD, main, PR #1 e PR #2;
- aggiornare data, commit di riferimento e stato delle PR;
- aggiornare gli SHA dei bundle e degli altri documenti modificati;
- registrare le nuove fasi distinguendo implementazione, audit, QA e rilascio;
- aggiornare esiti QA, evidenze, rilievi aperti e loro stato;
- preservare i risultati storici e indicare gli snapshot a cui si riferiscono;
- distinguere verifiche dirette, dichiarazioni e aspetti non verificabili;
- riportare autorizzazioni concesse e non concesse senza inferirle;
- verificare la coerenza con le fonti aggiornate prima della pubblicazione.

Non aggiornare questo registro sulla base di supposizioni o del solo ricordo di una chat. Ogni modifica deve derivare da fonti o verifiche identificabili.
