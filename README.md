# Panier 2.0 — Prix publics des épiceries du Québec

Ce dépôt héberge **uniquement des observations de prix publics** pour permettre à la PWA Panier 2.0 (Windows et Android) de consulter un catalogue commun, sans authentification et sans frais GitHub Actions.

## Fichiers

- `prix-publics.json` — catalogue d'ingrédients extrait et validé. Les prix peuvent être anciens; consulter **observed_at** avant toute décision d'achat.
- `statut.json` — dates, nombre de relevés, enseignes représentées et limites de couverture.

Les données viennent des API publiques **Bidou** et **épiceries.ca**, avec attribution dans chaque relevé. Les prix sont **indicatifs à l'échelle de l'enseigne** : ils ne prouvent ni les prix d'une succursale précise, ni la disponibilité, ni l'équivalence des formats (lots multiples).

**Couverture non exhaustive** : toutes les références et promotions des cinq enseignes ne sont pas nécessairement disponibles. Les fichiers publics sont mis à jour uniquement quand une nouvelle collecte validée est publiée; GitHub ne collecte rien lui-même.

## Confidentialité

Il n'y a ici **aucune donnée personnelle** : aucun panier, budget, recette privée, achat, inventaire, nom, adresse ou localisation.

Les deux dépôts de code restent privés :
- `Carl2977/panier-2.0` — application
- `Carl2977/panier-2.0-collecteur-prix` — collecteur et cache SQLite

Ne **jamais** publier les dossiers `sorties/`, `catalogue-public.sqlite3`, les diagnostics, les sauvegardes de Panier 2.0 ni des jetons GitHub. Le collecteur génère seulement les fichiers publics avec `PREPARER-CLOUD-WINDOWS.bat`.

## Fonctionnement

Après la publication d'un nouveau rapport sur ce dépôt, la PWA télécharge le fichier HTTPS suivant :

`https://raw.githubusercontent.com/Carl2977/panier-2-0-prix-publics/main/prix-publics.json`

Aucune minute GitHub Actions n'est utilisée. Les anciennes observations ne deviennent pas « récentes » simplement parce qu'un fichier est republié.
