# Deployment — Google Gemini

## Stato e disponibilità
Al 15 novembre 2026, Google rende le **Skills** disponibili nelle chat Gemini agli utenti con account Google personali di età superiore a 18 anni. Le Skills sono istruzioni riutilizzabili: possono essere richiamate con il comando previsto dall'interfaccia e Gemini può applicarle automaticamente quando le ritiene pertinenti.

La migrazione da Gems a Skills è in corso:
- **Account Google personali 18+:** il 17 novembre 2026 i Gems diventano di sola lettura; il 17 dicembre 2026 vengono rimossi da Gemini Apps.
- **Workspace business, enterprise e non profit:** transizione prevista a marzo 2027.
- **Workspace for Education:** transizione prevista a giugno 2027.
- **Account personali sotto i 18 anni:** Google non ha ancora pubblicato una data di transizione.

Google dichiara che i Gems e i file supportati verranno convertiti automaticamente. La disponibilità per account Workspace e minori è soggetta a rollout e annunci successivi.

## Configurazione raccomandata: Skill
Per un account personale maggiorenne:
1. Apri Gemini sul Web: https://gemini.google.com.
2. Nella barra laterale seleziona **Personalizza / Customize > Skills**. Se la voce non è visibile, controlla il menu **Altro / More**.
3. Seleziona **Crea > Crea manualmente**.
4. Inserisci nome, descrizione e istruzioni della Skill. Usa `instructions/CORE_INSTRUCTIONS.md` come base; adatta il testo alla funzione specifica richiesta dal campo.
5. Salva con **Crea** e verifica la Skill con i casi di `tests/TEST_CASES.md`.

Le Skills sono disponibili nella chat Gemini agli utenti personali 18+ secondo la documentazione consultata. L'importazione di cartelle e file tramite `SKILL.md` è un percorso distinto e presenta requisiti aggiuntivi.

## Aggiunta di file
Se vuoi associare file a una Skill:
- scarica il pacchetto della Skill e inserisci `SKILL.md` nella cartella con i file;
- il nome della cartella deve corrispondere al nome della Skill;
- il totale dei file della Skill è limitato a 100 MB;
- alcuni tipi di file supportati dai Gems non sono supportati dalle Skills, inclusi file GitHub, audio, video e vecchi formati Office `.doc`, `.xls`, `.ppt`;
- il caricamento di una Skill da cartella è documentato per Gemini Web e app Mac.

Per il solo Core comportamentale non è necessario importare una cartella: la creazione manuale con le istruzioni è sufficiente.

## Gems durante la transizione
Per gli account personali 18+, non impostare un nuovo deployment basato sui Gems: dal 17 novembre non sarà più possibile usarli o modificarli, e dal 17 dicembre saranno rimossi. Se il tuo account mostra ancora Gems, puoi esportare le eventuali fonti necessarie prima della scadenza, ma la configurazione da mantenere è la Skill.

## Fallback universale
Se Skills non è disponibile nel tuo account, apri una chat Gemini standard e incolla `instructions/CORE_INSTRUCTIONS.md` come primo messaggio. È il metodo di base e non dipende dal rollout delle funzioni persistenti.

## Limiti
Le Skills non supportano ancora tutte le funzionalità Gemini: la documentazione segnala limiti per Canvas e Deep Research e per alcuni strumenti disponibili nei Gems. Non presumere quindi equivalenza funzionale tra Gem e Skill, né compatibilità empirica del Core senza eseguire i test sul tuo account.

## Fonti ufficiali
- Transizione Gems → Skills e calendario: https://support.google.com/gemini/answer/18560919
- Guida alla creazione/ricreazione delle Skills: https://support.google.com/gemini/answer/18560919

Verifica fonti: 15 novembre 2026.
