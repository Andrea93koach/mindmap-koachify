# Mindmap Koachify Ecosistema — Stato Progetto

**Versione ufficiale:** completata e pubblicata  
**Data ultimo aggiornamento:** 24 giugno 2026  
**File principale:** `index.html` (93 KB, tutto inline — HTML + CSS + JS + SVG)  
**GitHub Pages:** https://andrea93koach.github.io/mindmap-koachify/  
**Repository:** https://github.com/Andrea93koach/mindmap-koachify (branch `master`)

---

## Cos'è

Mindmap interattiva SVG che mappa l'intero Ecosistema Formativo Koachify.  
Strumento visivo per workshop con clienti, presentazioni interne e panoramica dell'offerta Academy.

---

## Contenuto mappato

| Livello | Quantità |
|---------|----------|
| Sistemi | 3 (Prosperità, Libertà, Serenità) |
| Pianeti | 9 (3 per sistema) |
| Pilastri | 27 (3 per pianeta) |
| Argomenti formativi | 113 (distribuiti sui 27 pilastri) |
| Moduli completi (corsi approfonditi) | 32 |
| Framework (micro-argomenti) | 27 |

---

## Funzionalità implementate

- **Pan & zoom** — scroll wheel + drag
- **Minimap** — navigazione rapida in alto a sinistra
- **Toggle argomenti** — mostra/nascondi i 113 nodi di dettaglio
- **Filtro per pilastro** — click su un pilastro isola il suo ramo (root → sistema → pianeta → fw → argomenti)
- **Ricerca** — highlight nodi per keyword
- **Sidebar filtri** — filtra per tipo (Modulo Academy, Video YouTube, Lead Magnet)
- **Pannello Architettura** — box HTML fisso con contatori e struttura ecosistema
- **`fit()`** — funzione pubblica per adattare la vista all'intera mappa (usata da `__preview.html`)

---

## Stack tecnico

- Vanilla HTML5 / CSS3 / JavaScript — zero dipendenze, zero CDN
- SVG interattivo inline con 5 layer (`#cl`, `#dcl`, `#nl`, `#dl`, `#hl`)
- Layout algoritmico radiale via `layoutTree()` — 3 settori da 110° + gap 10° = 360°
- Raggi: R1=520 (sistemi), R2=980 (pianeti), R3=1380 (pilastri)
- Sub-nodi argomenti: distanza 200px dal pilastro, step 165px, direzione radiale
- Apribile con doppio clic (non via preview IDE — JS viene sandboxato)

---

## File nella cartella

| File | Descrizione |
|------|-------------|
| `index.html` | Unico file sorgente — tutta l'app |
| `__preview.html` | Wrapper 1600×900 che carica index e chiama `fit()` — per screenshot |
| `screenshot_home.png` | Screenshot della vista home (22 giu 2026) |
| `screenshot_fit.png` | Screenshot con mappa adattata alla finestra (22 giu 2026) |

---

## Tipi di argomento

Ogni argomento ha un tipo che determina il canale di distribuzione:

| Tipo | Canali |
|------|--------|
| `Entrambi` | Modulo Academy + Video YouTube |
| `Formazione Academy` | Modulo Academy |
| `Social / Content` | Video YouTube |
| `Lead Magnet` | Lead Magnet |

Argomenti con `completo: true` = corso approfondito (bordo spesso, testo più luminoso).  
Argomenti con `completo: false` = micro-argomento (bordo sottile, testo dimmer).

---

## Deploy

```bash
cd "c:\Users\Utente\Desktop\Claude Test Code\mindmap koachify ecosistema"
git add index.html
git commit -m "messaggio"
git push   # richiede PAT GitHub (scade ~90 giorni)
```

Branch: `master` — GitHub Pages punta a `/` su `master`.

---

## Stato attuale

La mappa è **completa e pubblicata**. Tutti i 113 argomenti sono inseriti e classificati.  
Il layout radiale è stabile — nessun overlap tra nodi.  
La versione live su GitHub Pages corrisponde all'ultima versione locale.
