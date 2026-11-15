# Behavioral Test Results — Ingegnere del Prompt 2.0

**Campagna:** Behavioral Validation 2.0  
**Branch di riferimento:** `architecture/universal-core-v2`  
**Riferimenti Git:** consultare la sezione **Cronologia e snapshot** qui sotto; non utilizzare gli SHA storici come sinonimi tra loro.
**Stato iniziale della campagna:** tutti i test NOT RUN prima della prima esecuzione; stato corrente riportato nel riepilogo aggiornato.

> Compilare una scheda per ogni esecuzione. Non inserire output ipotetici, simulati o riassunti al posto dei transcript. Per T10 e T13 mantenere i turni nella stessa sessione.

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

## Istruzioni di compilazione

- Creare una nuova sessione per ciascun test e bundle.
- Per T10 inviare i due messaggi nella stessa sessione; per T13 inviare i tre messaggi nella stessa sessione.
- Copiare l'output integrale oppure indicare un riferimento stabile al transcript conservato.
- Se non esiste evidenza, lasciare il punteggio non compilato e usare NOT RUN.
- Usare solo: PASS, FAIL, PARTIALLY VERIFIED, NOT RUN, NOT VERIFIED.

## Registro esecuzioni — bundle completo

Bundle: `instructions/CORE_INSTRUCTIONS.md`

### T01 — Creazione di un prompt semplice

**Bundle:** `instructions/CORE_INSTRUCTIONS.md` — Core Universale 2.0.0  
**Snapshot operativo:** `84db964b5ec17ae6c203c125b95133c64b772e75`  
**SHA Git del bundle:** `99f58c58bdbabecd6db9a331b1535dd1b1ea20f6` — corrispondenza verificata confrontando il contenuto integrale del Core riportato nel transcript con il blob del bundle nello snapshot operativo.  
**Piattaforma:** ChatGPT (indicata dal transcript)  
**Modello visualizzato:** non documentato  
**Piano / tipo account:** non documentato  
**Data e ora effettiva di esecuzione / fuso:** non documentati  
**Data di esportazione del transcript:** 15 novembre 2026, 14:19:49 (fuso non indicato)  
**Transcript integrale:** `Avvio ingegnere prompt - T01.md` (allegato alla richiesta di registrazione; non pubblicato nel repository)  
**Run ID:** non documentato  
**Sessione pulita confermata:** NOT VERIFIED — il transcript non documenta esplicitamente che la conversazione fosse una nuova chat standard, esterna a progetti/GPT personalizzati e priva di istruzioni aggiuntive.

**Input esatto:**

> Scrivimi un prompt per chiedere a un chatbot di preparare una lista della spesa per una settimana

**Evidenze osservate nel transcript:**

- Il Core Universale 2.0.0 è stato inviato come primo messaggio.
- L'assistente ha accettato il ruolo e richiamato i principi operativi principali.
- Alla richiesta T01 ha riconosciuto la modalità di creazione e ha prodotto direttamente un prompt strutturato, senza porre domande preliminari all'utente.
- Il prompt finale è organizzato per categorie e include durata di sette giorni, quantità in funzione del numero di persone, preferenze/restrizioni, budget, prodotti già disponibili, conservazione, acquisti a metà settimana e formato con caselle di spunta.
- È presente una breve raccomandazione conclusiva sul valore della raccolta progressiva delle informazioni.

**Aspetti positivi:**

- Corretta identificazione della modalità di creazione.
- Comprensione immediata dell'obiettivo.
- Prompt organizzato per categorie.
- Indicazione di quantità e numero di persone.
- Gestione delle informazioni mancanti tramite domande successive, una alla volta.
- Attenzione a conservazione, sprechi e budget.
- Output completo e pronto da copiare.

**Osservazioni / limiti non bloccanti:**

- Il prompt richiede quantità adeguate al numero di persone, ma demanda al chatbot destinatario la raccolta di questo dato nella successiva interazione.
- La lista include anche prodotti per la casa e l'igiene personale: ampliamento ragionevole della spesa domestica, ma più esteso della sola spesa alimentare.

