# Confronto tra piattaforme

## Scopo
Registrare quanto il Core si comporta in modo coerente su chatbot differenti. Il confronto deve basarsi su prove effettive, non sulla sola disponibilità di una funzione dichiarata dal fornitore.

## Matrice di capacità documentate
Questa tabella descrive le funzioni dichiarate nelle fonti ufficiali consultate il 15 novembre 2026. **Non rappresenta test comportamentali o prove eseguite su account reali.**

| Piattaforma | Modalità persistente | Disponibilità e limiti documentati | Fonti/contesto e differenze | Stato QA documentale |
|---|---|---|---|---|
| ChatGPT | Projects con istruzioni; Custom Instructions globali | Projects per utenti autenticati secondo piano/workspace. File per progetto: Free 5; Go/Plus 25; Edu/Pro/Business/Enterprise 40. Custom Instructions: Free/Go 1.500 caratteri; Plus/Pro/Business/Enterprise/Edu 5.000 caratteri per i campi di testo estesi | Istruzioni di progetto applicate solo nel progetto e prioritarie rispetto a quelle globali. Progetti non equivalgono a GPT personalizzati | **PASS** documentazione ufficiale consultata; configurazione in account non testata |
| Microsoft Copilot Notebooks | Istruzioni personalizzate per singolo notebook | Copilot Chat: fino a 50 fonti; Microsoft 365 Copilot Work/School: fino a 300 | Tipi di riferimento e strumenti differiscono: Copilot Chat non supporta URL esterni, Teams/meeting e fonti SharePoint/OneDrive elencate per Microsoft Copilot. Notebook non equivale a un GPT personalizzato globale | **PARTIALLY VERIFIED** documentazione e matrice licenze verificate; tenant/account non testato |
| Google Gemini | Skills per account Google personali maggiorenni; Gems in transizione | Skills disponibili nelle chat per account personali 18+. Gems read-only dal 17 novembre 2026 e rimossi il 17 dicembre 2026 per account personali; Workspace business/enterprise/non profit a marzo 2027, Education a giugno 2027 | Skills riutilizzabili e applicabili automaticamente o su richiamo; limite file 100 MB; alcune funzioni Gemini e tipi di file non sono supportati | **PARTIALLY VERIFIED** documentazione e date verificate; rollout per account specifici non testato |
| Anthropic Claude | Projects con istruzioni e knowledge base | Disponibile anche Free (massimo 5 Projects); piani a pagamento per RAG avanzato; condivisione Team/Enterprise | Project organizza chat, istruzioni e conoscenze, ma non è un GPT personalizzato pubblicato. Il contesto tra chat va aggiunto alla knowledge base per essere riusato | **PASS** disponibilità documentata; account e comportamento del Core non testati |
| Universal Chat | Istruzioni incollate come primo messaggio | Nessun progetto o piano aggiuntivo richiesto; servono una chat e capacità di accettare il testo | Le istruzioni valgono nel contesto della conversazione e non garantiscono persistenza in chat future | **PARTIALLY VERIFIED** percorso testuale ispezionato; non testato su account esterni |
| Altri chatbot | Da verificare prodotto per prodotto | Da verificare | Usare chat standard come fallback e non dichiarare compatibilità senza test | **NOT VERIFIED** |

## Scheda di esecuzione comportamentale
Compilare una scheda per ogni combinazione piattaforma/modello.

| Campo | Valore |
|---|---|
| Piattaforma e URL | [valore] |
| Piano / tipo account / workspace | [valore] |
| Modello e versione mostrata | [valore] |
| Data del test | [AAAA-MM-GG] |
| Modalità di configurazione | [chat / istruzioni / progetto / notebook / skill] |
| Bundle e versione | [CORE / COMPACT / UNIVERSAL, versione] |
| Casi eseguiti | [T01…T15] |
| Risultati | [PASS / PARTIALLY VERIFIED / FAIL / NOT RUN] |
| Problemi o limiti osservati | [dettagli] |
| Evidenze | [link o estratti senza dati sensibili] |

## Regole di confronto
- Utilizzare input equivalenti, non necessariamente output identici.
- Registrare modello, piano, account e data: il comportamento può cambiare.
- Separare limiti della piattaforma, limiti di licenza e difetti delle istruzioni.
- Non attribuire alla piattaforma funzioni non disponibili nell'account testato.
- Non definire un sistema “compatibile” finché non sono stati eseguiti test rappresentativi.
- Non inserire dati riservati nelle evidenze pubbliche.
- Una simulazione con il modello utilizzato per la QA non è un test multipiattaforma.

## Fonti ufficiali
### ChatGPT
- Projects e limiti: https://help.openai.com/en/articles/10169521-projects-in-chatgpt
- Custom Instructions e limiti per piano: https://help.openai.com/en/articles/8096356-chatgpt-custom-instructions

### Microsoft Copilot Notebooks
- Istruzioni per un notebook: https://support.microsoft.com/en-us/microsoft-365-copilot/provide-custom-instructions-for-your-microsoft-365-copilot-notebook
- Introduzione: https://support.microsoft.com/it-it/microsoft-365-copilot/get-started-with-microsoft-365-copilot-notebooks
- Funzionamento: https://support.microsoft.com/it-it/microsoft-365-copilot/how-microsoft-365-copilot-notebooks-works
- Differenze di licenza e limiti: https://support.microsoft.com/en-us/microsoft-365-copilot/copilot-notebooks-licensing

### Google Gemini
- Transizione Gems → Skills, date e limiti: https://support.google.com/gemini/answer/18560919

### Anthropic Claude
- Projects, disponibilità Free e RAG: https://support.claude.com/en/articles/9517075-what-are-projects
- Creare e gestire Projects: https://support.claude.com/en/articles/9519177-how-can-i-create-and-manage-projects

Ultima verifica documentale: 15 novembre 2026. Ricontrollare fonti e disponibilità prima di ogni rilascio.
