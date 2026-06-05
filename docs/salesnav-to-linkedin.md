[🇫🇷 Français](#français) | [🇬🇧 English](#english)

---

# Français

# SalesNav to LinkedIn — Redirection de profil

Convertit instantanément l'URL d'un profil LinkedIn Sales Navigator vers l'URL LinkedIn standard et vous y redirige.

## Ce qu'il fait

Quand vous êtes sur la fiche d'un profil dans Sales Navigator, ce bookmarklet extrait l'ID du profil dans l'URL et vous redirige vers le profil LinkedIn public correspondant.

**Avant :** `https://www.linkedin.com/sales/lead/ACwAAAxxxxxx,NAME_SEARCH`
**Après :** `https://www.linkedin.com/in/ACwAAAxxxxxx`

## Pourquoi c'est utile

- Envoyer un message hors InMail (via LinkedIn standard)
- Vérifier le profil public tel que le voit un recruteur lambda
- Partager un lien de profil à un collègue sans accès Sales Nav
- Utiliser des extensions tierces qui ne fonctionnent que sur LinkedIn standard

---

## Installation

1. Copier le contenu du fichier `SalesNav_to_LinkedIn`
2. Créer un nouveau marque-page dans votre navigateur
3. Remplacer l'URL par le code copié
4. Nommer le favori, ex. `↩ SalesNav → LinkedIn`

---

## Utilisation

1. Ouvrir une fiche profil dans LinkedIn Sales Navigator
2. Cliquer sur le bookmarklet
3. La page se recharge directement sur le profil LinkedIn standard

---

## Comment ça fonctionne

```javascript
var indexOfSalesLead = currentUrl.indexOf("/sales/lead/");
// Extrait l'ID entre "/sales/lead/" et la première virgule
// Reconstruit l'URL en "/in/<id>"
```

L'URL Sales Nav contient l'ID du profil suivi d'une virgule et de métadonnées. Le bookmarklet isole l'ID et reconstruit l'URL propre.

---

## Limitations

- Ne fonctionne que sur les fiches individuelles de type `/sales/lead/`
- Ne fonctionne pas sur les pages de recherche ni sur les fiches entreprise Sales Nav
- Si le profil est privé sur LinkedIn standard, la redirection aboutit mais le contenu peut être masqué

---

# English

# SalesNav to LinkedIn — Profile Redirect

Instantly converts a LinkedIn Sales Navigator profile URL to the standard LinkedIn URL and redirects you there.

## What it does

When you are on a profile page in Sales Navigator, this bookmarklet extracts the profile ID from the URL and redirects you to the corresponding public LinkedIn profile.

**Before:** `https://www.linkedin.com/sales/lead/ACwAAAxxxxxx,NAME_SEARCH`
**After:** `https://www.linkedin.com/in/ACwAAAxxxxxx`

## Why it's useful

- Send a message outside of InMail (via standard LinkedIn)
- Check the public profile as a regular recruiter would see it
- Share a profile link with a colleague who doesn't have Sales Nav access
- Use third-party extensions that only work on standard LinkedIn

---

## Installation

1. Copy the content of the `SalesNav_to_LinkedIn` file
2. Create a new bookmark in your browser
3. Replace the bookmark URL with the copied code
4. Name it, e.g. `↩ SalesNav → LinkedIn`

---

## How to use

1. Open a profile page in LinkedIn Sales Navigator
2. Click the bookmarklet
3. The page reloads directly on the standard LinkedIn profile

---

## How it works

```javascript
var indexOfSalesLead = currentUrl.indexOf("/sales/lead/");
// Extracts the ID between "/sales/lead/" and the first comma
// Rebuilds the URL as "/in/<id>"
```

The Sales Nav URL contains the profile ID followed by a comma and metadata. The bookmarklet isolates the ID and reconstructs the clean URL.

---

## Limitations

- Only works on individual profile pages of type `/sales/lead/`
- Does not work on search pages or Sales Nav company pages
- If the profile is private on standard LinkedIn, the redirect lands but content may be hidden
