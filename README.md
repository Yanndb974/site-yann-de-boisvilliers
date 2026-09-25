# Page personnelle de Yann de Boisvilliers

Site Jekyll servi par GitHub Pages, construit sur le thème [researcher](https://github.com/ankitsultana/researcher) d'Ankit Sultana (licence GPL-3.0, voir `LICENSE`).

## Photo et CV : où les déposer

Les deux fichiers vont **à la racine du dépôt**, à côté de `index.md` :

    site-yann-de-boisvilliers/
    ├── _config.yml
    ├── index.md
    ├── photo.jpg   ← portrait
    └── cv.pdf      ← CV

- **`photo.jpg`** (ou `photo.jpeg`, `photo.png`, `photo.webp`). Elle s'affiche en haut à droite de la rubrique *About*, recadrée en cercle de 140 px, et centrée au-dessus du texte sur téléphone. Elle sert aussi d'aperçu quand le lien du site est partagé (LinkedIn, messageries). Prévoir une image carrée d'au moins 600 × 600 px, visage centré dans la moitié haute, moins de 500 Ko.
- **`cv.pdf`**, exactement ce nom. Le lien *CV* apparaît alors dans le menu et dans *Contact*. Mettre en ligne la **version publique** : dans `CV_YDB_FR.tex`, laisser `\publictrue` (ni téléphone ni coordonnées des référents).

Tant qu'un fichier manque, le site masque la photo ou le lien : il n'y a rien à décommenter.

Le `cv.pdf` fourni est la version publique compilée le 25 septembre 2026 : il ne reste qu'à ajouter la photo.

Depuis l'interface web de GitHub : *Add file → Upload files*, glisser les deux fichiers, puis *Commit changes*. Le site se met à jour en une à deux minutes. Pour remplacer le CV, téléverser un nouveau `cv.pdf` du même nom ; si l'ancien s'affiche encore, recharger la page sans cache (Ctrl + Maj + R, ou Cmd + Maj + R sur Mac).

## Modifier le contenu

- Texte de la page : `index.md`.
- Titre, description (aperçu dans les moteurs de recherche et sur LinkedIn), menu : `_config.yml`.

## Adresse du site

Le dépôt s'appelle `site-yann-de-boisvilliers`, d'où `baseurl: "/site-yann-de-boisvilliers"` dans `_config.yml` : le site est servi à `https://<identifiant>.github.io/site-yann-de-boisvilliers/`. Si le dépôt est renommé `<identifiant>.github.io`, remplacer par `baseurl: ""` ; le site est alors servi à `https://<identifiant>.github.io`.

Dans *Settings → Pages* : source *Deploy from a branch*, branche `main`, dossier `/ (root)`.

## Aperçu en local (facultatif)

    gem install jekyll webrick
    jekyll serve

puis ouvrir <http://localhost:4000/site-yann-de-boisvilliers/>.

## Modifications apportées au thème

Mode sombre automatique ; menu compatible avec `baseurl` ; photo et lien CV affichés automatiquement dès que les fichiers existent ; photo recadrée sans déformation ; balises Open Graph corrigées (`property=`) ; script Google Analytics (Universal Analytics, arrêté en 2023) retiré ; contraste des liens renforcé.
