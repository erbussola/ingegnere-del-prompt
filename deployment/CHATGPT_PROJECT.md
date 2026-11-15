# Deployment — ChatGPT Projects

## Opzioni disponibili
La modalità universale tramite chat standard resta gratuita e non richiede un progetto. In alternativa, ChatGPT offre:
- **Progetti:** spazi di lavoro con chat, file/fonti e istruzioni specifiche del progetto.
- **Istruzioni personalizzate globali:** preferenze generali applicate alle conversazioni, quando attive.

I Progetti sono disponibili agli utenti ChatGPT autenticati, soggetti al piano e alle impostazioni del workspace. Non è corretto considerarli una funzione esclusiva dei piani premium.

## Configurazione di un Progetto
1. Seleziona **Nuovo progetto** nella barra laterale.
2. Apri il menu del progetto (**•••**) e seleziona **Impostazioni del progetto**.
3. Inserisci il testo di `instructions/CORE_INSTRUCTIONS.md` nelle istruzioni del progetto. Se il campo o l'esperienza del tuo account non accetta il testo completo, usa `instructions/COMPACT.md`.
4. Aggiungi come fonti i documenti pertinenti: RICCE, valutazione, checklist, template ed esempi. Non è necessario caricare tutto il repository.
5. Avvia una chat nel progetto e verifica il comportamento con `tests/TEST_CASES.md`.

Le istruzioni del progetto si applicano soltanto alle chat del progetto e prevalgono sulle istruzioni personalizzate globali. Il contesto delle chat e dei file può essere riutilizzato secondo le impostazioni di memoria del progetto e del workspace.

## Limiti di file documentati
Il numero massimo di file caricabili per progetto dipende dal piano:
- **Free:** 5 file per progetto.
- **Go e Plus:** 25 file per progetto.
- **Edu, Pro, Business ed Enterprise:** 40 file per progetto.

È possibile caricare al massimo 10 file per singola operazione. Il numero di progetti creabili è illimitato secondo la documentazione consultata. I limiti possono cambiare: controlla la pagina ufficiale aggiornata prima di pianificare una knowledge base ampia.

## Istruzioni personalizzate globali
Le Custom Instructions sono disponibili su tutti i piani, ma i campi di testo estesi hanno un limite di 1.500 caratteri ciascuno. Per questo motivo il Core completo non è adatto a essere inserito integralmente nelle sole istruzioni globali: usa un Progetto, quando disponibile, oppure la chat universale. Le impostazioni globali non sostituiscono la conoscenza specifica di un progetto.

## Cosa non fa un Progetto
Un Progetto non è un GPT personalizzato pubblicato né un agente autonomo. Fornisce un contesto organizzato, istruzioni specifiche e fonti alle chat al suo interno. Strumenti, modelli, memoria e controlli restano quelli disponibili nel piano e nel workspace.

## Materiali suggeriti
- Istruzioni: `instructions/CORE_INSTRUCTIONS.md` (o `COMPACT.md`).
- Metodo: `framework/RICCE.md`.
- Valutazione: `framework/PROMPT_EVALUATION.md`.
- Test: `tests/TEST_CASES.md`.
- Continuità: `core/CONTINUITY_ENGINE.md`.

## Fonti ufficiali
- Progetti ChatGPT e limiti: https://help.openai.com/en/articles/10169521-projects-in-chatgpt
- Istruzioni personalizzate: https://help.openai.com/en/articles/8096356-chatgpt-custom-instructions

Verifica fonti: 15 novembre 2026.
