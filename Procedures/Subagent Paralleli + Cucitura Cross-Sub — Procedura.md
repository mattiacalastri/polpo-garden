---
title: "Subagent Paralleli + Cucitura Cross-Sub — Procedura"
type: procedure
status: codified
codified_in: sess.1812 (12 maggio 2026)
tags: [polpo, subagent, parallelizzazione, cucitura, orchestrazione]
related:
  - "[[Garden Walk — Protocollo di Risveglio Cognitivo]]"
  - "[[Reality Check — Verifica contro Ground Truth]]"
  - "[[Premortem — Simulare il Fallimento]]"
---

# Subagent Paralleli + Cucitura Cross-Sub — Procedura

## Contesto di nascita

Sess.1812, 12 maggio 2026. Mattia: *"usa anche agenti dedicati in background se serve"*. Polpo aveva ~1 ora prima della call cliente Kongline 14:15, e tre fronti aperti contemporaneamente:
- Report mensile Kongline da generare (cliente-facing)
- 5 WhatsApp cliente non risposti da pulire
- Audit cassa pre-F24 giovedì da preparare

Linearmente: 30min × 3 = 90min. Impossibile.

Parallelamente con 3 subagent dedicati + main agent come cucitore: 8min totali.

## Il principio

> **I subagent paralleli moltiplicano la mano. Solo il main agent cuce. Il valore è nella cucitura, non nei thread.**

I subagent eseguono lavoro indipendente in cache loro. Il main agent **NON delega anche la sintesi** — la sintesi cross-sub è dove emergono le cuciture invisibili ai singoli thread.

## Protocollo a 4 fasi

### Fase 1 — Triage parallelizzabilità

Domanda chiave: *"Questi N task condividono dati o sono indipendenti?"*
- **Indipendenti** → parallelizza con N subagent (uno per task)
- **Sequenziali con dipendenza** → mai parallelizzare (il subagent #2 vedrebbe stato stale)
- **Indipendenti ma con potenziale insight cross-sub** → parallelizza + main agent fa cucitura

Esempio sess.1812:
- Report Kongline (cliente-specific) — indipendente
- 5 WA risposte (multi-cliente) — indipendente
- Audit cassa F24 (cross-cliente) — indipendente
- Cucitura: Anticipo Kongline = leva F24 (insight emerge solo dalla cucitura)

### Fase 2 — Brief subagent con context cucito

Per ogni subagent, brief che include:
1. **Sess identifier** + data
2. **Ground truth state** (numeri MRR, outstanding, deadline visibili)
3. **Obiettivo unico** del subagent
4. **Output format atteso** (concise <300 parole, JSON strutturato, file path)
5. **Constraint** ("non inviare nulla tu, Mattia legge e copia" / "salva in `~/path/file.md`")

Non lanciare subagent generic "fai X" — il context cucito previene confabulazione.

### Fase 3 — Cucitura cross-sub

Quando i subagent ritornano, il main agent fa:
1. **Lettura sequenziale dei N output**
2. **Identifica drift fra subagent** (es. CFO subagent dice "FT #26 Studio15" mentre vault dice "FT #26 Guerra, FT #27 Studio15" — ground truth filesystem prevale)
3. **Identifica insight emergenti dalla cucitura** che nessun subagent da solo poteva vedere
4. **Sintetizza per Mattia con framing operativo** ("dato A + dato B → decisione X")

### Fase 4 — Single-source-of-truth update

I subagent ritornano output in memoria conversazione. Il main agent persiste in vault/file:
- Session note (`~/Polpo Memory/Sessioni/sessXXXX.md`)
- Memory cuciture (`~/.claude/projects/.../memory/feedback_*.md`)
- Pre-cuciture operative (`/tmp/*_sess1812.md` per follow-up imminenti)

Niente vive solo in memoria conversazione — quella si comprime.

## Esempio applicato sess.1812

**Lanciati in parallelo:**
- `client-success-report-manager` → Report Kongline apr-2026 deployed
- `client-ops` → 5 draft WA pronti copy-paste
- `cfo-virtual` → Brief audit F24 con 3 decisioni giovedì

**Cucitura main agent (insight emerso solo cross-sub):**
- CFO: gap F24 €231 worst case se NO anticipo Kongline
- Report manager: cliente Kongline attivo, no churn signal, MRR €1.155 certo
- WA: "SI" di Sara alle 08:25 + configuratore live `kongline-configurator.pages.dev`

→ **Conclusione cucita**: 3 segnali convergenti per **alta probabilità close anticipo nella call 14:15**. Frase pivot pre-cucita per Mattia da usare in call: *"Sara, una nota operativa — F24 IVA Q1 chiude il 16. Avrei una richiesta..."*

Nessun subagent da solo poteva produrre questa sintesi. La cucitura ha generato lo strumento.

## Quando applicare

- 3+ task indipendenti con time pressure (pre-call cliente, deadline fiscale, audit settimanale)
- Crisis cross-superficie (cliente + cassa + tecnico simultanei)
- Garden walk full (post-compact, riavvio M5)
- Audit cross-pilastro (Astra OS + Astra Agency + AuraHome + BTC + AAH)

## Anti-pattern noti

- **Delegare cucitura a subagent**: la sintesi cross-sub è il valore. Subagent che fa sintesi vede solo il suo output.
- **Subagent che si sovrappongono su stessi file**: race condition, ultimo che scrive vince. Sempre target file diversi per subagent.
- **Brief subagent troppo generic**: confabulazione. Sempre ground truth state + constraint specifici.
- **Aspettare 1 subagent per lanciare il successivo**: serial in disguise. Vero parallelo lancia tutti subito.

## Cucitura cross-doc

- Session ground truth: [[1812 — Marco GEO patch runtime + Track A_B paralleli sess1812]]
- Garden walk MOC: [[Garden Walk — Protocollo di Risveglio Cognitivo]]
- Memory di riferimento: `feedback-focus-impegno-sess1812` (azione > protocollo)

---

*Codificata sess.1812 · 12 maggio 2026 · Polpo per Mattia Calastri — il valore è nella cucitura, non nei thread.*
