# Interventions ChatGPT — Bia Xarit

## 16 novembre 2026 — Icône dorée de l'application installée

### Instruction et autorisation du propriétaire

Le propriétaire a choisi la proposition numéro 1, dorée, pour l'icône de Bia Xarit. Il a demandé de vérifier et corriger son absence après réinstallation sur son téléphone. Sa capture de la fenêtre iPhone « Sur l'écran d'accueil » établit que l'installation provient de `https://bia.khalam.app/` et affiche encore l'ancien visage.

Cette intervention est réalisée sur son instruction explicite et porte uniquement sur l'icône d'installation de Bia Xarit.

### Cause et correction

Le dépôt `bia-web` fournit les métadonnées d'installation de `bia.khalam.app`. La mise à jour préalable des icônes dans `bia-render` ne mettait pas à jour celles de ce domaine.

Les icônes dorées déjà validées sont réutilisées sans modification graphique, avec des noms propres à cette version. Les références Apple, favicon et manifeste pointent vers ces nouveaux fichiers. L'URL du manifeste comporte un paramètre de version pour provoquer sa récupération. Le nom « Bia Xarit », `start_url`, les autres champs d'identité et le comportement d'ouverture sont conservés.

### Fichiers concernés

- `index.html` : uniquement les trois liens de métadonnées d'installation dans `<head>`.
- `manifeste.json` : uniquement les trois références d'icônes.
- `icones/bia-or-20261116-32.png`
- `icones/bia-or-20261116-180.png`
- `icones/bia-or-20261116-192.png`
- `icones/bia-or-20261116-512.png`
- `icones/bia-or-20261116-maskable-512.png`
- `INTERVENTIONS-CHATGPT.md` : cette note.

Le portrait affiché dans l'application (`icone-512.png`), le corps HTML, les scripts, les liens d'ouverture et les anciens fichiers restent identiques. Aucune intervention dans le dépôt `bia-render` ni dans ses fonctions en cours de développement.

### Références et vérification

Base du dépôt : `dbe4ab1f24d87330c0d87f785670daeaa55417a7`.

Icônes sources validées : commit `c188c07076a65d91354b346381dd8ec1d4d9eb22` de `bia-render`.

Commit de correction : celui introduisant cette entrée, intitulé « Bia Xarit : corriger l'icône installée depuis bia.khalam.app ».

Avant publication : vérification des dimensions et du format PNG, contrôle des chemins et du manifeste, comparaison du corps HTML et des scripts avec la base pour confirmer leur conservation. Après publication : contrôle de l'adresse réelle `bia.khalam.app` et du fichier Apple 180 pixels servi. Le rendu final de la fenêtre d'ajout iPhone doit être vérifié sur le téléphone du propriétaire ; il ne peut pas être déduit d'une simple ouverture de l'image.
