[🇫🇷 Français](#français) | [🇬🇧 English](#english)

---

# Français

# LK Helper Moulinette — Transformateur CSV LinkedHelper

Script Python qui transforme un export CSV brut de **LinkedHelper** en fichier Excel propre, avec les colonnes réorganisées et les URLs nettoyées.

> **Note :** Ce n'est pas un bookmarklet mais un **script Python** à lancer en ligne de commande.
>
> **Compatibilité :** Ce script est conçu exclusivement pour les fichiers exportés par **[LinkedHelper](https://linkedhelper.com)** — il ne fonctionnera pas avec un export CSV natif LinkedIn ou Sales Navigator.

## Ce qu'il fait

1. Lit un fichier CSV exporté depuis **LinkedHelper** (séparateur `;`)
2. Nettoie les URLs de profil : convertit `sales/people/...` en `/in/...` et supprime les paramètres après la virgule
3. Réorganise les colonnes dans un ordre lisible
4. Sauvegarde le résultat en **fichier Excel (.xlsx)** dans `~/Downloads`

## Colonnes retenues (dans l'ordre)

| Colonne | Contenu |
|---------|---------|
| headline | Titre / accroche du profil |
| current_company_position | Poste actuel |
| current_company | Entreprise actuelle |
| profile_url | URL LinkedIn propre (`/in/...`) |
| full_name | Nom complet |
| location_name | Localisation |

---

## Prérequis

- Python 3.x
- Bibliothèques `pandas` et `openpyxl`

```bash
pip install pandas openpyxl
```

---

## Utilisation

1. Placer votre fichier CSV dans `~/Downloads`
2. Ouvrir un terminal
3. Naviguer jusqu'au dossier contenant le script
4. Lancer :

```bash
python3 lKhelper_moulinette mon_export.csv
```

5. Le fichier transformé est sauvegardé sous `~/Downloads/mon_export_transfo.xlsx`

### Exemple complet

```bash
python3 lKhelper_moulinette export_jan2025.csv
# → File saved at /Users/pierre/Downloads/export_jan2025_transfo.xlsx
```

---

## Format d'entrée attendu

CSV délimité par des **points-virgules** (`;`) contenant au minimum les colonnes :
- `headline`
- `current_company_position`
- `current_company`
- `profile_url`
- `full_name`
- `location_name`

C'est le format des exports **LinkedHelper** — différent du format d'export natif LinkedIn ou Sales Navigator.

---

## Voir aussi

- [LKSN Scraper](./lksn-scraper-csv.md) — pour générer les CSV à transformer
- [SN XLS Scraper](./sn-xls-scraper.md) — alternative qui exporte directement en Excel

---

# English

# LK Helper Moulinette — LinkedHelper CSV Transformer

A Python script that transforms a raw **LinkedHelper** CSV export into a clean Excel file, with reorganized columns and cleaned URLs.

> **Note:** This is not a bookmarklet but a **Python script** to run from the command line.
>
> **Compatibility:** This script is designed exclusively for files exported by **[LinkedHelper](https://linkedhelper.com)** — it will not work with a native LinkedIn or Sales Navigator CSV export.

## What it does

1. Reads a CSV file exported from **LinkedHelper** (semicolon `;` delimiter)
2. Cleans profile URLs: converts `sales/people/...` to `/in/...` and strips parameters after the comma
3. Reorganizes columns into a readable order
4. Saves the result as an **Excel file (.xlsx)** in `~/Downloads`

## Retained columns (in order)

| Column | Content |
|--------|---------|
| headline | Profile headline / tagline |
| current_company_position | Current position |
| current_company | Current company |
| profile_url | Clean LinkedIn URL (`/in/...`) |
| full_name | Full name |
| location_name | Location |

---

## Requirements

- Python 3.x
- `pandas` and `openpyxl` libraries

```bash
pip install pandas openpyxl
```

---

## How to use

1. Place your CSV file in `~/Downloads`
2. Open a terminal
3. Navigate to the folder containing the script
4. Run:

```bash
python3 lKhelper_moulinette my_export.csv
```

5. The transformed file is saved as `~/Downloads/my_export_transfo.xlsx`

### Full example

```bash
python3 lKhelper_moulinette export_jan2025.csv
# → File saved at /Users/pierre/Downloads/export_jan2025_transfo.xlsx
```

---

## Expected input format

CSV delimited by **semicolons** (`;`) containing at least these columns:
- `headline`
- `current_company_position`
- `current_company`
- `profile_url`
- `full_name`
- `location_name`

This is the **LinkedHelper** export format — different from the native LinkedIn or Sales Navigator CSV format.

---

## See also

- [LKSN Scraper](./lksn-scraper-csv.md) — to generate the CSVs to transform
- [SN XLS Scraper](./sn-xls-scraper.md) — alternative that exports directly to Excel
