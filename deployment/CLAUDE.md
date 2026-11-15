# Deployment — Anthropic Claude

## Opzioni disponibili
La modalità universale tramite chat standard funziona incollando `instructions/CORE_INSTRUCTIONS.md` come primo messaggio.

Claude offre inoltre istruzioni di profilo per preferenze generali e **Projects** con istruzioni e conoscenza di progetto. La documentazione Anthropic indica che i Projects sono disponibili per gli utenti con piani Claude a pagamento; non considerarli un requisito del kit.

## Configurazione di un Project
1. Apri la sezione Projects e crea un nuovo progetto.
2. Apri **Set project instructions**.
3. Incolla `instructions/CORE_INSTRUCTIONS.md` oppure la versione `instructions/COMPACT.md`, in base ai limiti disponibili.
4. Aggiungi alla knowledge base i riferimenti necessari: RICCE, valutazione, template, esempi e guida alla continuità.
5. Avvia una chat nel progetto e prova gli scenari di test.

Le istruzioni del progetto si applicano alle chat in quel progetto. Il contesto di una chat non viene automaticamente condiviso con le altre chat: le informazioni che devono essere riutilizzabili vanno inserite nella knowledge base o esportate in un riepilogo portabile.

## Preferenze di profilo
Le preferenze di profilo sono più adatte a indicazioni generali, non a contenere tutto il Core. Evita di duplicare regole divergenti tra profilo e Project.

## Limiti e fallback
La disponibilità di Projects dipende dal piano e dalle condizioni correnti del servizio. Se non hai accesso, usa la chat standard. Non presumere che il contenuto di una conversazione sia condiviso automaticamente tra chat.

## Fonti ufficiali
- Cosa sono i Projects: https://support.anthropic.com/en/articles/9517075-what-are-projects
- Creare e gestire Projects: https://support.anthropic.com/en/articles/9519177-how-can-i-create-and-manage-projects
- Personalizzazione: https://support.anthropic.com/en/articles/10185728-understanding-claude-s-personalization-features

Verifica fonti: 15 novembre 2026.
