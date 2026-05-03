---
source_file: "m5_login_stack_audit.md"
type: "document"
community: "HomePod Connect"
location: "#anomalia-3"
status: "MONITORATO — non è un crash loop, è normale"
tags:
  - graphify/document
  - graphify/EXTRACTED
  - community/HomePod_Connect
  - audit/m5-login-stack
---

# Anomalia — jarvis-dettato PID Alto

**Stato:** ℹ️ Non critico — comportamento normale del toggle

## Diagnosi

PID 8142 (alto rispetto agli altri agent sotto 730) suggeriva crash loop. **Non è un crash loop.**

Il log `~/.local/run/jarvis/launcher.log` mostra il pattern reale: l'app viene stoppata esplicitamente da Mattia (`stt_disabled` flag), poi kickstartata di nuovo dal LaunchAgent quando il flag viene rimosso. Ogni ciclo ON/OFF crea un nuovo PID.

## KeepAlive configurato intelligentemente

```xml
<key>SuccessfulExit</key>
<false/>  <!-- NON riavvia su exit 0 (quit normale) -->
<key>Crashed</key>
<true/>   <!-- riavvia solo se crasha -->
<!-- se stt_disabled esiste → non riavvia -->
```

## Problema audio presente (bassa priorità)

Log `~/.local/run/jarvis/launchagent.out` mostra errori PortAudio/CoreAudio ricorrenti:
```
||PaMacCore (AUHAL)|| Error on line 1322: err='-10851', msg=Audio Unit: Invalid Property Value
```
Causa: cambio sample rate o device switching (HomePod ↔ speaker interno). Non blocca il funzionamento.

## STT engine attuale

```
idlewhispergeorge
```

## Connections
- [[com.astra.jarvis-dettato — Jarvis Dettatura (PID 8142)]] - `conceptually_related_to` [EXTRACTED]
- [[Jarvis STT Daemon]] - `shares_data_with` [INFERRED]

#audit/m5-login-stack #community/HomePod_Connect
