---
title: "Procedure — Premortem: Simulare il Fallimento"
type: procedure
status: growing
created: 2026-05-01
distilled_from: vault privato + Gary Klein 2007 (concetto originale)
tags:
  - procedure
  - decision-making
  - bias-prevention
  - operativa
  - public
related:
  - "[[Triplo Cablaggio di una Cicatrice]]"
  - "[[Seed — Tre Topologie di una Cicatrice]]"
  - "[[Le 7 Idee Pure]]"
  - "[[MOC — Indice Pubblico]]"
---

# Premortem — Simulare il Fallimento

> *"Immagina che il tuo piano sia gia morto. Adesso dimmi come."*

## 1. Cosa è il Premortem

Il **postmortem** è un esercizio retrospettivo: si fa **dopo** il fallimento, per imparare dalle cause. È utile, ma è un lusso pagato a caro prezzo — quello del fallimento già consumato.

Il **premortem** è il suo gemello immunitario: si fa **prima**. Si simula che la decisione che stai per prendere sia gia fallita 30-60 giorni nel futuro, e si fa **reverse engineering** dei modi in cui è morta. Non "potrebbe non andare bene". È **morta**. Adesso spiega come.

Il framework è stato formalizzato da Gary Klein nel 2007 (Harvard Business Review) come tecnica per disinnescare il bias dell'ottimismo nei team. Nel **Polpo Public Garden** lo applichiamo a un livello piu personale: la mente individuale di chi prende decisioni operative ad alto costo, dove non c'è un team a fare da contrappeso e l'unico anticorpo è una procedura interiorizzata.

Il premortem non è pessimismo. È **pianificazione adversariale di se stessi**.

## 2. Quando applicarlo (trigger)

Non ogni decisione merita un premortem — sarebbe paralisi. Applica la procedura quando si verificano **uno o piu** di questi trigger:

- **Decisione ad alto costo**: oltre 4 ore di lavoro irrecuperabile, oppure una spesa significativa rispetto alla tua scala personale
- **Alta irreversibilità**: una volta firmato/inviato/deployato, tornare indietro costa quanto rifare tutto
- **Comunicazioni a persone strategiche**: clienti chiave, partner, decisori — un'email mandata male non si "ritira"
- **Deploy in produzione con lock-in**: scelte infrastrutturali che ti incatenano per mesi
- **Commit a uno stack tecnologico**: scegliere un linguaggio, un framework, un database centrale per il progetto
- **Firma di contratti**: vincoli legali, finanziari, di esclusiva

Regola spannometrica: se ti accorgi che dopo aver detto "sì" non puoi ragionevolmente dire "no" senza dolore, sei nel territorio del premortem.

## 3. La procedura — 5 passi

### Passo 1 — Definizione

Scrivi la decisione **in una sola frase chiara**. Cosa stai per fare, perché, con che orizzonte temporale.

> *"Sto per investire 8 settimane nel costruire una pipeline di automazione X, perché credo che mi farà risparmiare 10h/settimana entro fine Q3."*

Se non riesci a comprimerla in una frase, la decisione non è ancora abbastanza chiara per essere presa.

### Passo 2 — Salto temporale

Chiudi gli occhi. Immagina che siano passati 30-60 giorni. La decisione è **fallita in modo evidente**. Non "non ha funzionato benissimo". Non "ha avuto qualche difficoltà". È **morta male**: hai perso tempo, soldi, reputazione, o tutti e tre.

L'istruzione interna è precisa: "assumi che il fallimento sia un fatto, non una possibilità".

### Passo 3 — Reverse engineering

Elenca **da 5 a 10 modi specifici** in cui è fallita. Sii concreto e granulare. No generici tipo "è stato troppo complesso". Sì specifici tipo:

- "Il deploy ha rotto il flusso X perché non avevo testato il caso Y"
- "Il cliente Z ha visto il tono dell'email e si è offeso, ha chiuso il contratto"
- "Il fornitore non ha consegnato Z entro la deadline e ho dovuto pagare penali"
- "Ho perso interesse alla settimana 4 e il progetto è diventato debito tecnico"

Piu sei specifico, piu il premortem è utile. Vaghezza = bias che si nasconde.

### Passo 4 — Probabilità + impatto

Per ogni modo di fallimento, segna due numeri:

- **Probabilità** (1-5): quanto è plausibile che accada davvero
- **Impatto** (1-5): quanto fa male se accade

Moltiplicali. Ottieni un punteggio da 1 a 25. **I top 3 sono il tuo focus** — ignora tutto il resto per ora.

### Passo 5 — Mitigazioni

Per ognuno dei top 3, scrivi 1-2 **mitigazioni concrete**. Non "starò piu attento". Concrete: "metto un check automatico", "stipulo contratto a prezzo fisso", "introduco milestone settimanale visibile a un terzo".

**Regola dura**: se non riesci a mitigare le top 3 in modo credibile, **rivedi la decisione**. O cambia il piano, o riduci lo scope, o rimanda. Non procedere "sperando che vada bene" — quello è il modo in cui le decisioni muoiono male.

## 4. Anti-pattern noti

Il premortem ha tre nemici interni che lo svuotano dall'interno:

