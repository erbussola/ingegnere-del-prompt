# Esempi avanzati

## Caso 1 – Confronto tecnico di offerte
**Richiesta iniziale:** «Confronta queste offerte e dimmi quale conviene».

**Analisi:** il verbo “conviene” richiede criteri e priorità; le offerte possono avere voci non omogenee.

**Criticità:** rischio di confrontare prezzi senza normalizzare copertura, durata, esclusioni e costi accessori.

**Cinque suggerimenti:** definire requisiti obbligatori; separare costi una tantum e ricorrenti; normalizzare durata e quantità; citare le fonti nei documenti; evidenziare dati mancanti e rischi contrattuali.

**Prompt finale:** «Agisci come analista procurement IT. Confronta i preventivi allegati per [servizio]. Valuta requisiti obbligatori [elenco], copertura, SLA, durata, costi una tantum, costi ricorrenti, esclusioni e rischi. Riporta per ogni voce il riferimento al documento e alla sezione. Non dedurre valori non presenti: usa “non specificato”. Distingui conformità, vantaggi, criticità e domande da chiarire. Consegna matrice comparativa, sintesi motivata e raccomandazione condizionata alle priorità [priorità].»

**Valutazione esemplificativa:** originale 4,2/10; versione rivista 8,6/10. La differenza deriva da criteri espliciti, tracciabilità e gestione delle lacune; non è una misura scientifica.

## Caso 2 – Progettazione di assistente interno
**Richiesta iniziale:** «Voglio un assistente che aiuti il service desk».

**Analisi:** occorre delimitare utenti, fonti autorizzate, attività e confini di sicurezza.

**Criticità:** nessuna distinzione tra supporto informativo e azioni operative; rischio di inventare procedure.

**Cinque suggerimenti:** definire perimetro L1; indicare knowledge base approvata; stabilire escalation; vietare modifiche ai sistemi; definire formato delle risposte e gestione dell'incertezza.

**Prompt finale:** «Sei un assistente informativo per il service desk di [organizzazione]. Supporta operatori L1 nel classificare richieste e consultare esclusivamente le procedure fornite. Per ogni caso restituisci sintesi, categoria, priorità proposta con motivazione, verifiche non invasive e procedura citata. Non eseguire azioni sui sistemi, non inventare procedure e non chiedere password o token. Se mancano informazioni o la procedura non copre il caso, dichiara il limite e suggerisci escalation a [gruppo]. Non includere dati personali non necessari.»
