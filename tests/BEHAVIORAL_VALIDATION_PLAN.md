# Behavioral Validation Plan — Ingegnere del Prompt 2.0

**Versione:** 1.0  
**Data preparazione:** 15 novembre 2026  
**Branch:** `architecture/universal-core-v2`  
**PR:** [#2 — Universal Core 2.0](https://github.com/erbussola/ingegnere-del-prompt/pull/2)  
**Baseline del codice sottoposto alla QA:** `c27935069a2961ad6bf6fd7f16bc18ef52136871`  
**Commit di pubblicazione QA / HEAD iniziale Behavioral Validation:** `85050807cb19f68c30aca484060c316b750ece06`

> Questo documento prepara l'esecuzione. Non contiene risultati di test comportamentali e non autorizza a dichiarare conclusa la validazione.

## Cronologia e snapshot

| Riferimento | SHA completo | Significato |
|---|---|---|
| Baseline della QA documentale | `c27935069a2961ad6bf6fd7f16bc18ef52136871` | Snapshot del branch esaminato; è il commit immediatamente precedente alla pubblicazione del rapporto QA. |
| Pubblicazione di `tests/QA_REPORT.md` | `85050807cb19f68c30aca484060c316b750ece06` | Commit che ha aggiunto il rapporto QA; il confronto con la baseline mostra esclusivamente l'aggiunta di `tests/QA_REPORT.md`. |
| HEAD iniziale della fase Behavioral Validation | `85050807cb19f68c30aca484060c316b750ece06` | HEAD rilevato all'avvio della preparazione Behavioral Validation. Coincide con il commit di pubblicazione QA, ma rappresenta un riferimento temporale distinto. |
| HEAD operativo di riferimento per l'esecuzione | `84db964b5ec17ae6c203c125b95133c64b772e75` | Snapshot Git del branch verificato dopo il primo allineamento dei quattro documenti e prima della sola pubblicazione finale di questo riferimento. Usare questo SHA come baseline immutabile per il checkout dei bundle e dei test case. |
| Bundle CORE — Git blob SHA | `99f58c58bdbabecd6db9a331b1535dd1b1ea20f6` | SHA del contenuto di `instructions/CORE_INSTRUCTIONS.md`, verificato nuovamente. |
| Bundle COMPACT — Git blob SHA | `bc852ec4925e9c81a5689c16a166fd8fb46181aa` | SHA del contenuto di `instructions/COMPACT.md`, verificato nuovamente. |

**Distinzione degli snapshot:** la baseline QA identifica il codice esaminato; il commit successivo pubblica il rapporto; il medesimo commit era anche l'HEAD all'avvio della preparazione Behavioral Validation. Il commit `84db964b5ec17ae6c203c125b95133c64b772e75` è lo snapshot operativo fissato per la campagna. Il commit finale di pubblicazione dell'allineamento aggiorna esclusivamente i quattro documenti di validazione per registrare questo riferimento; non cambia i bundle né i test case. Gli SHA dei bundle identificano i contenuti dei file, non commit Git.

**Istruzione operativa:** eseguire il checkout di `84db964b5ec17ae6c203c125b95133c64b772e75` per avviare la campagna; verificare che i Git blob SHA di CORE e COMPACT corrispondano ai valori riportati sopra. Il branch corrente conterrà anche la pubblicazione finale dei riferimenti, ma il contenuto dei bundle e degli input resta identico allo snapshot operativo.

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

L'identificazione del bundle richiesta al punto 2 può essere supportata dal Metodo A (confronto hash dell'operatore) oppure dal Metodo B (acquisizione diretta da GitHub) descritti al §10.1. Il Metodo B non richiede un ulteriore hash personale e non equivale a una verifica crittografica indipendente. Nessuno dei due metodi sostituisce il requisito di isolamento del punto 1. Se un confronto hash dà esito non corrispondente, il bundle di riferimento non è identificato come file utilizzato e il caso non può essere dichiarato PASS.

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

### 10.1 Identità del bundle e metodi di identificazione