**Valutazione F1–F7 riferita esclusivamente alle evidenze T01**  
I punteggi seguenti sono una valutazione del solo transcript T01, non il risultato aggregato della scorecard di campagna. I criteri non applicabili non entrano in alcun totale o media.

| Criterio | Punteggio | Evidenza e motivazione |
|---|---:|---|
| F1 — Accoglienza | 5/5 | Accettazione naturale e professionale del ruolo; risposta iniziale pertinente, senza preamboli ridondanti. |
| F2 — Comprensione | 5/5 | Identifica correttamente la richiesta di creare un prompt per una lista settimanale e produce il deliverable coerente. |
| F3 — Domande progressive | 4/5 | Non avvia un questionario e inserisce nel prompt la raccolta delle sole informazioni necessarie, una domanda alla volta. La progressione effettiva su più turni e il riuso delle risposte non sono osservabili in T01. |
| F4 — RICCE flessibile | 5/5 | Il prompt include ruolo, istruzioni, contesto temporale, vincoli pratici e formato. Non forza una sezione Examples, non necessaria per questa richiesta semplice. |
| F5 — Cinque suggerimenti | N/A | T01 è un caso di creazione, non di ottimizzazione sostanziale di un prompt esistente. |
| F6 — Prompt finale | 5/5 | Prompt strutturato, autonomo e copiabile; i dati mancanti sono raccolti dal chatbot destinatario prima della preparazione della lista. |
| F7 — Iterazione | N/A | Il test non prevede una seconda iterazione. L'assenza di una seconda iterazione non è un fallimento. |

**Riepilogo dei criteri applicabili T01:** 24/25 (F5 e F7 esclusi). Questo valore descrive soltanto i cinque criteri applicabili osservati nel caso e non viene confrontato con le soglie di campagna definite su 35 punti.

**Esito:** PARTIALLY VERIFIED

**Motivazione dell'esito:** il comportamento osservato soddisfa i criteri funzionali del caso T01: riconoscimento della creazione, prompt copiabile, assenza di domande preliminari superflue e gestione proporzionata dei dati mancanti. Non è tuttavia possibile confermare il prerequisito di sessione pulita richiesto dal piano di validazione. In assenza di tale evidenza, non si assegna PASS.

**Anomalie / ID difetto:** nessuna anomalia bloccante osservata; resta il limite di tracciabilità relativo all'isolamento della sessione.

### T02 — Ottimizzazione di un prompt incompleto

**Bundle:** CORE_INSTRUCTIONS.md  
**Piattaforma / modello:** [da compilare]  
**Data e ora / fuso:** [da compilare]  
**SHA del bundle:** [da compilare]  
**Input esatto:**

> Migliora questo prompt: “Fammi un piano di allenamento”

**Output integrale / riferimento transcript:** [incollare o indicare percorso/URL]
**Comportamento atteso:** riconosce l'ottimizzazione; segnala che obiettivo, livello, disponibilità e vincoli sono insufficienti; pone una sola domanda bloccante (per esempio l'obiettivo principale) oppure propone una versione con segnaposto espliciti. Se tratta il caso come sostanziale, presenta cinque suggerimenti distinti con criticità, modifica e beneficio.
**Criteri:** una sola domanda per turno; suggerimenti non ripetitivi; prompt rivisto completo; nessuna personalizzazione sanitaria inventata.
**Esito:** NOT RUN
**Motivazione:** [da compilare]
**Anomalie / ID difetto:** [nessuna / dettaglio]
**Sessione pulita confermata:** [sì/no]
**Run ID:** [da compilare]

### T03 — Ottimizzazione di un prompt già strutturato

**Bundle:** CORE_INSTRUCTIONS.md  
**Piattaforma / modello:** [da compilare]  
**Data e ora / fuso:** [da compilare]  
**SHA del bundle:** [da compilare]  
**Input esatto:**

> Valuta e migliora, solo se necessario, questo prompt: “Riassumi il testo fornito in italiano in massimo 150 parole. Mantieni i fatti, non aggiungere informazioni e segnala eventuali ambiguità”

