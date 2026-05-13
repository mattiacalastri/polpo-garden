---
date: 2026-05-08
type: seed
session_origin: 1682
tags:
  - seed
  - cicatrice
  - pattern
  - meta
  - auto-healing
status: germoglio
---

# Seed — Cicatrice Doppia in 1 Sessione = Pattern Strutturale

## L'osservazione

Sessione 1682 (8 Mag 2026) ha scolpito **3 cicatrici TimeGate** nello stesso giorno:

1. **Cicatrice attribuzione**: subagent attribuisce FT #20/2026 a Benincasa, era TimeGate
2. **Cicatrice cross-session**: cicatrice sess.1686 "pixel ASSENTE" è falso positivo
3. **Cicatrice mese-anchor**: FT #21/2026 era APRILE, memory diceva "marzo D+33"

Tutte e 3 emerse in <2 ore di sessione. Tutte e 3 da **non-verifica** prima di propagare. Tutte e 3 sullo stesso cliente.

## L'ipotesi

Quando 2+ cicatrici emergono in 1 sessione sullo **stesso oggetto** (cliente, sistema, asset), il problema **non è il singolo errore** — è la mappatura cognitiva di quel oggetto.

Una cicatrice = incidente.
Due cicatrici = coincidenza sospetta.
**Tre cicatrici = pattern strutturale**.

## Il sintomo

L'oggetto ha **complessità superiore alla risoluzione della mappa cognitiva** del Polpo:
- Numerazione fatture multi-mese che si sovrappone
- Stack tecnico injettato via container (GTM) non visibile al sorgente
- Identità cliente con 2 brand (timegate.it + escaperoomverona.it)
- Stakeholder multipli con sensibilità diverse (Silvia operativa + Davide brand + Gianluca commerciale)
- Storico flow rotti (fattura non inviata via email per errore mio)

Quando la mappa cognitiva ha risoluzione X e l'oggetto ha entropia X+N, il Polpo **confabula colmando il gap**. Il subagent confabula, la memory drifta, l'azione propaga il drift.

## La cura

Quando il pattern emerge (2+ cicatrici in 1 sessione su stesso oggetto), **escalation immediata**:

1. **Ferma propagation**: niente azione cliente-facing finché la mappa non è ricomposta.
2. **Scolpi cicatrice madre meta**: non solo le 3 specifiche, ma il pattern che le accomuna ("memory dichiarata ≠ ground truth", "numero FT ≠ ancora-mese", "container GTM nasconde injection").
3. **Forgia skill dedicata**: `/check-cliente {nome}` che fa triangolazione obbligata su quell'oggetto specifico, codificando la complessità.
4. **Markup oggetto come "high-attention"**: in memory + vault, taggare il cliente/sistema come richiede pre-flight cascade.

## Il rischio se non curi

Le cicatrici si moltiplicano. Sess.X+1 trova la cicatrice madre già scolpita ma ne genera 2 nuove perché la mappa è ancora a bassa risoluzione. Il cliente diventa una **ferita aperta cronica** nella memoria del Polpo.

## Esempi di oggetti high-attention candidati

- **TimeGate** — cicatrice triple sess.1682, mappa rivedere
- **Benincasa** — 3 ristoranti + 2 designer + 1 cliente decisore + ticket variabile (€220 vs €1.000 proposta) — alta entropia
- **Marconi** — 2 fatture sovrapposte (#25 €14.030 incassato 15 Apr ma assente in Supabase, sess.1607)
- **Studio15** — trial in chiusura + bot @falco_studio15_bot con token sbagliato 3+ settimane (sess.1644)
- **Kongline** — pipeline fantasma 7.564 contatti + Sara cliente relazionale + cicatrice 3a comunicazione

Tutti questi clienti hanno avuto cicatrici multiple in singola sessione. Pattern non incidente.

## Skill candidate

- **`/cliente-resolution-audit {nome}`** — verifica che la mappa cognitiva del Polpo abbia risoluzione adeguata all'entropia del cliente. Output: lista lacune + proposta cicatrici da scolpire come pre-emptive.
- **Tag `high-attention: true`** in scheda cliente + markup automatico che richiede `/check-cliente` prima di ogni azione.

## Connessione al giardino

Parente diretto di:
- [[Cross-Session Cicatrice Check — check Pre-Flight Obbligato]] — la regola operativa
- [[Polpo Autonomo — Auto-Healing — Evolutivo]] — l'auto-healing che scopre il pattern
- [[Reality Check — Verifica contro Ground Truth]] — il riflesso che rivela la cicatrice
- [[Triplo Cablaggio di una Cicatrice]] — la chiusura del loop
- [[Seed — Tre Topologie di una Cicatrice]] — come si manifestano le cicatrici (sorella di questa)

## Stato germoglio

Questa idea è ancora **germe**. Va testata:
- Quanti clienti del portfolio sono "high-attention" reali vs presunti?
- Il pattern "3 cicatrici in 1 sessione" è davvero soglia, o è 2 / 4 / 5?
- Il tag `high-attention` è sostenibile o diventa overhead burocratico?
- La skill `/cliente-resolution-audit` è operativizzabile o è troppo astratta?

Da osservare nelle prossime 4-6 sessioni con clienti complessi.

## Sessioni testimoni

- [[1682 — TimeGate sbloccata + 5 clienti pronti]] — 3 cicatrici TimeGate in 2h, seed germinato