L'identità del file bundle effettivamente utilizzato può essere documentata mediante due metodi alternativi, da mantenere distinti dalla verifica crittografica indipendente:

1. **Metodo A — Confronto hash effettuato dall'operatore:** l'operatore calcola personalmente l'hash del file effettivamente utilizzato e lo confronta con quello del file di riferimento nel repository. I due valori devono essere ottenuti con lo stesso algoritmo e la stessa modalità. Registrare nome file, algoritmo/tipo di hash, entrambi i valori e risultato del confronto.
2. **Metodo B — Acquisizione diretta da GitHub:** l'operatore fornisce un URL GitHub fissato a uno specifico commit immutabile; la chat accede al file, ne legge integralmente il contenuto e conferma esplicitamente l'acquisizione. Se il transcript documenta URL, commit, percorso del file e conferma di lettura integrale, registrare il Core come **identificato mediante acquisizione diretta da GitHub**. Non è richiesto un ulteriore hash personale dell'operatore; l'attestazione hash resta facoltativa.
3. **Verifica crittografica indipendente:** un processo tecnico indipendente calcola autonomamente l'hash del contenuto effettivamente acquisito e quello del riferimento, quindi verifica la corrispondenza. Questa evidenza non deve essere confusa con il Metodo A o con il Metodo B.
4. **Identità non verificata:** non è disponibile evidenza sufficiente per il Metodo A, il Metodo B o una verifica crittografica indipendente.
5. **Non corrispondente:** nel Metodo A o nella verifica indipendente, gli hash comparabili ottenuti con lo stesso algoritmo sono differenti.

Per ogni identificazione registrare il metodo e le evidenze disponibili. Per il Metodo A riportare almeno:
- nome del file effettivamente utilizzato;
- algoritmo e tipo di identificatore;
- hash del file utilizzato;
- hash del file di riferimento;
- esito dichiarato del confronto.

Per il Metodo B riportare almeno:
- URL GitHub completo fissato al commit;
- commit SHA;
- percorso del file;
- evidenza nel transcript della conferma di accesso e lettura integrale.

**SHA-256 del file e Git blob SHA non sono intercambiabili**: indicare sempre il tipo di identificatore. L'acquisizione diretta da GitHub identifica la provenienza documentata del contenuto dal commit indicato, ma non costituisce né va descritta come verifica crittografica indipendente.

Questa regola riguarda esclusivamente l'identità del file bundle. Non modifica il §6, non sana una sessione non isolata, non cambia i criteri F1–F7 e non determina automaticamente PASS. La conformità procedurale e l'esito comportamentale restano valutazioni separate.

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


## 15. Verifiche amministrative e stato PR

La cronologia degli snapshot e gli SHA dei bundle sono registrati nella sezione **Cronologia e snapshot** all'inizio del documento. Le osservazioni amministrative raccolte durante le verifiche precedenti non costituiscono riferimenti operativi alternativi.

Al controllo pre-allineamento:
- PR #2 risultava OPEN e DRAFT, non merged.
- Il campo `mergeable` è variato tra interrogazioni precedenti; non è stata acquisita una diagnosi attendibile della causa di `false`. Non attribuire cause né tentare correzioni automatiche.
- La PR #1 non è stata modificata.
- Il confronto branch/`main` mostrava 62 commit ahead e 0 behind; nessun file eliminato nel diff branch/`main`.
- Per il controllo CI sul commit allora corrente non sono stati restituiti status check né workflow run. Ciò non prova l'assenza di workflow configurati.

Queste osservazioni sono storiche. Lo stato corrente di PR #1 e PR #2 va riportato nel rapporto di pubblicazione di questo allineamento, senza modificare metadati o stato delle PR.

## A04 — Protocollo aggiornato e campagna post-implementazione

Questa sezione integra le istruzioni operative precedenti incompatibili; i risultati storici restano invariati.

