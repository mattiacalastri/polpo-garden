---
source_file: "m5_login_stack_audit.md"
type: "document"
community: "Login Items GUI"
location: "#anomalia-2"
status: "BASSA PRIORITÀ — comportamento atteso"
tags:
  - graphify/document
  - graphify/EXTRACTED
  - community/Login_Items_GUI
  - audit/m5-login-stack
---

# Anomalia — HomePod Timeout (Bassa Priorità)

**Stato:** ℹ️ Non critico — timeout graceful atteso

## Script

`~/scripts/jarvis_homepod_connect.sh`

## Comportamento

One-shot al login. Cerca "Mattia's HomePod mini" sulla rete WiFi, aspetta 60s con retry ogni 5s. Se non trovato → exit code 1, cede all'output audio default.

## Log output (last run)

```
[homepod_connect] Avvio connessione HomePod (pattern: 'Mattia's HomePod mini')
[homepod_connect] HomePod non disponibile — riprovo in 5s (0/60s)
...
[homepod_connect] ⚠️ HomePod non raggiunto dopo 60s — output su default
```

## Causa

Al login WiFi non ancora stabilizzato o HomePod in sleep. Non è un loop (KeepAlive: false, ThrottleInterval: 60s).

## Possibile miglioramento

Aggiungere delay iniziale di 30s prima del primo retry per aspettare WiFi stabilizzato.

## Connections
- [[com.jarvis.homepod.connect — HomePod Connect]] - `conceptually_related_to` [EXTRACTED]
- [[HomePod Mini di Mattia]] - `depends_on` [EXTRACTED]
- [[WiFi Stabilità al Login]] - `depends_on` [EXTRACTED]

#audit/m5-login-stack #community/Login_Items_GUI