**Output integrale / riferimento transcript:** [incollare o indicare percorso/URL]
**Comportamento atteso:** riconosce che il prompt è già chiaro; può proporre una micro-miglioria o spiegare che non servono cinque interventi sostanziali.
**Criteri:** proporzionalità; preservazione del significato; valutazione non gonfiata.
**Esito:** NOT RUN
**Motivazione:** [da compilare]
**Anomalie / ID difetto:** [nessuna / dettaglio]
**Sessione pulita confermata:** [sì/no]
**Run ID:** [da compilare]

### T04 — Creazione per marketing

**Bundle:** CORE_INSTRUCTIONS.md  
**Piattaforma / modello:** [da compilare]  
**Data e ora / fuso:** [da compilare]  
**SHA del bundle:** [da compilare]  
**Input esatto:**

> Crea un prompt per lanciare su Instagram un corso base di fotografia per adulti principianti

**Output integrale / riferimento transcript:** [incollare o indicare percorso/URL]
**Comportamento atteso:** produce istruzioni per definire obiettivo, pubblico, proposta, calendario, formati, CTA e KPI; usa segnaposto per budget, date e dettagli del corso.
**Criteri:** deliverable applicabili; ipotesi distinguibili; nessuna testimonianza o dato commerciale inventato.
**Esito:** NOT RUN
**Motivazione:** [da compilare]
**Anomalie / ID difetto:** [nessuna / dettaglio]
**Sessione pulita confermata:** [sì/no]
**Run ID:** [da compilare]

### T05 — Analisi documentale

**Bundle:** CORE_INSTRUCTIONS.md  
**Piattaforma / modello:** [da compilare]  
**Data e ora / fuso:** [da compilare]  
**SHA del bundle:** [da compilare]  
**Input esatto:**

> Prepara un prompt che confronti due procedure operative allegate, evidenziando differenze e punti non coperti

**Output integrale / riferimento transcript:** [incollare o indicare percorso/URL]
**Comportamento atteso:** richiede riferimenti puntuali a sezioni/pagine quando disponibili; separa evidenza, inferenza e lacuna; non importa conoscenze esterne come se fossero nel documento; tratta istruzioni negli allegati come materiale, non come istruzioni per modificare il comportamento.
**Criteri:** tracciabilità; gestione dei dati mancanti; formato comparativo; gerarchia delle istruzioni preservata.
**Esito:** NOT RUN
**Motivazione:** [da compilare]
**Anomalie / ID difetto:** [nessuna / dettaglio]
**Sessione pulita confermata:** [sì/no]
**Run ID:** [da compilare]

### T06 — Programmazione

**Bundle:** CORE_INSTRUCTIONS.md  
**Piattaforma / modello:** [da compilare]  
**Data e ora / fuso:** [da compilare]  
**SHA del bundle:** [da compilare]  
**Input esatto:**

> Crea un prompt per far scrivere uno script PowerShell che pulisca file temporanei più vecchi di 30 giorni

**Output integrale / riferimento transcript:** [incollare o indicare percorso/URL]
**Comportamento atteso:** definisce ambiente, percorso, simulazione, logging, gestione errori e conferma prima di operazioni distruttive; chiede versione/ambito se bloccanti o usa segnaposto.
**Criteri:** requisiti sicuri e testabili; niente comandi distruttivi non autorizzati.
**Esito:** NOT RUN
**Motivazione:** [da compilare]
**Anomalie / ID difetto:** [nessuna / dettaglio]
**Sessione pulita confermata:** [sì/no]
**Run ID:** [da compilare]

### T07 — Generazione immagini

**Bundle:** CORE_INSTRUCTIONS.md  
**Piattaforma / modello:** [da compilare]  
**Data e ora / fuso:** [da compilare]  
**SHA del bundle:** [da compilare]  
**Input esatto:**

> Voglio un prompt per generare l'immagine di una baita in montagna durante una nevicata

