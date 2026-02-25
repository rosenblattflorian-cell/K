# SOLAR MITTE ENERGY OS

Produktionsreifes Repo (Next.js 14 + Firebase) mit Schwerpunkt **Vor-Ort Abnahme + Kunden-Signatur per QR-Code (ohne Registrierung)**.

> **Rechtlicher Hinweis (Kurz):** Finger/Touch-Unterschrift = **einfache elektronische Signatur (SES)**. Für Abnahmen oft ausreichend, ersetzt aber nicht automatisch Schriftform. Siehe `/docs/LEGAL_NOTES.md`.

## Tech Stack (fix)
- Next.js 14 (App Router), TypeScript
- Tailwind CSS + shadcn/ui (lightweight in-repo)
- Firebase: Auth, Firestore, Storage, Cloud Functions (Node 20), **App Hosting** (für SSR/Next.js)
- PDF: **pdf-lib**
- QR: **qrcode**
- Tests: Vitest + Playwright
- ESLint + Prettier
- CI: GitHub Actions

## Quickstart (lokal, Emulatoren)
### 1) Voraussetzungen
- Node.js 20+
- Firebase CLI (aktuell)

### 2) Install
```bash
npm install
```

### 3) Firebase Projekt auswählen
```bash
firebase login
firebase use --add
```

### 4) Emulatoren starten + Webapp dev
In zwei Terminals:
```bash
npm run dev:emu
```
```bash
npm run dev:web
```

Oder gemeinsam:
```bash
npm run dev
```

### 5) Seed Templates (2 PDF-Templates mit AcroForm Feldern)
```bash
npm run seed:templates
```

## Deploy (Prod)
Dieses Repo ist für **Firebase App Hosting** konfiguriert.  
Siehe `/docs/ARCHITECTURE.md` und `/docs/SECURITY.md`.

- Backend (Functions + Rules + Indexes):
```bash
npm run deploy:backend
```

- App Hosting Rollout:
```bash
npm run deploy:web
```

## Wichtige Pfade
- Webapp: `apps/web`
- Functions: `functions`
- Doku: `docs/*`
- Brand Assets: `apps/web/public/brand/*`
- Template Seed: `scripts/seed-templates.ts`
