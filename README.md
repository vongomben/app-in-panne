# App in panne

Gioco didattico di orientamento ITS **Full-Stack Developer**. SPA in HTML/CSS/JS, senza framework e senza build.

Sei in una software house: un’app per prenotare laboratori si è rotta. Cinque stazioni in 5 minuti (niente prova AI).

## Come aprirlo

Serve un server statico (i file si caricano con percorsi relativi):

```bash
npx --yes serve .
```

Poi apri l’URL stampato (di solito `http://localhost:3000`).

## File

| File | Ruolo |
| --- | --- |
| `index.html` | Schermate start / gioco / fine |
| `css/styles.css` | Dashboard morbida, tablet-first |
| `js/stations.js` | Contenuti delle 5 stazioni |
| `js/app.js` | Timer, stazioni, drag/tap, localStorage |
| `js/storage.js` | Persistenza partita |
| `js/complete.js` | `onGameComplete(result)` — hook per un futuro backend |

## Fine partita

`onGameComplete` riceve `{ outcome, stationsCompleted, elapsedSeconds, remainingSeconds, startedAt, finishedAt }`. Oggi logga in console. Domani si può mandare a PocketBase da quella sola funzione.

Versione corrente: `v0.1.1` (costante `APP_VERSION` in `js/app.js`).

Header immagine per stazione (opzionale): campo `image` in `stations.js`.
Misura consigliata **1200 × 400 px** (3:1), oppure 1800 × 600 per schermi densi. WebP/JPG, 80–150 KB.

Il progresso sta in `localStorage` (`app-in-panne-v1`).
