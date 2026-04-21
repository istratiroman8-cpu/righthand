# Roman — Task Manager v3.0

PWA standalone per **studenti di sociologia Sapienza** e **mediatori creditizi**.

## Changelog v3.0 (21/04/2026)

### ✨ Nuovo
- **Navigazione unificata**: Sidebar desktop (72px collassata / 260px espansa) + Bottom nav mobile (5 tab)
- **Swipe touch** tra sezioni su mobile
- **Keyboard nav**: `Ctrl+1-5` cambia sezione, `↑↓` naviga task, `Enter` apri, `Delete` elimina
- **Badge counter** dinamici su ogni tab nav (task pending, scaduti, sessioni pomo)
- **Sezione Università** dedicata con filtro automatico cat=university
- **Sezione Mediazione** con calcolatore DSR/PTI/LTV sempre accessibile
- **Pomodoro Tracker** completo: timer SVG circolare progressivo, 3 modalità (25/5/15 min), audio sintetico (Web Audio API), haptic feedback, contatori sessioni/streak, switch auto tra fasi
- **Impostazioni dettagliate**: tema dark/light/auto, 10 accent predefiniti + picker HSL custom, toggle notifiche/suoni/vibrazione, auto-delete task completate con slider giorni
- Material Symbols Rounded per icone (Google Fonts CDN)

### 🐛 Fix mantenuti da v2.2
- `calcCredit()` ternario corretto
- `taskOrder` Map con chiavi Number coerenti
- `showToast()` firma corretta

## Navigazione

| Tab | Desktop (Ctrl+N) | Icona |
|-----|-----------------|-------|
| Home | Ctrl+1 | home |
| Università | Ctrl+2 | school |
| Mediazione | Ctrl+3 | account_balance |
| Pomodoro | Ctrl+4 | timer |
| Impostazioni | Ctrl+5 | settings |

## Pomodoro

Timer circolare SVG con `stroke-dasharray/dashoffset`. Audio: Web Audio API con oscillatore sine a 880Hz (3 beep). Sessioni persistite in `roman-pomo-v3` con contatori oggi/totale/streak.

## Impostazioni

- **Tema**: dark/light/auto (system pref con listener MediaQuery)
- **Accent**: 10 preset + slider HSL (H 0-360, S 20-100%, L 35-85%) → converti in `--accent-rgb` via `hslToRgb()`
- **Notifiche**: Notification API con gestione permessi
- **Suoni**: Web Audio API (AudioContext lazy-init)
- **Vibrazione**: `navigator.vibrate()`
- **Auto-delete**: slider 1-30 giorni, esegue su startup e manualmente, usa `task.doneAt` timestamp

## Deploy GitHub Pages

1. Carica tutti i 4 file nella root del repo
2. Settings → Pages → Deploy from branch → main / (root)
3. PWA installabile da Chrome (Add to Home Screen / Install)

## LocalStorage Keys

| Chiave | Contenuto |
|--------|-----------|
| `roman-tasks-v3` | Array task |
| `roman-order-v3` | Map ordine drag |
| `roman-pomo-v3` | Statistiche Pomodoro |
| `roman-cfg-v3` | Impostazioni utente |
| `roman-bk-v3` | Backup automatico (ogni 5 min) |
