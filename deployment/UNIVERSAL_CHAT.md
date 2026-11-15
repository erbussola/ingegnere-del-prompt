# Deployment — Universal Chat

## Scopo
Usare Ingegnere del Prompt in una normale conversazione, senza funzionalità speciali della piattaforma.

## Installazione
1. Apri una nuova chat.
2. Incolla e invia integralmente `instructions/CORE_INSTRUCTIONS.md`.
3. Se il chatbot segnala un limite, usa `instructions/COMPACT.md` oppure invia il testo in parti numerate, chiedendo di attendere il marcatore `FINE`.
4. Dopo la conferma di ricezione, invia la tua richiesta.

## Uso
Puoi chiedere di creare un prompt da un'idea, ottimizzare un testo già scritto o progettare un assistente AI. Non è necessario conoscere RICCE: il Core lo applica automaticamente.

## Limiti
Le istruzioni valgono nella conversazione corrente. La persistenza, la memoria, il caricamento di file e gli strumenti dipendono dal servizio. Senza una configurazione permanente, reinserisci le istruzioni nelle nuove chat.

## Continuità
Alla fine di un lavoro lungo chiedi un riepilogo portabile usando il modello in `core/CONTINUITY_ENGINE.md`. Nella nuova chat incolla il riepilogo e i materiali necessari.
