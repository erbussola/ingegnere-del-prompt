# Confronto tra piattaforme

## Scopo
Registrare quanto il Core si comporta in modo coerente su chatbot differenti. Il confronto deve basarsi su prove effettive, non sulla sola disponibilità di una funzione dichiarata dal fornitore.

## Matrice di capacità documentate
Questa tabella descrive le opzioni di configurazione documentate al 15 novembre 2026; non è un test comportamentale.

| Piattaforma | Istruzioni persistenti / spazio dedicato | Fonti o file | Limiti / note |
|---|---|---|---|
| ChatGPT | Istruzioni personalizzate globali; istruzioni per Progetto | File e fonti nel progetto | Istruzioni di Progetto prevalgono su quelle globali; disponibilità e limiti dipendono da piano/workspace |
| Microsoft Copilot Notebooks | Istruzioni personalizzate per singolo notebook | Riferimenti aggiunti al notebook | Licenze richieste e rollout progressivo; non equivale a un assistente globale |
| Google Gemini | Gems in migrazione a skills per account personali da novembre 2026; work/school nel 2027 | Fonti/file per Gem quando disponibili | Rollout e UI possono variare; verificare se l'account mostra Gems o skills |
| Anthropic Claude | Istruzioni di profilo; istruzioni per Project | Knowledge base di Project | Projects disponibili sui piani a pagamento; le chat non condividono automaticamente contesto non aggiunto alla knowledge base |
| Altri chatbot | Da verificare prodotto per prodotto | Da verificare | Usare chat standard come fallback |

## Scheda di esecuzione
Compilare una scheda per ogni combinazione piattaforma/modello.

| Campo | Valore |
|---|---|
| Piattaforma e URL | [valore] |
| Piano / tipo account / workspace | [valore] |
| Modello e versione mostrata | [valore] |
| Data del test | [AAAA-MM-GG] |
| Modalità di configurazione | [chat / istruzioni / progetto / notebook / skill] |
| Versione Core | [es. 2.0.0] |
| Casi eseguiti | [T01…T12] |
| Risultati | [superato / parziale / non superato] |
| Problemi o limiti osservati | [dettagli] |
| Evidenze | [link o estratti senza dati sensibili] |

## Regole di confronto
- Utilizzare input equivalenti, non necessariamente output identici.
- Registrare modello, piano e data: il comportamento può cambiare.
- Separare i limiti della piattaforma dai difetti delle istruzioni.
- Non attribuire alla piattaforma funzioni non disponibili nell'account testato.
- Non definire un sistema “compatibile” finché non sono stati eseguiti test rappresentativi.
- Non inserire dati riservati nelle evidenze pubbliche.

## Fonti ufficiali per le capacità
- ChatGPT Projects: https://help.openai.com/en/articles/10169521-projects-in-chatgpt
- ChatGPT Custom Instructions: https://help.openai.com/en/articles/8096356-chatgpt-custom-instructions
- Microsoft Copilot Notebooks — istruzioni: https://support.microsoft.com/en-us/microsoft-365-copilot/provide-custom-instructions-for-your-microsoft-365-copilot-notebook
- Microsoft Copilot Notebooks — panoramica: https://support.microsoft.com/it-it/microsoft-365-copilot/get-started-with-microsoft-365-copilot-notebooks
- Gemini — transizione Gems/skills: https://support.google.com/gemini/answer/18560919
- Gemini — Gems: https://support.google.com/gemini/answer/15146780
- Claude Projects: https://support.anthropic.com/en/articles/9517075-what-are-projects
- Claude Projects — gestione: https://support.anthropic.com/en/articles/9519177-how-can-i-create-and-manage-projects

Ultima verifica documentale: 15 novembre 2026. Ricontrollare le fonti prima di ogni rilascio.
