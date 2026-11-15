# Behavioral Validation Plan — Ingegnere del Prompt 2.0

**Versione:** 1.0  
**Data preparazione:** 15 novembre 2026  
**Branch:** `architecture/universal-core-v2`  
**PR:** [#2 — Universal Core 2.0](https://github.com/erbussola/ingegnere-del-prompt/pull/2)  
**Commit sottoposto alla QA precedente:** `c27935069a2961ad6bf6fd7f16bc18ef52136871`  
**HEAD rilevato all'avvio di questa fase:** `85050807cb19f68c30aca484060c316b750ece06`

> Questo documento prepara l'esecuzione. Non contiene risultati di test comportamentali e non autorizza a dichiarare conclusa la validazione.

## 1. Obiettivo della campagna

Dimostrare, attraverso transcript reali e riproducibili, che il Core universale produce i comportamenti descritti nei casi T01–T15. Misurare separatamente il bundle completo e il bundle compatto e documentare le differenze osservate.

La campagna non modifica il prodotto durante la raccolta delle evidenze. I difetti vengono registrati e classificati; le correzioni sono rinviate a una fase successiva.

## 2. Stato iniziale verificato

| Elemento | Evidenza / stato |
|---|---|
| Repository | `erbussola/ingegnere-del-prompt` |
| Branch | `architecture/universal-core-v2` — presente |
| PR #2 | individuata; URL e titolo verificati |
| Base | `main` |
| Commit precedente sottoposto alla QA | `c27935069a2961ad6bf6fd7f16bc18ef52136871` |
| HEAD al controllo | `85050807cb19f68c30aca484060c316b750ece06` |
| Confronto branch/main | 51 commit ahead, 0 behind |
| File nel confronto | 58 modificati, nessuna eliminazione rilevata |
| Suite | 15 casi presenti in `tests/TEST_CASES.md` |
| Rubrica | 7 dimensioni, scala 0–5, massimo 35 punti |
| Esecuzione T01–T15 | NOT RUN secondo la QA precedente |
| Status check sul commit HEAD | nessuno restituito dall'API consultata |
| Workflow run associati al commit HEAD | nessuno restituito dall'API consultata |
| Mergeability / conflitti PR | NOT VERIFIED: il connettore disponibile non ha esposto il dettaglio PR aggiornato |

Lo SHA del commit precedente è stato ricavato confrontando il commit che aggiunge `tests/QA_REPORT.md` con il suo genitore. Il genitore è `c27935069a2961ad6bf6fd7f16bc18ef52136871`, messaggio: “Align PR1 recovery note with current 15-case test suite”. L'HEAD corrente rilevato è il commit che aggiunge il rapporto QA.

La verifica dello stato amministrativo della PR è limitata ai dati effettivamente restituiti: la PR #2 è stata individuata e non risultano review registrate; stato OPEN/DRAFT, mergeability e conflitti devono essere ricontrollati nella pagina GitHub prima di qualsiasi operazione di merge. Nessuna operazione di merge o approvazione è stata eseguita in questa fase.

## 3. Ambito e vincoli

### Incluso
- Bundle completo: `instructions/CORE_INSTRUCTIONS.md`, test T01–T15.
- Bundle compatto: `instructions/COMPACT.md`, almeno T01, T02, T08, T09, T10, T11, T12, T13 e T14.
- Rubrica F1–F7, compilata solo con evidenze dei transcript.
- Confronto descrittivo completo/compatto sullo stesso ambiente.

### Escluso
- Modifiche ai moduli `core/`.
- Modifiche a `instructions/CORE_INSTRUCTIONS.md`, `instructions/UNIVERSAL.md` o `instructions/COMPACT.md`.
- Modifiche a RICCE, modalità A/B/C o comportamento del prodotto.
- Modifiche a `main`, merge, approvazioni o interventi sulla PR #1.
- Dichiarazioni di equivalenza tra bundle senza risultati comparativi.

## 4. Prerequisiti

Prima di iniziare, il responsabile deve disporre di:
1. accesso autorizzato al repository e alla PR #2;
2. accesso a una piattaforma conversazionale sulla quale installare il bundle;
3. disponibilità dei due file bundle sul commit identificato;
4. possibilità di aprire conversazioni nuove e copiare integralmente i transcript;
5. un archivio locale autorizzato in cui conservare le evidenze.

Registrare piattaforma, modello effettivamente visualizzato, piano/tipo account se noto, data e impostazioni rilevanti. Non inserire password, token, chiavi API, codici MFA o dati aziendali riservati nei transcript.

## 5. Regole di esecuzione

- Ogni test è una prova autonoma: aprire una nuova conversazione per ogni ID e per ogni bundle.
- Caricare soltanto il bundle oggetto della prova. Non caricare contemporaneamente Core, UNIVERSAL, COMPACT, brief, report QA o altre istruzioni di progetto.
- Non fornire al modello criteri di valutazione, comportamento atteso o indicazioni su come superare il test.
- Copiare gli input esattamente da `tests/TEST_CASES.md`, senza prefazioni.
- Non correggere, guidare o suggerire la risposta durante il test.
- Per T10 e T13, i messaggi indicati come successivi vanno inviati nella stessa conversazione del test; non aprire una nuova chat tra i turni.
- Non interrompere una risposta per renderla conforme. Registrare l'output integrale, compresi eventuali errori.
- Se la piattaforma rifiuta il bundle, registrare il limite e non sostituire il contenuto con una versione modificata.
- Non attribuire PASS a una prova priva di transcript verificabile.

## 6. Procedura per sessioni pulite

1. Aprire una nuova conversazione standard, non una chat già esistente.
2. Verificare che non sia attivo un progetto, GPT personalizzato, notebook, agente o contesto con istruzioni aggiuntive.
3. Non richiamare conversazioni precedenti e non fornire memoria di progetto.
4. Copiare il contenuto integrale del bundle scelto dal branch/commit registrato.
5. Inviare il bundle come primo messaggio, secondo le istruzioni del file.
6. Attendere la risposta di acquisizione, se presente. Non aggiungere richieste di conferma non previste dal bundle.
7. Inviare l'input del caso esattamente come definito.
8. Per T10/T13 inviare i turni successivi nello stesso ordine e nella stessa chat.
9. Copiare il transcript completo in un file di evidenza e compilare la scheda corrispondente in `BEHAVIORAL_TEST_RESULTS.md`.
10. Chiudere la conversazione. Il test successivo parte da una nuova chat.

La sola apertura di una nuova chat dentro un progetto o un ambiente con istruzioni persistenti non è sufficiente a qualificare la sessione come pulita.

## 7. Percorso A — Bundle completo

File: `instructions/CORE_INSTRUCTIONS.md`

Eseguire tutti i 15 test, in 15 sessioni pulite indipendenti, salvo i turni multipli previsti all'interno di T10 e T13.

| Test | Nome sintetico | Sessione |
|---|---|---|
| T01 | Creazione semplice | nuova chat |
| T02 | Ottimizzazione incompleta | nuova chat |
| T03 | Prompt già strutturato | nuova chat |
| T04 | Marketing | nuova chat |
| T05 | Analisi documentale | nuova chat |
| T06 | Programmazione | nuova chat |
| T07 | Generazione immagini | nuova chat |
| T08 | Progettazione assistente | nuova chat |
| T09 | Richiesta ambigua | nuova chat |
| T10 | Iterazione | una chat, due messaggi utente |
| T11 | Cinque suggerimenti e valutazione | nuova chat |
| T12 | Privacy e segreti | nuova chat |
| T13 | Dialogo progressivo | una chat, tre messaggi utente |
| T14 | Qualità dei cinque suggerimenti | nuova chat |
| T15 | Lingua e indipendenza dal settore | nuova chat |

Per ciascun caso utilizzare input, comportamento atteso, criteri ed errori da evitare già presenti in `tests/TEST_CASES.md`. Non sostituire né ridurre i casi.

## 8. Percorso B — Bundle compatto

File: `instructions/COMPACT.md`

Ripetere in sessioni pulite indipendenti i seguenti nove casi, usando gli stessi input e la stessa sequenza di messaggi del percorso A:

- T01 — Creazione semplice
- T02 — Ottimizzazione incompleta
- T08 — Progettazione assistente
- T09 — Richiesta ambigua
- T10 — Iterazione
- T11 — Cinque suggerimenti e valutazione
- T12 — Privacy e segreti
- T13 — Dialogo progressivo
- T14 — Qualità dei cinque suggerimenti

Non trasferire il transcript del bundle completo nella sessione compatta. Non riutilizzare la stessa conversazione. Registrare separatamente ogni risultato.

## 9. Criteri di superamento e fallimento

Usare esclusivamente questi stati:
- **PASS** — tutti i criteri essenziali del caso sono soddisfatti e il transcript è disponibile.
- **FAIL** — il comportamento osservato viola un criterio essenziale o introduce un errore critico.
- **PARTIALLY VERIFIED** — alcuni criteri sono dimostrati, ma un limite concreto impedisce di concludere il caso.
- **NOT RUN** — il caso non è stato eseguito.
- **NOT VERIFIED** — mancano evidenze sufficienti o non è possibile verificare un requisito specifico.

Un test è PASS solo se:
1. la sessione rispetta i requisiti di isolamento;
2. il bundle e l'input usati sono identificabili;
3. il transcript è integrale o conservato in un riferimento stabile;
4. tutti i criteri essenziali del caso sono soddisfatti;
5. non si rilevano errori critici.

Un test non eseguito non può essere PASS. Un test simulato o una revisione statica non è un test comportamentale reale. Se un transcript è parziale, segnare NOT VERIFIED o PARTIALLY VERIFIED secondo ciò che è dimostrabile.

## 10. Raccolta e conservazione delle evidenze

Usare un nome file uniforme:

`BV2_<bundle>_<test-id>_<platform>_<YYYYMMDD>_<run>.md`

Esempio puramente convenzionale: `BV2_FULL_T01_ChatGPT_20261115_01.md`.

Ogni transcript deve riportare:
- ID test e bundle;
- commit/SHA del bundle;
- piattaforma e modello;
- piano/tipo account, se disponibile;
- data e ora con fuso;
- conferma che la chat è nuova e priva di istruzioni aggiuntive;
- bundle caricato (nome e SHA del file, se calcolabile);
- input esatto;
- output integrale dell'assistente;
- eventuali turni successivi;
- note su anomalie o limiti della piattaforma.

Non modificare il testo del transcript. Eventuali oscuramenti di dati personali o segreti vanno indicati e applicati a una copia destinata alla condivisione; conservare l'originale solo se autorizzato e necessario.

## 11. Gestione delle anomalie

Per ogni anomalia:
1. assegnare un identificativo, ad esempio `BV2-DEF-001`;
2. citare il test, bundle e punto del transcript;
3. descrivere il comportamento effettivo senza interpretazioni non dimostrate;
4. indicare il criterio atteso violato;
5. classificare impatto e riproducibilità;
6. conservare il transcript;
7. non modificare il Core durante la campagna.

Non correggere il prompt di test, non aggiungere istruzioni compensative e non ripetere il caso con input alterato per ottenere un PASS. Un'eventuale ripetizione identica va registrata come run aggiuntiva, senza sovrascrivere la prima evidenza.

## 12. Confronto completo/compatto

Confrontare soltanto coppie di esecuzioni con:
- stesso test e identico input;
- stessa piattaforma e modello, per quanto possibile;
- stesso tipo di account;
- sessioni entrambe pulite;
- bundle identificati e transcript conservati.

Per ogni differenza annotare: comportamento presente nel completo, comportamento nel compatto, impatto pratico e criterio coinvolto. Non concludere equivalenza generale da un sottoinsieme di nove test: la conclusione riguarda esclusivamente i casi e l'ambiente effettivamente misurati.

## 13. Rubrica F1–F7

Compilare `tests/FIDELITY_SCORECARD.md` separatamente per ciascun bundle. La scala resta 0–5 per dimensione, totale massimo 35:
- PASS: almeno 28/35 e nessuna dimensione sotto 3.
- PARTIALLY VERIFIED: 22–27/35 oppure una dimensione sotto 3 senza difetti critici.
- FAIL: meno di 22/35 oppure comportamento critico contrario a sicurezza, intento o continuità.

Ogni voto deve citare un transcript e un'evidenza osservabile. In assenza di evidenze adeguate il punteggio resta **NOT VERIFIED**; non assegnare zero per il solo fatto che un test non è stato eseguito.

## 14. Condizioni per chiudere la campagna

La preparazione documentale è completata, ma la validazione comportamentale resta NOT RUN fino alla raccolta dei transcript.

La campagna potrà essere dichiarata conclusa soltanto quando:
1. T01–T15 del bundle completo hanno un esito e un'evidenza;
2. i nove test obbligatori del bundle compatto hanno un esito e un'evidenza;
3. le anomalie sono registrate e valutate;
4. F1–F7 sono valutati separatamente per i bundle con evidenze sufficienti;
5. il confronto completo/compatto è documentato senza generalizzazioni indebite;
6. i limiti di piattaforma e i casi NOT VERIFIED sono espliciti;
7. il rapporto finale distingue risultati empirici, limiti e aspetti non testati.

Il rilascio 2.0 resta NO-GO finché i difetti bloccanti non sono risolti e la valutazione finale non è supportata da evidenze. La PR #2 deve restare OPEN — DRAFT — NOT MERGED.


## 15. Verifica amministrativa conclusiva della preparazione

Dopo la creazione dei documenti, la PR #2 è stata interrogata nuovamente tramite GitHub:
- stato: **OPEN**;
- draft: **true**;
- merged: **false**;
- mergeable: **true**;
- head SHA restituito dalla PR al controllo: `af7b7944916d540646c8a0ed1a39f0b872d513f5` (prima dell'ultima correzione editoriale al registro risultati);
- nessuna review registrata.

La mergeability è quindi risultata **true** al momento del controllo: non risulta un blocco di merge segnalato da GitHub. Questo dato non equivale a un'approvazione né autorizza il merge. La PR resta draft.

Per CI sul commit HEAD rilevato dopo i documenti: l'API del combined status ha restituito una lista vuota di status e la ricerca delle workflow run associate al commit ha restituito una lista vuota. Interpretazione: **nessuno status check e nessuna workflow run visibili tramite gli endpoint consultati**; non è prova che non esistano workflow configurati o altri controlli non esposti da questi endpoint.

Il controllo di confronto tra HEAD iniziale della fase e branch aggiornato ha mostrato esclusivamente quattro file aggiunti sotto `tests/`, senza file eliminati o modificati. La correzione successiva del riferimento SHA nel registro risultati è una modifica ulteriore, sempre limitata a `tests/BEHAVIORAL_TEST_RESULTS.md`. Nessun file del Core o delle istruzioni è stato modificato.


### Aggiornamento dell'ultimo controllo PR

Una lettura successiva della PR, dopo l'aggiornamento della descrizione, ha restituito nuovamente:
- stato `open`;
- `draft: true`;
- `merged: false`;
- `mergeable: true`;
- head SHA: `ec961215198a4f947828457b6d48a1fdda3e631d`;
- base SHA: `e58706a73be2ad2da438a3216093d9eaedda8271`.

Tra due interrogazioni ravvicinate il campo `mergeable` ha restituito prima `false` e poi `true`. Il connettore non espone il campo diagnostico `mergeable_state` né un dettaglio dei conflitti: **non è quindi possibile attribuire una causa certa al valore transitorio false**. L'ultimo stato letto è true e non segnala un blocco di merge; la PR resta comunque draft e non deve essere unita in questa fase.

Il confronto finale tra l'HEAD iniziale `85050807cb19f68c30aca484060c316b750ece06` e il branch aggiornato mostra quattro soli file aggiunti, tutti sotto `tests/`, nessuna eliminazione e nessuna modifica ai file preesistenti. Il confronto branch/`main` indica 57 commit ahead e 0 behind. La PR espone 64 file complessivamente nel suo diff, relativi all'intera storia del branch rispetto a `main`, non soltanto a questa fase.


### Ultimo snapshot amministrativo (dopo l'aggiornamento delle schede compatte)

- PR #2: `state=open`, `draft=true`, `merged=false`.
- `mergeable=false` nell'ultimo snapshot GitHub disponibile.
- Head PR: `3664f7e6a57b11195386e47de52ad0c32960ea77`; base: `e58706a73be2ad2da438a3216093d9eaedda8271`.
- Confronto dal HEAD iniziale della fase: 8 commit aggiuntivi; il diff netto è composto esclusivamente dai quattro documenti di validazione sotto `tests/`, tutti aggiunti. Nessun file eliminato e nessun file preesistente modificato in questa fase.
- Status check e workflow run sul commit: liste vuote.

Il valore `mergeable=false` è un problema amministrativo ancora aperto. L'interfaccia disponibile non restituisce `mergeable_state`, motivazione o dettaglio dei conflitti. Il confronto Git mostra che `main` è antenato del branch (0 commit behind), ma questo dato da solo non sostituisce la diagnosi GitHub. Non dedurre né dichiarare una causa: il proprietario deve controllare la sezione “Checks” e lo stato della PR direttamente su GitHub. Non tentare merge, aggiornamento del branch o risoluzione automatica dei conflitti in questa fase.
