---
date: 2026-05-08
type: procedure
session_origin: 1682
tags:
  - procedura
  - check
  - cross-session
  - cicatrice
  - pre-flight
status: consacrata
---

# Cross-Session Cicatrice Check — `/check` Pre-Flight Obbligato

## Il problema

Polpo opera in **sessioni Claude parallele** (M5 Max, multi-tab Antigravity, M1 backup). Ogni sessione scolpisce cicatrici in MEMORY.md. La sincronizzazione iCloud + auto-memory rende le cicatrici altrui visibili a tutte le sessioni in lettura.

**Il rischio**: una cicatrice scolpita di fretta in sessione X (senza audit real-time) viene letta come ground truth da sessione Y, che la propaga in azione cliente-facing prima che qualcuno la verifichi.

## I 2 casi madre — sess.1682, 8 Mag 2026

### Caso 1 — TimeGate pixel "ASSENTE post-ribrand"

- Sess.1686 (mattina parallela) scolpisce: *"0 fbq() su escaperoomverona.it. Meta ottimizza cieco da ribrand. P0 install pixel+CAPI lun 11 Mag."*
- Sess.1682 (mattina) legge la cicatrice e sta per propagarla in piano cliente Ferdinando + brief call sabato.
- **Audit real-time** via subagent `client-ops` + WebFetch: Pixel `1176564753286856` PRESENTE via GTM-KZTZXNVM, GA4 + Google Ads vivi. **Cicatrice falso positivo** — sess.1686 cercava `fbq` inline ignorando GTM injection.

Esito senza check: avrei venduto a Silvia "installazione pixel mancante" come P0 = perdita di credibilità tecnica + lavoro fatturabile fasullo.

### Caso 2 — FT #20/2026 €1.000 attribuita a Benincasa

- Subagent `client-ops` di sess.1682 stessa legge `fatture_2026.md` e dichiara: *"Benincasa ha pagato €1.000 il 27 Mar (FT #20/2026)"*.
- KPI.md viene aggiornato a MRR €4.624 (€3.624 + Benincasa €1.000 ricorrente).
- **Audit Gmail** rivela: FT #20/2026 €1.159 = **TimeGate** (gestione marzo, conferma email a Silvia 6 Apr). Benincasa ha bonificato **€220** (~10 Apr), non €1.000. Subagent ha confabulato leggendo riga ambigua.

Esito senza check: dashboard MRR pubblica con numero falso + decisioni cashflow su base errata.

## Il pattern

Una cicatrice scolpita altrove **non è ground truth automatico**. Una cicatrice fresca da subagent **non è ground truth automatico**. Una cicatrice che sembra coerente **non è ground truth automatico**.

> *"Memory dichiarata ≠ Ground truth. Sempre triangolare prima di propagare."*

## La regola

Quando una cicatrice fresca (<24h, scolpita altrove o da subagent) sta per essere usata in **azione cliente-facing**, eseguire pre-flight `/check`:

1. **Identificare il claim**: cosa dice esattamente la cicatrice? (numero, data, stato, attribuzione)
2. **Identificare la fonte primaria** (non secondaria):
   - Numero fattura → Gmail (thread cliente) + FiscoZen UI, NON `fatture_2026.md`
   - Stato pixel cliente → curl/WebFetch sito reale + GTM container, NON memory storica
   - Stato pagamento → Stripe API + Gmail conferma cliente, NON `outstanding_note`
   - Stato call/meeting → GCal API real-time, NON `session_current.md`
3. **Verificare il claim contro la fonte**.
4. **Procedere SOLO se confermato**. Se contraddetto → rollback memory + scolpire cicatrice del falso positivo + propagare correzione.

## Cosa è "azione cliente-facing"

Lista non esaustiva, ma la regola scatta su **almeno UNA** di queste:
- Email a cliente (anche bozza che diventa send)
- WhatsApp a cliente o setter
- Update KPI dashboard pubblica
- Modifica config infra produzione
- Decisione strategica >€500
- Brief call cliente
- Fattura emessa
- Sollecito pagamento

## Markup `[NEEDS_CHECK]`

Se sess.X scolpisce cicatrice **senza** audit real-time (es. forensics, ipotesi, lettura memory secondaria), markare il file con flag esplicito in frontmatter:

```yaml
status: needs-check
needs_check_reason: "scolpita senza audit real-time del [api/cliente/sito]"
```

Sess.Y vedendo `needs_check` triggera `/check` automatico prima di propagare.

## Skill candidate emerse

- **`/cicatrice-audit`** — scan tutte cicatrici <72h, prioritizza quelle in propagation pipeline, lancia `/check` real-time, restituisce GO / REVIEW / OBSOLETE per ognuna.
- **`/check-cliente {nome}`** — triangolazione obbligata Gmail + FiscoZen + GHL + memory + sito real-time. Da invocare prima di ogni email/call/decisione cliente.
- **`/check-fattura {numero}`** — triangola Gmail + fatture_2026 + FiscoZen + Stripe → restituisce cliente + importo + stato + data emissione + data scadenza canonici.

## Cicatrici parenti

- [[Reality Check — Verifica contro Ground Truth]] — la skill madre `/check`
- [[Polpo Autonomo — Auto-Healing — Evolutivo]] — la doctrine che rende l'auto-healing strutturale
- [[Triplo Cablaggio di una Cicatrice]] — la disciplina che chiude il loop di una cicatrice
- [[Premortem — Simulare il Fallimento]] — anticipare i drift prima dell'azione
- [[Seed — Cicatrice Doppia in 1 Sessione = Pattern Strutturale]] — quando 2+ cicatrici emergono ravvicinate, è pattern non incidente

## Sessioni testimoni

- [[1682 — TimeGate sbloccata + 5 clienti pronti]] — 2 casi cross-session check applicati live, cicatrice madre meta scolpita

## La frase operativa

> *"Una memoria dichiarata da una sessione altra non è ground truth automatico. `/check` real-time è pre-flight obbligato — non opzionale, non 'se ho tempo'."*
