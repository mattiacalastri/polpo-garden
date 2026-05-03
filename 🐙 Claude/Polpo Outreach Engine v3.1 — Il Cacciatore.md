---
title: "Polpo Outreach Engine v3.1 — Il Cacciatore"
type: tool
version: "3.1.0"
codename: "Il Cacciatore"
session: "sess.1459"
created: 2026-05-03
updated: 2026-05-03
status: live
file: "~/scripts/astra_outreach_tui_v3.py"
ssot: "~/scripts/setters.yaml"
tags:
  - tool
  - outreach
  - tui
  - astra-digital
  - sales
  - ghl
  - textual
  - graphify/document
community: Astra_Infrastructure
---

# Polpo Outreach Engine v3.1 — Il Cacciatore

> *Il Polpo non aspetta i lead. Li costruisce.*
> — Mattia Calastri, Astra Digital Marketing

---

## Identita'

TUI in Python/Textual per la gestione attiva del pipeline commerciale di Astra Digital Marketing. Non e' un CRM. E' un pannello di comando per un cacciatore — visualizza lo stato in tempo reale del funnel GHL, coordina 5 setter, attiva call AI outbound via ElevenLabs ConvAI.

**Principio fondante:** il setter non aspetta che arrivi un lead. Questo tool rende visibile dove sono i lead, chi li sta lavorando, e permette di agire sulla prossima mossa adesso.

---

## Stack tecnico

| Componente | Valore |
|---|---|
| File | `~/scripts/astra_outreach_tui_v3.py` |
| Runtime | Python 3.10 |
| TUI framework | Textual 8.2.4 |
| Config SSOT | `~/scripts/setters.yaml` |
| HTTP | `urllib` stdlib (no requests) |
| CRM | GHL (GoHighLevel) — cache TTL 60s |
| AI calls | ElevenLabs ConvAI (configurabile per setter) |
| Design tokens | `polpo.tokens.json` |

**Design System:**
- Background: `#0a0f1a`
- Accent teal: `#00d4aa`

---

## Layout TUI

### Bottom dual panel (sempre visibile)

Due pannelli fissi in basso, visibili da qualsiasi tab:

- **GRAFO** — knowledge graph del pipeline: nodi per setter, deal, stato. Visualizzazione delle connessioni tra lead attivi.
- **PILOTA** — autopilot daemon: stato del loop automatico, prossima azione schedulata, log eventi recenti.

### 7 Tab

| # | Nome | Contenuto |
|---|---|---|
| 1 | CODA | Lead in attesa di contatto, priorita' per setter |
| 2 | CACCIA | Pipeline attivo — opportunita' in lavorazione |
| 3 | SQUADRA | Dashboard setter: stato, quota, performance |
| 4 | NERVI | Log sistema, errori, alert GHL |
| 5 | SEGNALE | Metriche di funnel, conversion rate, velocita' pipeline |
| 6 | POLSO | Heartbeat sistema — salute connessioni GHL/ElevenLabs |
| 7 | VOICE | Configurazione e log call AI outbound |

---

## Keybinding

| Tasto | Azione |
|---|---|
| `q` | Esci |
| `r` | Refresh dati GHL |
| `p` | Pausa autopilot |
| `a` | Attiva/disattiva autopilot |
| `n` | Nuova caccia (crea opportunita') |
| `c` | Chiama AI (ElevenLabs ConvAI, lead selezionato) |
| `b` | Batch AI call (tutti i lead in coda) |
| `1`-`7` | Naviga tra i tab |

---

## Setter monitorati

5 setter nel pipeline + 1 block AI configurabile:

| Setter | Stage Keys GHL |
|---|---|
| Carmen | da_contattare, discovery_fissata |
| Luca | da_contattare, discovery_fissata |
| Luljete | `da_contattare`, `discovery_fissata` (aggiunti sess.1459) |
| Claudia | da_contattare, discovery_fissata |
| Fabrizia | da_contattare, discovery_fissata |

SSOT configurazione: `~/scripts/setters.yaml` — include sezione `ai_setter` per ElevenLabs ConvAI.

---

## Bug fix sessione

**sess.1459 — Luljete stage keys mancanti**

`_KEY_STAGES` e `_FUNNEL` non includevano `da_contattare` e `discovery_fissata` per Luljete. Il pipeline di Luljete risultava vuoto nel grafo. Fix applicato: chiavi aggiunte a entrambe le strutture dati in `astra_outreach_tui_v3.py`.

---

## GHL integration

- Live stats con cache TTL 60 secondi
- Monitoraggio 5 pipeline setter in parallelo
- Stage tracking: ogni setter ha i propri stage keys mappati in `_KEY_STAGES`
- Funnel aggregato in `_FUNNEL` per calcolo conversion cross-setter

---

## ElevenLabs ConvAI

Outbound AI calls configurabili per setter via `setters.yaml`:

```yaml
ai_setter:
  agent_id: <elevenlabs_agent_id>
  voice_id: <voice_id>
  enabled: true
  targets:
    - stage: da_contattare
      max_calls_per_run: 5
```

Il VOICE tab mostra log delle call, stato connessione, transcript disponibili.

---

## Connections

- [[com.astra.outreach.daemon — Outreach Automation]] - `evolved_from` — il daemon precedente
- [[Setter System]] - `reads_config_from` — setters.yaml, roster, Daily Protocol
- [[GHL MCP v0.4.0]] - `reads_data_from` — pipeline GHL live

---

*Nota tecnica creata da Astra OS / sess.1459 — 2026-05-03*
