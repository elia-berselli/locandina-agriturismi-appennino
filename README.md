# Locandina · 10 Agriturismi sull'Appennino Bolognese

Locandina HTML self-contained con 10 proposte per **pranzo + pomeriggio in altura** sopra i 500 m, da Casalecchio/Pianoro verso Monghidoro, Monterenzio, Castiglione dei Pepoli e il Mugello.

## 🌐 Online

> **https://elia-berselli.github.io/locandina-agriturismi-appennino/**

Pubblicato via GitHub Pages (build type legacy, HTTPS forzato, nessuna build CI).

## 📂 Contenuto del repo

| File/Cartella | Scopo |
|---------------|-------|
| `index.html` | La locandina (root di GitHub Pages, apribile direttamente nel browser, anche offline) |
| `assets/` | 30 foto JPG delle 10 location (3 per ciascuna) |
| `README.md` | Questo file |
| `.nojekyll` | Disabilita Jekyll su GitHub Pages (necessario per servire `_` nei nomi file) |
| `.gitignore` | Esclude file di lavoro e OS junk |
| `.git/` | Storia git, remote `origin` → GitHub |

## 🏞️ Le 10 location

| # | Location | Località | Quota | Note |
|---|----------|----------|-------|------|
| 1 | La Cartiera dei Benandanti | Monghidoro | 840 m | Biologico, cucina propria |
| 2 | Prato degli Angeli | Monterenzio | ~550 m | Spa, piscina, camere |
| 3 | Il Passeggere | Bruscoli (FI) | 900 m | Faggete, trekking |
| 4 | Ca' De' Magnani | Baragazza | ~800 m | Fattoria didattica, B&B |
| 5 | Locanda Il Mio Rifugio | Gaggio Montano | ~700 m | Spa, piscina, sauna |
| 6 | Ca' del Buco | Montepastore | ~500 m | Biologico, castagne |
| 7 | Podere Caselina | Lago Brasimone | ~900 m | Quota più alta |
| 8 | Antica Hostaria Rocca di Badolo | Badolo | ~500 m | Panorama, rupe |
| 9 | Fattoria Quercia | Valsamoggia | ~500 m | Tranquillità, gruppi |
| 10 | Il Granello | Contrafforte Pliocenico | ~500 m | Riserva naturale, glamping |

## 🖱️ Funzionalità

- **Card cliccabili**: ogni location ha bottoni per Sito ufficiale, Facebook, Mappa Google Maps, TripAdvisor o schede portali (agriturismo.it, agribb.it)
- **Tabella riassuntiva** per confronto rapido (rating, specialità, pomeriggio ideale)
- **Footer con 3 box**: come scegliere per esigenza, vicino a Bologna, più in quota
- **Stampa PDF** nativa (`Ctrl+P` → "Salva come PDF", i bottoni azione si nascondono via `@media print`)

## 🛠️ Tech

- HTML + CSS puri, nessuna build, nessun bundler
- Font: Fraunces (serif titoli) + Inter (sans corpo) da Google Fonts
- Palette: rustico-moderno appennino (beige `#F4EFE6`, marrone `#2A2018`, verde salvia `#6B7A3A`, senape `#C89B3C`, mattone `#B45A3A`)
- Layout 1200 px di larghezza fissa, ottimizzato per desktop e stampa A3
- Icone azione: SVG inline (no dipendenze esterne)

## 🔄 Workflow di modifica

