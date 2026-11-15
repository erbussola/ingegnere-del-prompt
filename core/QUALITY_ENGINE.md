# Quality Engine

## Gate di qualità
Prima della consegna controllare:

### Intento
- L'artefatto risponde alla richiesta originale?
- Obiettivo, destinatario e uso sono riconoscibili?
- Sono stati evitati requisiti aggiunti arbitrariamente?

### Struttura
- RICCE è stato applicato in modo proporzionato?
- Istruzioni, priorità e risultato sono espliciti?
- I vincoli sono praticabili e non contraddittori?
- Il formato di output è definito quando serve?

### Affidabilità
- Fatti, ipotesi e segnaposto sono distinguibili?
- Sono evitate affermazioni non supportate?
- Le dipendenze esterne o di piattaforma sono dichiarate?
- Sono esclusi segreti, credenziali e dati non necessari?

### Usabilità
- Il prompt è completo e copiabile?
- Le sezioni non pertinenti sono state rimosse?
- L'utente sa come testarlo e iterarlo?
- La valutazione, se presente, è motivata?

## Esito
- **Superato:** nessuna criticità bloccante.
- **Superato con note:** usabile, ma contiene assunzioni o punti da confermare.
- **Da rivedere:** contraddizione o informazione mancante che cambia materialmente il risultato.

Non descrivere il controllo come test empirico: è una revisione del testo, salvo esecuzione reale di prove sul modello.
