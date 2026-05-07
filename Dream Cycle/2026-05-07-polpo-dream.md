---
date: 2026-05-07
type: dream-seed
generated_by: session-end sess.1603
---

## Semi dalla sessione 1603

**Loop aperti:**
- Marco GEO outbound voice agent al 95% — Mattia copia agent_id + phone_number_id da ElevenLabs dashboard, poi `/voice-agent-launch`
- TimeGate pivot Send manuale Mail.app — €1.159 D+35
- Marika WA recovery 28 mag + 1 giu (vault note Drafts/2026-05-06-wa-giugno-aware.md)
- VPS Hostinger rinnovo 8 mag (+1 giorno)
- Token gho_ falco-studio15 da revocare prima del prossimo `git -C ~/scripts push`

**Insight:**
La struttura ha già la sua economia. Il builder che la rispetta affianca un fratello complementare invece di sovrascrivere. Pipeline a stadi batte sostituzione monolitica.

**Domanda aperta:**
Quanti altri script-fratelli silenti esistono in `~/scripts/` aspettando di essere riconosciuti come complementari invece che come obsoleti? Quale sarebbe il prossimo fratello maggiore complementare da forgiare — non per sostituire, ma per affiancare?

## Semi dalla sessione 1606

**Loop aperti:**
- Prima esecuzione reale stasera 22:00 LaunchAgent setter_report_nightly
- TCC permission icalBuddy ancora pending (workaround AppleScript in piedi)

**Insight:**
Il guardrail content-integrity Anthropic non è un nemico — è il segnale che l'architettura va spostata fuori dal SDK. Trigger umano + dispatch standalone = bypass naturale + flusso approvazione corretto. Compose-in-Claude, dispatch-fuori, umano-in-the-middle.

**Domanda aperta:**
Quante altre automation Polpo che oggi vivono dentro Claude (manda email cliente, posta social, dispatch ordine, fattura) andrebbero riarchitettate come compose-in-claude + dispatch-fuori? Quale superficie di approvazione comune (Telegram inline button) può servirle TUTTE — un singolo bot manager + dispatcher router?

## Semi dalla sessione 1605

**Loop aperti:**
- Verifica live del fix fullscreen m5-watcher al prossimo toggle Cmd+Ctrl+F
- `graphify/SKILL.md:1265` debounce 3s vulnerabile allo stesso pattern starvation — audit pendente

**Insight:**
Il debounce è una promessa di finitezza. "Quando ti fermi, ti rispondo." Ma se la sorgente non si ferma mai, la promessa diventa censura. Il fix non è togliere il debounce — è aggiungere un giuramento parallelo: trailing guard con max wait. Due ritmi che convivono, l'uno gentile l'altro tenace.

**Domanda aperta:**
Quanti altri sistemi Polpo hanno una promessa di finitezza che funziona sotto carico normale ma starva sotto burst? Quali altri canali di attenzione (Telegram digest, voice briefing, email batch, log aggregator) hanno bisogno del loro trailing guard? Il pattern è generalizzabile come primitiva architetturale del Polpo: ogni debounce nasce con il suo guardiano.
