# Roman — Task Manager Pro v2.1

Task manager PWA standalone per **studenti di sociologia** (Sapienza) e **mediatori creditizi**.

## Funzionalità

### Core
- ✅ Gestione task con categorie: Università, Mediazione Credito, Personale, Urgente
- 🔄 Drag & Drop manuale (touch + mouse sincronizzato)
- ⏳ Snooze con countdown live (10/15/20/30 min)
- 🔍 Ricerca full-text case-insensitive
- 📊 Filtri per priorità + ordinamento multiplo
- 📅 Template rapidi (LTV/DSR, Prep Esame, Pomodoro…)
- 📈 Progress bar e statistiche real-time

### Professional
- 🧮 **Calcolatore DSR/PTI/LTV** inline per pratiche creditizie
- 🍅 **Timer Pomodoro** (25 min lavoro + 5 min pausa)
- 🖨 **Export PDF** task scaduti (stampa nativa)
- 💾 **Export/Import JSON** con backup automatico ogni 5 min
- 🔔 Notifiche browser push

### Mobile/Desktop Adaptive
- **Mobile** (≤768px): layout fullscreen, swipe tab, touch-drag
- **Desktop** (≥1024px): sidebar fissa 280px, grid 2 colonne, keyboard shortcuts

### Keyboard Shortcuts (Desktop)
| Shortcut | Azione |
|----------|--------|
| `Ctrl/⌘ + N` | Nuova task |
| `Ctrl/⌘ + F` | Cerca |
| `Ctrl/⌘ + Enter` | Salva task (nel modal) |
| `↑ / ↓` | Naviga task |
| `Enter` | Apri task selezionata |
| `Delete` | Elimina task selezionata |
| `Esc` | Chiudi modal/drawer |

## Deploy su GitHub Pages

1. Carica tutti i file nella repository
2. Vai su **Settings → Pages**
3. Source: `Deploy from branch` → `main` → `/ (root)`
4. Accedi a `https://<username>.github.io/<repo>/`

## File inclusi

| File | Descrizione |
|------|-------------|
| `index.html` | App principale (standalone) |
| `sw.js` | Service Worker per offline |
| `manifest.json` | PWA manifest |
| `README.md` | Documentazione |

## Persistenza

- **LocalStorage** `roman-tasks-v3`: dati task
- **LocalStorage** `roman-order-v3`: ordine drag & drop (Map serializzata)
- **LocalStorage** `roman-backup-v3`: backup automatico ogni 5 min

## Aggiornamento da v2

La v2.1 migra automaticamente i dati dalla chiave `roman-tasks-v2` a `roman-tasks-v3`.
