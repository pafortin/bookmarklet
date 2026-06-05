[🇫🇷 Français](#français) | [🇬🇧 English](#english)

---

# Français

# New SN Scraper — LinkedIn Sales Navigator vers CSV (V8.3)

Version améliorée du scraper Sales Navigator avec des délais plus longs pour une meilleure fiabilité sur les connexions lentes ou les pages lourdes.

## Ce qu'il fait

Identique au [LKSN Scraper](./lksn-scraper-csv.md) avec deux ajustements :

- **Attente de 2,5 secondes** au chargement de chaque page (contre 1 s en V8) pour laisser le DOM se rendre complètement
- **6 secondes entre les pages** (contre 4 s en V8) pour absorber la latence réseau

Exporte les données en **CSV** (format identique au V8).

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

CSV avec BOM UTF-8, nommé `SalesNav_Leads_AAAA-MM-JJ.csv`.

---

## Installation

1. Copier intégralement le contenu du fichier `new_SN_scraper`
2. Créer un nouveau marque-page dans votre navigateur
3. Remplacer l'URL du marque-page par le code copié
4. Nommer le favori, ex. `📑 SalesNav Scraper V8.3`

---

## Utilisation

1. Aller sur une page de résultats Sales Navigator
2. Cliquer sur le bookmarklet
3. Un panneau bleu apparaît en bas à droite
4. Attendre la fin ou cliquer **"Arrêter & Télécharger CSV"** à tout moment

---

## Quand utiliser cette version ?

- Votre connexion internet est lente ou instable
- Vous observez des profils manqués ou des pages vides avec la V8
- Vous êtes sur un réseau d'entreprise avec latence élevée

## Voir aussi

- [LKSN Scraper (V8 — plus rapide)](./lksn-scraper-csv.md)
- [SN XLS Scraper (V8.2 — export Excel)](./sn-xls-scraper.md)

---

# English

# New SN Scraper — LinkedIn Sales Navigator to CSV (V8.3)

An improved version of the Sales Navigator scraper with longer delays for better reliability on slow connections or heavy pages.

## What it does

Identical to the [LKSN Scraper](./lksn-scraper-csv.md) with two adjustments:

- **2.5-second wait** on each page load (vs. 1 s in V8) to let the DOM fully render
- **6 seconds between pages** (vs. 4 s in V8) to absorb network latency

Exports data as **CSV** (same format as V8).

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

UTF-8 BOM CSV, named `SalesNav_Leads_YYYY-MM-DD.csv`.

---

## Installation

1. Copy the entire content of the `new_SN_scraper` file
2. Create a new bookmark in your browser
3. Replace the bookmark URL with the copied code
4. Name it, e.g. `📑 SalesNav Scraper V8.3`

---

## How to use

1. Go to a Sales Navigator results page
2. Click the bookmarklet
3. A blue panel appears in the bottom-right
4. Wait for completion or click **"Stop & Download CSV"** at any time

---

## When to use this version?

- Your internet connection is slow or unstable
- You notice missed profiles or empty pages with V8
- You are on a corporate network with high latency

## See also

- [LKSN Scraper (V8 — faster)](./lksn-scraper-csv.md)
- [SN XLS Scraper (V8.2 — Excel export)](./sn-xls-scraper.md)
