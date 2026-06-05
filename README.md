[🇫🇷 Français](#français) | [🇬🇧 English](#english)

---

# Français

# Bookmarklets — Boîte à outils LinkedIn & Sourcing

Collection de bookmarklets JavaScript (et un script Python) pour automatiser le sourcing sur LinkedIn Sales Navigator et Meetup.com.

---

## Installer un bookmarklet

Un bookmarklet est un favori de navigateur dont l'URL contient du code JavaScript. Pour en installer un :

1. Afficher la **barre de favoris** (`Ctrl+Shift+B` sur Windows/Linux, `Cmd+Shift+B` sur Mac)
2. Faire un **clic droit** sur la barre → "Ajouter un favori" ou "Nouveau signet"
3. Donner un **nom** au favori
4. Dans le champ **URL / Adresse**, coller intégralement le contenu du fichier (la ligne commençant par `javascript:`)
5. Sauvegarder

Pour l'utiliser : naviguer vers la page cible, puis cliquer sur le favori dans la barre.

---

## Outils disponibles

### Sales Navigator — Scrapers

| Outil | Description | Format | Doc |
|-------|-------------|--------|-----|
| `LKSN_Scraper` | Scraper V8 Infinity — jusqu'à 1 000 leads | CSV | [→ doc](docs/lksn-scraper-csv.md) |
| `new_SN_scraper` | Scraper V8.3 — plus lent, plus fiable | CSV | [→ doc](docs/new-sn-scraper-csv.md) |
| `SN_XLS_scraper` | Scraper V8.2 — export Excel direct | XLS | [→ doc](docs/sn-xls-scraper.md) |

Les trois scrapers extraient : nom, prénom, titre, entreprise, localisation et URL LinkedIn propre.

### Sales Navigator — Utilitaires

| Outil | Description | Doc |
|-------|-------------|-----|
| `SalesNav_to_LinkedIn` | Redirige un profil SalesNav vers LinkedIn standard | [→ doc](docs/salesnav-to-linkedin.md) |
| `Titles&Cies` | Génère des URLs SalesNav filtrées via une UI — un terme par ligne | [→ doc](docs/titles-and-companies.md) |
| `OR & , Builder` | Convertit une liste en requête booléenne `OR` ou liste à virgules | [→ doc](docs/or-comma-builder.md) |
| `100` | Force l'affichage de 100 résultats par page | [→ doc](docs/100-par-page.md) |

### Meetup

| Outil | Description | Format | Doc |
|-------|-------------|--------|-----|
| `meetup_scraper.js` | Scrape tous les participants de tous les événements d'un groupe | CSV | [→ doc](docs/meetup-scraper.md) |

### Utilitaires généraux

| Outil | Description | Doc |
|-------|-------------|-----|
| `autoscroll` | Défilement automatique pour les pages à chargement infini | [→ doc](docs/autoscroll.md) |
| `timestampConverter_linux_to_date` | Convertit un timestamp Unix (ms) en date lisible | [→ doc](docs/timestamp-converter.md) |

### Script Python

| Outil | Description | Doc |
|-------|-------------|-----|
| `lKhelper_moulinette` | Transforme un CSV SalesNav en Excel propre | [→ doc](docs/lkhelper-moulinette.md) |

---

## Workflows recommandés

### Sourcing Sales Navigator

```
1. [Titles&Cies]          → Générer l'URL de recherche avec vos filtres
2. [OR & , Builder]       → Préparer vos listes de synonymes en booléen
3. [LKSN_Scraper]         → Scraper les résultats en CSV
4. [lKhelper_moulinette]  → Nettoyer et reformater en Excel
```

### Sourcing Meetup

```
1. Ouvrir la page événements du groupe Meetup
2. [Autoscroll]           → Charger tous les événements visibles
3. [meetup_scraper.js]    → Exporter tous les participants en CSV
```

---

## Compatibilité

Testés sur **Chrome** et **Firefox**. Fonctionnent sur Edge et Brave. Safari impose des restrictions sur les bookmarklets — certains peuvent ne pas s'exécuter.

---

# English

# Bookmarklets — LinkedIn & Sourcing Toolkit

A collection of JavaScript bookmarklets (and one Python script) to automate sourcing on LinkedIn Sales Navigator and Meetup.com.

---

## Installing a bookmarklet

A bookmarklet is a browser bookmark whose URL contains JavaScript code. To install one:

1. Show the **bookmarks bar** (`Ctrl+Shift+B` on Windows/Linux, `Cmd+Shift+B` on Mac)
2. **Right-click** the bar → "Add bookmark" or "New bookmark"
3. Give it a **name**
4. In the **URL / Address** field, paste the entire content of the file (the line starting with `javascript:`)
5. Save

To use it: navigate to the target page, then click the bookmark in the bar.

---

## Available tools

### Sales Navigator — Scrapers

| Tool | Description | Format | Doc |
|------|-------------|--------|-----|
| `LKSN_Scraper` | Scraper V8 Infinity — up to 1,000 leads | CSV | [→ doc](docs/lksn-scraper-csv.md) |
| `new_SN_scraper` | Scraper V8.3 — slower, more reliable | CSV | [→ doc](docs/new-sn-scraper-csv.md) |
| `SN_XLS_scraper` | Scraper V8.2 — direct Excel export | XLS | [→ doc](docs/sn-xls-scraper.md) |

All three scrapers extract: first name, last name, job title, company, location and clean LinkedIn URL.

### Sales Navigator — Utilities

| Tool | Description | Doc |
|------|-------------|-----|
| `SalesNav_to_LinkedIn` | Redirects a SalesNav profile to standard LinkedIn | [→ doc](docs/salesnav-to-linkedin.md) |
| `Titles&Cies` | Generates filtered SalesNav URLs via a UI — one term per line | [→ doc](docs/titles-and-companies.md) |
| `OR & , Builder` | Converts a list into a boolean `OR` query or comma-separated list | [→ doc](docs/or-comma-builder.md) |
| `100` | Forces 100 results per page display | [→ doc](docs/100-par-page.md) |

### Meetup

| Tool | Description | Format | Doc |
|------|-------------|--------|-----|
| `meetup_scraper.js` | Scrapes all attendees from all events of a Meetup group | CSV | [→ doc](docs/meetup-scraper.md) |

### General utilities

| Tool | Description | Doc |
|------|-------------|-----|
| `autoscroll` | Auto-scrolls infinite-scroll pages to load all content | [→ doc](docs/autoscroll.md) |
| `timestampConverter_linux_to_date` | Converts a Unix timestamp (ms) to a readable date | [→ doc](docs/timestamp-converter.md) |

### Python script

| Tool | Description | Doc |
|------|-------------|-----|
| `lKhelper_moulinette` | Transforms a SalesNav CSV into a clean Excel file | [→ doc](docs/lkhelper-moulinette.md) |

---

## Recommended workflows

### Sales Navigator sourcing

```
1. [Titles&Cies]          → Generate the search URL with your filters
2. [OR & , Builder]       → Prepare synonym lists in boolean format
3. [LKSN_Scraper]         → Scrape results to CSV
4. [lKhelper_moulinette]  → Clean and reformat to Excel
```

### Meetup sourcing

```
1. Open the Meetup group's events page
2. [Autoscroll]           → Load all visible events
3. [meetup_scraper.js]    → Export all attendees to CSV
```

---

## Browser compatibility

Tested on **Chrome** and **Firefox**. Works on Edge and Brave. Safari has restrictions on bookmarklets — some may not execute.
