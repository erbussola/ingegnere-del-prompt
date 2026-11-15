# Istruzioni distribuibili

- [CORE_INSTRUCTIONS.md](CORE_INSTRUCTIONS.md): bundle completo e canonico, autosufficiente e copiabile in una normale chat o in un campo istruzioni.
- [UNIVERSAL.md](UNIVERSAL.md): copia integrale e autonoma del bundle completo, destinata all'avvio mediante semplice copia-incolla in una nuova conversazione.
- [COMPACT.md](COMPACT.md): versione ridotta per campi o contesti con limiti di lunghezza.
- [CHATGPT.md](CHATGPT.md) e [GEMINI.md](GEMINI.md): collegamenti alle guide aggiornate in `deployment/`.

## Coerenza dei bundle
`CORE_INSTRUCTIONS.md` è la fonte distribuibile completa; `UNIVERSAL.md` deve rimanere identico al Core completo. Quando cambia un modulo normativo in `core/`, aggiornare contestualmente entrambi i bundle completi, la versione compatta e i test correlati.

I bundle sono autonomi: non devono richiedere che il chatbot apra altri file o link per comprendere le regole operative.
