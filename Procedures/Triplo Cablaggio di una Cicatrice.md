---
title: Procedure — Triplo Cablaggio di una Cicatrice
type: procedure
status: growing
created: 2026-05-01
distilled_from: vault privato (cicatrice operativa + conferma sperimentale)
tags:
  - procedure
  - cicatrice
  - sistema-immunitario
  - operativa
  - public
related:
  - "[[Seed — Tre Topologie di una Cicatrice]]"
  - "[[Seed — Oracolo Passivo]]"
  - "[[Le 7 Idee Pure]]"
  - "[[MOC — Indice Pubblico]]"
  - "[[Premortem — Simulare il Fallimento]]"
  - "[[Reality Check — Verifica contro Ground Truth]]"
  - "[[Garden Walk — Protocollo di Risveglio Cognitivo]]"
  - "[[Lettera al Prossimo Claude]]"
---

# 🩹⚙️ Procedure — Triplo Cablaggio di una Cicatrice

> *La procedura operativa associata al [[Seed — Tre Topologie di una Cicatrice]].*
> *Quando un errore ricorrente diventa cicatrice, segui questi 3 passi. Sempre. Salvo le 2 eccezioni esplicite.*

---

## Quando applicarla

Triggera la procedura quando si verifica **almeno una** di queste condizioni:

- ✅ Hai appena risolto un bug **ricorrente** (è già successo prima, o ha alta probabilità di ripresentarsi)
- ✅ Il bug ha **gemelle** già scolpite nel sistema (cicatrici correlate per tema, tecnologia, pattern)
- ✅ Il bug appartiene a una **zona calda** del tuo lavoro (lo toccherai di nuovo nei prossimi giorni)

Se nessuna delle 3 è vera → **NON applicare** (vedi eccezioni in fondo).

---

## I 3 Passi

### Passo 1 — Filesystem (la barriera)

Il fix tecnico è applicato e versionato.

- [ ] Il codice/config che risolve il bug è in posto
- [ ] È stato committato (o, se non è in un repo, è backuppato in un altro modo persistente)
- [ ] Il fix ha un test minimo (una invocazione che dimostra il bug fissato)

> Senza questo passo, la cicatrice non esiste. È solo conversazione.

### Passo 2 — Memoria (il principio)

Il why + l'how-to-apply sono scolpiti in una nota di feedback ad alta densità, leggibile in ogni futura sessione/contesto.

Schema della nota di feedback:

```yaml
---
name: <titolo descrittivo, max 80 char>
description: <one-liner che descrive quando ri-applicare il principio>
type: feedback
originSessionId: <quando è successo, in qualsiasi formato>
---

**Regola**: <l'azione/non-azione concreta>

**Why**: <il caso reale che ha generato la cicatrice — sii specifico, non generico>

**How to apply**:
- <quando si attiva la regola>
- <come applicarla concretamente>
- <eccezioni e edge case>

**Connesso a**: <link a cicatrici correlate, se esistono>
```

> Senza questo passo, la cicatrice è muta nel tempo. Il prossimo "te" la rifarà.

### Passo 3 — Grafo (la sinapsi)

Il principio è cablato come nodo nel knowledge graph del tuo sistema cognitivo (Obsidian, Roam, Logseq, Notion con backlinks, ecc.).

- [ ] La nota esiste nel grafo (file con frontmatter conforme allo standard del tuo vault)
- [ ] Ha **almeno 3 wikilink uscenti** verso nodi correlati
- [ ] È **bidirezionalmente connessa**: ogni nota linkata, dove sensato, deve linkare di ritorno
- [ ] Tag coerenti con la tassonomia del vault (almeno 1 tag generico + 1 tag specifico)

> Senza questo passo, la cicatrice è isolata. Non emergerà mai in graph view, mai sarà votata da uno script di "sogno" notturno, mai si legherà a una gemella futura.

---

## Le 2 eccezioni (quando NON applicare)

### Eccezione A — Fix banali
Typo, off-by-one, bug locale che non si ripresenta.
→ Solo Passo 1 + 2. Salta il Passo 3. Il grafo non guadagna nulla a inglobare rumore.

### Eccezione B — Cicatrice esplorativa
Hai trovato un bug, l'hai aggirato in modo grezzo, ma non hai ancora capito la causa profonda.
→ Solo Passo 1 (fix temporaneo) + Passo 2 con `status: draft`. Lascia il Passo 3 per quando il principio sarà maturo. Non cablare nel grafo qualcosa che non sai ancora cos'è.

---

## Il debt da chiudere (gemelle mute)

Se mentre stai scolpendo una cicatrice nuova ti accorgi che la **gemella esistente** è solo Passo 1 + 2 (mute nel grafo), **cabla anche lei**.

NON triggerare batch automatico di "mirror tutta la memoria nel grafo". Pruning silenzioso. La gemella si cabla solo quando la sinapsi tra la nuova e la vecchia diventa **necessaria**.

Esempio:
- Stai scolpendo cicatrice B (nuova)
- Ti accorgi che B è gemella di A (esistente, ma solo in memoria)
- Cabla A nel grafo **adesso**, perché ti serve la sinapsi A↔B
- NON cablare anche C, D, E (altre cicatrici mute) "già che ci sei" — il batch è scope creep

---

## Verifiche di qualità (after action)

Dopo aver chiuso il triplo cablaggio, controlla:

- [ ] Il fix non si rompe se rieseguito? (idempotenza)
- [ ] La nota di feedback contiene il **why specifico** (con esempio reale), non solo astrazioni?
- [ ] Il nodo nel grafo è **trovabile** via search del vault con almeno 2 query naturali diverse?
- [ ] Se cerco la cicatrice gemella più ovvia, la trovo via wikilink in 1 hop?

Se 4/4 → cicatrice viva. Se 3/4 → fix il punto mancante. Se ≤2/4 → la procedura non è completa, non sei in stato di sicurezza.

---

## Perché è una procedura, non un'idea

Il [[Seed — Tre Topologie di una Cicatrice]] è il **principio**. Questa procedura è il **gesto** che lo concretizza.

Senza il gesto, il principio resta filosofia. Senza il principio, il gesto diventa burocrazia. Insieme: **disciplina cognitiva replicabile**.

---

## Vedi anche

- [[Seed — Tre Topologie di una Cicatrice]] — il principio teorico
- [[Seed — Oracolo Passivo]] — perché il triplo cablaggio è precondizione: solo cicatrici cablate al livello 3 partecipano al ranking notturno e producono predizione
- [[Le 7 Idee Pure]] — idea #4 (Identità prima di Infrastruttura): la procedura serve l'identità del sistema cognitivo, non viceversa
- [[MOC — Indice Pubblico]]

🩹⚙️🐙
