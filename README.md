# Ingegnere del Prompt

**Un motore universale di Prompt Engineering, in italiano, pronto da usare nel chatbot che già utilizzi.**

Ingegnere del Prompt è un kit open source di istruzioni, metodi, template, esempi e guide. Consente di creare prompt, ottimizzare quelli esistenti e progettare assistenti AI senza sviluppare un'applicazione e senza API a pagamento obbligatorie.

## Inizia in pochi minuti

1. Apri [instructions/CORE_INSTRUCTIONS.md](instructions/CORE_INSTRUCTIONS.md).
2. Copia il contenuto e incollalo come primo messaggio in una nuova chat. Per istruzioni passo-passo leggi [Avvio universale](deployment/UNIVERSAL_CHAT.md).
3. Descrivi cosa vuoi ottenere: un prompt nuovo, la revisione di un prompt o un assistente AI.

Non servono un account premium, un GPT personalizzato o un progetto: basta una chat che accetti testo. Se la piattaforma impone un limite, usa la [versione compatta](instructions/COMPACT.md).

## Cosa fa

- **Crea prompt** a partire da idee e richieste informali.
- **Ottimizza prompt** esistenti, preservandone l'intento e fornendo cinque suggerimenti nelle revisioni sostanziali.
- **Progetta assistenti AI** con identità, comportamento, istruzioni, vincoli, fonti e test.
- Applica il framework **RICCE** in modo flessibile.
- Valuta i prompt su chiarezza, completezza, specificità, coerenza e utilizzabilità.

## Architettura: un Core, molte piattaforme

Il comportamento centrale è indipendente dal fornitore. Le regole sono descritte nei moduli [core/](core/); il pacchetto [instructions/CORE_INSTRUCTIONS.md](instructions/CORE_INSTRUCTIONS.md) riunisce le regole essenziali in un testo autonomo e copiabile. I documenti [deployment/](deployment/) spiegano come adattare lo stesso Core a ChatGPT, Microsoft Copilot Notebooks, Google Gemini, Anthropic Claude e altri chatbot. Non devono introdurre metodologie divergenti.

## Documentazione

| Area | Contenuto |
|---|---|
| [Core](core/) | Identità, comportamento, conversazione, RICCE, generazione, analisi, valutazione, qualità, modalità, continuità, sicurezza |
| [Istruzioni](instructions/) | Bundle completo, compatto e avvio universale |
| [Deployment](deployment/) | Chat standard, ChatGPT Projects, Copilot Notebooks, Gemini, Claude e altri chatbot |
| [Framework](framework/) | RICCE, valutazione, checklist e continuità |
| [Template](templates/) | Business, marketing, analisi, scrittura e generazione immagini |
| [Esempi](examples/) | Esempi base e avanzati |
| [Test](tests/) | Piano, 12 casi di test e matrice multipiattaforma |
| [Knowledge Base](knowledge/) | Guida all'organizzazione delle fonti |
| [Guide](docs/) | Brief, architettura, installazione, uso, FAQ e troubleshooting |
| [Roadmap](roadmap/FUTURE_VERSIONS.md) | Evoluzione prevista |

## Principi

- **Gratuito e portabile:** nessuna API o servizio a pagamento obbligatorio.
- **Conversazionale:** capisce prima di costruire; chiede solo ciò che serve.
- **Proporzionato:** un prompt breve e preciso può essere migliore di uno lungo.
- **Trasparente:** non inventa contesto, fonti o capacità.
- **Privacy by design:** il kit non trasmette dati e non richiede segreti.
- **Open source:** i materiali originali sono proposti con licenza CC BY-SA 4.0.

La disponibilità di istruzioni permanenti, memoria, caricamento file e strumenti dipende dalla piattaforma e dal piano. La modalità chat standard resta il fallback universale.

## Stato del progetto

Versione 2.0 in sviluppo e revisione. Il Core e la suite documentale sono in implementazione; i test multipiattaforma devono essere eseguiti e registrati prima di dichiarare una compatibilità verificata. Vedi [criteri di accettazione](docs/PROJECT_BRIEF.md) e [test](tests/TEST_PLAN.md).

## Contribuire

Leggi [CONTRIBUTING.md](CONTRIBUTING.md), il [Codice di condotta](CODE_OF_CONDUCT.md) e il [modello Pull Request](.github/PULL_REQUEST_TEMPLATE.md). Le proposte per nuove piattaforme devono includere fonti ufficiali e risultati di test riproducibili.

## Licenza

I materiali originali del progetto sono proposti con licenza [Creative Commons Attribution-ShareAlike 4.0 International](LICENSE.md). Materiali di terze parti e marchi restano soggetti ai rispettivi diritti e condizioni.
