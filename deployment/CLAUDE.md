# Deployment — Anthropic Claude

## Opzioni disponibili
La modalità universale tramite chat standard funziona incollando `instructions/CORE_INSTRUCTIONS.md` come primo messaggio.

Claude offre anche:
- **Projects:** spazi di lavoro con chat e knowledge base.
- **Istruzioni di profilo:** indicazioni generali a livello account.
- **Istruzioni di progetto:** regole specifiche del progetto, la cui disponibilità va verificata rispetto al piano.
- **Skills:** comportamenti e competenze riutilizzabili, con modalità e limiti propri.

## Disponibilità di Projects
La documentazione Anthropic indica che Projects è disponibile anche per gli account Claude Free, con un massimo di **cinque Projects**. I piani a pagamento offrono ulteriori capacità, in particolare il RAG avanzato della knowledge base (Pro, Max, Team ed Enterprise). La condivisione dei Projects è documentata per Team ed Enterprise e dipende dalle impostazioni dell'organizzazione.

**Attenzione alle istruzioni persistenti:** la pagina ufficiale di personalizzazione Claude indica le project instructions tra le funzioni dei piani a pagamento. Le informazioni di disponibilità generale dei Projects non implicano quindi che ogni account Free possa impostare istruzioni personalizzate nel progetto. Verifica l'interfaccia e le funzioni effettivamente presenti nell'account.

## Configurazione di un Project
1. Apri **Projects** dalla barra laterale oppure visita https://claude.ai/projects.
2. Seleziona **New Project** e assegna un nome e una descrizione.
3. Se il tuo piano mostra **Set project instructions**, incolla `instructions/CORE_INSTRUCTIONS.md`. Se il campo non accetta il testo completo, usa `instructions/COMPACT.md`.
4. Se il piano non offre project instructions, usa il percorso universale: apri una chat all'interno del progetto o una chat standard e incolla il Core come primo messaggio. La persistenza tra chat non è garantita.
5. Aggiungi alla knowledge base i riferimenti necessari, se il piano lo consente: RICCE, valutazione, checklist, template ed esempi. Evita di caricare l'intero repository senza motivo.
6. Verifica gli scenari di `tests/TEST_CASES.md`.

Le istruzioni di progetto (quando disponibili) e la knowledge base si applicano alle chat del progetto. Non presumere che il contesto di una chat venga condiviso automaticamente con le altre: inserisci nella knowledge base le informazioni comuni oppure conserva un riepilogo portabile.

## Preferenze di profilo
Usa le istruzioni di profilo soltanto per preferenze generali. Evita di duplicare nel profilo le regole operative del Core se hai già un Project configurato.

## Limiti e fallback
Projects non è equivalente a un GPT personalizzato pubblicato: è uno spazio di lavoro. Modelli, limiti di utilizzo, istruzioni persistenti, RAG e condivisione dipendono dal piano. Se non hai accesso a una funzione, usa la chat standard con il Core incollato come primo messaggio.

## Fonti ufficiali
- Projects, disponibilità Free e RAG: https://support.claude.com/en/articles/9517075-what-are-projects
- Creare e gestire Projects: https://support.claude.com/en/articles/9519177-how-can-i-create-and-manage-projects
- Personalizzazione Claude e disponibilità delle istruzioni di progetto: https://support.claude.com/en/articles/10185728-understanding-claude-s-personalization-features

Verifica fonti: 15 novembre 2026. Le pagine del fornitore possono essere aggiornate o mostrare disponibilità diverse durante rollout e beta.
