# Consignes pour les agents de code

## À lire d'abord

`README.md` (organisation, commandes) et `docs/architecture.md` (pourquoi le
site est construit ainsi).

## Règles

1. **Contenu vérifiable uniquement.** Toute information (diplôme, date,
   chiffre, prix, communication) doit figurer dans `cv.pdf` / `cv-fr.pdf` ou
   être fournie par le propriétaire. Ne jamais inventer de publication, de
   chiffre ou de témoignage.
2. **Toujours les deux langues.** Une modification de contenu touche la page
   anglaise et sa traduction (même `ref`), ainsi que les deux champs `en` / `fr`
   des fichiers `_data/`.
3. **Aucune ressource tierce** : pas de CDN, de police distante, d'analytics,
   d'iframe ni de script. Le gabarit déclare `script-src 'none'` : ajouter du
   JavaScript suppose de revoir la CSP et `docs/architecture.md`.
4. **Plugins** : seulement ceux de la liste blanche de GitHub Pages
   (déploiement classique).
5. **Pas de secret, pas de donnée privée** dans le dépôt.
6. **Ne pas pousser sur `main` ni modifier les réglages GitHub** sans accord.

## Vérifier avant de rendre la main

```bash
export PATH="/opt/homebrew/opt/ruby@3.3/bin:$PATH" LANG=en_US.UTF-8
JEKYLL_ENV=production bundle exec jekyll build
bundle exec htmlproofer _site --disable-external \
  --swap-urls "^/site-yann-de-boisvilliers:" --ignore-files "/redirects.json/"
```

Puis contrôler visuellement à 375 px et à 1280 px, et vérifier qu'il n'y a
aucune erreur de console (une erreur CSP signale une ressource interdite).
Indiquer clairement ce qui a été exécuté et ce qui ne l'a pas été.
