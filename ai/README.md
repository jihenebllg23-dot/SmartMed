# Module IA SmartMed

Ce dossier contient les données et les modules intelligents du projet.

## Structure

- `data/` : données simulées et nettoyées
- `prepare/` : scripts de génération et de nettoyage
- `notebooks/` : exploration des variables
- `recommend/` : recommandation de médecins (Sprint 6)
- `wait/` : prédiction du temps d'attente (Sprint 6)
- `reviews/` : analyse des avis (Sprint 6)

## Dictionnaire de données

### Recommandation de médecins

| Variable | Type | Description |
|---|---|---|
| specialty_match | 0/1 | La spécialité correspond à la recherche |
| distance_km | float | Distance patient - médecin |
| rating_norm | float | Note moyenne normalisée (0 à 1) |
| reviews_count | int | Nombre d'avis |
| days_to_next_slot | int | Jours avant le prochain créneau |
| preference_match | 0/1 | Correspond aux préférences du patient |

Cible : `score` (0 à 1)

### Prédiction du temps d'attente

| Variable | Type | Description |
|---|---|---|
| patients_before | int | Patients avant soi dans la file |
| avg_consult_duration | float | Durée moyenne des consultations (min) |
| hour_of_day | int | Heure du rendez-vous |
| day_of_week | int | Jour de la semaine (0 à 6) |
| current_delay | float | Retard accumulé du médecin (min) |
| doctor_avg_overrun | float | Dépassement moyen habituel (min) |

Cible : `wait_minutes` (temps d'attente réel)

### Analyse des avis

| Variable | Type | Description |
|---|---|---|
| review_text | texte | Commentaire du patient |
| rating | int | Note de 1 à 5 |
| language | texte | fr, ar ou mixte |

Cibles : `sentiment` (positif, neutre, négatif) et `themes` (attente, accueil, écoute, prix...)
