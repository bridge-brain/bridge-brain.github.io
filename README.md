# bridgebrAIn Website

Moderne, minimalistische Website für bridgebrAIn – KI-gestützte Strategieberatung für den Mittelstand.

## 🚀 Tech Stack

- **[Astro](https://astro.build/)** – Schnelles, statisches Site-Framework
- **[Tailwind CSS](https://tailwindcss.com/)** – Utility-first CSS
- **[GitHub Pages](https://pages.github.com/)** – Hosting

## 📁 Projektstruktur

```
bridgebrain-website/
├── public/              # Statische Assets (Logos, Favicon, Teamfotos)
├── src/
│   ├── components/      # Wiederverwendbare Komponenten
│   │   ├── Header.astro
│   │   ├── Footer.astro
│   │   ├── Hero.astro
│   │   ├── Products.astro   # Sektion: Unsere Produktentwicklung
│   │   ├── UseCases.astro   # Sektion: KI-Use-Cases für den Mittelstand
│   │   ├── Target.astro     # Sektion: Für wen bridgebrAIn gedacht ist
│   │   ├── Team.astro
│   │   └── Contact.astro
│   ├── layouts/         # Seitenlayouts
│   │   └── Layout.astro
│   ├── pages/           # Seiten (Routing basiert auf Dateistruktur)
│   │   ├── index.astro         # Redirect → /de
│   │   ├── de/                 # Deutsche Seiten (Standard-Sprache, kein /de-Prefix nötig)
│   │   │   ├── index.astro     # Onepager Homepage
│   │   │   ├── imprint.astro
│   │   │   ├── privacy.astro
│   │   │   └── login.astro
│   │   └── en/                 # Englische Seiten
│   │       ├── index.astro
│   │       ├── imprint.astro
│   │       ├── privacy.astro
│   │       └── login.astro
│   └── styles/          # Globale Styles
│       └── global.css
├── astro.config.mjs     # Astro Konfiguration
├── tailwind.config.mjs  # Tailwind Konfiguration
└── package.json
```

## 🛠️ Setup

### 1. Dependencies installieren

```bash
npm install
```

### 2. Development Server starten

```bash
npm run dev
```

Die Seite ist dann unter `http://localhost:4321` erreichbar.

### 3. Für Produktion bauen

```bash
npm run build
```

### 4. Produktions-Build testen

```bash
npm run preview
```

## 🖼️ Teamfotos hinzufügen

1. Erstelle den Ordner `public/team/`
2. Füge Fotos hinzu (z.B. `michael.jpg`, `thorsten.jpg`, `matthias.jpg`)
3. Aktualisiere die Bildpfade in `src/components/Team.astro`

## 🌐 Deployment auf GitHub Pages

Das Deployment läuft über das `gh-pages`-Paket und deployt direkt in den Branch `gh-pages`:

```bash
npm run deploy
```

Dieser Befehl baut die Seite (`npm run build`) und pusht das Ergebnis automatisch in den Branch `gh-pages`, von dem GitHub Pages dann ausliefert.

### GitHub Pages einrichten

1. Gehe zu **Settings** → **Pages**
2. Unter **Source**, wähle **Deploy from a branch**
3. Branch: `gh-pages`, Ordner: `/ (root)`

### Custom Domain einrichten

1. Erstelle eine Datei `public/CNAME` mit dem Inhalt:
   ```
   bridge-brain.ai
   ```

2. Bei deinem Domain-Provider (DNS):
   - Für Apex Domain (`bridge-brain.ai`):
     ```
     A     @     185.199.108.153
     A     @     185.199.109.153
     A     @     185.199.110.153
     A     @     185.199.111.153
     ```
   - Für www-Subdomain:
     ```
     CNAME   www   DEIN-USERNAME.github.io
     ```

3. In GitHub Pages Settings: Custom Domain eintragen und "Enforce HTTPS" aktivieren

## ✏️ Inhalte bearbeiten

### Texte ändern

Die Texte sind in den jeweiligen Komponenten in `src/components/` definiert. Jede Komponente hat ein `content`-Objekt mit deutschen und englischen Übersetzungen.

### Farben anpassen

Die Markenfarben sind in `tailwind.config.mjs` unter `colors.brand` definiert:

```js
brand: {
  'navy': '#0a1628',      // Hauptfarbe (dunkel)
  'blue': '#00a0e3',      // Akzentfarbe (hell)
  'blue-dark': '#006ba6', // Akzentfarbe (dunkel)
}
```

### Neue Seiten hinzufügen

1. Erstelle eine neue `.astro`-Datei in `src/pages/`
2. Für englische Version: in `src/pages/en/`
3. Die URL entspricht dem Dateipfad

## 📧 E-Mail-Obfuscation

E-Mail-Adressen werden automatisch obfuskiert (z.B. `info[at]bridge-brain[dot]ai`) und erst beim Hover/Klick de-obfuskiert, um Spam zu reduzieren.

## 🔧 Mit Claude Code weiterarbeiten

Das Projekt ist so strukturiert, dass es einfach mit Claude Code bearbeitet werden kann:

- Klare Komponentenstruktur
- Tailwind für schnelles Styling
- Astro für einfaches Hinzufügen neuer Seiten
- Alle Texte zentral in den Komponenten

Beispiel-Prompts für Claude Code:
- "Füge eine neue Sektion 'Services' zur Homepage hinzu"
- "Ändere die Hintergrundfarbe des Hero-Bereichs"
- "Füge einen Blog-Bereich hinzu"

---

**Bridgebrain.AI GmbH** – KI-gestützte Strategieberatung für den Mittelstand
