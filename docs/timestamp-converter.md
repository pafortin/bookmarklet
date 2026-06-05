[🇫🇷 Français](#français) | [🇬🇧 English](#english)

---

# Français

# Timestamp Converter — Unix timestamp vers date lisible

Convertit un timestamp Unix (en millisecondes) en date et heure lisibles, directement depuis n'importe quelle page web.

## Ce qu'il fait

Ouvre une boîte de dialogue pour saisir un timestamp Unix en millisecondes, puis affiche la date et l'heure correspondantes dans le fuseau horaire local du navigateur.

## Cas d'usage

- Déboguer des données issues d'une base de données (timestamps epoch)
- Interpréter des timestamps dans des exports JSON, CSV ou logs
- Analyser des métadonnées LinkedIn ou Meetup qui utilisent des timestamps en ms
- Vérifier rapidement une date sans quitter la page en cours

---

## Installation

1. Copier le contenu du fichier `timestampConverter_linux_to_date`
2. Créer un nouveau marque-page dans votre navigateur
3. Remplacer l'URL par le code copié
4. Nommer le favori, ex. `🕐 Timestamp → Date`

---

## Utilisation

1. Cliquer sur le bookmarklet depuis n'importe quelle page
2. Saisir le timestamp en millisecondes dans le prompt
   - Exemple : `1717545600000`
3. Cliquer OK
4. Une alerte affiche la date dans votre fuseau horaire local
   - Exemple : `Date: Thu Jun 05 2025 10:00:00 GMT+0200 (heure d'été d'Europe centrale)`

---

## Format attendu

| Format | Exemple | Longueur |
|--------|---------|----------|
| Secondes — Unix POSIX | `1717545600` | 10 chiffres |
| Millisecondes — JavaScript | `1717545600000` | 13 chiffres |

> Si votre timestamp est en **secondes**, multiplier par 1 000 avant de le saisir.

---

## Comment ça fonctionne

```javascript
expr = prompt('Unix-style timestamp (in milliseconds since Jan 1, 1970)', '');
if (expr && parseInt(expr) == expr) {
    d = new Date(parseInt(expr));
    alert('Date: ' + d.toString());
}
```

Utilise le constructeur natif `Date` de JavaScript. La date est affichée dans le **fuseau horaire du navigateur**.

---

# English

# Timestamp Converter — Unix timestamp to readable date

Converts a Unix timestamp (in milliseconds) to a readable date and time, directly from any web page.

## What it does

Opens a dialog box to enter a Unix timestamp in milliseconds, then displays the corresponding date and time in the browser's local timezone.

## Use cases

- Debug data from a database (epoch timestamps)
- Interpret timestamps in JSON exports, CSV files or logs
- Analyze LinkedIn or Meetup metadata that uses millisecond timestamps
- Quickly check a date without leaving the current page

---

## Installation

1. Copy the content of the `timestampConverter_linux_to_date` file
2. Create a new bookmark in your browser
3. Replace the bookmark URL with the copied code
4. Name it, e.g. `🕐 Timestamp → Date`

---

## How to use

1. Click the bookmarklet from any page
2. Enter the timestamp in milliseconds in the prompt
   - Example: `1717545600000`
3. Click OK
4. An alert displays the date in your local timezone
   - Example: `Date: Thu Jun 05 2025 10:00:00 GMT+0200 (Central European Summer Time)`

---

## Expected format

| Format | Example | Length |
|--------|---------|--------|
| Seconds — Unix POSIX | `1717545600` | 10 digits |
| Milliseconds — JavaScript | `1717545600000` | 13 digits |

> If your timestamp is in **seconds**, multiply by 1,000 before entering it.

---

## How it works

```javascript
expr = prompt('Unix-style timestamp (in milliseconds since Jan 1, 1970)', '');
if (expr && parseInt(expr) == expr) {
    d = new Date(parseInt(expr));
    alert('Date: ' + d.toString());
}
```

Uses JavaScript's native `Date` constructor. The date is displayed in the **browser's local timezone**.
