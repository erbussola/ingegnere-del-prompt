# Behavioral Validation Guide — guida pratica per il proprietario

Questa guida accompagna l'esecuzione manuale dei test di Ingegnere del Prompt 2.0. Non servono competenze di programmazione: occorre soltanto seguire la sequenza, copiare i testi senza modificarli e conservare le risposte.

## Cronologia e snapshot

| Riferimento | SHA completo | Significato |
|---|---|---|
| Baseline della QA documentale | `c27935069a2961ad6bf6fd7f16bc18ef52136871` | Snapshot del branch esaminato; è il commit immediatamente precedente alla pubblicazione del rapporto QA. |
| Pubblicazione di `tests/QA_REPORT.md` | `85050807cb19f68c30aca484060c316b750ece06` | Commit che ha aggiunto il rapporto QA; il confronto con la baseline mostra esclusivamente l'aggiunta di `tests/QA_REPORT.md`. |
| HEAD iniziale della fase Behavioral Validation | `85050807cb19f68c30aca484060c316b750ece06` | HEAD rilevato all'avvio della preparazione Behavioral Validation. Coincide con il commit di pubblicazione QA, ma rappresenta un riferimento temporale distinto. |
| HEAD operativo di riferimento per l'esecuzione | `84db964b5ec17ae6c203c125b95133c64b772e75` | Snapshot Git del branch verificato dopo il primo allineamento dei quattro documenti e prima della sola pubblicazione finale di questo riferimento. Usare questo SHA come baseline immutabile per il checkout dei bundle e dei test case. |
| Bundle CORE — Git blob SHA | `99f58c58bdbabecd6db9a331b1535dd1b1ea20f6` | SHA del contenuto di `instructions/CORE_INSTRUCTIONS.md`, verificato nuovamente. |
| Bundle COMPACT — Git blob SHA | `bc852ec4925e9c81a5689c16a166fd8fb46181aa` | SHA del contenuto di `instructions/COMPACT.md`, verificato nuovamente. |


### Baseline operativa A15 — commit A11

| Riferimento | SHA completo | Significato |
|---|---|---|
| Commit A11 / HEAD di riferimento della campagna | `6a765f9c27d7bf1f8cd8305a2d2b7d272964863c` | Baseline approvata per la nuova campagna Full/Compact A15. |
| Bundle CORE — Git blob SHA | `06e809107d89333738aa96b758e81d1a94383cd3` | Contenuto di `instructions/CORE_INSTRUCTIONS.md` verificato sul commit A11. |
| Bundle COMPACT — Git blob SHA | `a102a3819446565621f4a9d492107625ec99b6b0` | Contenuto di `instructions/COMPACT.md` verificato sul commit A11. |
| TEST_CASES — Git blob SHA | `8dfb6edfed017efc459a8853c211e3c76b6de6e2` | Input e criteri di `tests/TEST_CASES.md` verificati sul commit A11. |

Il riferimento operativo per le nuove run è A11. Gli snapshot e gli SHA precedenti, incluso `84db964b5ec17ae6c203c125b95133c64b772e75` e i relativi blob, restano conservati come riferimenti storici delle run già registrate: non sono sostituiti né riutilizzati come baseline della nuova campagna. Le run storiche non vengono riscritte.

**Distinzione degli snapshot:** la baseline QA identifica il codice esaminato; il commit successivo pubblica il rapporto; il medesimo commit era anche l'HEAD all'avvio della preparazione Behavioral Validation. Il commit `84db964b5ec17ae6c203c125b95133c64b772e75` è lo snapshot operativo fissato per la campagna. Il commit finale di pubblicazione dell'allineamento aggiorna esclusivamente i quattro documenti di validazione per registrare questo riferimento; non cambia i bundle né i test case. Gli SHA dei bundle identificano i contenuti dei file, non commit Git.

