# Sécurité

## Signaler une vulnérabilité

Écrire à yann.deboisvilliers@psl.eu, sans ouvrir de ticket public. Réponse
sous une semaine.

## État de sécurité (octobre 2026)

Le site est statique : pas de serveur applicatif, pas de base de données, pas
de formulaire, pas d'authentification, pas de cookie, pas de JavaScript. Les
risques OWASP liés aux entrées utilisateur (injection, CSRF, contrôle
d'accès) ne s'appliquent donc pas.

| Contrôle | Mise en œuvre | Vérifié |
|---|---|---|
| Transport | HTTPS et HSTS fournis par github.io | en-tête `strict-transport-security` constaté en production |
| Politique de contenu | `<meta>` CSP : `default-src 'self'`, `script-src 'none'`, `form-action 'none'`, `object-src 'none'`, `base-uri 'self'` | aucune erreur CSP dans la console sur les 9 pages (build local) |
| Fuite d'URL | `<meta name="referrer" content="strict-origin-when-cross-origin">` | dans le HTML généré |
| Tiers | aucune ressource externe : police auto-hébergée, pas d'analytics | aucune requête externe au chargement |
| Données personnelles | photo sans EXIF ni GPS ; PDF sans chemin local dans leurs métadonnées | vérifié le 09/10/2026 |
| Secrets | aucun secret nécessaire ; gitleaks en CI ; historique Git vérifié | aucun secret trouvé |
| Dépendances | gems épinglées par `Gemfile.lock` (version de GitHub Pages) ; build en CI | Dependabot à activer dans les réglages du dépôt |

## Risques résiduels

- **En-têtes HTTP non configurables sur GitHub Pages** : `frame-ancestors`
  et `X-Frame-Options` ne peuvent pas passer par `<meta>`, donc le site peut
  être affiché dans un cadre. L'impact est faible, puisqu'il n'y a aucune
  action à détourner. Un hébergeur avec en-têtes (Netlify, Cloudflare Pages)
  lèverait cette limite.
- **`X-Content-Type-Options` et `Permissions-Policy`** : même limite.
- **Adresse électronique en clair** : choix assumé (elle figure déjà sur le
  CV), au prix d'un peu de spam.
- **Pages de redirection** (`/resume/`) : générées par `jekyll-redirect-from`,
  elles contiennent un petit script de redirection, hors du gabarit et donc
  hors CSP. Elles ne contiennent aucune donnée.

## Si un secret était commité

Ce dépôt n'en utilise aucun. Si un jeton ou une clé y entrait par erreur :
le révoquer immédiatement, en créer un nouveau hors du dépôt, puis nettoyer
l'historique avec `git filter-repo` avant tout nouveau push.
