---
source_file: "m5_login_stack_audit.md"
type: "document"
community: "macOS Login System"
location: "#sistema"
audit_date: "2026-05-03"
session: "sess.1406"
tags:
  - graphify/document
  - graphify/EXTRACTED
  - community/Ollama_Conflict
  - audit/m5-login-stack
---

# M5 Max macOS Login Stack

Audit completo dei processi di avvio del Mac di Mattia — sess.1406, 2026-05-03.

## Login Items (GUI — System Settings)

| App | Funzione |
|-----|----------|
| [[Antigravity — Terminale Principale Polpo]] | Terminale principale Polpo |
| [[NordVPN Login Item]] | VPN always-on |
| [[Stats — Monitor Risorse Menu Bar]] | CPU/RAM/GPU menu bar |
| [[Raycast — Launcher Comandi]] | Launcher — gestisce Ollama (PID 873) |
| Obsidian | Vault knowledge |
| [[Maccy — Clipboard Manager]] | Clipboard history |
| [[Telegram — Messaggistica Login Item]] | Messaggistica |
| [[Dropover — Drag-and-Drop Utility]] | Drag-and-drop utility |
| [[Fathom — Registrazione Call]] | Recording call |
| [[JarvisToggle — Toggle Voce Jarvis]] | Toggle STT/TTS |
| Note (Apple Notes) | Note veloci |

## LaunchAgents con PID vivo (audit 09:54)

| PID | Agent | Stato |
|-----|-------|-------|
| 612 | [[com.astra.outreach.daemon — Outreach Automation]] | OK |
| 616 | [[com.mattia.healthbot — Health Monitoring]] | OK |
| 617 | [[com.polpo.tab-watcher — Tab Monitoring]] | OK |
| 621 | [[com.astra.sites-health — Siti Health Check]] | OK |
| 622 | [[com.astra.tg-mobile-bridge — Telegram Bridge]] | OK |
| 627 | [[com.mattia.screenshot-watcher — Screenshot Watcher]] | OK |
| 630 | [[com.jarvis.autosend — Jarvis Auto-Send STT]] | OK |
| 638 | [[com.polpo.claude-keepalive — Claude Keepalive]] | OK |
| 646 | [[com.polpo.homepod.radioguard — HomePod Radio Guard]] | OK |
| 649 | [[com.astra.vault-rag-server — Vault RAG Server]] | OK |
| 651 | [[com.astra.garden-server — Garden Server Obsidian]] | OK |
| 709 | [[com.astra.polpo-voice — Polpo Voice]] | OK |
| 8142 | [[com.astra.jarvis-dettato — Jarvis Dettatura (PID 8142)]] | OK |

## Anomalie

| Anomalia | Priorità | Stato |
|----------|----------|-------|
| [[Anomalia — Ollama Doppia Istanza CRITICA]] | 🔴 CRITICA | ✅ FIXATA sess.1406 |
| [[Anomalia — HomePod Timeout (Bassa Priorità)]] | 🟡 BASSA | ℹ️ Atteso |
| [[Anomalia — jarvis-dettato PID Alto Crash-Loop]] | 🟡 BASSA | ℹ️ Normale |
| com.polpo.m5-watcher.plist.LEGACY | 🟢 INFO | ✅ RIMOSSO sess.1406 |

## Connections
- [[Antigravity — Terminale Principale Polpo]] - `conceptually_related_to` [EXTRACTED]
- [[Homebrew Services Ollama (PID 873, porta 11434)]] - `conceptually_related_to` [INFERRED]

#audit/m5-login-stack #community/macOS_Login_System
