[🇫🇷 Français](#français) | [🇬🇧 English](#english)

---

# Français

# Titles & Cies — Générateur d'URLs Sales Navigator

Génère des URLs de recherche LinkedIn Sales Navigator pré-filtrées par entreprises et titres de poste, via une interface graphique en deux étapes. **Un terme par ligne.**

## Ce qu'il fait

Ouvre une fenêtre popup en deux étapes :

1. **Étape 1** — Coller la liste d'entreprises (une par ligne), cliquer **Play**
2. **Étape 2** — Coller la liste de titres de poste (un par ligne), cliquer **Let the music play!**

Les URLs Sales Navigator se génèrent et s'ouvrent directement dans de **nouveaux onglets**. Si la liste d'entreprises dépasse 50 entrées, plusieurs onglets sont ouverts automatiquement (Sales Navigator limite à 50 entreprises par requête).

## Cas d'usage

Vous avez une liste de 30 entreprises cibles et 5 titres à prospecter. En lieu et place de configurer manuellement chaque filtre dans Sales Navigator, ce bookmarklet génère les URLs complètes pré-filtrées et les ouvre en un clic.

---

## Installation

1. Copier le contenu du fichier `Titles&Cies`
2. Créer un nouveau marque-page dans votre navigateur
3. Remplacer l'URL par le code copié
4. Nommer le favori, ex. `🎯 Titles & Cies`

---

## Utilisation

1. Cliquer sur le bookmarklet depuis n'importe quelle page
2. Une fenêtre **"Sales Navigator Accelerator by Anara"** s'ouvre

**Étape 1 — Entreprises**

3. Coller vos entreprises dans la zone de texte, **une par ligne** :
   ```
   Salesforce
   HubSpot
   Pipedrive
   Zoho
   Freshworks
   ```
4. Cliquer **Play**

**Étape 2 — Titres**

5. Coller vos titres de poste, **un par ligne** :
   ```
   Sales Director
   VP Sales
   Head of Sales
   Chief Revenue Officer
   ```
6. Cliquer **Let the music play!**

7. Les URLs s'ouvrent dans de nouveaux onglets, la popup se ferme automatiquement

---

## Détails techniques

- Séparateur : **saut de ligne** (`\n`)
- Chaque terme est encodé au format attendu par l'API Sales Navigator
- Région hardcodée sur **France** (`id: 105015875`)
- Maximum 50 entreprises par URL — plusieurs onglets si liste plus longue

---

## Limitations

- Région fixée sur la **France** — pour d'autres pays, modifier l'ID de région dans le code
- Les URLs correspondent au format d'API Sales Navigator au moment de la création — peut casser si LinkedIn modifie son format

## Voir aussi

- [OR & , Builder](./or-comma-builder.md) — pour préparer des listes de synonymes en booléen
- [LKSN Scraper](./lksn-scraper-csv.md) — pour scraper les résultats une fois la recherche ouverte

---

# English

# Titles & Cies — Sales Navigator URL Generator

Generates LinkedIn Sales Navigator search URLs pre-filtered by companies and job titles, through a two-step graphical interface. **One term per line.**

## What it does

Opens a popup window in two steps:

1. **Step 1** — Paste your company list (one per line), click **Play**
2. **Step 2** — Paste your job title list (one per line), click **Let the music play!**

The Sales Navigator URLs are generated and open directly in **new tabs**. If the company list exceeds 50 entries, multiple tabs open automatically (Sales Navigator limits to 50 companies per query).

## Use case

You have a list of 30 target companies and 5 titles to prospect. Instead of manually configuring each filter in Sales Navigator, this bookmarklet generates the complete pre-filtered URLs and opens them in one click.

---

## Installation

1. Copy the content of the `Titles&Cies` file
2. Create a new bookmark in your browser
3. Replace the bookmark URL with the copied code
4. Name it, e.g. `🎯 Titles & Cies`

---

## How to use

1. Click the bookmarklet from any page
2. A **"Sales Navigator Accelerator by Anara"** window opens

**Step 1 — Companies**

3. Paste your companies into the text area, **one per line**:
   ```
   Salesforce
   HubSpot
   Pipedrive
   Zoho
   Freshworks
   ```
4. Click **Play**

**Step 2 — Titles**

5. Paste your job titles, **one per line**:
   ```
   Sales Director
   VP Sales
   Head of Sales
   Chief Revenue Officer
   ```
6. Click **Let the music play!**

7. The URLs open in new tabs, the popup closes automatically

---

## Technical details

- Separator: **newline** (`\n`)
- Each term is encoded in the format expected by the Sales Navigator API
- Region hardcoded to **France** (`id: 105015875`)
- Maximum 50 companies per URL — multiple tabs if the list is longer

---

## Limitations

- Region fixed to **France** — for other countries, change the region ID in the code
- URLs match the Sales Navigator API format at time of creation — may break if LinkedIn changes its URL format

## See also

- [OR & , Builder](./or-comma-builder.md) — to prepare synonym lists in boolean format
- [LKSN Scraper](./lksn-scraper-csv.md) — to scrape results once the search is open
