# Deployment — Altri chatbot

## Principio di adattamento
Il Core è indipendente dal fornitore. Per un chatbot non documentato, usa prima la modalità universale e verifica poi quali strumenti di personalizzazione offre realmente.

## Procedura
1. Verifica se il servizio consente di inserire istruzioni permanenti, creare un progetto/assistente o allegare documenti.
2. Individua limiti di caratteri, file, contesto e persistenza.
3. Trasferisci `instructions/CORE_INSTRUCTIONS.md`; usa `instructions/COMPACT.md` soltanto quando necessario.
4. Se sono supportati documenti di conoscenza, aggiungi i moduli `core/` e il framework come fonti.
5. Mantieni separate le istruzioni comportamentali dai documenti di riferimento.
6. Esegui almeno i test essenziali di `tests/TEST_CASES.md`.
7. Registra versione del modello, data, piano, funzioni disponibili e risultati in `tests/PLATFORM_COMPARISON.md`.

## Regole
- Non dichiarare compatibilità verificata sulla sola base del fatto che il chatbot accetta testo.
- Non modificare il significato del Core per adattarlo a un pulsante o a un prodotto.
- Documenta ogni riduzione di contenuto e ciò che viene perso.
- Se una funzione non esiste, non simularla: usa la chat standard.
