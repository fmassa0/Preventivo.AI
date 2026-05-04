# Preventivo.AI

> Generatore di preventivi professionali in italiano, scritti dall'AI in 30 secondi. Singolo file HTML, gira interamente nel browser. Configurabile con Claude (Anthropic) o GPT (OpenAI). Export PDF nativo.

![Single file](https://img.shields.io/badge/single--file-HTML-1A1714?style=flat-square)
![No build](https://img.shields.io/badge/build-not%20required-C84B31?style=flat-square)
![License](https://img.shields.io/badge/license-MIT-5C5751?style=flat-square)

---

## Cosa fa

Inserisci i dati grezzi (azienda, cliente, voci di costo) e l'AI li trasforma in un preventivo che vende:

- Introduzione persuasiva che collega bisogno e soluzione
- Beneficio concreto per ogni voce di costo
- Sezione "Cosa otterrai" con value proposition
- Closing con CTA operativa
- Calcoli automatici di imponibile, IVA, totale
- Export PDF A4 pronto da inviare

UI editoriale moderna, palette cream/terracotta, fully responsive.

---

## Come usarlo

### Online (più veloce)

Vai su `https://fmassa0.github.io/preventivo-ai/`, apri **Impostazioni**, incolla la tua API key (Anthropic o OpenAI) e genera.

### In locale

Scarica `index.html` e aprilo nel browser. Tutto qui.

```bash
git clone https://github.com/<tuo-username>/preventivo-ai.git
cd preventivo-ai
open index.html  # macOS
# oppure: xdg-open index.html (Linux), start index.html (Windows)
```

---

## Deploy su GitHub Pages

1. Fai il fork o crea un nuovo repo pubblico
2. Carica `index.html` nella root
3. Vai su **Settings → Pages**
4. Branch: `main`, folder: `/ (root)` → **Save**
5. In ~1 minuto sarà live

---

## Stack

| Layer | Tech |
|---|---|
| Markup | HTML5 single-file |
| Styling | Tailwind CSS (CDN) |
| Reattività | Alpine.js 3.x (CDN) |
| AI | Fetch diretto a Claude / OpenAI |
| PDF | html2canvas + jsPDF (CDN) |
| Font | Fraunces (display) + Geist (body) |

Nessuna dipendenza npm, nessun build step.

---

## API key e privacy

Le chiavi API sono salvate **solo** nel `localStorage` del browser dell'utente e inviate direttamente al provider AI scelto (api.anthropic.com o api.openai.com). Nessun server intermediario.

> ⚠️ Per le chiamate ad Anthropic dal browser è necessario l'header `anthropic-dangerous-direct-browser-access: true`. Questo significa che l'app è pensata come strumento personale: ogni utente usa la propria API key. **Non incollare mai la tua chiave dentro l'HTML prima di pushare**.

### Dove ottenere le API key

- **Anthropic**: [console.anthropic.com](https://console.anthropic.com/) → API Keys
- **OpenAI**: [platform.openai.com](https://platform.openai.com/api-keys)

---

## Costi indicativi per preventivo

| Provider | Modello | Costo stimato |
|---|---|---|
| Anthropic | claude-opus-4-7 | ~ $0.04 |
| Anthropic | claude-haiku-4-5 | ~ $0.005 |
| OpenAI | gpt-4o | ~ $0.02 |
| OpenAI | gpt-4o-mini | ~ $0.002 |

Stima per ~1.500 token input + ~1.500 token output.

---

## Personalizzazione

Tutto è in `index.html`:

- **Palette colori**: blocco `tailwind.config` nel `<head>`
- **System prompt AI**: costante `SYSTEM_PROMPT` dentro il `<script>`
- **Modelli supportati**: `<select>` nel pannello Impostazioni
- **Layout preventivo**: blocco `#preventivo-output`

---

## Licenza

MIT — usa, modifica, distribuisci liberamente.
