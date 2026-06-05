[🇫🇷 Français](#français) | [🇬🇧 English](#english)

---

# Français

# SN XLS Scraper — LinkedIn Sales Navigator vers Excel (V8.2)

Scrape les résultats d'une recherche LinkedIn Sales Navigator et exporte directement en fichier **Excel (.xls)** — sans passer par un CSV intermédiaire.

## Ce qu'il fait

Même moteur de scraping que les versions CSV, mais la sortie est un **XML SpreadsheetML** (`.xls`) reconnu nativement par Excel :

- Scroll automatique simulant un comportement humain
- Extraction des profils visibles au fur et à mesure
- Pagination automatique
- Export Excel sans problème d'encodage des virgules ou des guillemets

## Données collectées

| Colonne | Contenu |
|---------|---------|
| Profile ID | Identifiant unique LinkedIn |
| First Name | Prénom |
| Last Name | Nom |
| Full Name | Nom complet |
| Title | Titre de poste |
| Company | Entreprise actuelle |
| Location | Localisation |
| URL | URL LinkedIn standard (`/in/...`) |

## Format de sortie

Fichier `.xls` (SpreadsheetML), nommé `SalesNav_Leads_AAAA-MM-JJ.xls`, directement ouvrable dans Excel, LibreOffice ou Google Sheets.

---

## Installation

1. Copier intégralement le contenu du fichier `SN_XLS_scraper`
2. Créer un nouveau marque-page dans votre navigateur
3. Remplacer l'URL du marque-page par le code copié
4. Nommer le favori, ex. `⚡ SalesNav → Excel`

---

## Utilisation

1. Aller sur une page de résultats LinkedIn Sales Navigator
2. Cliquer sur le bookmarklet
3. Le panneau "Scraper V8.2" apparaît en bas à droite (bouton vert)
4. Laisser tourner ou cliquer **"Arrêter & Télécharger XLS"**
5. Le fichier `.xls` se télécharge automatiquement

---

## CSV vs XLS — quand choisir quoi ?

| | CSV | XLS |
|-|-----|-----|
| S'ouvre directement dans Excel | Parfois | Toujours |
| Problèmes d'encodage | Possible | Non |
| Données avec virgules | Guillemets requis | Géré nativement |
| Import CRM | Généralement oui | Dépend du CRM |

## Configuration

```javascript
const CONFIG = {
    minScrollTime: 200,
    maxScrollTime: 600,
    scrollStepMin: 150,
    scrollStepMax: 400,
    resultsTarget: 1000,
    nextPageWaitTime: 6000,  // 6 s entre pages
};
```

## Voir aussi

- [LKSN Scraper (CSV, V8)](./lksn-scraper-csv.md)
- [New SN Scraper (CSV, V8.3)](./new-sn-scraper-csv.md)

---

# English

# SN XLS Scraper — LinkedIn Sales Navigator to Excel (V8.2)

Scrapes LinkedIn Sales Navigator search results and exports them directly as an **Excel (.xls)** file — no intermediate CSV required.

## What it does

Same scraping engine as the CSV versions, but the output is a **SpreadsheetML XML** (`.xls`) natively recognized by Excel:

- Automatic scrolling simulating human behavior
- Extracts visible profiles as they load
- Automatic pagination
- Excel export with no comma or quote encoding issues

## Data collected

| Column | Content |
|--------|---------|
| Profile ID | Unique LinkedIn identifier |
| First Name | First name |
| Last Name | Last name |
| Full Name | Full name |
| Title | Job title |
| Company | Current company |
| Location | Location |
| URL | Standard LinkedIn URL (`/in/...`) |

## Output format

`.xls` file (SpreadsheetML), named `SalesNav_Leads_YYYY-MM-DD.xls`, directly openable in Excel, LibreOffice or Google Sheets.

---

## Installation

1. Copy the entire content of the `SN_XLS_scraper` file
2. Create a new bookmark in your browser
3. Replace the bookmark URL with the copied code
4. Name it, e.g. `⚡ SalesNav → Excel`

---

## How to use

1. Go to a LinkedIn Sales Navigator results page
2. Click the bookmarklet
3. The "Scraper V8.2" panel appears in the bottom-right (green button)
4. Let it run or click **"Stop & Download XLS"**
5. The `.xls` file downloads automatically

---

## CSV vs XLS — when to choose which?

| | CSV | XLS |
|-|-----|-----|
| Opens directly in Excel | Sometimes | Always |
| Encoding issues | Possible | No |
| Data with commas | Quotes required | Handled natively |
| CRM import | Generally yes | Depends on CRM |

## Configuration

```javascript
const CONFIG = {
    minScrollTime: 200,
    maxScrollTime: 600,
    scrollStepMin: 150,
    scrollStepMax: 400,
    resultsTarget: 1000,
    nextPageWaitTime: 6000,  // 6 s between pages
};
```

## See also

- [LKSN Scraper (CSV, V8)](./lksn-scraper-csv.md)
- [New SN Scraper (CSV, V8.3)](./new-sn-scraper-csv.md)
