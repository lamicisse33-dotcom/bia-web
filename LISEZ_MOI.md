# bia.khalam.app — la page d'accueil de BIA

Une seule page. Elle montre le visage de BIA pendant que le serveur se
réveille, puis bascule dessus toute seule.

## Pourquoi elle existe

BIA vit sur `app.khalam.app`. Le serveur s'endort après quinze minutes sans
visite et met environ une minute à revenir ; pendant ce temps, c'est la page
de l'hébergeur qui s'affiche — fond noir, « APPLICATION LOADING ». Sur une
démonstration, c'est sa marque à lui qu'on montre, pas la nôtre.

Cette page-ci vit sur GitHub Pages, qui ne dort jamais. Elle s'affiche tout de
suite, réveille BIA en arrière-plan, et ne bascule qu'une fois qu'elle répond
vraiment.

## Mettre en ligne — trois étapes, une seule fois

**1. Un dépôt GitHub public.** Crée `lamicisse33-dotcom/bia-web`, **public** —
GitHub Pages n'est pas disponible sur les dépôts privés avec un compte
gratuit, et c'est pour ça que `bia-render` ne peut pas s'en charger lui-même.
Dépose-y tout le contenu de ce dossier, à la racine.

**2. GitHub Pages.** Dépôt → Settings → Pages → Source : `Deploy from a
branch`, branche `main`, dossier `/ (root)`. Le fichier `CNAME` fait le
reste : GitHub y lit `bia.khalam.app` et sert le site sous ce nom.

**3. Le DNS, chez Namecheap** (compte khalam33), sur le domaine khalam.app :

| Type | Host | Value |
|---|---|---|
| CNAME | `bia` | `lamicisse33-dotcom.github.io.` |

Exactement comme `gewel` et `wolof`. Compte de quelques minutes à une heure
avant que l'adresse réponde, puis coche **Enforce HTTPS** dans les réglages
Pages.

## Ce qu'il faut savoir

- Le raccourci de l'écran d'accueil doit pointer sur **bia.khalam.app**, plus
  jamais sur l'adresse de l'hébergeur — elle est désactivée depuis le
  9 septembre 2026 et ne répond plus du tout. Le bouton « Installer » de la page suspend la
  bascule exprès, pour qu'on puisse poser le raccourci sur la bonne adresse.
- Si l'adresse du serveur change un jour, une seule ligne à modifier dans
  `index.html` :

      const SERVEURS = ['https://app.khalam.app'];

- La page lit `/api/etat` pour savoir si BIA est debout. Cet accès depuis un
  autre domaine exige un en-tête `access-control-allow-origin` côté serveur :
  il a été ajouté dans `bia-render/app/api/etat/route.ts`. **Sans le
  déploiement de cette version, la page ne basculera jamais toute seule** —
  elle proposera seulement le lien au bout de 90 secondes.
- Les icônes sont le visage « douce » de BIA, découpé dans la planche des
  24 expressions.

## Le wolof à relire

Ces formulations viennent de la liste de Lamine, sauf trois que j'ai écrites
et qu'il faut vérifier :

- `Ay simili rekk…` — « encore quelques secondes »
- `BIA mungi fi.` — « BIA est là »
- `Taxawal na tuuti.` — « ouverture suspendue »
- `Dugg léegi` — « entrer maintenant »

Les autres (`Xaaral tuuti…`, `Bàyyil ma tuuti…`, `Bul ragal, système bi rekk
moo di daw tuuti !`, `Wolof mooy sama làkk bu njëkk`) sont déjà de lui.
