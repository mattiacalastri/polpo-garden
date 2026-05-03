---
source_file: "m5_login_stack_audit.md"
type: "document"
community: "Ollama Conflict"
location: "#anomalia-1"
status: "FIXATO — 2026-05-03 sess.1406"
tags:
  - graphify/document
  - graphify/EXTRACTED
  - community/Ollama_Conflict
  - audit/m5-login-stack
---

# Anomalia — Ollama Doppia Istanza (FIXATA)

**Stato:** ✅ FIXATO il 2026-05-03

## Root Cause

**Raycast** (PID 700) avvia automaticamente `ollama serve` tramite un'estensione Ollama al login.
Allo stesso tempo, il LaunchAgent `com.calastri.ollama` (KeepAlive: true) tentava di avviare un secondo processo `ollama serve` sulla stessa porta 11434.

Risultato: loop infinito di errori nel log `~/.local/state/ollama/ollama.err.log` (14.460 righe accumulate).

## Evidenza

```
Error: listen tcp 127.0.0.1:11434: bind: address already in use
```
Ripetuta 14.460 volte.

## Fix applicato

```bash
launchctl unload ~/Library/LaunchAgents/com.calastri.ollama.plist
```

Ollama PID 873 (figlio di Raycast) continua a girare correttamente. Il LaunchAgent conflittuale è stato unloadato.

## Nota per il futuro

Se si vuole usare il LaunchAgent personalizzato (che ha config migliore: `OLLAMA_KEEP_ALIVE=5m`, `MAX_LOADED_MODELS=1`), occorre prima disabilitare l'auto-start Ollama in Raycast Preferences → Extensions → Ollama.

## Connections
- [[Homebrew Services Ollama (PID 873, porta 11434)]] - `blocks` [EXTRACTED]
- [[com.calastri.ollama LaunchAgent]] - `conceptually_related_to` [EXTRACTED]

#audit/m5-login-stack #community/Ollama_Conflict
