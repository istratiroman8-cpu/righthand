# Roman Task Manager

**v3.3** — PWA Task Manager per sociologia Sapienza e mediatori creditizi.

## Deploy su GitHub Pages

1. Carica tutti i file nella root del repository
2. Vai su **Settings → Pages → Source: Deploy from branch → main / root**
3. Attendi ~60 secondi e visita `https://tuousername.github.io/nome-repo`

## Installazione su iPhone

1. Apri l'URL in **Safari**
2. Tocca **Condividi →Aggiungi alla schermata Home**
3. L'app si apre come app nativa (standalone, senza barra Safari)

## File

| File | Descrizione |
|------|-------------|
| `index.html` | App principale |
| `sw.js` | Service Worker (offline) |
| `manifest.json` | PWA manifest |
| `icon-192.png` | Icona dark 192px |
| `icon-512.png` | Icona dark 512px |
| `icon-light-192.png` | Icona classic 192px |
| `icon-light-512.png` | Icona classic 512px |
| `apple-touch-icon.png` | Icona home screen iOS (dark) |
| `apple-touch-icon-light.png` | Icona home screen iOS (classic) |

## Changelog

- **v3.3** — Selettore icona (Dark / Classic) nelle impostazioni + 12 fix di stabilità
- **v3.2** — iOS native feel, safe areas, `-webkit-fill-available`, touch targets 44pt
- **v3.1** — Bugfix autosave, menu drawer mobile, auto-delete task completate
