# Esempi avanzati

## 1 — Confronto tecnico di offerte
**Richiesta:** «Confronta queste offerte e dimmi quale conviene».

**Analisi:** il termine “conviene” richiede criteri e priorità; le offerte potrebbero non essere omogenee.

**Cinque suggerimenti:** definire requisiti obbligatori; separare costi una tantum e ricorrenti; normalizzare durata e quantità; citare documento e sezione; evidenziare dati mancanti e rischi contrattuali.

**Prompt finale:** «Agisci come analista procurement IT. Confronta i preventivi allegati per [SERVIZIO]. Valuta requisiti obbligatori [ELENCO], copertura, SLA, durata, costi una tantum, costi ricorrenti, esclusioni e rischi. Riporta per ogni voce il riferimento al documento e alla sezione. Non dedurre valori non presenti: usa “non specificato”. Distingui conformità, vantaggi, criticità e domande da chiarire. Consegna matrice comparativa, sintesi motivata e raccomandazione condizionata alle priorità [PRIORITÀ]».

## 2 — Assistente per service desk
**Richiesta:** «Voglio un assistente che aiuti il service desk».

**Cinque suggerimenti:** delimitare attività L1; indicare fonti approvate; stabilire escalation; vietare azioni sui sistemi; definire formato di risposta e gestione dell'incertezza.

**Prompt finale:** «Sei un assistente informativo per il service desk di [ORGANIZZAZIONE]. Supporta operatori L1 nel classificare richieste e consultare esclusivamente le procedure fornite. Per ogni caso restituisci sintesi, categoria, priorità proposta con motivazione, verifiche non invasive e procedura citata. Non eseguire azioni sui sistemi, non inventare procedure e non chiedere password o token. Se mancano informazioni o la procedura non copre il caso, dichiara il limite e suggerisci escalation a [GRUPPO]. Non includere dati personali non necessari».

## 3 — Programmazione
**Richiesta:** «Scrivimi uno script che elimina i file vecchi».

**Prompt finale:** «Agisci come sviluppatore esperto di [LINGUAGGIO] su [SISTEMA]. Prepara uno script che individua file più vecchi di [GIORNI] in [PERCORSO]. Prima implementa una modalità di sola simulazione che mostri i file selezionati, motivazione e spazio stimato. Non eliminare file fuori dal percorso specificato, non seguire symlink/reparse point e gestisci errori e permessi. Chiedi conferma esplicita prima di abilitare la cancellazione effettiva. Includi commenti, prerequisiti, esempio d'uso e piano di test. Se una scelta dipende dall'ambiente, chiedi versione e shell prima di assumere i comandi».

## 4 — Analisi documentale
**Richiesta:** «Analizza questa procedura e trova errori».

**Prompt finale:** «Agisci come revisore tecnico. Analizza esclusivamente la procedura allegata. Per ogni rilievo riporta titolo/sezione e, quando disponibili, pagina o paragrafo. Separa errore verificabile, ambiguità, omissione e suggerimento. Non integrare prassi esterne come se fossero contenute nel documento. Consegna tabella con gravità, evidenza, impatto e correzione proposta. Indica esplicitamente ciò che non può essere verificato con il materiale disponibile».

## 5 — Valutazione esemplificativa
I punteggi dei casi sono da assegnare durante l'esecuzione, non sono preimpostati. Non attribuire al prompt una capacità di validazione che richiede l'esecuzione reale su un ambiente.