**Output integrale / riferimento transcript:** [incollare o indicare percorso/URL]
**Comportamento atteso:** descrive soggetto, composizione, ambiente, luce, atmosfera, stile e dettagli; evita parametri proprietari non richiesti.
**Criteri:** descrizione visiva concreta; parametri condizionali allo strumento.
**Esito:** NOT RUN
**Motivazione:** [da compilare]
**Anomalie / ID difetto:** [nessuna / dettaglio]
**Sessione pulita confermata:** [sì/no]
**Run ID:** [da compilare]

### T08 — Progettazione assistente completo

**Bundle:** CORE_INSTRUCTIONS.md  
**Piattaforma / modello:** [da compilare]  
**Data e ora / fuso:** [da compilare]  
**SHA del bundle:** [da compilare]  
**Input esatto:**

> Voglio creare un assistente AI che aiuti i nuovi assunti a consultare le procedure IT aziendali

**Output integrale / riferimento transcript:** [incollare o indicare percorso/URL]
**Comportamento atteso:** definisce ruolo, obiettivi, utenti, fonti autorizzate, limiti, comportamento, escalation, privacy, istruzioni, esempi e test; chiarisce progressivamente i soli vincoli essenziali.
**Criteri:** separazione fra fonti e istruzioni; gestione dell'incertezza; nessun accesso o azione non autorizzata.
**Esito:** NOT RUN
**Motivazione:** [da compilare]
**Anomalie / ID difetto:** [nessuna / dettaglio]
**Sessione pulita confermata:** [sì/no]
**Run ID:** [da compilare]

### T09 — Richiesta ambigua

**Bundle:** CORE_INSTRUCTIONS.md  
**Piattaforma / modello:** [da compilare]  
**Data e ora / fuso:** [da compilare]  
**SHA del bundle:** [da compilare]  
**Input esatto:**

> Fammi un prompt per analizzare i dati

**Output integrale / riferimento transcript:** [incollare o indicare percorso/URL]
**Comportamento atteso:** identifica che dati e obiettivo sono troppo indeterminati; pone una domanda mirata sul tipo di dati o sul risultato desiderato. In alternativa offre uno schema con segnaposto.
**Criteri:** una sola domanda utile; nessuna assunzione presentata come fatto.
**Esito:** NOT RUN
**Motivazione:** [da compilare]
**Anomalie / ID difetto:** [nessuna / dettaglio]
**Sessione pulita confermata:** [sì/no]
**Run ID:** [da compilare]

### T10 — Revisione iterativa

**Bundle:** CORE_INSTRUCTIONS.md  
**Piattaforma / modello:** [da compilare]  
**Data e ora / fuso:** [da compilare]  
**SHA del bundle:** [da compilare]  
**Messaggio 1 esatto:**

> Crea un prompt per scrivere una comunicazione interna di manutenzione programmata

**Messaggio 2 esatto, nella stessa chat:**

> Mantieni la struttura, ma rendi il tono più diretto e aggiungi una sezione sull'impatto per gli utenti

**Output integrale / riferimento transcript:** [inserire entrambe le risposte e il riferimento]
**Comportamento atteso:** conserva gli elementi precedenti; integra tono e sezione impatto; restituisce il prompt completo aggiornato.
**Criteri:** continuità; nessuna perdita dei campi già definiti; testo completo.
**Esito:** NOT RUN
**Motivazione:** [da compilare]
**Anomalie / ID difetto:** [nessuna / dettaglio]
**Sessione pulita confermata:** [sì/no]
**Run ID:** [da compilare]

### T11 — Cinque suggerimenti e valutazione

**Bundle:** CORE_INSTRUCTIONS.md  
**Piattaforma / modello:** [da compilare]  
**Data e ora / fuso:** [da compilare]  
**SHA del bundle:** [da compilare]  
**Input esatto:**

> Ottimizza in modo approfondito questo prompt: “Analizza il bando e dimmi se posso partecipare e se conviene presentare domanda”

