# Framework RICCE

RICCE è il metodo comune del progetto per progettare, analizzare e ottimizzare prompt. È una guida flessibile: non va applicata come checklist rigida né trasformata in cinque paragrafi obbligatori.

| Sigla | Componente | Contenuto da definire |
|---|---|---|
| R | Role | Ruolo, competenze e prospettiva utili |
| I | Instructions | Obiettivo, compiti, passaggi, priorità e output |
| C | Context | Scenario, destinatari, informazioni e risorse |
| C | Constraints | Limiti, esclusioni, requisiti, sicurezza e formato |
| E | Examples | Esempi di input/output o comportamento desiderato |

## R — Role
Definisce la prospettiva da cui il modello deve lavorare. Specifica competenze funzionali al compito, evitando titoli altisonanti privi di valore operativo.

Esempio: «Agisci come consulente didattico con esperienza nella formazione degli adulti».

## I — Instructions
Definisce cosa fare e in quale ordine. Usa verbi operativi, priorità, criteri di completamento e output atteso.

Esempio: «Progetta un percorso di quattro settimane con tre esercizi pratici a settimana e una verifica finale».

## C — Context
Fornisce scenario, destinatari, obiettivi, dati e risorse disponibili. Distingue ciò che è noto dalle informazioni mancanti.

Esempio: «I partecipanti sono principianti, dispongono di 20 minuti al giorno e utilizzano uno smartphone».

## C — Constraints
Stabilisce limiti, esclusioni, requisiti, lingua, tono, lunghezza, fonti e formato. I vincoli devono essere realizzabili e non contraddittori.

Esempio: «Non richiedere attrezzatura aggiuntiva; consegna una tabella settimanale».

## E — Examples
Mostra un input/output, uno schema o un comportamento desiderato quando è difficile descriverlo in modo astratto.

Esempio: «Per ogni lezione indica obiettivo, durata, materiali, esercizio e verifica».

## Applicazione pratica
1. Comprendi il risultato desiderato.
2. Rileva quali elementi RICCE sono già contenuti nella richiesta.
3. Aggiungi solo quelli mancanti e utili.
4. Chiedi chiarimenti solo per lacune che cambiano materialmente il risultato.
5. Rimuovi ripetizioni e contraddizioni.
6. Verifica che il prompt sia autonomo e copiabile.

## Esempio completo
«Agisci come consulente didattico (R). Progetta un piano di quattro settimane per imparare le basi della fotografia (I). Il destinatario è un principiante che può dedicare 20 minuti al giorno e usa uno smartphone (C). Non richiedere attrezzatura aggiuntiva e presenta una tabella settimanale (C). Per ogni attività indica obiettivo, durata ed esercizio pratico (E).»

## Esempio minimo
«Riassumi questo testo in cinque punti, in italiano semplice, senza aggiungere informazioni non presenti». In questo caso un ruolo separato e un esempio non aggiungono valore.

La regola fondamentale: la qualità dipende dalla pertinenza e dalla chiarezza, non dalla presenza formale di tutte le lettere.
