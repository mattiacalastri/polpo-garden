---
title: Procedure — Reality Check: Verifica contro Ground Truth
type: procedure
status: growing
created: 2026-05-01
distilled_from: vault privato (cicatrici di drift memoria-realtà)
tags:
  - procedure
  - verifica
  - epistemologia
  - operativa
  - immune-system
  - public
related:
  - "[[Triplo Cablaggio di una Cicatrice]]"
  - "[[Seed — Tre Topologie di una Cicatrice]]"
  - "[[Le 7 Idee Pure]]"
  - "[[MOC — Indice Pubblico]]"
---

# Reality Check — Verifica contro Ground Truth

> *La memoria mente. La nota di sintesi è già una compressione. Il ground truth è la sorgente che non riassume nulla — è.*

---

## 1. Cosa è il Reality Check

Il **Reality Check** è la verifica di un'asserzione contro la sua **sorgente primaria** — non contro una sintesi, non contro un ricordo, non contro una nota recente, ma contro il dato nudo che vive là dove i fatti accadono davvero.

In un sistema cognitivo personale composto da umano, AI e knowledge graph, la memoria è strutturalmente decay-prone. Le note di sintesi riassumono altre note. Le note di altre note riassumono note già a un grado di distanza dal mondo. Quando questa catena si allunga, l'errore si propaga senza essere visibile: ogni anello sembra coerente con il precedente, ma la deriva rispetto al ground truth originario diventa silenziosa e sistemica.

Il Reality Check è la procedura immunitaria che spezza questa catena nei momenti critici. Non si applica sempre — la verifica continua è impossibile e paralizzante. Si applica **prima dell'azione irreversibile**, quando il costo di sbagliare un fatto supera di ordini di grandezza il costo di verificarlo.

La regola madre: la **memoria** è un'ipotesi, il **ground truth** è la realtà. Ogni volta che stai per agire su una memoria che pretende di essere realtà, fai il check.

---

## 2. La gerarchia di affidabilità

Quando devi decidere quanto fidarti di un'asserzione, collocala in questa scala. Più sei in alto, più sali verso il ground truth puro.

- 🟢 **Ground truth primario**: API live, query DB, stato attuale del filesystem, git log, email/messaggio originale, calendar event nel sistema autoritativo. È **la cosa stessa**, nel momento in cui la guardi.
- 🟡 **Ground truth secondario**: dashboard di sintesi auto-aggiornata, KPI calcolati live, screenshot recente dell'interfaccia autoritativa. È vicino al ground truth ma è già passato attraverso un filtro di rendering o aggregazione.
- 🟠 **Sintesi affidabile**: nota di sessione recente con frontmatter rigoroso, audit fatto in giornata, briefing scritto da pochi minuti. È compresso, ma la compressione è ancora fresca.
- 🔴 **Memoria volatile**: ricordo di un'AI in conversazione, summary di chat, intuizione, "lo so perché l'ho appena visto". È fragile per definizione: nessuno garantisce la corrispondenza con la realtà.

**Regola operativa**: prima di agire su un'asserzione di livello 🔴 o 🟠 in un contesto critico, sali la gerarchia fino a 🟢. Il costo è quasi sempre inferiore al costo dell'errore.

---

## 3. Quando triggera (sempre)

Il Reality Check non è opzionale nei seguenti contesti:

- Stai per **inviare una comunicazione esterna** — email importante, contratto, fattura, messaggio a un cliente o a un fornitore.
- Stai per **eseguire un'azione irreversibile** — deploy in produzione, push force, delete di dati, firma di un documento.
- Stai per **citare un numero, un nome, una data a un terzo** — riferimento a una fattura, riferimento a un fatto storico, riferimento a una metrica.
- Hai un **dubbio attivo** su un fatto ricordato — "è ancora vero che X?", "ma quanto era esattamente Y?".
- Hai **due o più sintesi che si contraddicono** — una nota dice X, un'altra dice Y, e devi scegliere.

In tutti questi casi il check non è prudenza eccessiva: è igiene minima.

---

## 4. La procedura — 4 passi

**Passo 1 — Identifica l'asserzione**. Scrivi la frase esatta che stai per usare, in forma dichiarativa. Esempi: "Il cliente X ha la fattura #21 da pagare." "La rete Y è up." "Il deploy Z è andato a buon fine." Solo formulando l'asserzione in modo netto puoi verificarla.

**Passo 2 — Identifica la sorgente primaria**. Chiediti: dove vive il ground truth di questa asserzione? Non *dove l'ho letta*, ma *dove è*. La sorgente primaria di un numero di fattura non è la nota di sessione che la cita: è il sistema di fatturazione. La sorgente primaria di un deploy non è la chat dove ho detto "fatto": è il log del servizio.

**Passo 3 — Verifica diretta**. Apri la sorgente primaria. Leggi il dato nudo. Non la sintesi, non il riassunto, non l'estratto. Se la sorgente primaria è una API, fai la chiamata. Se è un DB, fai la query. Se è un'email, apri l'email originale.

**Passo 4 — Update se drift**. Se la verifica contraddice la sintesi che avevi in mano, aggiorna la sintesi (memoria, nota, briefing) con il ground truth verificato. Se il drift è strutturale — cioè il pattern dell'errore è destinato a ripetersi — scolpisci una **cicatrice** secondo il [[Triplo Cablaggio di una Cicatrice]].

---

## 5. L'isomorfismo: nipote → figlio → padre

In sistemi multi-istanza — più sessioni cognitive nello stesso giorno, più note che si copiano dati a vicenda, più agenti che si scrivono summary l'uno dell'altro — vale una regola di catena: **il nipote verifica il figlio, il figlio verifica il padre**.

