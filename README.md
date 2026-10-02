# Metaltec Italia – sito web

Sito statico (HTML + immagini + cataloghi PDF) pubblicato su Cloudflare:
https://metaltec-italia.metaltec-italia.workers.dev/

## Struttura

- `public/` – contenuto del sito (`index.html`, `images/`, `cataloghi/`)
- `wrangler.jsonc` – configurazione Cloudflare (Worker `metaltec-italia` con asset statici)

## Collegare il repository a Cloudflare (una volta sola)

1. Cloudflare Dashboard → **Workers & Pages** → apri il progetto **metaltec-italia**.
2. **Settings → Build → Git repository → Connect**.
3. Autorizza GitHub e scegli `metaltec-italia/metaltec-web`, branch `main`.
4. Impostazioni di build:
   - Build command: *(vuoto)*
   - Deploy command: `npx wrangler deploy`
   - Root directory: `/`
5. Salva. Da quel momento ogni push su `main` pubblica automaticamente il sito.

## Modificare il sito

Modifica i file in `public/`, fai commit e push su `main`: Cloudflare ripubblica da solo.

Anteprima locale: `npx wrangler dev` oppure apri `public/index.html` nel browser.
