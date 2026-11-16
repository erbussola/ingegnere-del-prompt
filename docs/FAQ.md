# FAQ

## È un'applicazione?
No. È un kit testuale di istruzioni, framework, esempi, template e guide.

## È gratuito?
I materiali del repository sono liberamente disponibili secondo la licenza indicata. Il chatbot e le sue funzioni possono avere piani, limiti o costi propri.

## Servono API o competenze di programmazione?
No. Il percorso principale consiste nel copiare il Core in una normale chat.

## Devo usare RICCE manualmente?
No. RICCE è un metodo interno flessibile. L'assistente seleziona gli elementi pertinenti.

## Perché esistono più file Core?
I moduli in `core/` sono la fonte normativa e spiegano ciascun motore. `instructions/CORE_INSTRUCTIONS.md` riunisce le regole operative in un testo autonomo per il copia-incolla.

## Perché c'è una versione compatta?
Alcuni campi istruzioni hanno limiti di caratteri. La versione compatta conserva il comportamento essenziale sacrificando parte del dettaglio.

## Funziona con qualsiasi chatbot?
Non è garantito. Ogni servizio interpreta le istruzioni in modo diverso e può imporre limiti propri. La compatibilità va testata.

## Copilot Notebooks può ricevere istruzioni?
Sì, Microsoft documenta istruzioni personalizzate per singolo notebook. Copilot Chat prevede fino a 50 fonti; la licenza Microsoft 365 Copilot Work/School fino a 300, con differenze anche nei tipi di fonte e negli strumenti. Non è un GPT personalizzato globale. Consulta [la guida dedicata](../deployment/COPILOT_NOTEBOOKS.md).

## Gemini usa ancora i Gems?
Al 15 novembre 2026 le Skills sono già disponibili nelle chat per account Google personali maggiorenni. I Gems personali 18+ diventano di sola lettura il 17 novembre e vengono rimossi il 17 dicembre 2026; la transizione Workspace è prevista nel 2027. Consulta [la guida Gemini](../deployment/GEMINI.md) e verifica gli aggiornamenti ufficiali.

## Claude Projects è gratuito?
Sì. La documentazione Anthropic aggiornata indica Projects disponibile anche sul piano Free, con massimo cinque progetti. Il RAG avanzato della knowledge base è riservato ai piani a pagamento; la condivisione è prevista per Team ed Enterprise. Consulta [la guida Claude](../deployment/CLAUDE.md).

## Il punteggio 1–10 garantisce un buon risultato?
No. È una valutazione qualitativa del testo del prompt, non una misura scientifica né una garanzia sul comportamento del modello.

## Come avvio il Core senza funzioni speciali?
Apri una nuova chat e incolla integralmente `instructions/CORE_INSTRUCTIONS.md` oppure `instructions/UNIVERSAL.md`. Entrambi sono bundle autonomi; `COMPACT.md` è l'alternativa per campi o contesti con limiti di lunghezza.

## Il chatbot ricorderà il lavoro?
Non necessariamente. Usa un progetto o una knowledge base quando disponibili e conserva un riepilogo portabile per riprendere il lavoro altrove.

## Il repository invia dati a terzi?
No. Il kit è composto da file statici e non introduce chiamate a servizi esterni. I dati inviati al chatbot sono regolati dal relativo fornitore.

## Posso inserire informazioni riservate?
Solo dopo aver verificato policy, autorizzazioni e condizioni del servizio. Non inserire credenziali o segreti.
