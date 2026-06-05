[🇫🇷 Français](#français) | [🇬🇧 English](#english)

---

# Français

# Meetup Scraper — Export des participants d'événements

Récupère la liste de tous les participants à tous les événements d'un groupe Meetup et exporte les données en CSV enrichi.

## Ce qu'il fait

Utilise l'API GraphQL interne de Meetup.com pour récupérer les participants de chaque événement visible sur la page du groupe :

1. Détecte automatiquement le nom du groupe depuis l'URL
2. Extrait les IDs de tous les événements visibles dans la page
3. Interroge l'API en parallèle (lots de 5 événements) avec pagination automatique
4. Gère les erreurs réseau et les rate limits (`429`) avec retry et backoff exponentiel
5. Exporte un CSV enrichi avec les détails de participation

## Données collectées

| Colonne | Contenu |
|---------|---------|
| eventId | ID de l'événement |
| memberName | Nom du membre |
| memberId | ID Meetup du membre |
| status | Statut RSVP (YES, ATTENDED) |
| guests | Nombre d'accompagnants |
| eventsAttended | Nombre total d'événements assistés |
| noShowCount | Nombre de no-shows |
| memberRole | Rôle dans le groupe (MEMBER, ORGANIZER...) |
| memberStatus | Statut dans le groupe (ACTIVE...) |
| isFamiliarFace | 1 si membre régulier, 0 sinon |

## Format de sortie

CSV nommé `meetup_<groupe>_enriched_AAAA-MM-JJ.csv`.

---

## Installation

1. Copier le contenu du fichier `meetup_scraper.js`
2. Créer un nouveau marque-page dans votre navigateur
3. Remplacer l'URL par le code copié
4. Nommer le favori, ex. `🎯 Meetup Scraper`

---

## Utilisation

### Étape 1 — Préparer la page

1. Aller sur la page d'événements d'un groupe Meetup (`meetup.com/nom-du-groupe/events/`)
2. **Faire défiler la page manuellement** pour charger tous les événements — ou utiliser le [bookmarklet Autoscroll](./autoscroll.md)

### Étape 2 — Lancer le scraper

3. Cliquer sur le bookmarklet
4. Un panneau apparaît en haut à droite avec une barre de progression
5. Attendre la fin — le temps dépend du nombre d'événements et de participants

### Étape 3 — Résultat

6. Le fichier CSV se télécharge automatiquement
7. Le panneau affiche le bilan (X événements, Y participants)

---

## Fonctionnalités

- **Bouton Pause / Resume** : suspendre et reprendre la récupération
- **Retry automatique** : jusqu'à 5 tentatives avec backoff exponentiel en cas d'erreur réseau
- **Gestion du rate limit** : respecte le header `Retry-After` de l'API Meetup

---

## Limitations

- Requiert d'être **connecté à Meetup.com** avec un compte ayant accès au groupe
- Ne récupère que les événements **visibles sur la page** au moment du lancement
- Récupère uniquement les RSVP `YES` et `ATTENDED` (pas les `NO` ni les listes d'attente)
- L'API GraphQL de Meetup peut évoluer — si le scraper ne fonctionne plus, le hash de requête dans le code doit être mis à jour

## Voir aussi

- [Autoscroll](./autoscroll.md) — charger tous les événements avant de scraper

---

# English

# Meetup Scraper — Event Attendee Export

Retrieves the list of all attendees for all events of a Meetup group and exports the data as an enriched CSV.

## What it does

Uses Meetup.com's internal GraphQL API to retrieve attendees for each event visible on the group page:

1. Automatically detects the group name from the URL
2. Extracts IDs of all events visible on the page
3. Queries the API in parallel (batches of 5 events) with automatic pagination
4. Handles network errors and rate limits (`429`) with retry and exponential backoff
5. Exports an enriched CSV with participation details

## Data collected

| Column | Content |
|--------|---------|
| eventId | Event ID |
| memberName | Member name |
| memberId | Meetup member ID |
| status | RSVP status (YES, ATTENDED) |
| guests | Number of guests |
| eventsAttended | Total events attended |
| noShowCount | Number of no-shows |
| memberRole | Role in the group (MEMBER, ORGANIZER...) |
| memberStatus | Group membership status (ACTIVE...) |
| isFamiliarFace | 1 if regular attendee, 0 otherwise |

## Output format

CSV named `meetup_<group>_enriched_YYYY-MM-DD.csv`.

---

## Installation

1. Copy the content of the `meetup_scraper.js` file
2. Create a new bookmark in your browser
3. Replace the bookmark URL with the copied code
4. Name it, e.g. `🎯 Meetup Scraper`

---

## How to use

### Step 1 — Prepare the page

1. Go to a Meetup group's events page (`meetup.com/group-name/events/`)
2. **Scroll the page manually** to load all events — or use the [Autoscroll bookmarklet](./autoscroll.md)

### Step 2 — Run the scraper

3. Click the bookmarklet
4. A panel appears in the top-right with a progress bar
5. Wait for completion — time depends on the number of events and attendees

### Step 3 — Result

6. The CSV file downloads automatically
7. The panel shows the final count (X events, Y attendees)

---

## Features

- **Pause / Resume button**: suspend and resume the fetch
- **Automatic retry**: up to 5 attempts with exponential backoff on network errors
- **Rate limit handling**: respects the API's `Retry-After` header

---

## Limitations

- Requires being **logged into Meetup.com** with an account that has access to the group
- Only retrieves events **visible on the page** at the time of launch
- Only collects `YES` and `ATTENDED` RSVPs (not `NO` or waitlist)
- Meetup's GraphQL API may change — if the scraper stops working, the request hash in the code needs to be updated

## See also

- [Autoscroll](./autoscroll.md) — load all events before scraping
