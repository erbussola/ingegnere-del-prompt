# Deployment — Microsoft Copilot Notebooks

## Cosa consente la piattaforma
Microsoft documenta Notebook di Copilot come uno spazio che riunisce riferimenti e contenuti pertinenti. È possibile configurare **istruzioni personalizzate per il singolo notebook**. Non equivale a installare un assistente globale che opera in ogni conversazione Copilot.

La disponibilità dipende dalle licenze e dal rollout. La documentazione Microsoft aggiornata a novembre 2026 indica requisiti di licenza Microsoft Copilot o Copilot Chat e un piano di servizio SharePoint o OneDrive per creare notebook; la disponibilità può variare in base al tipo di account e all'esperienza distribuita.

## Configurazione
1. Apri Microsoft Copilot e seleziona **Blocchi appunti / Notebooks**. In alcune esperienze la voce può trovarsi nel launcher delle app.
2. Crea o apri un notebook dedicato, per esempio **Ingegnere del Prompt**.
3. Aggiungi fonti pertinenti nell'area dei riferimenti: Core, RICCE, valutazione, template, esempi e continuità.
4. Apri le istruzioni del notebook:
   - nell'app Microsoft Copilot: menu **Altre opzioni (...) > Istruzioni**;
   - in OneNote: menu accanto al nome del notebook > **Istruzioni di Copilot**.
5. Incolla `instructions/CORE_INSTRUCTIONS.md`. Se il campo impone un limite, usa `instructions/COMPACT.md`.
6. Salva e verifica con uno scenario dei test.

## Istruzioni e fonti: ruoli distinti
- Le **istruzioni** descrivono come Copilot deve comportarsi.
- I **riferimenti** forniscono metodo, esempi, definizioni e contenuti da consultare.
- Le chat e le risposte prodotte non sostituiscono il registro portabile di continuità.

Un notebook condiviso può rendere visibili le istruzioni e consentire modifiche collaborative: condividilo solo con persone autorizzate.

## Limiti e fallback
La UI Home e la distribuzione delle funzionalità sono soggette a rollout; se il notebook o il campo istruzioni non è disponibile, usa una chat standard e incolla `instructions/CORE_INSTRUCTIONS.md` come primo messaggio. Non presumere che un notebook esista in ogni licenza o tenant.

## Fonti ufficiali
- Istruzioni personalizzate per un notebook: https://support.microsoft.com/en-us/microsoft-365-copilot/provide-custom-instructions-for-your-microsoft-365-copilot-notebook
- Introduzione ai notebook: https://support.microsoft.com/it-it/microsoft-365-copilot/get-started-with-microsoft-365-copilot-notebooks
- Come funzionano i notebook: https://support.microsoft.com/it-it/microsoft-365-copilot/how-microsoft-365-copilot-notebooks-works

Verifica fonti: 15 novembre 2026. Alcune funzioni sono in distribuzione graduale.