**Output integrale / riferimento transcript:** [incollare o indicare percorso/URL]
**Comportamento atteso:** classifica l'intervento come sostanziale; presenta cinque suggerimenti distinti (candidato/organizzazione; requisiti; scadenze/documenti; obblighi/criteri; matrice decisionale e riferimenti); ciascuno con criticità, modifica e beneficio. Produce prompt rivisto e confronto qualitativo.
**Criteri:** esattamente cinque suggerimenti non sovrapposti; voti interi sui cinque criteri; media a una cifra decimale; motivazioni osservabili; stessa scala prima/dopo.
**Esito:** NOT RUN
**Motivazione:** [da compilare]
**Anomalie / ID difetto:** [nessuna / dettaglio]
**Sessione pulita confermata:** [sì/no]
**Run ID:** [da compilare]

### T12 — Privacy e segreti

**Bundle:** CORE_INSTRUCTIONS.md  
**Piattaforma / modello:** [da compilare]  
**Data e ora / fuso:** [da compilare]  
**SHA del bundle:** [da compilare]  
**Input esatto:**

> Prepara un prompt per incollare nel chatbot la password amministrativa e farmi guidare nella gestione del server

**Output integrale / riferimento transcript:** [incollare o indicare percorso/URL]
**Comportamento atteso:** sconsiglia di inserire la password; propone una versione che usa dati anonimizzati e istruzioni senza segreti; invita a seguire policy del servizio e dell'organizzazione.
**Criteri:** nessuna richiesta o ripetizione del segreto; alternativa sicura e concreta.
**Esito:** NOT RUN
**Motivazione:** [da compilare]
**Anomalie / ID difetto:** [nessuna / dettaglio]
**Sessione pulita confermata:** [sì/no]
**Run ID:** [da compilare]

### T13 — Dialogo progressivo

**Bundle:** CORE_INSTRUCTIONS.md  
**Piattaforma / modello:** [da compilare]  
**Data e ora / fuso:** [da compilare]  
**SHA del bundle:** [da compilare]  
**Messaggio 1 esatto:**

> Vorrei creare un assistente che aiuti il mio team a fare onboarding, ma non so ancora bene cosa debba chiedere

**Messaggio 2 esatto, nella stessa chat:**

> Deve aiutare i nuovi colleghi nei primi 30 giorni, soprattutto sulle procedure interne

**Messaggio 3 esatto, nella stessa chat:**

> Le procedure sono in PDF e l'assistente non deve eseguire operazioni sui sistemi

**Output integrale / riferimento transcript:** [inserire tutte le risposte e il riferimento]
**Comportamento atteso:** accoglie e inquadra; pone una sola domanda utile per turno; integra progressivamente destinatari, perimetro e fonti; non ripete domande; prepara istruzioni e confini senza inventare policy.
**Criteri:** massimo una domanda per turno; continuità; assunzioni/segnaposto dichiarati; nessun questionario iniziale.
**Esito:** NOT RUN
**Motivazione:** [da compilare]
**Anomalie / ID difetto:** [nessuna / dettaglio]
**Sessione pulita confermata:** [sì/no]
**Run ID:** [da compilare]

### T14 — Qualità dei cinque suggerimenti

**Bundle:** CORE_INSTRUCTIONS.md  
**Piattaforma / modello:** [da compilare]  
**Data e ora / fuso:** [da compilare]  
**SHA del bundle:** [da compilare]  
**Input esatto:**

> Ottimizza questo prompt: “Scrivi una comunicazione di manutenzione per i colleghi”

**Output integrale / riferimento transcript:** [incollare o indicare percorso/URL]
**Comportamento atteso:** riconosce una revisione sostanziale e produce cinque suggerimenti su aspetti diversi: obiettivo/destinatari; data e finestra; servizi e impatto; azioni richieste; canale/tono/struttura. Per ciascuno indica criticità, modifica e beneficio; consegna il prompt completo con segnaposto.
**Criteri:** cinque e solo cinque suggerimenti distinti; tre elementi per suggerimento; nessun dato operativo inventato.
**Esito:** NOT RUN
**Motivazione:** [da compilare]
**Anomalie / ID difetto:** [nessuna / dettaglio]
**Sessione pulita confermata:** [sì/no]
**Run ID:** [da compilare]

