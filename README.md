# MBSR Auto — site vitrine

Site vitrine one-page pour **MBSR Auto — Mobile Body Smart Repair** : Smart Repair &
carrosserie mobile en Loir-et-Cher (41) et Indre-et-Loire (37).

Même base technique que le site Éclat Auto Centre : HTML / CSS / JS statiques,
aucune étape de build, servi tel quel par Vercel.

## Stack

- `index.html` — page unique : Prestations / La méthode / Réalisations / Déroulé / Contact
- `assets/styles.css` — thème sombre « sport » (rouge `#e4002b` / noir), responsive, carrousel swipe mobile
- `assets/main.js` — reveals progressifs dégradables, nav mobile, parallax GSAP du hero, lightbox galerie, formulaire de contact (mailto + lien DM Instagram)
- `assets/logo-mbsr.svg` — logo MBSR (wordmark italique + slash rouge) en version blanche pour fond sombre, d’après le logo fourni
- `assets/favicon.svg` — favicon
- `assets/img/` — photos reprises du compte Instagram **@mbsr_auto** (chantiers réels) :
  `hero-spray.jpg` (hero) + `ig-01…ig-09.jpg` (galerie / section méthode)
- GSAP + ScrollTrigger via CDN (cdnjs), optionnels : le site fonctionne sans

## À personnaliser / compléter

| Élément | État actuel | À faire |
|---|---|---|
| Logo | Recréé en SVG d’après l’image fournie (type + slash rouge), version blanche | Remplacer par le fichier vectoriel officiel si disponible (même nom `logo-mbsr.svg`) |
| Photos | 9 clichés repris d’Instagram, ~480–640 px | Remplacer par des versions HD en gardant les mêmes noms de fichiers |
| E-mail | `contact@mbsr-auto.fr` (à confirmer) dans `main.js` + JSON-LD | Mettre la vraie adresse ; sinon le CTA Instagram reste le canal principal |
| Téléphone | non communiqué | Ajouter dans la colonne `.cinfo` (+ lien `tel:`) si souhaité |
| Zone (carte) | Emprise 41 + 37 approximative (OpenStreetMap) | Affiner le `bbox` / `marker` de l’iframe |
| Textes | Rédigés d’après la bio Instagram et les photos | Relire / corriger avec le client (tarifs, délais, communes couvertes) |
| Horaires | non affichés | Ajouter si le client veut communiquer des créneaux |

## Formulaire

Pas de backend : le formulaire ouvre le client mail avec la demande pré-remplie.
CTA secondaire = DM Instagram `@mbsr_auto`. Pour un vrai envoi, brancher Formspree /
Web3Forms ou une fonction serverless.

## Déploiement

Fichiers statiques → Vercel (projet `mbsr-auto`). `vercel.json` : `cleanUrls`,
HTML/CSS/JS en `must-revalidate`, images en cache court. Pour l’auto-déploiement sur
push, lier le dépôt GitHub au projet Vercel.
