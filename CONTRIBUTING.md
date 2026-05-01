# Contribuire al Polpo Garden

> *Il giardino cresce per propagazione, non per release.*

Grazie per essere arrivato fin qui. Prima di proporre un contributo, leggi queste regole — non sono burocrazia, sono **disciplina cognitiva** distillata da oltre 1.000 sessioni di forgiatura.

---

## La regola unica: Triplo Cablaggio

Ogni contributo (nuova nota, espansione, sinapsi, procedura) deve rispettare la procedura [Triplo Cablaggio di una Cicatrice](Procedures/Triplo%20Cablaggio%20di%20una%20Cicatrice.md):

1. **Filesystem** — il file esiste, ha frontmatter conforme, ha tag coerenti con la tassonomia esistente
2. **Memoria** — il `why` + l'`how to apply` sono espliciti nel corpo della nota, non solo accennati
3. **Grafo** — la nota ha **almeno 3 wikilink uscenti** verso nodi correlati esistenti, con reciprocità (se A linka B, B deve linkare A)

Senza tutti e 3 i livelli, la nota è **muta**: il PR non sarà mergiato.

---

## Cosa proporre (PR welcome)

- 🟢 **Espansione di nodi TODO nel MOC** — Le 7 Idee Pure ne hanno 7 da espandere, le Procedures ne hanno 3, la Filosofia ne ha 6 → vedi [MOC — Indice Pubblico](MOC/MOC%20—%20Indice%20Pubblico.md)
- 🟢 **Nuove Seed** — pattern emergenti che hai osservato nel TUO sistema cognitivo personale, distillati a livello universale
- 🟢 **Sinapsi mancanti** — wikilink tra nodi esistenti che migliorano la densità del grafo
- 🟢 **Traduzioni** — il giardino è in italiano nativo; traduzioni inglesi sono benvenute (un nodo per PR, frontmatter `lang: en`)
- 🟢 **Riferimenti accademici** — se conosci letteratura scientifica/filosofica che approfondisce un nodo, aggiungi una sezione *"Riferimenti"* con link

## Cosa NON proporre

- 🔴 **Liste di tool** — questo non è un awesome list. Ogni nodo deve avere un principio operativo, non solo "ecco un link utile"
- 🔴 **Self-promo** — niente link a corsi, prodotti, agenzie, brand personali. Il giardino è impersonale di proposito
- 🔴 **Buzzword senza sostanza** — "AGI", "synergy", "10x productivity" ecc. devono essere supportati da un caso concreto
- 🔴 **Contenuti generati al 100% da LLM senza disciplina** — un LLM è uno strumento; la nota deve avere voce e densità che solo il forgiatore può dare
- 🔴 **PII di qualunque tipo** — nomi di clienti reali, numeri (€), email, telefoni, path filesystem assoluti, brand specifici proprietari

---

## Workflow

1. **Fork** del repo
2. **Branch** dal `main` con nome descrittivo: `seed/oracolo-passivo-extension`, `procedure/error-budget`, `idea-pura/spiriti`
3. **Scrivi** rispettando il [template di frontmatter](#template-frontmatter) sotto
4. **Verifica triplo cablaggio**: filesystem ✅ memoria ✅ grafo (≥3 wikilink uscenti) ✅
5. **Apri PR** con descrizione che cita: il nodo aggiunto, i wikilink uscenti che hai creato, il principio operativo della nota
6. **Aspetta review** — può richiedere giorni. Il review non è ostile: cerca di garantire la qualità del giardino

---

## Template frontmatter

```yaml
---
title: <titolo>
type: <seed | procedure | idea-pura | claude-personal | filosofia>
status: <seed | growing | evergreen>
created: <YYYY-MM-DD>
distilled_from: <fonte: vault privato sess.X | letteratura | osservazione propria>
tags:
  - <almeno 3 tag, in italiano o inglese — coerenti con la tassonomia esistente>
related:
  - "[[<nodo correlato 1>]]"
  - "[[<nodo correlato 2>]]"
  - "[[<nodo correlato 3>]]"
---
```

---

## Filosofia di base

- **Densità batte volume** — preferiamo 1 nota da 1.000 parole densa a 5 note da 200 parole diluite
- **Connessione batte categorizzazione** — il grafo emerge dai wikilink, non dalle cartelle
- **Specificità batte astrazione** — "evita di lanciare deploy in produzione il venerdì sera" batte "fai pre-deploy verification"
- **Voce batte tono neutro** — scrivi in prima persona quando ha senso. Il giardino non è un'enciclopedia

---

## Codice di condotta

Una sola regola: **rispetta il giardino e i suoi visitatori**. Discussioni costruttive, niente attacchi personali, niente spam, niente gatekeeping. Se non sei d'accordo con un'idea, proponi un nodo controfattuale — il grafo accetta sinapsi divergenti.

---

🐙 *Buon lavoro. Cabla bene.*