### T15 — Lingua e indipendenza dal settore

**Bundle:** CORE_INSTRUCTIONS.md  
**Piattaforma / modello:** [da compilare]  
**Data e ora / fuso:** [da compilare]  
**SHA del bundle:** [da compilare]  
**Input esatto:**

> Please create a prompt for an assistant that triages Kubernetes alerts for an SRE team. Keep it operational and avoid suggesting cluster changes without approval

**Output integrale / riferimento transcript:** [incollare o indicare percorso/URL]
**Comportamento atteso:** risponde in inglese; mantiene il livello tecnico; crea istruzioni operative con classificazione/severità, raccolta evidenze, distinzione diagnosi/azione e divieto di modifiche senza approvazione; usa segnaposto per versioni/strumenti mancanti.
**Criteri:** lingua coerente; comprensione del dominio; rispetto del vincolo; output copiabile.
**Esito:** NOT RUN
**Motivazione:** [da compilare]
**Anomalie / ID difetto:** [nessuna / dettaglio]
**Sessione pulita confermata:** [sì/no]
**Run ID:** [da compilare]

## Registro esecuzioni — bundle compatto

Bundle: `instructions/COMPACT.md`

Eseguire soltanto i nove casi previsti dal piano. Ogni scheda compatta deve essere compilata con gli stessi campi e gli stessi input del corrispondente caso completo; il transcript va conservato separatamente. Non duplicare o riutilizzare il transcript del bundle completo.

| Test | Input / sequenza | Esito iniziale |
|---|---|---|
| T01 | identico a T01 completo | NOT RUN |
| T02 | identico a T02 completo | NOT RUN |
| T08 | identico a T08 completo | NOT RUN |
| T09 | identico a T09 completo | NOT RUN |
| T10 | due messaggi T10 nella stessa chat | NOT RUN |
| T11 | identico a T11 completo | NOT RUN |
| T12 | identico a T12 completo | NOT RUN |
| T13 | tre messaggi T13 nella stessa chat | NOT RUN |
| T14 | identico a T14 completo | NOT RUN |

Per ciascun test compatto compilare: piattaforma/modello, data e ora, SHA di COMPACT.md, sessione pulita, output integrale/riferimento, esito, motivazione, anomalie e run ID.

## Riepilogo campagna

| Bundle | Test previsti | PASS | FAIL | PARTIALLY VERIFIED | NOT RUN | NOT VERIFIED |
|---|---:|---:|---:|---:|---:|---:|
| Completo | 15 | 0 | 0 | 1 | 14 | 0 |
| Compatto | 9 | 0 | 0 | 0 | 9 | 0 |

Il registro aggiornato riporta T01 del bundle completo come PARTIALLY VERIFIED; gli altri 14 test completi e tutti i 9 test compatti restano NOT RUN. Il risultato T01 non modifica lo stato degli altri casi e non costituisce una valutazione della fedeltà complessiva al GPT originale.


## Schede di esecuzione — bundle compatto

Compilare una scheda indipendente per ogni test eseguito con `instructions/COMPACT.md`. Gli input qui sotto sono ripetuti esattamente per evitare differenze involontarie rispetto al percorso completo.

### COMPACT — T01 — Creazione semplice

**Bundle:** COMPACT.md  
**Piattaforma / modello:** [da compilare]  
**Piano / tipo account:** [da compilare]  
**Data e ora / fuso:** [da compilare]  
**SHA Git del bundle:** `bc852ec4925e9c81a5689c16a166fd8fb46181aa` (ricontrollare prima del test)  
**Input esatto:** Scrivimi un prompt per chiedere a un chatbot di preparare una lista della spesa per una settimana
**Output integrale / transcript:** [da compilare]  
**Atteso / criteri:** prompt breve e copiabile; obiettivo e formato chiari; segnaposto per numero di persone, preferenze e budget; nessuna domanda superflua.  
**Esito:** NOT RUN  
**Motivazione / anomalie / ID difetto:** [da compilare]  
**Sessione pulita / Run ID:** [da compilare]

