# Venstre Syddjurs – App

Officiel mobil PWA (Progressive Web App) for Venstre Syddjurs. Bruges af medlemmer, vælgere, bestyrelsen, byrådsgruppen og administratorer til nyheder, kalender, video og mærkesager.

**Live:** https://johnfinmann-ctrl.github.io/venstre-gemini/

## Struktur

```
index.html      – Hele appen (HTML, CSS via Tailwind, JavaScript)
manifest.json   – PWA-manifest (navn, ikoner, farver, installation)
sw.js           – Service worker (offline-cache)
icon-192.png    – App-ikon, 192×192
icon-512.png    – App-ikon, 512×512
README.md       – Denne fil
```

## Teknologi

- Rent HTML/CSS/JS – ingen build-trin nødvendigt
- [Tailwind CSS](https://tailwindcss.com/) via CDN
- [Lucide Icons](https://lucide.dev/) via CDN
- Data gemmes i `localStorage` (midlertidig løsning – forberedt til migrering til Supabase)

## Funktioner

- **Forside** – hero, fremhævet video, seneste nyheder og kommende aktiviteter
- **Nyheder** – kategoriseret nyhedsmodul med fuld CRUD via admin
- **Kalender** – aktivitetskalender med fuld CRUD via admin
- **Video** – videoliste med automatisk YouTube-thumbnail
- **Mere** – Mærkesager, Byrådet, Bestyrelse, VU, Bliv medlem, Kontakt, Privatliv/GDPR, Admin
- **Admin** – login-beskyttet dashboard til at redigere alt indhold i appen

## Kørsel lokalt

Åbn `index.html` direkte i en browser, eller kør en simpel lokal server, fx:

```bash
python3 -m http.server 8080
```

og besøg `http://localhost:8080`.

## Deployment (GitHub Pages)

Siden er statisk, så GitHub Pages kan serve den direkte fra `main`-branchen (roden af repoet). Under **Settings → Pages**:

- **Source:** Deploy from a branch
- **Branch:** `main` / `(root)`

Ingen build-trin er nødvendige.

## Roadmap

- Migrering fra `localStorage` til Supabase, så flere administratorer kan redigere indhold i realtid
- Push-notifikationer
- Udvidet CMS for VU-siden og kontaktoplysninger
