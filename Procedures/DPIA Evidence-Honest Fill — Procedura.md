---
title: "DPIA Evidence-Honest Fill — Procedura"
type: procedure
status: codified
codified_in: sess.1812 (12 maggio 2026)
tags: [compliance, gdpr, dpia, legale, evidence, polpo]
related:
  - "[[Reality Check — Verifica contro Ground Truth]]"
  - "[[Seed — Auto-classifier come Terzo Guardiano]]"
  - "[[Cross-Session Cicatrice Check — check Pre-Flight Obbligato]]"
---

# DPIA Evidence-Honest Fill — Procedura

## Contesto di nascita

Sess.1812, 12 maggio 2026. Polpo doveva preparare il DPIA per il sistema Marco GEO Voice Agent AI per Studio Storari (Avv. Severino) — validazione legale art.35 GDPR + art.50 AI Act. Il DPIA bozza v0.1-skeleton conteneva 7 placeholder `[DA COMPILARE]`.

La tentazione era: compilare i placeholder con valori plausibili standard (es. "Cifratura AES-256 standard cloud") creando un DPIA "ready for review". Questa è **fiction** mascherata da operatività.

Polpo ha scelto invece la via dell'**evidence honest**: verificare ogni claim contro ground truth filesystem/realtà, e quando il dato richiesto NON esiste, **dichiararlo esplicitamente** insieme a un'action concreta con data.

## Il principio

> **Un DPIA con verità onesta + action items datati vale 10× un DPIA con finzione plausibile.**

Lo Studio Storari legale valida la realtà presente, non l'ottimismo dichiarativo. Se la cifratura at-rest è documentata dai provider, citala con link al trust center. Se la polizza cyber non è attiva, dichiaralo + indica condizioni di attivazione + data limite. Se il registro art.30 non esiste, scrivi "DA CREARE entro 16/05/2026 — affidato a Studio Storari come deliverable parallelo".

## Protocollo a 5 passi

### 1. Audit ground truth filesystem

Per ogni placeholder `[DA COMPILARE]`, verifica con comando Bash:
- Esiste il file/cartella citata? (es. `~/Documents/Astra/DPA/`, `~/Documents/Astra/registro_trattamenti*`)
- Esiste l'asset web pubblicato? (es. `curl -sIL https://digitalastra.it/privacy-policy/`)
- Esiste l'evidence in vault? (es. grep across `~/Documents/Astra/`)

### 2. Categorizza ogni placeholder in 4 stati

| Stato | Significato | Compilazione |
|---|---|---|
| ✅ EVIDENCE | Dato esiste, verificato, citabile | Compila con citazione + link |
| 🟡 STANDARD | Dato è policy standard provider (es. AES-256) | Compila citando trust center provider |
| ⚠️ DA VERIFICARE | Probabilmente esiste, ma non confermato | Compila + flag DA VERIFICARE entro DATA |
| ❌ NON ATTIVO | Dato non esiste, non implementato | Dichiara + roadmap di attivazione + mitigation interim |

### 3. Bump versione documento

Da `v0.1-skeleton` (compilazione futura) a `v0.2-evidence-filled` (compilazione presente onesta). Aggiungi `data_revisione` + nome sess. Lo Studio Storari riconosce a colpo d'occhio che il documento è stato aggiornato con realtà cucita.

### 4. Cucitura cross-doc

Ogni claim deve essere ancorato:
- Misura tecnica → riferimento file/script esistente (es. `rpo_precheck.py funzionante — WINDOWS hardcoded 9-13/14:30-18:30 + WHITELIST + opt-out check`)
- Policy provider → link trust center pubblico
- Action item → data limite + owner

### 5. Email accompagnamento legale

Quando si manda il DPIA allo studio legale, **non chiedere "valida questo"** generic. Chiedi **specifico**:
- Validazione contenuti già redatti (sezioni complete con evidence)
- Compilazione campi che richiedono input specialistico (DPA archive, registro art.30, polizza cyber, mailbox privacy, decisione DPO)
- Conferma o rettifica analisi rischi residui

L'avvocato risponde 10× più rapidamente a richiesta granulare che a "guarda tu se va bene".

## Esempio applicato

**Placeholder originale:**
```
- Polizza cyber-liability. [DA COMPILARE — indicare compagnia, massimale, scadenza]
```

**Riempimento fiction (CATTIVO):**
```
- Polizza cyber-liability: Generali Cyber Edge, massimale €100k, scadenza 12/05/2027.
```

**Riempimento evidence-honest (BUONO):**
```
- **Polizza cyber-liability**: ⚠️ NON ATTIVA al 12/05/2026. Valutazione in corso (Generali / AIG / Hiscox cyber). Premio stimato €800-1.500/anno per massimale €50k-100k. Decisione finale prevista post-validation DPIA + condizionata a scaling >5.000 chiamate/mese. Nel frattempo: limitazione volumetrica pilot 50-200 chiamate/mese contiene esposizione.
```

Il secondo dice la verità + dichiara mitigation + invita conversazione legale concreta.

## Quando applicare

- Drafting DPIA art.35 GDPR per nuovo sistema AI
- Drafting DPA cliente enterprise
- Drafting privacy notice pubblica
- Audit compliance interna pre-funzionalità in produzione
- Risposta a richiesta accesso/cancellazione interessato

## Anti-pattern noti

- "Lo riempiamo dopo con i dati veri" → diventa fiction mai aggiornata
- "Lo Studio Legale ci dice loro" → l'avvocato non sa cosa hai in filesystem
- "Mettiamo lo standard cloud poi se va male amen" → AI Act + Garante richiedono evidence at-the-time
- "Boh non so cosa scrivere" → migliore di fiction: scrivi DA COMPILARE + data + owner

## Cucitura cross-doc

- Session in cui è stata codificata: [[1812 — Marco GEO patch runtime + Track A_B paralleli sess1812]]
- Riferimento legale operativo: Studio Storari Verona (Avv. Alessio Storari + Avv. Severino + Avv. Vivirito Pellegrino)
- DPIA target: `~/Documents/Astra/dpia_voice_agent_marco_geo.md` (v0.2-evidence-filled)

---

*Codificata sess.1812 · 12 maggio 2026 · Polpo per Mattia Calastri — la verità onesta è il binding legale più forte.*