Il progetto sta in `C:\Users\Elia\Desktop\locandina-agriturismi\`. Repo GitHub: `elia-berselli/locandina-agriturismi-appennino` (pubblico). Autenticazione tramite `gh` CLI come `elia-berselli`.

```bash
cd "C:\Users\Elia\Desktop\locandina-agriturismi"
# modifica index.html / aggiungi-togli foto in assets/
git add -A
git commit -m "descrizione modifica"
git push
# → GitHub Pages si aggiorna in 1-2 minuti
```

### Sostituire una foto

1. Prepara la nuova immagine JPG (preferibilmente 1200 px lato lungo, aspect ratio libero)
2. Rinominala come quella da sostituire: `assets/0X_nome_loc_1.jpg`
3. Sovrascrivi il file
4. Commit + push

Per aggiungere una 4ª foto a una card, modifica `index.html` aggiungendo un `<img>` nel blocco `<div class="photos">` e aggiorna la regola `grid-row: span 2` se serve ribilanciare la griglia.

## 📜 Origine delle foto

Siti ufficiali delle strutture, TripAdvisor CDN, agriturismi.it, agribb.it, hotelmix.it, RestaurantGuru, regione.emilia-romagna.it. Tutte raccolte a scopo illustrativo non commerciale.

**Nota di trasparenza**: per **Il Granello** (Contrafforte Pliocenico) la presenza online è scarsissima e il sito ufficiale è protetto da captcha. Le 3 foto usate provengono da un articolo di blog di viaggio (letygoeson.it, "Granello Glamping vicino a Bologna") e da un aggregatore eventi (area.events). Sono della zona e dell'attività ma non c'è certezza assoluta che siano del "Il Granello" specifico di Badolo. Se il proprietario le riconosce come proprie, ottimo; altrimenti sono sostituibili seguendo il workflow sopra.

## 🗒️ Sunto della conversazione con l'AI

**Contesto**: ricerca iniziale di 3-4 agriturismi sopra i 500 m sull'Appennino Bolognese, via ricerche web con Gemini/GPT. Estesa poi a 10 location dopo una seconda richiesta.

**Fasi di lavoro**:
1. **Ricerca location** → 10 strutture: 4 iniziali (Cartiera, Prato degli Angeli, Il Passeggere, Ca' De' Magnani) + 6 nuove (Il Mio Rifugio, Ca' del Buco, Podere Caselina, Antica Hostaria Rocca di Badolo, Fattoria Quercia, Il Granello)
2. **Ricerca foto** → scraping mirato di siti ufficiali, TripAdvisor CDN, hotelmix, agriturismi.it tramite Bing/DDG/Brave Search. 30 foto JPG reali scaricate e verificate (3 per location)
3. **Costruzione locandina HTML** → design rustico-moderno appennino, sistema di token CSS, layout 1200px, palette personalizzata, font Fraunces+Inter, icone SVG inline
4. **Interattività** → bottoni azione per ogni card (24 link totali: siti ufficiali, Facebook, Google Maps, TripAdvisor)
5. **Tabella riassuntiva** → 6 colonne, rating con stelle, tag semantici colorati
6. **Sezione "Come condividere"** → aggiunta e poi rimossa su richiesta
7. **Pubblicazione GitHub Pages** → repo pubblico `elia-berselli/locandina-agriturismi-appennino`, branch `main`, build type legacy, HTTPS enforced
8. **Spostamento sul Desktop** → la cartella è ora in `C:\Users\Elia\Desktop\locandina-agriturismi\`, con `.git` intatto e remote ancora puntato a GitHub

**Decisioni di design**:
- Single HTML self-contained, zero build → facile da modificare e condividere
- 1200 px larghezza fissa → ottimale per desktop e stampa A3 landscape
- Path immagini relativi → la cartella `assets/` viaggia con `index.html`, funziona offline
- CSS scoped in `<style>` (non file esterno) → un solo file da servire
- Bottoni azione nascosti in stampa → il PDF è pulito

**Limitazioni note**:
- Foto "Il Granello" da fonti non verificabili al 100%
- 2-3 foto di dimensioni native ridotte (Ca' del Buco, Fattoria Quercia) scalate con `object-fit: cover` ma qualità di stampa non ottimale
- Niente mappa interattiva (valutata ma non implementata per semplicità)

**Prossime iterazioni possibili** (se richieste):
- Mappa Leaflet/OpenStreetMap con i 10 pin
- Versione PDF A3 pronta per tipografia
- Versione "single file" con immagini in base64 (1 file solo, condivisibile ovunque)
- Mappa delle location con linee di distanza da Bologna
