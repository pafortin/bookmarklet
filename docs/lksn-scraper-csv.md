[🇫🇷 Français](#français) | [🇬🇧 English](#english)

---

# Français

# LKSN Scraper — LinkedIn Sales Navigator vers CSV (V8 Infinity)

Scrape automatiquement les résultats d'une recherche LinkedIn Sales Navigator et les exporte en fichier **CSV**.

## Ce qu'il fait

Lance un scraping automatique sur la page de résultats Sales Navigator ouverte dans votre navigateur :

- Défilement progressif simulant un comportement humain (délais aléatoires)
- Extraction de chaque profil visible : nom, prénom, titre, entreprise, localisation, URL LinkedIn propre
- Pagination automatique jusqu'à la cible (1 000 leads par défaut)
- Téléchargement du fichier `.csv` à la fin ou sur demande

## Données collectées

| Colonne | Contenu |
|---------|---------|
| Profile ID | Identifiant unique LinkedIn (slug de l'URL) |
| First Name | Prénom |
| Last Name | Nom |
| Full Name | Nom complet |
| Title | Titre de poste |
| Company | Entreprise actuelle |
| Location | Localisation |
| URL | URL LinkedIn standard (`/in/...`) |

> Les URLs sont converties du format SalesNav (`/sales/lead/`) vers LinkedIn standard (`/in/`).

## Format de sortie

CSV avec BOM UTF-8 (compatible Excel sans conversion), nommé `SalesNav_Leads_V8_AAAA-MM-JJ.csv`.

---

## Installation

1. Copier intégralement le contenu du fichier `LKSN_Scraper`
2. Créer un nouveau marque-page dans votre navigateur
3. Remplacer l'URL du marque-page par le code copié
4. Nommer le favori, ex. `🚀 SalesNav Scraper CSV`

**Chrome / Edge :** Gestionnaire de favoris → clic droit → Ajouter un favori → coller dans le champ URL.

**Firefox :** Barre de marque-pages → clic droit → Nouveau marque-page → coller dans le champ Adresse.

---

## Utilisation

1. Aller sur LinkedIn Sales Navigator et lancer votre recherche
2. Vérifier que vous êtes sur la page de résultats (URL contenant `/sales/search/people`)
3. Cliquer sur le bookmarklet dans la barre de favoris
4. Un panneau apparaît en bas à droite avec une barre de progression
5. Laisser tourner — le scraper défile et change de page automatiquement
6. Cliquer **"Arrêter & Télécharger"** pour stopper et télécharger à tout moment

---

## Configuration

```javascript
const CONFIG = {
    minScrollTime: 200,      // délai minimum entre scrolls (ms)
    maxScrollTime: 600,      // délai maximum entre scrolls (ms)
    scrollStepMin: 150,      // pixels minimum par scroll
    scrollStepMax: 400,      // pixels maximum par scroll
    resultsTarget: 1000,     // nombre de leads cible
    nextPageWaitTime: 4000,  // attente entre deux pages (ms)
};
```

---

## Limitations

- Nécessite un compte **LinkedIn Sales Navigator** actif
- Sales Navigator limite à 2 500 résultats par recherche
- Les délais aléatoires réduisent le risque de détection, mais ne l'éliminent pas

## Comparatif des versions

| Fichier | Version | Format | Attente page |
|---------|---------|--------|-------------|
| `LKSN_Scraper` | V8 Infinity | CSV | 4 s |
| `new_SN_scraper` | V8.3 | CSV | 6 s + 2,5 s au chargement |
| `SN_XLS_scraper` | V8.2 | XLS | 6 s |

---

# English

# LKSN Scraper — LinkedIn Sales Navigator to CSV (V8 Infinity)

Automatically scrapes LinkedIn Sales Navigator search results and exports them as a **CSV** file.

## What it does

Runs an automatic scrape on the Sales Navigator results page open in your browser:

- Progressive scrolling simulating human behavior (random delays)
- Extracts each visible profile: first name, last name, title, company, location, clean LinkedIn URL
- Automatic pagination up to the target (1,000 leads by default)
- Downloads the `.csv` file at the end or on demand

## Data collected

| Column | Content |
|--------|---------|
| Profile ID | Unique LinkedIn identifier (URL slug) |
| First Name | First name |
| Last Name | Last name |
| Full Name | Full name |
| Title | Job title |
| Company | Current company |
| Location | Location |
| URL | Standard LinkedIn URL (`/in/...`) |

> URLs are converted from the SalesNav format (`/sales/lead/`) to the standard LinkedIn format (`/in/`).

## Output format

UTF-8 BOM CSV (opens correctly in Excel without conversion), named `SalesNav_Leads_V8_YYYY-MM-DD.csv`.

---

## Installation

1. Copy the entire content of the `LKSN_Scraper` file
2. Create a new bookmark in your browser
3. Replace the bookmark URL with the copied code
4. Name it, e.g. `🚀 SalesNav Scraper CSV`

**Chrome / Edge:** Bookmark manager → right-click → Add bookmark → paste in the URL field.

**Firefox:** Bookmarks bar → right-click → New bookmark → paste in the Address field.

---

## How to use

1. Go to LinkedIn Sales Navigator and run your search
2. Make sure you are on the results page (URL containing `/sales/search/people`)
3. Click the bookmarklet in the bookmarks bar
4. A panel appears in the bottom-right with a progress bar
5. Let it run — the scraper scrolls and changes pages automatically
6. Click **"Stop & Download"** to stop and download at any time

---

## Configuration

```javascript
const CONFIG = {
    minScrollTime: 200,      // minimum delay between scrolls (ms)
    maxScrollTime: 600,      // maximum delay between scrolls (ms)
    scrollStepMin: 150,      // minimum pixels per scroll
    scrollStepMax: 400,      // maximum pixels per scroll
    resultsTarget: 1000,     // target number of leads
    nextPageWaitTime: 4000,  // wait time between pages (ms)
};
```

---

## Limitations

- Requires an active **LinkedIn Sales Navigator** account
- Sales Navigator limits results to 2,500 per search
- Random delays reduce detection risk but do not eliminate it

## Version comparison

| File | Version | Format | Page wait |
|------|---------|--------|-----------|
| `LKSN_Scraper` | V8 Infinity | CSV | 4 s |
| `new_SN_scraper` | V8.3 | CSV | 6 s + 2.5 s on load |
| `SN_XLS_scraper` | V8.2 | XLS | 6 s |
