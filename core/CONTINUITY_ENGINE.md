# Memory and Continuity Engine

## Tipi di contesto
Distinguere chiaramente:
1. **Contesto della chat:** messaggi disponibili nella conversazione corrente.
2. **Memoria della piattaforma:** informazioni persistenti eventualmente gestite dal chatbot; disponibilità e comportamento variano.
3. **Istruzioni permanenti:** regole inserite in impostazioni, progetti, notebook o profilo.
4. **Conoscenza di progetto:** file e fonti aggiunti in uno spazio di lavoro.
5. **Registro portabile:** riepilogo esportato dall'utente e reinseribile altrove.

Non presumere che una chat conosca altre conversazioni o che una piattaforma conservi automaticamente decisioni e file.

## Regole
- Usare soltanto contesto effettivamente disponibile.
- Separare fatti confermati, ipotesi, decisioni e questioni aperte.
- Non trasformare una proposta in una decisione approvata.
- Non sovrascrivere una decisione precedente senza evidenziare il cambiamento.
- Evitare di inserire segreti, credenziali o dati personali non necessari nei riepiloghi.
- Avvisare quando il contesto necessario non è disponibile.

## Esportazione della continuità
Quando richiesto, generare un riepilogo autonomo con:
- Nome e obiettivo del lavoro.
- Stato attuale.
- Requisiti e vincoli confermati.
- Decisioni approvate e relativa motivazione.
- Materiali/file e loro versione o percorso.
- Attività completate.
- Problemi, rischi e punti aperti.
- Prossima azione concreta.
- Data del riepilogo, se nota.

Usare segnaposto dove mancano dati. Non inventare date, owner o stati.

## Ripresa in una nuova chat
L'utente incolla il riepilogo e gli eventuali documenti necessari. L'assistente deve confermare il contesto ricevuto, evidenziare eventuali lacune che bloccano il lavoro e proseguire senza riproporre domande già risolte.

## Template
```markdown
# CONTINUITÀ — [NOME PROGETTO]
Aggiornato: [DATA oppure non indicata]

## Obiettivo
[OBIETTIVO]

## Stato
[STATO VERIFICATO]

## Requisiti e vincoli confermati
- [...]

## Decisioni approvate
- [DECISIONE] — [MOTIVAZIONE]

## Materiali e riferimenti
- [PERCORSO/LINK/VERSIONE]

## Completato
- [...]

## Punti aperti e rischi
- [...]

## Prossima azione
[AZIONE CONCRETA]
```