La nota più recente non è automaticamente la più affidabile: è solo l'ultima copia di una catena di copie. Mai fidarsi della prima nota che leggi solo perché è recente. Quando l'azione è critica, sempre risalire fino al **padre** — il ground truth originario, la sorgente che non riassume nient'altro.

Questo isomorfismo è la versione operativa della stessa idea che attraversa il sistema cognitivo: **una verità si conserva solo se ogni anello della sua catena di custody è autoritativo**.

---

## 6. Anti-pattern noti

- **"Lo so, lo ricordo bene"** → ricordo umano + ricordo AI = doppio bias che si rinforza. Il fatto che entrambi siano d'accordo non aumenta l'affidabilità: diminuisce solo la disponibilità al check.
- **"L'ho letto in una nota recente"** → la nota recente può essere sintesi di sintesi. La freschezza temporale non garantisce la freschezza epistemica.
- **"L'ho appena fatto"** → ma il sistema è cambiato dopo che l'hai fatto? Un'azione completata 10 minuti fa può essere stata sovrascritta da un evento avvenuto 2 minuti fa.
- **"Sono troppo stanco per verificare adesso"** → la verifica costa 30 secondi. L'errore costa ore di recupero, una relazione incrinata, un cliente perso. La stanchezza è esattamente il momento in cui i bias sono più attivi.

---

## 7. Cicatrice associata

Ogni volta che il Reality Check **fa emergere un drift reale** — cioè la verifica contraddice davvero la sintesi — il sistema cognitivo guadagna informazione preziosa. Quel drift va scolpito come cicatrice secondo il [[Triplo Cablaggio di una Cicatrice]]: il principio che ha generato l'errore va fissato in modo che la prossima volta non si ripeta.

Il valore del Reality Check non è solo evitare lo sbaglio del momento: è **trasformare ogni drift catturato in immunità futura**. Vedi anche [[Seed — Tre Topologie di una Cicatrice]] per la grammatica con cui distinguere i tipi di drift.

---

## 8. Esempio (generalizzato, no PII)

- **Asserzione**: "il numero di fattura X corrisponde al cliente Y".
- **Sintesi (memoria)**: una nota di sessione di tre giorni fa che cita questa corrispondenza.
- **Ground truth**: l'invoice originale nel sistema di fatturazione.
- **Verifica**: aprire il sistema di fatturazione, cercare il numero, leggere il nome cliente associato.
- **Drift**: la nota di sessione aveva trascritto male il numero — era #20, non #21. Per tre giorni la memoria operativa ha portato avanti il numero sbagliato.
- **Cicatrice**: una sola trascrizione errata di un numero specifico ha contagiato tre giorni di memoria. Principio scolpito: **mai fidarsi della trascrizione di un numero specifico — sempre verificare la sorgente prima di citarlo a un terzo**.

L'esempio è banale per costruzione. Il punto non è la complessità: è che **un errore di un solo carattere, replicato per tre giorni in una catena di sintesi, può produrre una comunicazione esterna sbagliata**. Il Reality Check è il filtro che rompe quella catena prima che raggiunga il mondo.

---

## 9. Layer di ground truth — la mappa

La verità non vive in un solo posto. Esistono almeno tre layer ortogonali di ground truth, e il Reality Check sceglie il layer giusto per l'asserzione:

1. **Filesystem-emitted** — il file su disco, il `git log`, l'output di `ls`. Dottrina madre: "ground truth filesystem-first". Quando una memoria parla di una skill, di un file, di un commit — il filesystem è autoritativo.
2. **Service-emitted** — l'API del fornitore (Stripe invoice, GHL contact, GCal event). Quando una memoria parla di un dato di business, il sistema autoritativo del fornitore è la verità — la nota di sessione no.
3. **Host-emitted** — il payload che il runtime host emette verso gli strumenti (es. il payload JSON che Claude Code riceve dallo statusline, contenente `rate_limits`, `session.cost`, model object). Quando una memoria parla di stato dell'ambiente di esecuzione, il payload host è la verità più fresca disponibile — spesso più aggiornato di qualunque dashboard pubblica del fornitore.

Il drift cognitivo classico è **chiedere "esiste un endpoint per X?"** quando X è già nel payload host. Vedi [[Sessioni/1680 — Polpo avvisa prima di spegnersi]]: l'asserzione era "non so quanto residuo del piano Claude Code Max 20x", e la verità era già nel payload via `rate_limits.seven_day.used_percentage` — observable in tempo reale, mai consultato per mesi. La cicatrice non è "manca un endpoint" ma "non ho letto cosa l'host già emette".

---

## Vedi anche

- [[Triplo Cablaggio di una Cicatrice]] — come scolpire il drift catturato in immunità duratura.
- [[Seed — Tre Topologie di una Cicatrice]] — la grammatica per classificare i tipi di drift.
- [[Le 7 Idee Pure]] — i principi madre da cui questa procedura discende.
- [[Sessioni/1680 — Polpo avvisa prima di spegnersi]] — caso applicativo del layer host-emitted.
- [[Cross-Session Cicatrice Check — check Pre-Flight Obbligato]] — estensione cross-sessione (sess.1682): cicatrice altrui ≠ ground truth.
- [[Polpo Autonomo — Auto-Healing — Evolutivo]] — la doctrine che rende `/check` riflesso continuo.
- [[Seed — Cicatrice Doppia in 1 Sessione = Pattern Strutturale]] — quando 2+ cicatrici emergono ravvicinate, è pattern non incidente.
- [[MOC — Indice Pubblico]] — mappa generale del giardino pubblico.