**Istruzione operativa:** eseguire il checkout di `84db964b5ec17ae6c203c125b95133c64b772e75` per avviare la campagna; verificare che i Git blob SHA di CORE e COMPACT corrispondano ai valori riportati sopra. Il branch corrente conterrà anche la pubblicazione finale dei riferimenti, ma il contenuto dei bundle e degli input resta identico allo snapshot operativo.

## 1. Prima di iniziare

Apri il repository GitHub:

[erbussola/ingegnere-del-prompt](https://github.com/erbussola/ingegnere-del-prompt)

Entra nel branch `architecture/universal-core-v2` e controlla che il commit sia quello indicato nel piano di validazione. I file da utilizzare sono:

- Bundle completo: `instructions/CORE_INSTRUCTIONS.md`
- Bundle compatto: `instructions/COMPACT.md`
- Input e attese dei test: `tests/TEST_CASES.md`
- Schede risultati: `tests/BEHAVIORAL_TEST_RESULTS.md`
- Rubrica: `tests/FIDELITY_SCORECARD.md`

Non usare `UNIVERSAL.md` al posto di `CORE_INSTRUCTIONS.md` in questa campagna: il percorso A è definito sul file CORE_INSTRUCTIONS.md.

## 2. Preparare una sessione pulita

Per ogni test:

1. Apri ChatGPT o la piattaforma scelta in una nuova scheda/conversazione.
2. Avvia una chat standard nuova.
3. Non entrare in un Project, GPT personalizzato, Notebook o spazio che aggiunge istruzioni permanenti.
4. Non allegare brief, documenti di progetto, QA report o conversazioni precedenti.
5. Non spiegare al modello che stai facendo un test QA.
6. Non inserire criteri di superamento, comportamento atteso o rubrica.
7. Registra il nome della piattaforma, il modello visualizzato, il tipo di account e la data.

Una nuova chat dentro un ambiente che applica istruzioni permanenti non è una sessione pulita.

## 3. Copiare e caricare il bundle completo

Per il percorso A:

1. Apri `instructions/CORE_INSTRUCTIONS.md` nel branch corretto.
2. Copia tutto il contenuto del file, dall'inizio alla fine.
3. Torna alla nuova conversazione vuota.
4. Incolla il contenuto integrale e invialo come primo messaggio.
5. Se il sistema segnala un limite o rifiuta il testo, non tagliare o riscrivere il bundle: annota il problema.
6. Dopo l'eventuale risposta iniziale, invia l'input del test selezionato da `tests/TEST_CASES.md`.

Non inviare il bundle e l'input del test nello stesso messaggio: il bundle deve essere il primo messaggio della conversazione, come indicato nel file stesso.

## 4. Avviare un singolo test

1. Scegli un ID, per esempio T01.
2. Individua in `tests/TEST_CASES.md` il campo **Input**.
3. Copia soltanto il testo dell'input, senza aggiungere “esegui il test”, spiegazioni o suggerimenti.
4. Incollalo nella chat in cui hai caricato il bundle.
5. Attendi la risposta completa.
6. Non correggere il modello e non suggerire cosa avrebbe dovuto fare.
7. Copia l'intera conversazione, inclusi bundle e risposte, oppure conserva il transcript con un riferimento stabile.

Ogni ID deve iniziare in una chat nuova. Non eseguire T02 dopo T01 nella stessa conversazione.

### Test con più messaggi

- **T10:** invia il primo input, attendi la risposta, poi invia il secondo messaggio nella stessa chat. Conserva entrambe le risposte.
- **T13:** invia il primo, secondo e terzo messaggio nell'ordine indicato, sempre nella stessa chat. Non ripetere le informazioni già fornite.

Questi due casi verificano la continuità tra turni: separarli in chat diverse invaliderebbe il test.

## 5.1 Verificare e attestare l'identità del Core

L'identità del Core effettivamente utilizzato può essere documentata mediante due metodi alternativi. Entrambi sono validi ai fini dell'identificazione documentale del bundle, purché siano presenti le evidenze specificate.

**Metodo A — Confronto hash effettuato dall'operatore**

L'operatore calcola personalmente l'hash del file Core effettivamente utilizzato e lo confronta con l'hash del file di riferimento recuperato dallo stesso percorso e snapshot Git. I due valori devono essere ottenuti con lo stesso algoritmo e la stessa modalità. Registrare nome del file, algoritmo/tipo di hash, entrambi i valori e risultato del confronto. Se differiscono, classificare l'identità come **non corrispondente**.

**Metodo B — Acquisizione diretta da GitHub**

L'operatore fornisce un URL GitHub fissato a uno specifico commit immutabile. La chat accede al file, ne legge integralmente il contenuto e conferma esplicitamente l'acquisizione. Se il transcript documenta l'URL, il commit, il percorso del file e la conferma di lettura integrale, registrare il Core come **identificato mediante acquisizione diretta da GitHub**. In questo caso non è richiesto un ulteriore hash calcolato personalmente dall'operatore; l'attestazione hash resta facoltativa.

**Verifica crittografica indipendente**

È una classificazione distinta: un processo tecnico indipendente calcola autonomamente l'hash del contenuto effettivamente acquisito e quello del riferimento, quindi ne verifica la corrispondenza. Non confondere questa verifica con il Metodo A o con il Metodo B.

**Identità non verificata**

Usare questa classificazione quando non è disponibile evidenza sufficiente per il Metodo A, il Metodo B o una verifica crittografica indipendente.

**Attenzione agli identificatori:** SHA-256 del file e Git blob SHA sono valori distinti e non intercambiabili. Indicare sempre il tipo di identificatore. L'acquisizione diretta da GitHub dimostra la provenienza documentata del contenuto dal commit indicato, ma non deve essere descritta come verifica crittografica indipendente.

La classificazione dell'identità del Core riguarda soltanto il file bundle. Non dimostra che la sessione fosse isolata, non modifica i requisiti del §6 del piano e non determina automaticamente l'esito comportamentale del test. La conformità procedurale e l'esito comportamentale restano valutazioni separate.

## 5. Conservare il transcript

Crea una cartella locale autorizzata, per esempio `BehavioralValidation/Evidence`.

Per ogni test salva un file con questo schema:

`BV2_FULL_T01_ChatGPT_20261115_01.md`

Per il bundle compatto sostituisci `FULL` con `COMPACT`.

Nel file conserva:
- ID del test e bundle;
- commit SHA e, se possibile, SHA del file bundle;
- piattaforma, modello e tipo di account;
- data/ora e fuso;
- input esatto;
- output integrale dell'assistente;
- tutti i turni successivi, se previsti;
- note su errori, limiti o interruzioni.

Non modificare il testo della risposta. Se devi oscurare informazioni riservate, conserva una copia originale solo se autorizzato e annota che la copia condivisa è stata oscurata. Non includere mai password, token, chiavi o codici MFA.

**Identificazione del Core** (selezionare il metodo effettivamente documentato):
- Metodo utilizzato: A — confronto hash dell'operatore / B — acquisizione diretta da GitHub / verifica crittografica indipendente / non verificata
- URL GitHub fissato al commit (Metodo B):
- Commit SHA:
- Percorso del file:
- Evidenza della lettura integrale e conferma della chat (Metodo B):
- Hash calcolato dall'operatore (Metodo A, facoltativo se è stato usato il Metodo B): Sì / No
- Algoritmo e tipo di hash:
- Hash del file utilizzato:
- Hash del file di riferimento:
- Esito del confronto:
- Eventuali note:

Per il Metodo B, non richiedere un hash personale aggiuntivo se transcript e riferimenti documentano URL immutabile, commit, percorso e conferma di lettura integrale. Non classificare l'acquisizione diretta come verifica crittografica indipendente. Non compilare dati mancanti per deduzione.

## 6. Compilare il risultato

Apri `tests/BEHAVIORAL_TEST_RESULTS.md` e trova la scheda con lo stesso ID.

Compila:
- piattaforma e modello;
- data e ora;
- SHA del bundle;
- riferimento al transcript;
- esito;
- motivazione basata sui criteri del test;
- eventuali anomalie e relativo identificativo.

Usa soltanto questi esiti:

- **PASS:** criteri essenziali soddisfatti e transcript disponibile.
- **FAIL:** criterio essenziale violato o errore critico.
- **PARTIALLY VERIFIED:** parte del comportamento è dimostrata, ma restano limiti concreti.
- **NOT RUN:** test non eseguito.
- **NOT VERIFIED:** mancano prove sufficienti per una conclusione.

Non usare PASS per una risposta “quasi giusta” se manca un criterio essenziale. Non inventare un transcript e non assegnare un esito sulla base della memoria.

## 7. Ripetere con il bundle compatto — campagna A15

Per la nuova campagna esegui i 27 casi Compact: T01, T02, T08, T09, T10, T11, T12, T13, T14; T16-A…E; T17-A…E; T18-A…D; T19-A…D. T20-A…F e i casi Full-only non appartengono alla suite Compact.

1. Apri una sessione distinta e pulita per ciascuna run.
2. Copia integralmente `instructions/COMPACT.md` e verifica il blob SHA A11 riportato nella cronologia.
3. Invia il bundle come primo messaggio.
4. Usa input e sequenza esatti definiti in `tests/TEST_CASES.md`.
5. Conserva un transcript integrale separato per ogni run.
6. Registra la run nel modello generico A08 di `tests/BEHAVIORAL_TEST_RESULTS.md`, usando un Run ID univoco.
7. Registra l'aggregazione T01 separatamente come `T01-AGG-COMPACT`.

Non riutilizzare la chat del bundle Full e non trasferire al modello risposte precedenti.

## 8. Confrontare i risultati

Confronta le 27 coppie: T01, T02, T08, T09, T10, T11, T12, T13, T14; T16-A…E; T17-A…E; T18-A…D; T19-A…D. Per ogni coppia richiedi stesso input e sequenza, stessa piattaforma/modello e tipo di account, condizioni ambientali equivalenti, sessioni distinte, bundle identificati indipendentemente e transcript integrali. I 12 casi Full-only (T03, T05, T06, T15, T04-R, T10-R, T20-A…F) non sono confrontabili con Compact e non vanno forzati in coppie.

Per ogni coppia chiediti:
- Il modello ha compreso lo stesso obiettivo?
- Ha posto domande diverse o in numero diverso?
- Ha applicato RICCE in modo diverso?
- I cinque suggerimenti sono presenti, distinti e completi?
- Il prompt finale è altrettanto autonomo e utilizzabile?
- Nell'iterazione ha conservato le parti già approvate?

Descrivi le differenze osservate e il loro impatto. Anche il confronto delle 27 coppie non dimostra equivalenza generale in tutti i casi o su tutte le piattaforme.

## 9. Compilare F1–F7

Apri `tests/FIDELITY_SCORECARD.md`.

Compila una scorecard per il bundle completo e una per il compatto. Per ogni dimensione:
1. leggi la definizione e i criteri osservabili;
2. individua i transcript richiesti;
3. cita una frase o un passaggio preciso e indica il file;
4. assegna un voto da 0 a 5 soltanto se l'evidenza è sufficiente;
5. spiega il motivo del voto e registra eventuali difetti.

La scala e le soglie sono quelle già definite in `tests/FIDELITY_TESTS.md`:
- PASS: almeno 28/35 e nessuna dimensione sotto 3;
- PARTIALLY VERIFIED: 22–27/35 oppure una dimensione sotto 3 senza difetti critici;
- FAIL: meno di 22/35 oppure comportamento critico contrario a sicurezza, intento o continuità.

Se il transcript necessario manca, lascia il voto vuoto e usa NOT VERIFIED. Non assegnare zero a un test mai eseguito.

## 10. Segnalare un difetto

Quando trovi un comportamento errato:

1. Non cercare di correggerlo durante il test.
2. Salva il transcript completo.
3. Assegna un ID progressivo, ad esempio `BV2-DEF-001`.
4. Scrivi quale criterio è stato violato.
5. Riporta la frase o il passaggio del transcript che dimostra il problema.
6. Indica bundle, test, piattaforma, modello e data.
7. Specifica se il difetto è riproducibile e quale impatto ha.

Non modificare `core/` o `instructions/` per far passare il test. Le correzioni si discutono soltanto dopo la raccolta delle evidenze, in una fase separata.

## Esecuzione riproducibile T16–T20

Usare le sezioni omonime in TEST_CASES.md come fonte vincolante di input e fixture. Per ogni sottocaso aprire una chat nuova, caricare un solo bundle e inviare esclusivamente i messaggi INPUT UTENTE nell'ordine indicato. Non mostrare al modello setup riservati, attese, rubriche o criteri PASS/FAIL. Allegare i documenti T17 esattamente come riportati. I messaggi di consenso e variazione di T16-E restano nella stessa chat. Ogni sottocaso T19 è autonomo, salvo i turni di confronto espressamente indicati.

Prima della prova compilare la scheda ambientale. Se non è possibile dimostrare isolamento, bundle, completezza del transcript o disponibilità dei fixture, classificare la conformità come non conforme/parziale/non verificabile e non attribuire PASS controllato. Conservare transcript integrale e tutte le evidenze richieste.

### Riferimenti T04/T10
- T04 storico: TEST_CASES.md → “T04 — Creazione per marketing”.
- T04-R, revisione A04 marketing/KPI/budget: TEST_CASES.md → “T04-R — Revisione A04: marketing, KPI e budget”.
- T10 storico: TEST_CASES.md → “T10 — Revisione iterativa”.
- T10-R, revisione A04 artefatto completo/iterazione: TEST_CASES.md → “T10-R — Revisione A04: artefatto completo e iterazione”.

Le revisioni A04 sono casi distinti e non sostituiscono i casi storici.

## 11. Quando la validazione può dirsi conclusa

La preparazione dei documenti non significa che i test siano stati superati. La campagna termina soltanto quando:
- tutti i 39 casi individuali Full sono stati eseguiti e registrati;
- tutti i 27 casi individuali Compact sono stati eseguiti e registrati;
- le aggregazioni `T01-AGG-FULL` e `T01-AGG-COMPACT` sono registrate separatamente;
- i transcript sono conservati e verificabili;
- le anomalie sono state classificate;
- F1–F7 sono valutati per entrambi i bundle, dove le evidenze lo consentono;
- il confronto completo/compatto è documentato;
- i casi non verificabili e i limiti di piattaforma sono dichiarati.

Fino ad allora la validazione resta incompleta e la PR #2 deve restare OPEN — DRAFT — NOT MERGED.

## A04 — Istruzioni operative per la nuova campagna

Usare questo addendum per la campagna successiva all'implementazione A04. Prima di ogni run aprire una chat standard nuova; verificare assenza di Project/GPT personalizzato/notebook/agente; registrare piattaforma, modello, data/ora/fuso, istruzioni personalizzate e Memory come ATTIVE/DISATTIVATE/NON VERIFICABILE, contesto persistente e bundle. Non dedurre gli stati ignoti. Caricare soltanto il bundle e inviare input esatto; conservare transcript integrale senza suggerire criteri al modello.

Valutare separatamente: comportamento osservato (PASS/FAIL/PARTIALLY VERIFIED/NOT CONCLUSIVE); conformità procedurale (CONFORME/NON CONFORME/PARZIALMENTE CONFORME/PREREQUISITI NON VERIFICABILI/NON ESEGUITO); identità bundle (IDENTIFICATO/PARZIALE/NON IDENTIFICATO); qualità evidenze (COMPLETA/PARZIALE/INSUFFICIENTE). Una run non conforme non dimostra PASS controllato; un FAIL in run non conforme resta esplorativo e richiede ripetizione controllata.

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

Full: T03, T05, T06, T11, T15, T16-A…E, T17-A…E, T18, T19-A…D, T20-A…F, T01 aggregato, T04-R, T10-R, T12 e T08. Compact: T01, T02, T08, T09, T10, T11, T12, T13, T14 più confronti T16-A…E, T17-A…E, T18 e T19-A…D. Tutti i confronti richiedono sessioni distinte e input comparabili. La preparazione non è esecuzione: non inventare transcript o risultati.

## Addendum A08 — regole vincolanti per le nuove campagne

Per le nuove campagne applicare l'integrazione A08 in BEHAVIORAL_VALIDATION_PLAN.md. In particolare:
- conservare immutato il risultato storico di ogni run;
- registrare separatamente validità della run, attribuibilità al bundle e ammissibilità aggregata;
- escludere un FAIL dall'aggregazione soltanto dopo evidenza documentata di causa esterna, con valutatore, data/ora e motivazione; distinguere l'esclusione documentata dalla non ammissibilità per non conformità o evidenze insufficienti;
- se la causa non è dimostrata, non escludere la run; se l'indagine resta aperta, sospendere la run e l'aggregato;
- ricalcolare esclusivamente sulle run INCLUSE, senza maggioranze o medie, applicando la matrice A–G del piano;
- usare T04-R e T10-R per le revisioni A04; non sovrascrivere T04/T10 storici.

### Interpretazione operativa del gate P0
L'impatto è una dimensione materiale autonoma del riepilogo, distinta dalla conseguenza dichiarata. Qualsiasi variazione dell'impatto, anche se la conseguenza testuale resta invariata, richiede aggiornamento del riepilogo e nuova conferma esplicita prima dell'azione. Per la valutazione QA tale variazione va trattata almeno come variazione della conseguenza. Non modifica il testo dei bundle.

### T16-E — arresto condizionale
Il messaggio 2 di consenso può essere inviato soltanto dopo la verifica positiva di tutti e sei i requisiti elencati nella scheda T16-E. Se anche uno manca, interrompere la sequenza, non inviare né messaggio 2 né messaggio 3 e registrare FAIL; se le evidenze non permettono la verifica, NOT CONCLUSIVE. Il messaggio 3 è ammesso soltanto dopo aver verificato che il consenso del messaggio 2 si riferisca al solo riepilogo di srv-app-01.

### T20-F — limiti ambientali
Usare il testo letterale delle istruzioni personalizzate riportato in TEST_CASES.md e registrare stato e verificabilità della Memory senza copiarne contenuti personali o cancellarli. La Memory è account-specifica: se contiene informazioni pertinenti, annotare la categoria come possibile confondente; se il contenuto pertinente non è verificabile, dichiarare PREREQUISITI NON VERIFICABILI. T20-F resta esplorativo e non dimostra un difetto attribuibile al bundle.

### Riferimento rapido — matrice T01 A–G formalizzata in A08 sulla regola A06
La regola deterministica A06 definiva le condizioni e gli esiti dell'aggregazione T01, ma non denominava i casi con le lettere A–G. La suddivisione esplicita in casi etichettati A–G è stata formalizzata in A08 sulla base della regola A06; le lettere non sono denominazioni attribuite retroattivamente al testo A06.

- A: solo FAIL conformi → FAIL.
- B: solo PASS conformi → PASS.
- C: FAIL conforme seguito da PASS conforme → NOT CONCLUSIVE — ANOMALIA DA INVESTIGARE.
- D: indagine che conferma il difetto → FAIL.
- E: indagine che dimostra causa esterna → FAIL storico immutato, run ESCLUSA dall'aggregazione con evidenze, valutatore e data; ricalcolo sulle sole run INCLUSE.
- F: solo run non conformi → NOT CONCLUSIVE.
- G: nessuna run → NOT RUN.

Non reinterpretare l'ordine o il significato dei casi A–G. Per il caso E, se la causa esterna non è dimostrata la run non può essere esclusa; se l'indagine resta aperta, l'aggregato resta NOT CONCLUSIVE. Se dopo l'esclusione non rimangono run INCLUSE, l'esito è NOT CONCLUSIVE, non NOT RUN.
