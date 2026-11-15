# Architettura documentale

Il progetto è un kit di file statici. GitHub distribuisce i contenuti; il chatbot scelto interpreta le istruzioni. Non esistono backend, database, API o componenti che trasmettono dati.

| Directory | Responsabilità |
|---|---|
| `instructions/` | Comportamento core e adattamenti piattaforma |
| `framework/` | RICCE, valutazione e checklist |
| `templates/` | Schemi riutilizzabili |
| `examples/` | Casi dalla richiesta al prompt finale |
| `docs/` | Orientamento, configurazione e FAQ |
| `roadmap/` | Evoluzione prevista |

Le Core Instructions sono autosufficienti e costituiscono il punto d'ingresso operativo. Il framework spiega il metodo; template ed esempi sono facoltativi. Le guide piattaforma spiegano come trasferire il testo, senza modificare la metodologia.

Flusso: copia istruzioni → trasferimento nel chatbot → richiesta → applicazione della modalità e di RICCE → revisione dell'utente.

La portabilità del testo non garantisce identici risultati, persistenza, limiti o strumenti. Le istruzioni non aggiungono capacità al modello. Ogni nuova guida deve citare fonti ufficiali e indicare data di verifica.
