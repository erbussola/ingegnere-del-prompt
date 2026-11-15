# Project Brief — Ingegnere del Prompt 2.0

## Visione
Realizzare un motore universale di Prompt Engineering che consenta a chiunque di creare il proprio assistente personale specializzato, utilizzando il chatbot che già possiede.

## Missione
Preservare il più possibile l'esperienza conversazionale del GPT di riferimento **The Prompt Master**, ricostruendola sulla base delle caratteristiche osservabili e migliorandone chiarezza, affidabilità, portabilità e qualità. Non si presume di avere accesso alle istruzioni riservate dell'assistente originale.

## Prodotto
Un kit documentale open source, non necessariamente un'applicazione, composto da:
- Core comportamentale e moduli metodologici.
- Istruzioni universali complete e compatte.
- Pacchetti di deployment.
- Framework RICCE e valutazione qualitativa.
- Template, esempi, test e guide.
- Sistema di continuità portabile.

## Destinatari
Principianti, professionisti, studenti, creatori di contenuti e team che usano chatbot AI in contesti personali o professionali.

## Funzioni fondamentali
1. Creazione di prompt da idee.
2. Analisi e ottimizzazione di prompt esistenti.
3. Progettazione di assistenti AI completi.
4. Suggerimenti di miglioramento specifici nelle ottimizzazioni sostanziali.
5. Valutazione qualitativa su cinque criteri.
6. Iterazione controllata e continuità tra sessioni.

## Requisiti
- Italiano predefinito, adattamento alla lingua dell'utente.
- Dialogo amichevole e professionale.
- RICCE flessibile, non rigido.
- Nessuna API o servizio a pagamento obbligatorio.
- Utilizzabile mediante una normale conversazione.
- Nessuna dipendenza obbligatoria da un provider.
- Nessuna trasmissione dati introdotta dal kit.
- Documentazione comprensibile anche ai principianti.
- Distinzione tra regole universali e specificità di piattaforma.

## Architettura
I moduli `core/` sono la fonte normativa del comportamento. `instructions/` contiene il bundle autonomo per il copia-incolla. `deployment/` adatta il medesimo Core alle piattaforme. Framework, template, esempi e test sono risorse di supporto. La struttura è dettagliata in [ARCHITECTURE.md](ARCHITECTURE.md).

## Criteri di accettazione
La 2.0 non sarà dichiarata completata finché:
- i moduli Core e i bundle completo/compatto sono coerenti;
- le tre modalità operative sono definite;
- RICCE e valutazione sono documentati e utilizzabili;
- i deployment richiesti sono presenti e basati su fonti ufficiali;
- memoria e continuità portabile sono descritte;
- sono disponibili almeno 10 casi completi;
- template e guide sono utilizzabili;
- licenza, community, privacy e sicurezza sono documentate;
- i link e i controlli documentali sono verificati;
- i test comportamentali sono eseguiti e i risultati registrati, senza confondere disponibilità di documentazione e compatibilità empirica.

## Stato
Sviluppo iniziale della versione 2.0. La presenza di un test case non equivale al suo superamento. La compatibilità multipiattaforma deve essere dimostrata con prove ripetibili.
