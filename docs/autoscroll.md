[🇫🇷 Français](#français) | [🇬🇧 English](#english)

---

# Français

# Autoscroll — Défilement automatique de page

Fait défiler automatiquement et en continu une page vers le bas au fur et à mesure que son contenu se charge.

## Ce qu'il fait

Lance une boucle qui vérifie toutes les **100 ms** si la hauteur de la page a augmenté (nouveau contenu chargé en lazy-load) et, si c'est le cas, scrolle jusqu'en bas.

Utile pour les pages avec **chargement infini** (infinite scroll) : fils LinkedIn, listes Meetup, résultats de recherche, etc.

## Cas d'usage

- Charger tous les résultats d'une recherche LinkedIn avant de lancer un scraper
- Précharger tous les événements d'une page Meetup avant le [Meetup Scraper](./meetup-scraper.md)
- Tout site avec infinite scroll où vous avez besoin que tout le contenu soit rendu dans le DOM

---

## Installation

1. Copier le contenu du fichier `autoscroll`
2. Créer un nouveau marque-page dans votre navigateur
3. Remplacer l'URL par le code copié
4. Nommer le favori, ex. `⬇️ Autoscroll`

---

## Utilisation

1. Naviguer vers la page à faire défiler
2. Cliquer sur le bookmarklet
3. La page commence à défiler automatiquement
4. Pour arrêter : recharger la page (`F5` / `Cmd+R`)

> Il n'y a pas de bouton "Stop" — le rechargement de page est la façon d'arrêter.

---

## Comment ça fonctionne

```javascript
var lastScrollHeight = 0;
function autoScroll() {
    var sh = document.documentElement.scrollHeight;
    if (sh != lastScrollHeight) {   // du nouveau contenu est apparu
        lastScrollHeight = sh;
        document.documentElement.scrollTop = sh;  // scroll en bas
    }
}
window.setInterval(autoScroll, 100);  // vérifie toutes les 100 ms
```

L'intervalle persiste jusqu'au rechargement de la page.

---

## Limitations

- Impossible d'arrêter sans recharger la page
- Certains sites peuvent détecter le scroll automatique
- Ne simule pas les interactions utilisateur — certains chargements nécessitent un vrai scroll humain

## Voir aussi

- [Meetup Scraper](./meetup-scraper.md) — utiliser autoscroll avant pour charger tous les événements
- [LKSN Scraper](./lksn-scraper-csv.md) — intègre son propre scroll, l'autoscroll n'est pas nécessaire

---

# English

# Autoscroll — Automatic page scrolling

Automatically and continuously scrolls a page downward as its content loads.

## What it does

Starts a loop that checks every **100 ms** whether the page height has increased (new lazy-loaded content) and, if so, scrolls to the bottom.

Useful for **infinite scroll** pages: LinkedIn feeds, Meetup event lists, search results, etc.

## Use cases

- Load all results of a LinkedIn search before running a scraper
- Pre-load all events on a Meetup page before running the [Meetup Scraper](./meetup-scraper.md)
- Any infinite-scroll site where you need all content rendered in the DOM

---

## Installation

1. Copy the content of the `autoscroll` file
2. Create a new bookmark in your browser
3. Replace the bookmark URL with the copied code
4. Name it, e.g. `⬇️ Autoscroll`

---

## How to use

1. Navigate to the page you want to scroll
2. Click the bookmarklet
3. The page starts scrolling automatically
4. To stop: reload the page (`F5` / `Cmd+R`)

> There is no "Stop" button — reloading the page is the way to stop it.

---

## How it works

```javascript
var lastScrollHeight = 0;
function autoScroll() {
    var sh = document.documentElement.scrollHeight;
    if (sh != lastScrollHeight) {   // new content appeared
        lastScrollHeight = sh;
        document.documentElement.scrollTop = sh;  // scroll to bottom
    }
}
window.setInterval(autoScroll, 100);  // checks every 100 ms
```

The interval persists until the page is reloaded.

---

## Limitations

- Cannot be stopped without reloading the page
- Some sites may detect automatic scrolling
- Does not simulate user interactions — some lazy loads require a real human scroll

## See also

- [Meetup Scraper](./meetup-scraper.md) — use autoscroll first to load all events
- [LKSN Scraper](./lksn-scraper-csv.md) — has its own built-in scroll, autoscroll is not needed
