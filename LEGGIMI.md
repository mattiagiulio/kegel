# Marea — installazione su iPhone

Quattro file più le icone. Vanno messi online insieme, nella stessa cartella.

## 1. Pubblicare (5 minuti, gratis)

### Opzione A — Netlify Drop, la più veloce
1. Vai su https://app.netlify.com/drop
2. Trascina l'intera cartella `kegel` nella finestra del browser
3. Ricevi subito un indirizzo tipo `https://qualcosa-1234.netlify.app`

Non serve nemmeno registrarsi per provarla, ma se crei un account gratuito il sito resta permanente e puoi rinominarlo.

### Opzione B — GitHub Pages
1. Crea una repo nuova su GitHub, anche privata non va bene: deve essere **pubblica**
2. Carica i file (bottone "Add file" → "Upload files")
3. Settings → Pages → Source: `Deploy from a branch`, Branch: `main`, cartella `/ (root)` → Save
4. Dopo un paio di minuti l'indirizzo è `https://TUONOME.github.io/NOMEREPO/`

## 2. Installare sull'iPhone

1. Apri l'indirizzo **con Safari** (non Chrome: su iOS solo Safari può aggiungere alla schermata Home)
2. Tocca il bottone Condividi, il quadrato con la freccia in su
3. Scorri e tocca **Aggiungi a Home**
4. Conferma

Ora hai l'icona tra le app. Aprendola parte a tutto schermo, senza barra del browser, e funziona anche in aereo o senza campo.

## 3. Da sapere

- **Apri l'app una prima volta con internet.** Il service worker salva tutto in cache, comprese le due font. Dalla seconda volta funziona offline.
- **I dati stanno solo sul telefono**, in `localStorage`. Nessun server, nessun account, niente esce dal dispositivo.
- **iOS può cancellare i dati** se non apri l'app per diverse settimane. In *Progressi → Dati* trovi Esporta: salva il file JSON su iCloud Drive ogni tanto e con Importa lo rimetti a posto.
- **Aggiornamenti:** se modifichi `index.html`, cambia anche `const CACHE = 'marea-v1'` in `sw.js` (per esempio `marea-v2`), altrimenti il telefono continua a servire la versione vecchia dalla cache.
- **Suoni:** su iPhone il primo suono parte solo dopo che hai toccato "Inizia". È normale, è una regola di Safari, non un difetto.
- **Vibrazione:** iOS non la supporta dalle pagine web, per questo i segnali sono sonori e vocali.

## 4. I file

| File | A cosa serve |
|---|---|
| `index.html` | Tutta l'app: interfaccia, timer, 16 allenamenti, statistiche |
| `manifest.json` | Nome, icone e modalità a tutto schermo |
| `sw.js` | Funzionamento offline |
| `apple-touch-icon.png` | L'icona che vedi sulla schermata Home di iOS |
| `icon-192.png`, `icon-512.png`, `icon-maskable-512.png` | Icone per manifest e Android |

## 5. Il programma di allenamento

Quattro livelli, quattro allenamenti ciascuno. L'app ne sceglie sempre uno diverso dagli ultimi tre svolti, e sale di livello dopo 15 sessioni completate.

| Livello | Posizione | Cosa allena |
|---|---|---|
| 1 · Fondamenta | Sdraiato | Tecnica, tenute 3–5 s |
| 2 · Costruzione | Seduto | Tenute 6–7 s, controllo ad ascensore |
| 3 · Forza | In piedi | Tenute 8 s, sub-massimali prolungate |
| 4 · Funzionale | In piedi | Tenute 10 s, pre-contrazione allo sforzo |

Struttura basata sul protocollo standard di *pelvic floor muscle training*: contrazioni lente per le fibre di tipo I, contrazioni rapide per quelle di tipo II, recupero pari o doppio rispetto alla tenuta, progressione per durata, volume e posizione.

Da 1 a 3 sessioni al giorno, 5–6 giorni a settimana. I risultati sui sintomi compaiono di norma tra la sesta e la dodicesima settimana.

**Nota.** È uno strumento di allenamento, non una valutazione clinica. In caso di dolore, sintomi che peggiorano, difficoltà a percepire la contrazione, o in situazioni particolari come gravidanza, post parto e post chirurgia prostatica, la cosa giusta è una valutazione da un fisioterapista del pavimento pelvico: un pavimento ipertonico dà sintomi simili a uno debole ma richiede il trattamento opposto.
