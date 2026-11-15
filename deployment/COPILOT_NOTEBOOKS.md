# Deployment — Microsoft Copilot Notebooks

## Ruolo della piattaforma
Microsoft Copilot Notebooks è uno spazio di lavoro contestuale che raccoglie istruzioni e fonti per supportare le chat riferite a un determinato notebook. **Non è un GPT personalizzato equivalente**: non crea un agente universale disponibile in ogni chat, non aggiunge capacità al modello e le fonti/strumenti disponibili dipendono dalla licenza Copilot.

## Disponibilità e differenze di licenza
La documentazione Microsoft distingue:
- **Copilot Chat:** Notebook incluso per gli utenti eleggibili; fino a 50 fonti per notebook.
- **Microsoft 365 Copilot (Work/School):** esperienza estesa; fino a 300 fonti per notebook.

La differenza non è soltanto quantitativa. Nella modalità Copilot Chat non sono disponibili, tra l'altro, riferimenti suggeriti da Work IQ, URL, Teams chats, meeting content, OneNote notebooks e fonti SharePoint/OneDrive. Con la licenza Microsoft Copilot queste tipologie sono supportate secondo le condizioni del tenant. Funzioni come Researcher/Deep Research e altre elaborazioni avanzate sono anch'esse differenziate.

Notebook richiede un account/licenza supportati e i servizi Microsoft 365 previsti dalla documentazione. L'effettiva disponibilità può dipendere da piano, tenant, impostazioni amministrative e rollout. Verifica la matrice licenze prima di progettare il deployment.

## Configurazione
1. Apri Microsoft Copilot e seleziona **Notebooks / Blocchi appunti**. La posizione dell'elemento può variare durante il rollout.
2. Crea o apri un notebook dedicato, per esempio **Ingegnere del Prompt**.
3. Aggiungi le fonti pertinenti e autorizzate: framework RICCE, valutazione, checklist, template ed esempi.
4. Aggiungi le istruzioni del notebook:
   - nell'app Microsoft Copilot: menu **Altre opzioni (...) > Istruzioni**;
   - in OneNote: menu accanto al nome del notebook > **Istruzioni di Copilot**.
5. Incolla `instructions/CORE_INSTRUCTIONS.md`. Se non viene accettato integralmente, usa `instructions/COMPACT.md`.
6. Salva e verifica con i test di `tests/TEST_CASES.md`.

## Separazione tra istruzioni e fonti
- Le **istruzioni** descrivono il comportamento da seguire.
- I **riferimenti** forniscono metodo, esempi e conoscenze specifiche del notebook.
- Le chat e le risposte non sostituiscono un registro portabile di continuità.

Un notebook condiviso può rendere visibili istruzioni e fonti ad altri collaboratori. Condividilo soltanto con persone autorizzate e non caricare segreti o dati non approvati.

## Fallback
Se Notebooks non è disponibile nel tuo account o tenant, usa Copilot Chat o un altro chatbot in una conversazione standard e incolla `instructions/CORE_INSTRUCTIONS.md` come primo messaggio. Il fallback non offre la persistenza e la knowledge base proprie del notebook.

## Fonti ufficiali
- Istruzioni personalizzate per un notebook: https://support.microsoft.com/en-us/microsoft-365-copilot/provide-custom-instructions-for-your-microsoft-365-copilot-notebook
- Introduzione ai notebook: https://support.microsoft.com/it-it/microsoft-365-copilot/get-started-with-microsoft-365-copilot-notebooks
- Funzionamento: https://support.microsoft.com/it-it/microsoft-365-copilot/how-microsoft-365-copilot-notebooks-works
- Differenze di licenza, fonti e limiti: https://support.microsoft.com/en-us/microsoft-365-copilot/copilot-notebooks-licensing

Verifica fonti: 15 novembre 2026.
