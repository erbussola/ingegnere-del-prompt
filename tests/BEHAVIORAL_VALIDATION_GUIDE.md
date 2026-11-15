# Behavioral Validation Guide — guida pratica per il proprietario

Questa guida accompagna l'esecuzione manuale dei test di Ingegnere del Prompt 2.0. Non servono competenze di programmazione: occorre soltanto seguire la sequenza, copiare i testi senza modificarli e conservare le risposte.

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

## 7. Ripetere con il bundle compatto

Dopo aver completato il percorso A:

1. Apri una nuova conversazione pulita.
2. Copia integralmente `instructions/COMPACT.md`.
3. Invia il bundle come primo messaggio.
4. Esegui uno dei nove test obbligatori: T01, T02, T08, T09, T10, T11, T12, T13 o T14.
5. Usa lo stesso input e la stessa sequenza di messaggi del test completo.
6. Conserva un nuovo transcript separato.
7. Compila la sezione del bundle compatto nel registro risultati.

Non riutilizzare la chat del bundle completo e non trasferire al modello la risposta precedente.

## 8. Confrontare i risultati

Confronta completo e compatto soltanto quando test, input, piattaforma e modello sono gli stessi (o quando le differenze sono esplicitamente annotate).

Per ogni coppia chiediti:
- Il modello ha compreso lo stesso obiettivo?
- Ha posto domande diverse o in numero diverso?
- Ha applicato RICCE in modo diverso?
- I cinque suggerimenti sono presenti, distinti e completi?
- Il prompt finale è altrettanto autonomo e utilizzabile?
- Nell'iterazione ha conservato le parti già approvate?

Descrivi le differenze osservate e il loro impatto. Nove test comparativi non dimostrano che i due bundle siano equivalenti in tutti i casi o su tutte le piattaforme.

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

## 11. Quando la validazione può dirsi conclusa

La preparazione dei documenti non significa che i test siano stati superati. La campagna termina soltanto quando:
- tutti i 15 test del bundle completo sono stati eseguiti e registrati;
- tutti i nove test obbligatori del bundle compatto sono stati eseguiti e registrati;
- i transcript sono conservati e verificabili;
- le anomalie sono state classificate;
- F1–F7 sono valutati per entrambi i bundle, dove le evidenze lo consentono;
- il confronto completo/compatto è documentato;
- i casi non verificabili e i limiti di piattaforma sono dichiarati.

Fino ad allora la validazione resta incompleta e la PR #2 deve restare OPEN — DRAFT — NOT MERGED.