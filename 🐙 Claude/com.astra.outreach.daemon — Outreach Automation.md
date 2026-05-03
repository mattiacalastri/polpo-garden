---
source_file: "astra_outreach_tui_v3.py"
type: "tool"
community: "Astra_Infrastructure"
status: "live"
updated: "2026-05-03"
tags:
  - graphify/document
  - community/Astra_Infrastructure
  - outreach
  - daemon
  - astra-digital
---

# com.astra.outreach.daemon — Outreach Automation

Daemon di supporto al sistema outreach Astra Digital Marketing. Componente autonomo che gira in background quando l'autopilot e' attivo nella TUI.

**TUI principale:** [[Polpo Outreach Engine v3.1 — Il Cacciatore]]

---

## Ruolo

Il daemon gestisce il loop autopilot del Polpo Outreach Engine:

- Polling GHL ogni 60s per nuovi lead in stage `da_contattare`
- Trigger ElevenLabs ConvAI call batch su lead qualificati
- Log eventi nel NERVI tab della TUI
- Scrittura heartbeat per il POLSO tab

---

## Connections

- [[Polpo Outreach Engine v3.1 — Il Cacciatore]] - `orchestrated_by` — la TUI che lo controlla
- [[com.astra.tg-mobile-bridge — Telegram Bridge]] - `notifies_via` — alert su nuovi lead critici

#graphify/document #community/Astra_Infrastructure