### Scheda ambientale obbligatoria
Per ogni run registrare piattaforma/chat, modello, piano se visibile, data/ora/fuso, tipo sessione, presenza di GPT personalizzato/progetto/notebook/agente, stato istruzioni personalizzate (DISATTIVATE/ATTIVE/NON VERIFICABILE), stato Memory (DISATTIVATA/ATTIVA/NON VERIFICABILE), file/brief/contesto persistente, bundle e identificatore, transcript integrale e riferimento stabile. Non dedurre che un'impostazione sia disattivata.

### Quattro dimensioni indipendenti
A. Comportamento: PASS / FAIL / PARTIALLY VERIFIED / NOT CONCLUSIVE. B. Conformità procedurale: CONFORME / NON CONFORME / PARZIALMENTE CONFORME / PREREQUISITI NON VERIFICABILI / NON ESEGUITO. C. Identità bundle: IDENTIFICATO (Metodo A/B documentato) / PARZIALE / NON IDENTIFICATO. D. Evidenze: COMPLETA / PARZIALE / INSUFFICIENTE. Una run non conforme non dimostra PASS controllato. Un FAIL non conforme resta evidenza esplorativa e va ripetuto in condizioni conformi per attribuirlo. Conservare ogni run.

### Aggregazione T01 — regola deterministica

Conservare sempre tutte le run e i loro quattro assi (comportamento, conformità procedurale, identità bundle, qualità delle evidenze). Non cancellare, sovrascrivere o riclassificare retroattivamente un risultato storico. Le run non conformi restano evidenza esplorativa e non dimostrano PASS controllato.

Applicare nell'ordine le seguenti regole, senza maggioranze, medie o voto prevalente:

1. **NOT RUN:** non esiste alcuna run registrata.
2. **NOT CONCLUSIVE:** esistono soltanto run non conformi oppure prerequisiti/evidenze non consentono una valutazione controllata.
3. **NOT CONCLUSIVE — ANOMALIA DA INVESTIGARE:** esiste almeno un FAIL controllato e almeno una run conforme successiva con esito PASS. Il FAIL controllato resta esplicitamente aperto; nessun PASS aggregato è consentito finché la discordanza non è investigata e risolta.
4. **FAIL:** tutte le run conformi valutabili sono FAIL e non esistono PASS conformi discordanti.
5. **PASS:** tutte le run conformi valutabili sono PASS e non esistono FAIL controllati irrisolti.
6. **NOT CONCLUSIVE:** ogni altra combinazione discordante o incompleta, inclusi FAIL controllati associati a run conformi PARTIALLY VERIFIED/NOT CONCLUSIVE, oppure anomalie non risolte.

**Indagine:** registrare ipotesi, controlli, evidenze, responsabile, data e conclusione. Se l'indagine conferma un difetto, mantenere l'aggregato FAIL. Se dimostra che il FAIL dipendeva da causa esterna o condizione non riproducibile, documentare causa, evidenze e decisione esplicita di riclassificazione per l'aggregato; il risultato originale resta nel registro storico e non viene eliminato né riscritto. Solo dopo una risoluzione documentata si può ricalcolare l'aggregato.

Un PASS conforme non annulla un FAIL controllato. Un FAIL non conforme resta esplorativo. La conformità non trasforma da sola un risultato comportamentale in PASS.

### Riferimenti univoci ai casi storici e alle revisioni A04

- **T04 storico:** TEST_CASES.md → “T04 — Creazione per marketing”. Input e criteri storici restano invariati.
- **T04 — Revisione A04: marketing, KPI e budget:** TEST_CASES.md → sezione omonima. Prova distinta con input iniziale invariato e requisiti A04 aggiuntivi.
- **T10 storico:** TEST_CASES.md → “T10 — Revisione iterativa”. Sequenza storica a due messaggi, invariata.
- **T10 — Revisione A04: artefatto completo e iterazione:** TEST_CASES.md → sezione omonima. Prova distinta sui campi completi al primo turno e sulla loro conservazione al secondo.

