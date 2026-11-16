# Architettura — Universal Core

## Principio fondamentale
**Un solo motore centrale. Molteplici modalità di utilizzo. Nessuna duplicazione delle regole fondamentali.**

Ingegnere del Prompt è un kit documentale statico. Il repository conserva le istruzioni e le risorse; il chatbot di destinazione interpreta il bundle. Non esistono backend, database, API, telemetria o servizi necessari per l'uso.

## Livelli

### 1. Core universale
La directory `core/` è la fonte normativa e scompone il comportamento in moduli:
- Identity Engine
- Behavioral Engine
- Conversation Engine
- RICCE Engine
- Prompt Analysis Engine
- Prompt Generation Engine
- Prompt Evaluation Engine
- Quality Engine
- Operating Modes
- Memory and Continuity Engine
- Security and Privacy Principles

Un cambiamento a un modulo Core richiede una revisione delle istruzioni distribuibili e dei test correlati.

### 2. Istruzioni distribuibili
`instructions/CORE_INSTRUCTIONS.md` riunisce in un documento autonomo le regole necessarie al funzionamento in una singola chat. `instructions/COMPACT.md` conserva le funzioni essenziali con minore dettaglio. `instructions/UNIVERSAL.md` spiega il primo avvio.

Il bundle è deliberatamente autosufficiente: un chatbot non può dipendere dai link del repository per comprendere le istruzioni appena copiate. Per evitare divergenze, ogni modifica al Core deve aggiornare contestualmente i bundle e la checklist di qualità.

### 3. Deployment
`deployment/` descrive come trasferire il medesimo Core nelle funzioni disponibili su ChatGPT, Copilot Notebooks, Gemini, Claude o altri chatbot. I file deployment non devono modificare identità, RICCE, modalità o criteri di qualità. Registrano solo interfaccia, limiti, disponibilità e fonti del provider.

### 4. Risorse di supporto
- `framework/`: metodo e criteri di valutazione.
- `templates/`: prompt riutilizzabili per domini specifici.
- `examples/`: esempi illustrativi.
- `tests/`: casi e risultati di verifica.
- `knowledge/`: indicazioni per le basi di conoscenza.
- `docs/`: orientamento, uso, installazione e troubleshooting.
- `roadmap/`: evoluzione.

## Flusso di utilizzo
Richiesta dell'utente → comprensione e classificazione → applicazione del Core/RICCE → costruzione o analisi → controllo qualità → consegna del prompt → eventuale iterazione.

## Principi di manutenzione
1. Core come fonte di verità.
2. Un bundle completo e uno compatto, senza fork metodologici.
3. Adattamenti piattaforma separati e verificati.
4. Test aggiornati quando cambiano le regole.
5. Decisioni architetturali documentate.
6. Nessuna funzionalità dichiarata compatibile senza verifica.

## Diagramma logico
```text
                    +---------------------+
                    |    Richiesta utente |
                    +----------+----------+
                               |
                    +----------v----------+
                    |     Universal Core  |
                    | Identity / Behavior |
                    | Conversation / RICCE|
                    | Analysis / Generate |
                    | Evaluate / Quality  |
                    | Continuity / Safety |
                    +----------+----------+
                               |
                    +----------v----------+
                    |    Operating Modes  |
                    | Create / Optimize   |
                    | Design Assistant    |
                    +----------+----------+
                               |
                    +----------v----------+
                    | Output + Iteration  |
                    +---------------------+

   Core -> Instructions (full/compact) -> Platform deployments
   Core -> Framework / Tests / Templates / Examples
```

## Limiti
La portabilità delle istruzioni non rende identici i modelli. Contesto, memoria, strumenti, limiti di testo, piani e politiche restano dipendenti dal provider.
