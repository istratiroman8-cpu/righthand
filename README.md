# Roman — Task Manager v3.1

PWA standalone per **studenti di sociologia Sapienza** e **mediatori creditizi**.

## Changelog v3.1 (21/04/2026)

### 🐛 Bug Fix
- **Drag & Drop**: `onDragEnd` usava una funzione anonima che non veniva rimossa correttamente da `removeEventListener` → ora usa `onDragUp` come named function, fix completo
- **Auto-delete**: era basato su giorni e non funzionava. Ora usa **secondi (0-10s)** con slider "Istantaneo / 1-10 sec". Ogni task completata riceve un timer individuale in `autoDelTimers` Map
- **Auto-delete Undo**: il toast "Annulla" chiama ora `cancelAutoDel(id)` prima di ripristinare la task
- **Auto-delete animazione**: la card fa fade-out prima di sparire (`fading-out` CSS class)

### 🗂 Navigation Redesign
- **Bottom nav mobile**: 4 tab (Home / Uni / Medias / Pomo) + **FAB centrale** integrato nella barra → più compatta, nessun tab "Menu" fuori posto
- **Hamburger ☰ top-left** (mobile): apre un **slide drawer** con tutta la navigazione, sezioni, strumenti e link a Impostazioni. Accessibile anche da swipe-to-close sull'overlay
- **Desktop sidebar**: invariata, 5 voci con separatore prima di Impostazioni

### 💾 Autosave on Close
- `visibilitychange` → salva quando la tab passa in background
- `beforeunload` → salva prima del refresh/chiusura
- `pagehide` → salva su iOS PWA (che non emette `beforeunload`)
- Nessun intervallo periodico superfluo — salvataggio reattivo

### Fix minori
- `swipe` non reagisce più se il drawer è aperto
- `Ctrl+,` apre Impostazioni
- `Ctrl+1-4` (non più 5) per le 4 sezioni principali
- Seed task usa helper locale `d(n)` per date offset invece di `offsetStr` rimosso

## Navigazione

### Mobile
| Elemento | Posizione | Azione |
|----------|-----------|--------|
| ☰ hamburger | Top-left | Apre drawer con tutto |
| Bottom nav | Fixed bottom | Home / Uni / Medias / Pomo |
| FAB + | Centro bottom nav | Nuova task |
| Swipe ← → | Task area | Cambia sezione |

### Desktop
| Shortcut | Azione |
|----------|--------|
| `Ctrl+1` | Home |
| `Ctrl+2` | Università |
| `Ctrl+3` | Mediazione |
| `Ctrl+4` | Pomodoro |
| `Ctrl+,` | Impostazioni |
| `Ctrl+N` | Nuova task |
| `↑↓` | Naviga task |
| `Enter` | Apri task selezionata |
| `Delete` | Elimina task selezionata |

## Auto-eliminazione Task Completate

Quando attivata (⚙️ → Impostazioni):
1. Task marcata ✓ → timer `setTimeout` parte
2. Se 0 sec → eliminazione istantanea
3. Se 1-10 sec → card fa fade-out CSS, poi sparisce
4. "Annulla" nel toast → `cancelAutoDel(id)` + ripristino
5. Se si segna come non-completata → timer cancellato

## Deploy GitHub Pages
Carica i 4 file nella root, abilita Pages da Settings → Pages → main / (root).
