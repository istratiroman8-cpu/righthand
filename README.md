# Roman — Task Manager Pro v2.2

Task manager PWA standalone per **studenti di sociologia** (Sapienza) e **mediatori creditizi**.

## Changelog v2.2 (20/04/2026)
- 🐛 **Bug fix critico**: `calcCredit()` — il ternario per il verdetto DSR/PTI era una stringa letterale non eseguita
- 🐛 **Bug fix**: `taskOrder` Map ora usa chiavi `Number` in modo coerente (lettura, scrittura, import)
- 🐛 **Bug fix**: `showToast()` firma corretta — callback undo è il 3° argomento, rimosso 4° fantasma
- 🗑 **Rimossa** progress bar (liberato spazio verticale)
- ⚙️ **Aggiunta** modale Impostazioni (accessibile da ⚙️ in header, tab menu, drawer, sidebar desktop)
- 🎨 **Tema chiaro/scuro/auto** — si sincronizza con il sistema in modalità auto
- 🎨 **Accent color** — 10 colori scelti (Blu, Indigo, Viola, Rosa, Rosso, Arancio, Giallo, Verde, Teal, Grigio)
- ♻️ Rimossa variabile `renderDebounceTimer` doppia (sostituita da `_renderTimer`)
- ♻️ Rimossa `isUpcoming` inutilizzata
- 🔑 Shortcut `Ctrl/⌘+,` apre le impostazioni

## Impostazioni

### Tema
| Opzione | Comportamento |
|---------|--------------|
| 🌙 Scuro | Sempre dark |
| ☀️ Chiaro | Sempre light |
| ⚙️ Auto | Segue `prefers-color-scheme` del SO |

### Accent Color
10 colori disponibili: Blu (default), Indigo, Viola, Rosa, Rosso, Arancio, Giallo, Verde, Teal, Grigio.
Il colore accent si applica a: tab attivi, bordi highlight, tooltip, indicator drag, contatori.

## Funzionalità Core
- ✅ Task con categorie Università/Credito/Personale/Urgente
- 🔄 Drag & Drop manuale (touch + mouse)
- ⏳ Snooze con countdown live (10/15/20/30 min)
- 🔍 Ricerca full-text, filtri priorità, sort multiplo
- 📅 Template rapidi
- 🧮 Calcolatore DSR/PTI/LTV inline
- 🍅 Pomodoro 25+5 min
- 🖨 Stampa PDF scaduti
- 💾 Export/Import JSON + backup automatico 5 min
- 🔔 Notifiche browser push

## Keyboard Shortcuts (Desktop)
| Shortcut | Azione |
|----------|--------|
| `Ctrl/⌘ + N` | Nuova task |
| `Ctrl/⌘ + F` | Cerca |
| `Ctrl/⌘ + ,` | Impostazioni |
| `Ctrl/⌘ + Enter` | Salva task (nel modal) |
| `↑ / ↓` | Naviga task |
| `Enter` | Apri task selezionata |
| `Delete` | Elimina task selezionata |
| `Esc` | Chiudi modal/drawer |

## File da caricare su GitHub Pages
| File | Descrizione |
|------|-------------|
| `index.html` | App principale |
| `sw.js` | Service Worker offline |
| `manifest.json` | PWA manifest |
| `README.md` | Documentazione |