Non sostituire, rinominare o sovrascrivere i casi storici. Nel registro usare T04-R e T10-R per le revisioni A04; T04 e T10 restano riservati ai casi storici.

### Nuova campagna Full
Eseguire T03, T05, T06, T11, T15, T16-A…E, T17-A…E, T18, T19-A…D, T20-A…F, T01 con nuova aggregazione, T04-R, T10-R, T12 e T08.

### Suite Compact
Eseguire T01, T02, T08, T09, T10, T11, T12, T13 e T14. Aggiungere confronti P0/P1 T16-A…E, T17-A…E, T18 e T19-A…D con input e condizioni comparabili.

La checklist ambientale va preparata fuori dalla chat di test; non mostrare al modello criteri o rubriche. Ogni run richiede transcript integrale e bundle identificato. L'aggiornamento documentale non costituisce test comportamentale; tutti i test nuovi restano da eseguire.

## Addendum A08 — attribuibilità e aggregazione T01, impatto e conseguenza

Questo addendum integra la regola A06 per il solo trattamento delle cause esterne e rende espliciti i campi di registrazione. In caso di divergenza, per le nuove campagne prevalgono le definizioni A08 qui riportate. Nessun risultato storico viene modificato.

### Aggregazione T01 — regola deterministica
Conservare ogni run e i quattro assi già previsti. Non cancellare o riscrivere il risultato storico della singola run. Per l'aggregazione aggiungere tre campi distinti: **validità della run rispetto alle condizioni/bundle**, **attribuibilità al bundle** e **ammissibilità aggregata**.

Per ogni run registrare:
- **Esito storico della run:** PASS / FAIL / PARTIALLY VERIFIED / NOT CONCLUSIVE / NOT RUN; immutabile.
- **Conformità procedurale, identità bundle e qualità evidenze:** secondo le classificazioni già definite.
- **Validità della run rispetto alle condizioni/bundle:** VALIDA / NON VALIDA / INDETERMINATA. VALIDA richiede prerequisiti conformi, bundle identificato ed evidenze complete; NON VALIDA indica condizioni non conformi o causa esterna dimostrata; INDETERMINATA indica che le evidenze non consentono di decidere.
- **Attribuibilità al bundle:** ATTRIBUIBILE / CAUSA ESTERNA DIMOSTRATA / INDAGINE APERTA / NON DETERMINABILE.
- **Ammissibilità aggregata:** INCLUSA / ESCLUSA PER CAUSA ESTERNA DOCUMENTATA / NON AMMISSIBILE (NON CONFORMITÀ O EVIDENZE INSUFFICIENTI) / SOSPESA IN ATTESA DI INDAGINE.
- **Decisione:** ID indagine, causa, evidenze puntuali, valutatore, data/ora, motivazione e riferimento alla run originaria.

Una run è **INCLUSA** soltanto se la validità è VALIDA, la conformità è CONFORME, il bundle è identificato, le evidenze sono complete e l'attribuibilità è al bundle. Una run non conforme o con evidenze insufficienti è NON AMMISSIBILE e resta esplorativa; non va confusa con una run ESCLUSA per causa esterna documentata. Una run con indagine aperta che può cambiare l'attribuibilità è SOSPESA e blocca la conclusione dell'aggregato finché l'indagine non è chiusa.

**Esclusione per causa esterna:** è ammessa soltanto quando l'indagine documenta evidenze sufficienti e verificabili che dimostrano che il FAIL è dovuto a una causa esterna non attribuibile al bundle o a una condizione di prova non riproducibile. Conservare il risultato storico FAIL senza modificarlo; impostare `Validità = NON VALIDA`, `Attribuibilità = CAUSA ESTERNA DIMOSTRATA` e `Ammissibilità = ESCLUSA PER CAUSA ESTERNA DOCUMENTATA`; registrare evidenze, valutatore, data/ora e motivazione. L'esclusione riguarda esclusivamente il calcolo aggregato, non cancella né converte il FAIL storico. Se le evidenze non dimostrano la causa esterna, la run non può essere esclusa discrezionalmente: chiudere l'indagine come non dimostrata e includere il FAIL se gli altri requisiti di ammissibilità sono soddisfatti. Se la causa resta incerta, mantenerla SOSPESA e l'aggregato NOT CONCLUSIVE.