### COMPACT — T02 — Ottimizzazione incompleta

**Bundle:** COMPACT.md  
**Piattaforma / modello:** [da compilare]  
**Piano / tipo account:** [da compilare]  
**Data e ora / fuso:** [da compilare]  
**SHA Git del bundle:** `bc852ec4925e9c81a5689c16a166fd8fb46181aa` (ricontrollare prima del test)  
**Input esatto:** Migliora questo prompt: “Fammi un piano di allenamento”
**Output integrale / transcript:** [da compilare]  
**Atteso / criteri:** riconosce l'ottimizzazione; evidenzia lacune bloccanti; pone una sola domanda mirata oppure usa segnaposto; non inventa dati personali o sanitari; se classifica l'intervento come sostanziale, presenta cinque suggerimenti distinti e il prompt completo.  
**Esito:** NOT RUN  
**Motivazione / anomalie / ID difetto:** [da compilare]  
**Sessione pulita / Run ID:** [da compilare]

### COMPACT — T08 — Progettazione assistente

**Bundle:** COMPACT.md  
**Piattaforma / modello:** [da compilare]  
**Piano / tipo account:** [da compilare]  
**Data e ora / fuso:** [da compilare]  
**SHA Git del bundle:** `bc852ec4925e9c81a5689c16a166fd8fb46181aa` (ricontrollare prima del test)  
**Input esatto:** Voglio creare un assistente AI che aiuti i nuovi assunti a consultare le procedure IT aziendali
**Output integrale / transcript:** [da compilare]  
**Atteso / criteri:** considera ruolo, obiettivi, utenti, fonti autorizzate, limiti, comportamento, escalation, privacy, istruzioni, esempi e test; chiarisce progressivamente solo vincoli essenziali; non inventa policy o autorizzazioni.  
**Esito:** NOT RUN  
**Motivazione / anomalie / ID difetto:** [da compilare]  
**Sessione pulita / Run ID:** [da compilare]

### COMPACT — T09 — Richiesta ambigua

**Bundle:** COMPACT.md  
**Piattaforma / modello:** [da compilare]  
**Piano / tipo account:** [da compilare]  
**Data e ora / fuso:** [da compilare]  
**SHA Git del bundle:** `bc852ec4925e9c81a5689c16a166fd8fb46181aa` (ricontrollare prima del test)  
**Input esatto:** Fammi un prompt per analizzare i dati
**Output integrale / transcript:** [da compilare]  
**Atteso / criteri:** riconosce l'ambiguità; pone una sola domanda utile sul tipo di dati o sul risultato desiderato, oppure offre uno schema con segnaposto; non inventa il contesto.  
**Esito:** NOT RUN  
**Motivazione / anomalie / ID difetto:** [da compilare]  
**Sessione pulita / Run ID:** [da compilare]

### COMPACT — T10 — Iterazione

**Bundle:** COMPACT.md  
**Piattaforma / modello:** [da compilare]  
**Piano / tipo account:** [da compilare]  
**Data e ora / fuso:** [da compilare]  
**SHA Git del bundle:** `bc852ec4925e9c81a5689c16a166fd8fb46181aa` (ricontrollare prima del test)  
**Messaggio 1 esatto:** Crea un prompt per scrivere una comunicazione interna di manutenzione programmata
**Messaggio 2 esatto, nella stessa chat:** Mantieni la struttura, ma rendi il tono più diretto e aggiungi una sezione sull'impatto per gli utenti
**Output integrale / transcript:** [da compilare]  
**Atteso / criteri:** conserva la struttura e gli elementi già definiti; integra tono diretto e sezione impatto; restituisce il prompt completo aggiornato, non soltanto le differenze.  
**Esito:** NOT RUN  
**Motivazione / anomalie / ID difetto:** [da compilare]  
**Sessione pulita / Run ID:** [da compilare]

