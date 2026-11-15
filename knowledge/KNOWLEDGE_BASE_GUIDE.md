# Guida alla Knowledge Base

## Scopo
Spiegare come distribuire i documenti del progetto come fonti di riferimento, senza duplicare le regole comportamentali del Core.

## Distinzione fondamentale
- **Istruzioni/Core:** definiscono come l'assistente deve comportarsi.
- **Framework:** approfondisce il metodo RICCE, la valutazione e i controlli.
- **Template:** offre strutture riutilizzabili per specifici compiti.
- **Esempi:** mostra applicazioni illustrative.
- **Guide piattaforma:** spiega le modalità di installazione e i limiti di una specifica piattaforma.
- **Registro di continuità:** contiene le decisioni e lo stato di un lavoro specifico, non le regole generali del prodotto.

## Set minimo
Per una configurazione permanente, caricare:
1. `instructions/CORE_INSTRUCTIONS.md` nel campo istruzioni, non come documento di conoscenza se esiste un campo dedicato.
2. `framework/RICCE.md`.
3. `framework/PROMPT_EVALUATION.md`.
4. `framework/QUALITY_CHECKLIST.md`.
5. I template pertinenti al caso d'uso.

## Set esteso
Aggiungere esempi, guide, test e documenti di settore solo quando migliorano le risposte. Evitare di caricare l'intero repository senza una ragione: troppe fonti possono introdurre rumore.

## Manutenzione
- Ogni file deve indicare chiaramente il proprio scopo.
- Le regole normative devono restare nel Core.
- Quando il Core cambia, aggiornare il bundle completo e quello compatto.
- Le guide specifiche devono essere verificate rispetto alle fonti ufficiali.
- Rimuovere copie obsolete dalla knowledge base, se la piattaforma non gestisce versioni.
- Per i lavori che cambiano nel tempo, conservare un registro di continuità distinto dal Core.

## Privacy
Caricare solo materiali autorizzati e necessari. La disponibilità di una knowledge base non cambia i termini di trattamento dati del fornitore.
