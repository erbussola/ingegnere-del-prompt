# Troubleshooting

## Il chatbot non segue le istruzioni
Verifica che il bundle sia stato incollato integralmente e che il modello abbia ricevuto il testo. In una nuova chat ripeti l'avvio e chiedi conferma. Se il servizio impone limiti, usa la versione compatta.

## Il campo istruzioni è troppo corto
Usa `instructions/COMPACT.md`. Non tagliare casualmente sezioni dal Core completo: potresti eliminare regole importanti. Se il servizio supporta fonti di progetto, aggiungi i moduli Core come documenti di riferimento.

## Le risposte sono troppo lunghe
Chiedi un output più breve o specifica limiti e formato nel prompt. Il Core non obbliga a produrre analisi estese per richieste semplici.

## L'assistente fa troppe domande
Specifica quali assunzioni può usare o quali campi desideri lasciare come segnaposto. Segnala che vuoi domande soltanto per dati bloccanti.

## L'assistente inventa informazioni
Riformula la richiesta chiedendo di distinguere dati forniti, inferenze e ipotesi; indicare fonti e lacune; non colmare le informazioni mancanti. Se si tratta di materiale allegato, chiedi riferimenti puntuali al contenuto.

## Il prompt rivisto cambia troppo l'intento
Chiedi di preservare esplicitamente obiettivo, destinatario e vincoli originali e di elencare ogni modifica sostanziale. Il prompt completo deve essere riconsegnato.

## La funzione Projects, Notebook, Gems o Skills non è visibile
La disponibilità può dipendere da piano, account, area geografica e rollout. Usa la normale conversazione con il Core come fallback e verifica le fonti ufficiali della piattaforma.

## Non ricorda una chat precedente
Il contesto potrebbe non essere disponibile. Incolla il riepilogo esportato e gli eventuali file necessari. Non presumere che il nome del progetto o la cronologia siano sufficienti.

## Due documenti danno indicazioni differenti
Verifica la gerarchia: moduli Core per le regole normative, bundle per la distribuzione, deployment per i dettagli del provider. Se due moduli Core sono in conflitto, segnala il problema e non scegliere arbitrariamente.
