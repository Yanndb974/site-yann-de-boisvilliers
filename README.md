# Yann de Boisvilliers — site personnel

Site académique bilingue (anglais / français) : présentation, recherche
(Observatoire Laudisi, mémoires, communications), CV et contact.

En ligne : <https://yanndb974.github.io/site-yann-de-boisvilliers/>

Site statique Jekyll, publié par GitHub Pages. Ni base de données, ni
formulaire, ni cookie, ni JavaScript : la surface d'attaque se limite à des
fichiers servis en HTTPS.

## Organisation

```
_config.yml          réglages, chemins du CV et de la photo, plugins
_data/
  i18n.yml           libellés de l'interface (en / fr) et menu
  news.yml           actualités de l'accueil (en / fr)
  talks.yml          communications (titre dans sa langue d'origine)
_includes/
  timeline.html      liste datée (actualités, communications)
  date.html          date dans la langue de la page
_layouts/default.html  gabarit unique : en-têtes, sécurité, SEO, menu, pied de page
_sass/               styles (variables, typographie, listes, mise en page)
assets/fonts/        EB Garamond auto-hébergée (licence SIL OFL, voir OFL.txt)
index.md, research.html, cv.html, contact.html   pages anglaises (racine)
fr/                  pages françaises (/fr/, /fr/recherche/, /fr/cv/, /fr/contact/)
404.html             page d'erreur bilingue
cv.pdf, cv-fr.pdf, photo.jpg
docs/architecture.md décisions d'architecture, de design et de sécurité
```

### Pages et traductions

Chaque page porte deux variables : `lang` (déduite du dossier, `fr/` ou
racine) et `ref`. Deux pages qui partagent le même `ref` sont des
traductions l'une de l'autre : le gabarit en déduit le lien de changement de
langue, les balises `hreflang` et l'onglet actif.

Ajouter une page :

1. créer `nouvelle.html` (anglais) avec `ref: nouvelle`, `title`,
   `permalink`, `description` ;
2. créer `fr/nouvelle.html` avec le même `ref` ;
3. si elle doit figurer dans le menu, l'ajouter aux deux listes `nav_items`
   de `_data/i18n.yml`.

Ajouter une actualité ou une communication : une entrée dans
`_data/news.yml` ou `_data/talks.yml`, avec les deux langues. Une date
future affiche le point rouge « à venir ».

## Installation

Prérequis : Ruby 3.3, la version utilisée par GitHub Pages. Les versions plus
récentes ne sont pas prises en charge par le gem `github-pages`.

```bash
brew install ruby@3.3
export PATH="/opt/homebrew/opt/ruby@3.3/bin:$PATH" LANG=en_US.UTF-8
bundle config set --local path vendor/bundle
bundle install
```

`LANG` en UTF-8 est nécessaire : sinon Sass refuse les caractères accentués
des feuilles de style.

## Développement

```bash
bundle exec jekyll serve          # http://127.0.0.1:4000/site-yann-de-boisvilliers/
```

## Tests

```bash
JEKYLL_ENV=production bundle exec jekyll build
bundle exec htmlproofer _site --disable-external \
  --swap-urls "^/site-yann-de-boisvilliers:" --ignore-files "/redirects.json/"
```

La CI (`.github/workflows/ci.yml`) lance le build, la vérification des liens
internes et la recherche de secrets (gitleaks) à chaque push et à chaque pull
request.

## Déploiement

GitHub Pages construit le site depuis la branche `main` (mode classique,
configuré dans *Settings → Pages*). Un merge sur `main` met le site en ligne
en une à deux minutes. Pour revenir en arrière : `git revert` du commit
fautif, puis push.

## Contribuer

Branche par changement, puis pull request vers `main` une fois la CI au
vert. Pour toute modification de contenu, mettre à jour **les deux langues**
et ne publier que des informations vérifiables (le CV PDF fait référence).
Consignes détaillées pour les agents de code : [AGENTS.md](AGENTS.md).

## Sécurité

Voir [SECURITY.md](SECURITY.md) pour signaler une vulnérabilité et pour les
contrôles en place.

## Licence

Le code est dérivé du thème [researcher](https://github.com/ankitsultana/researcher)
d'Ankit Sultana (GPL-3.0, voir `LICENSE`). Les textes, le CV et la photo
restent la propriété de Yann de Boisvilliers et ne sont pas couverts par la
GPL. La police EB Garamond est distribuée sous licence SIL OFL 1.1.