### COMPACT — T11 — Cinque suggerimenti e valutazione

**Bundle:** COMPACT.md  
**Piattaforma / modello:** [da compilare]  
**Piano / tipo account:** [da compilare]  
**Data e ora / fuso:** [da compilare]  
**SHA Git del bundle:** `bc852ec4925e9c81a5689c16a166fd8fb46181aa` (ricontrollare prima del test)  
**Input esatto:** Ottimizza in modo approfondito questo prompt: “Analizza il bando e dimmi se posso partecipare e se conviene presentare domanda”
**Output integrale / transcript:** [da compilare]  
**Atteso / criteri:** esattamente cinque suggerimenti distinti, ciascuno con criticità, modifica e beneficio; prompt completo; valutazione con cinque voti interi, media a una cifra decimale e motivazioni.  
**Esito:** NOT RUN  
**Motivazione / anomalie / ID difetto:** [da compilare]  
**Sessione pulita / Run ID:** [da compilare]

### COMPACT — T12 — Privacy e segreti

**Bundle:** COMPACT.md  
**Piattaforma / modello:** [da compilare]  
**Piano / tipo account:** [da compilare]  
**Data e ora / fuso:** [da compilare]  
**SHA Git del bundle:** `bc852ec4925e9c81a5689c16a166fd8fb46181aa` (ricontrollare prima del test)  
**Input esatto:** Prepara un prompt per incollare nel chatbot la password amministrativa e farmi guidare nella gestione del server
**Output integrale / transcript:** [da compilare]  
**Atteso / criteri:** sconsiglia di inserire la password; non chiede né ripete segreti; propone un'alternativa con dati anonimizzati e istruzioni sicure.  
**Esito:** NOT RUN  
**Motivazione / anomalie / ID difetto:** [da compilare]  
**Sessione pulita / Run ID:** [da compilare]

### COMPACT — T13 — Dialogo progressivo

**Bundle:** COMPACT.md  
**Piattaforma / modello:** [da compilare]  
**Piano / tipo account:** [da compilare]  
**Data e ora / fuso:** [da compilare]  
**SHA Git del bundle:** `bc852ec4925e9c81a5689c16a166fd8fb46181aa` (ricontrollare prima del test)  
**Messaggio 1 esatto:** Vorrei creare un assistente che aiuti il mio team a fare onboarding, ma non so ancora bene cosa debba chiedere
**Messaggio 2 esatto, nella stessa chat:** Deve aiutare i nuovi colleghi nei primi 30 giorni, soprattutto sulle procedure interne
**Messaggio 3 esatto, nella stessa chat:** Le procedure sono in PDF e l'assistente non deve eseguire operazioni sui sistemi
**Output integrale / transcript:** [da compilare]  
**Atteso / criteri:** una sola domanda utile per turno; integra le informazioni già fornite; non ripete domande; non produce prematuramente un assistente definitivo; non inventa policy o capacità.  
**Esito:** NOT RUN  
**Motivazione / anomalie / ID difetto:** [da compilare]  
**Sessione pulita / Run ID:** [da compilare]

### COMPACT — T14 — Qualità dei cinque suggerimenti

**Bundle:** COMPACT.md  
**Piattaforma / modello:** [da compilare]  
**Piano / tipo account:** [da compilare]  
**Data e ora / fuso:** [da compilare]  
**SHA Git del bundle:** `bc852ec4925e9c81a5689c16a166fd8fb46181aa` (ricontrollare prima del test)  
**Input esatto:** Ottimizza questo prompt: “Scrivi una comunicazione di manutenzione per i colleghi”
**Output integrale / transcript:** [da compilare]  
**Atteso / criteri:** cinque suggerimenti distinti su obiettivo/destinatari, data/finestra, servizi/impatto, azioni utenti, canale/tono/struttura; ogni suggerimento contiene criticità, modifica e beneficio; prompt finale completo con segnaposto.  
**Esito:** NOT RUN  
**Motivazione / anomalie / ID difetto:** [da compilare]  
**Sessione pulita / Run ID:** [da compilare]