**Calcolo deterministico, senza maggioranze, medie o voto prevalente:**
1. Nessuna run registrata → **NOT RUN** (caso G).
2. Solo run non conformi/esplorative → **NOT CONCLUSIVE** (caso F).
3. Una o più run SOSPESE per indagine aperta → **NOT CONCLUSIVE — INDAGINE APERTA**; in particolare, un FAIL conforme seguito da un PASS conforme richiede indagine e non consente PASS aggregato (caso C).
4. Indagine conclusa con conferma del difetto → **FAIL** (caso D), anche se esiste una run PASS successiva discordante.
5. Indagine conclusa con causa esterna dimostrata → escludere esclusivamente quella run dall'aggregazione, conservando il FAIL storico, quindi ricalcolare sulle sole run INCLUSE (caso E).
6. Dopo aver applicato le esclusioni documentate: sole run conformi ammissibili PASS → **PASS** (caso B); sole run conformi ammissibili FAIL → **FAIL** (caso A).
7. Ogni altra combinazione, inclusi risultati parziali, evidenze insufficienti o PASS/FAIL ammissibili discordanti non risolti → **NOT CONCLUSIVE**.

Dopo una decisione documentata di esclusione o inclusione, ricalcolare sulle sole run INCLUSE e riportare ID e numero delle run INCLUSE, ESCLUSE e SOSPESE. Non ricalcolare se la decisione non è documentata. Se una causa esterna non è dimostrata, il FAIL non può essere escluso; se l'indagine resta aperta, la run è SOSPESA e l'aggregato resta NOT CONCLUSIVE.

**Matrice A–G, coerente con i casi A06:**
- **A — solo FAIL conformi:** **FAIL**.
- **B — solo PASS conformi:** **PASS**.
- **C — FAIL conforme seguito da PASS conforme:** **NOT CONCLUSIVE — ANOMALIA DA INVESTIGARE**; nessun PASS aggregato finché la discordanza non è risolta.
- **D — indagine che conferma il difetto:** **FAIL**; il difetto confermato non viene annullato da un PASS successivo.
- **E — indagine che dimostra causa esterna:** conservare il FAIL storico, documentare causa/evidenze/valutatore/data, marcare la run ESCLUSA e ricalcolare soltanto sulle run INCLUSE; senza run INCLUSE l'esito è NOT CONCLUSIVE.
- **F — solo run non conformi:** **NOT CONCLUSIVE**.
- **G — nessuna run:** **NOT RUN**.

Un FAIL controllato non viene annullato da un PASS successivo. Un FAIL non conforme resta esplorativo. La decisione di esclusione non è una riclassificazione del risultato storico.

### Interpretazione operativa del gate P0
Il riepilogo distingue operazione, ambito, risorsa, impatto e conseguenze. **Impatto** descrive gli effetti concreti e la loro portata (ad esempio disponibilità, prestazioni, utenti, dati o servizi coinvolti); **conseguenza** descrive l'esito che può derivarne. Una variazione dell'impatto è una variazione materiale autonoma: anche se la conseguenza testuale già dichiarata non cambia, occorre aggiornare il riepilogo e chiedere una nuova conferma esplicita. Ai fini della valutazione QA, una variazione dell'impatto va trattata almeno come variazione della conseguenza. Questa è un'interpretazione conservativa del gate esistente, non una modifica dei bundle.

### Riferimenti campagna
Nella campagna Full usare esclusivamente gli ID **T04-R** e **T10-R** per le revisioni A04; T04 e T10 senza suffisso identificano i casi storici. T16-D usa la fixture deterministica definita in TEST_CASES.md; T16-E applica la condizione di arresto prima dell'invio del consenso; T20-F usa il testo letterale e i prerequisiti ambientali definiti in TEST_CASES.md.