- **"Sì ma a noi non succederà"** — è il bias dell'ottimismo (Kahneman, *Thinking, Fast and Slow*). La mente, di default, sottostima la probabilità degli eventi negativi sui propri progetti del 30-50%. Il premortem esiste **proprio** per neutralizzare questo bias. Se lo neutralizzi a sua volta dicendo "tanto a me non capita", hai sprecato la procedura.
- **"L'ho già fatto altre volte"** — l'esperienza è preziosa, ma il **contesto è cambiato**. Il fornitore di 2 anni fa non è quello di oggi. Il cliente di ieri non ha lo stesso umore. Lo stack tecnico ha avuto 18 release. L'esperienza ti dà priori, non garanzie.
- **"Il fallimento sarebbe minimo"** — sei sicuro? Hai considerato i **second-order effects**? Una piccola perdita finanziaria può aprire una crisi di fiducia. Una piccola call andata male può generare un'onda di passaparola negativo. Stima sempre l'impatto sul **sistema completo**, non sul singolo evento.

## 5. Output del premortem

Alla fine della procedura devi produrre **un artefatto scritto**, non un'impressione mentale. Tre componenti minime:

1. **Decisione** — un paragrafo: confermata, modificata, o rimandata. Se modificata, specificare cosa cambia.
2. **Mitigazioni applicate** — lista delle azioni concrete che metti in atto **prima** di partire.
3. **Trigger di check successivo** — quando rivedi se le mitigazioni stanno tenendo. Esempio: *"Rivedi a 14 giorni post-launch. Se il modo di fallimento #2 si manifesta, abort"*.

Senza un check successivo programmato, il premortem diventa rito sterile — fai la simulazione, ti senti rassicurato, e ti dimentichi delle mitigazioni il giorno dopo.

## 6. Connessione col sistema cognitivo

Nel dialect del Polpo Public Garden ([[Le 7 Idee Pure]]), una **cicatrice** è una lezione interiorizzata che modifica la struttura della mente. Normalmente le cicatrici sono **post-attive**: nascono dal dolore di un fallimento già accaduto.

Il premortem produce **cicatrici pre-attive**. Sono **inoculazioni**. Il principio emerge prima dell'evento.

Il punto non ovvio è questo: anche se il fallimento poi non avviene, il principio identificato dal premortem **è comunque vero** e merita di essere scolpito. La procedura del [[Triplo Cablaggio di una Cicatrice]] si applica anche qui — la cicatrice pre-attiva va cablata simbolicamente, operativamente e architetturalmente, perché abbia memoria.

Vedi anche [[Seed — Tre Topologie di una Cicatrice]] per la mappa delle forme che una cicatrice può assumere: la pre-attiva è la quarta variante, ottenuta per simulazione.

## 7. Esempio concretizzato

**Decisione**: stai per investire 8 settimane in costruire una nuova pipeline di automazione end-to-end per ridurre il lavoro manuale ricorrente.

**Premortem (salto temporale a 60 giorni)**: la pipeline è morta. È fallita perché:

- **[a]** hai sotto-stimato il tempo di setup di un fattore 3 — quello che pensavi 2 settimane sono diventate 6, e l'energia è finita prima dell'integrazione finale (probabilità 4 × impatto 5 = **20**)
- **[b]** il fornitore principale dello stack ha alzato i prezzi del 40% al rinnovo, rendendo la pipeline non sostenibile economicamente (probabilità 3 × impatto 4 = **12**)
- **[c]** hai perso interesse alla settimana 4, distratto da un'opportunità nuova; il progetto è diventato debito tecnico abbandonato (probabilità 4 × impatto 3 = **12**)

**Top 3 = a, b, c.**

**Mitigazioni**:

- **a**: time-box settimanale rigido + ogni venerdì check sullo scope; se sforo del 50% riduco l'ambito invece che estendere il tempo
- **b**: contratto a prezzo fisso minimo 12 mesi con clausola di non-aumento, oppure secondo fornitore identificato come backup
- **c**: milestone visibili settimanali che mantengono motivazione (output tangibile ogni 7 giorni); accountability esterna a una persona di fiducia che mi chiede stato

**Output**: decisione **confermata con scope ridotto** (6 settimane invece di 8, con feature core invece di full pipeline). Check a 14 giorni: se rate di completamento <60%, abort e pivot a soluzione no-code esistente.

---

## Vedi anche

- [[Triplo Cablaggio di una Cicatrice]] — come trasformare una lezione (anche pre-attiva) in struttura cognitiva persistente
- [[Seed — Tre Topologie di una Cicatrice]] — mappa delle forme di cicatrice nel sistema
- [[Le 7 Idee Pure]] — i principi fondativi del Polpo Public Garden
- [[MOC — Indice Pubblico]] — punto di ingresso al giardino

## Riferimenti

- Klein, G. (2007). *Performing a Project Premortem*. Harvard Business Review, September 2007. [Link Wikipedia: Pre-mortem](https://en.wikipedia.org/wiki/Pre-mortem)
- Kahneman, D. (2011). *Thinking, Fast and Slow*. Farrar, Straus and Giroux. (Capitoli su optimism bias e planning fallacy)
