# Architecture et décisions

## Constat initial (audit du 9 octobre 2026)

- Site Jekyll (thème *researcher*, GPL-3.0) publié par GitHub Pages en mode
  classique ; 4 pages en anglais ; aucune CI ; build impossible en local
  (ni `Gemfile` ni Ruby récent).
- Points forts conservés : typographie EB Garamond reprise du CV PDF, mise en
  page à colonne de dates, point rouge des événements à venir, HTML
  accessible (lien d'évitement, `aria-current`), mode sombre, aucun script.
- Problèmes corrigés : police chargée chez Google (transfert d'adresses IP,
  risque RGPD), aucun titre de page visible, ni `robots.txt` ni sitemap,
  « Resume » au lieu de « CV », aucune version française, pas de CSP.

## Décisions

| Décision | Raison | Alternative écartée |
|---|---|---|
| Rester sur Jekyll + GitHub Pages | site éditorial, déjà en ligne, gratuit ; un générateur statique suffit | migrer vers Astro ou Next : coût et risque sans gain pour un site de 9 pages |
| Bilingue sans plugin : `lang` + `ref` par page, libellés dans `_data/i18n.yml` | `jekyll-polyglot` n'est pas autorisé par GitHub Pages en mode classique | build par GitHub Actions : changerait le mode de déploiement |
| Anglais à la racine, français sous `/fr/` | conserve toutes les URL existantes (déjà indexées et partagées) | — |
| Police auto-hébergée, sous-ensemble latin (≈ 67 Ko) | plus aucune requête tierce ; le latin couvre le français | Google Fonts |
| CSP par `<meta>`, `script-src 'none'` | GitHub Pages n'envoie pas d'en-têtes personnalisés ; le site n'a besoin d'aucun script | — |
| `/resume/` redirigé vers `/cv/` | les anciens liens continuent de fonctionner | supprimer l'ancienne URL |
| Pas d'onglet Publications ni Carnet | aucune publication évaluée ni stratégie éditoriale à ce jour : un onglet vide nuit à la crédibilité | à ouvrir dès la première publication |
| Laudisigram absent pour l'instant | n'est pas encore en ligne ; à présenter sur la page Recherche le jour de sa mise en ligne | — |

## Parcours et hypothèses UX

| Choix | Hypothèse | Mécanisme | Comment l'évaluer |
|---|---|---|---|
| Titre de page visible, petit, au-dessus de la phrase d'ouverture | on sait plus vite où l'on est sans perdre la phrase clé | repérage immédiat, plutôt que de déduire la page de l'onglet actif | test de 5 secondes : « sur quelle page êtes-vous ? » |
| Fiche « Laudisi » en lignes (chaînes, corpus, méthodes, code) | un évaluateur juge plus vite le sérieux du projet avec des faits vérifiables qu'avec un paragraphe | lecture en diagonale, crédibilité fondée sur des faits vérifiables | temps pour retrouver la taille du corpus |
| Trois liens sous l'introduction (Recherche, CV, courriel) | les deux visites typiques, comité de sélection et chercheur, trouvent leur suite sans chercher | réduction du coût de décision, actions proportionnées | clics sur ces liens par rapport au menu (si des statistiques sont un jour ajoutées, sans cookie) |
| Pas de menu « hamburger » sur mobile | quatre entrées tiennent sur une ligne ; les cacher coûte un geste de plus | reconnaissance plutôt que rappel | vérifié à 375 px |
| CV : téléchargement en tête de page | le comité veut souvent le PDF, pas la page | action principale visible tout de suite | — |

Ce sont des hypothèses, non des faits établis. Aucune mesure d'audience
n'est en place (choix de confidentialité).

## Objectifs de qualité

| Objectif | Cible | État au 09/10/2026 |
|---|---|---|
| Build de production | sans erreur | ✅ local (Jekyll 3.10, github-pages 232) |
| Liens internes | 0 cassé | ✅ html-proofer : 17 liens, 9 fichiers |
| Débordement horizontal à 375 px | aucun | ✅ vérifié sur Recherche, CV (FR) |
| Contraste du texte secondaire | ≥ 4,5:1 (WCAG AA) | ✅ 4,84:1 (clair), 6,91:1 (sombre) |
| Titres | un `h1` par page, ordre logique | ✅ 9 pages |
| Requêtes tierces | 0 | ✅ |
| Lighthouse / Core Web Vitals | ≥ 95 | ⏳ non mesuré, à faire sur la version en ligne |
| Lecteur d'écran (VoiceOver) | parcours complet | ⏳ contrôle manuel à faire |

## Limites connues

- `robots.txt` n'est lu par les moteurs qu'à la racine du domaine : sur une
  page de projet GitHub (`/site-yann-de-boisvilliers/`), il est sans effet.
  Le sitemap peut être déclaré dans Google Search Console. Un domaine
  personnel lèverait la limite.
- En-têtes HTTP non configurables (voir `SECURITY.md`).
