# Servergedöns 🐧

Ein persönlicher Blog über Server, Linux, Docker, Selfhosting und Technik – erstellt mit [Hugo](https://gohugo.io/) und dem schlanken Theme [PaperMod](https://github.com/adityatelange/hugo-PaperMod).

---

## 🚀 Schnelleinstieg

### 1. Lokalen Entwicklungsserver starten

Navigiere in den Ordner und starte Hugo:

```bash
cd servergedoens
hugo server -D
```

Die Website ist anschließend unter [http://localhost:1313/](http://localhost:1313/) im Browser erreichbar (mit Live-Reloading bei Änderungen).

### 2. Einen neuen Blogbeitrag erstellen

```bash
hugo new content posts/mein-neuer-beitrag.md
```

Die Datei wird in `content/posts/mein-neuer-beitrag.md` mit Frontmatter angelegt. 
Wenn der Beitrag fertig ist, setze `draft = false` im Header des Beitrags.

---

## 🌐 Bereitstellung auf GitHub Pages

Die automatische Veröffentlichung ist über GitHub Actions vorbereitet (`.github/workflows/deploy.yml`).

### Schritt 1: GitHub Repository anlegen & verknüpfen

Erstelle auf GitHub ein neues Repository (z. B. `servergedoens` oder `<dein-github-name>.github.io`) und führe lokal aus:

```bash
git remote add origin git@github.com:<dein-github-name>/<repo-name>.git
git push -u origin main
```

### Schritt 2: GitHub Pages aktivieren

1. Gehe in deinem GitHub-Repository auf **Settings** > **Pages**.
2. Wähle unter **Build and deployment** bei **Source** die Option **GitHub Actions** aus.
3. Bei jedem `git push` auf den `main`-Branch wird der Blog nun automatisch gebaut und online gestellt!

### Schritt 3: `baseURL` anpassen (optional)

In `hugo.toml` kannst du die `baseURL` für lokale Konsistenz anpassen:
- Wenn das Repository `<name>.github.io` heißt: `baseURL = 'https://<name>.github.io/'`
- Wenn das Repository `servergedoens` heißt: `baseURL = 'https://<name>.github.io/servergedoens/'`

*(Der GitHub Actions Workflow erkennt die Pages-URL dank `actions/configure-pages` auch automatisch).*

---

## 📁 Projektstruktur

```text
servergedoens/
├── .github/workflows/
│   └── deploy.yml          # GitHub Pages CI/CD Workflow
├── archetypes/
│   └── default.md          # Vorlage für neue Beiträge
├── content/
│   ├── archives.md         # Archiv-Seite
│   ├── search.md           # Suchseite
│   └── posts/              # Deine Blogbeiträge (*.md)
├── themes/
│   └── PaperMod/           # Git Submodule für das Theme
├── hugo.toml               # Hugo- und Theme-Konfiguration
└── .gitignore
```
