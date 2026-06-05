[🇫🇷 Français](#français) | [🇬🇧 English](#english)

---

# Français

# 100 par page — Affichage maximal des résultats

Modifie l'URL de la page courante pour forcer l'affichage de 100 résultats par page.

## Ce qu'il fait

Cherche le paramètre `nbParPage` dans l'URL courante et le remplace par `100`, puis recharge la page.

```
Avant : ...&nbParPage=10...
Après : ...&nbParPage=100...
```

## Sites compatibles

Tout site utilisant le paramètre `nbParPage` dans son URL de pagination. Si le paramètre est absent, l'URL reste inchangée et rien ne se passe.

---

## Installation

1. Copier le contenu du fichier `100`
2. Créer un nouveau marque-page dans votre navigateur
3. Remplacer l'URL par le code copié
4. Nommer le favori, ex. `📄 100 par page`

---

## Utilisation

1. Naviguer vers une page de résultats qui supporte `nbParPage` dans l'URL
2. Cliquer sur le bookmarklet
3. La page se recharge avec 100 résultats affichés

---

## Comment ça fonctionne

```javascript
var newUrl = url.replace(/&nbParPage=\d+/, '&nbParPage=100');
window.location.href = newUrl;
```

Remplacement regex simple sur l'URL courante.

---

# English

# 100 per page — Maximum results display

Modifies the current page URL to force displaying 100 results per page.

## What it does

Looks for the `nbParPage` parameter in the current URL and replaces it with `100`, then reloads the page.

```
Before: ...&nbParPage=10...
After:  ...&nbParPage=100...
```

## Compatible sites

Any site using the `nbParPage` parameter in its pagination URL. If the parameter is absent, the URL remains unchanged and nothing happens.

---

## Installation

1. Copy the content of the `100` file
2. Create a new bookmark in your browser
3. Replace the bookmark URL with the copied code
4. Name it, e.g. `📄 100 per page`

---

## How to use

1. Navigate to a results page that supports `nbParPage` in the URL
2. Click the bookmarklet
3. The page reloads showing 100 results

---

## How it works

```javascript
var newUrl = url.replace(/&nbParPage=\d+/, '&nbParPage=100');
window.location.href = newUrl;
```

Simple regex replacement on the current URL.
