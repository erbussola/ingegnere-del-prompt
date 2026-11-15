# Deployment — Anthropic Claude

## Opzioni disponibili
La modalità universale tramite chat standard funziona incollando `instructions/CORE_INSTRUCTIONS.md` come primo messaggio.

Claude offre anche:
- **Projects:** spazi di lavoro con chat, istruzioni e knowledge base.
- **Istruzioni di profilo:** indicazioni generali a livello account.
- **Skills:** comportamenti e competenze riutilizzabili, con modalità e limiti propri.

## Disponibilità di Projects
La documentazione Anthropic aggiornata indica che Projects è disponibile anche per gli account Claude Free, con un massimo di **cinque Projects**. I piani a pagamento Pro, Max, Team ed Enterprise offrono ulteriori capacità; in particolare, la knowledge base con RAG avanzato è disponibile sui piani a pagamento. La condivisione dei Projects è limitata ai piani Team ed Enterprise e soggetta alle impostazioni dell'organizzazione.

Non confondere l'accesso gratuito a Projects con la disponibilità delle funzioni avanzate RAG o di collaborazione.

## Configurazione di un Project
1. Apri **Projects** dalla barra laterale oppure visita https://claude.ai/projects.
2. Seleziona **New Project** e assegna un nome e una descrizione.
3. Apri il progetto e seleziona **Set project instructions**.
4. Incolla `instructions/CORE_INSTRUCTIONS.md`. Se il campo non accetta il testo completo, usa `instructions/COMPACT.md`.
5. Aggiungi alla knowledge base i riferimenti necessari: RICCE, valutazione, checklist, template ed esempi. Evita di caricare l'intero repository senza motivo.
6. Avvia una chat nel progetto e verifica gli scenari di `tests/TEST_CASES.md`.

Le istruzioni e la knowledge base del progetto si applicano alle chat del progetto. Il contesto di una chat non viene automaticamente condiviso con le altre chat del progetto: inserisci nella knowledge base le informazioni che devono essere comuni oppure conserva un riepilogo portabile.

## Preferenze di profilo
Usa le istruzioni di profilo soltanto per preferenze generali. Evita di duplicare nel profilo le regole operative del Core se hai già un Project configurato.

## Limiti e fallback
Projects non è equivalente a un GPT personalizzato pubblicato: è uno spazio di lavoro con istruzioni, file e chat. Modelli, limiti di utilizzo, RAG e funzioni disponibili dipendono dal piano. Se non hai accesso a Projects, usa la chat standard.

## Fonti ufficiali
- Cosa sono i Projects, disponibilità Free e funzioni RAG: https://support.claude.com/en/articles/9517075-what-are-projects
- Creare e gestire Projects: https://support.claude.com/en/articles/9519177-how-can-i-create-and-manage-projects
- Personalizzazione Claude: https://support.claude.com/en/articles/10185728-understanding-claude-s-personalization-features

Verifica fonti: 15 novembre 2026.
