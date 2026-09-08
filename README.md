# Mobile Body Smart Repair — site vitrine

Site vitrine one-page pour **Mobile Body Smart Repair** (MBSR) — Smart Repair &
carrosserie mobile en Loir-et-Cher (41) et Indre-et-Loire (37).

Même base technique que le site Éclat Auto Centre : HTML / CSS / JS statiques,
aucune étape de build, servi tel quel par Vercel.

## Stack

- `index.html` — page unique, sections Prestations / Méthode / Réalisations / Déroulé / Contact
- `assets/styles.css` — thème sombre, tokens couleur, responsive, carrousel swipe mobile
- `assets/main.js` — reveals progressifs (dégradables), nav mobile, parallax GSAP du visuel hero, formulaire de contact (mailto)
- `assets/favicon.svg` — favicon
- GSAP + ScrollTrigger via CDN (cdnjs), optionnels : le site fonctionne sans

## À personnaliser (contenu manquant dans le profil Instagram)

Le profil `@mbsr_auto` ne fournissait ni logo, ni photos exploitables, ni coordonnées.
Les éléments suivants sont donc des **placeholders** à remplacer :

| Élément | État actuel | À faire |
|---|---|---|
| Logo | Wordmark typographique « MBSR » | Fournir un vrai logo (SVG de préférence) → remplacer `.wm` dans `index.html` par `<img>` |
| Photos réalisations | 6 tuiles dégradées « photo à venir » | Déposer les photos dans `assets/img/` et remplacer les `<li class="gitem ph">` par des `<li class="gitem"><img …></li>` |
| Visuel hero | Panneau peint animé en CSS | Peut être remplacé par une vraie photo pleine largeur |
| E-mail | `contact@mbsr-auto.fr` (fictif) dans `main.js` + JSON-LD | Mettre la vraie adresse |
| Téléphone | absent | Ajouter dans la colonne `.cinfo` + `tel:` si souhaité |
| Couleur d’accent | Bleu `#2f7bf6` (choisi pour « Smart ») | Ajuster `--accent` / `--accent-2` dans `styles.css` si une couleur de marque existe |
| Zone (carte) | Emprise 41 + 37 approximative (OpenStreetMap) | Affiner le `bbox` / `marker` de l’iframe |
| Textes prestations | Rédigés à partir de la bio (« Rayures / Jantes / Retouches peinture ») | Relire / corriger avec le client |

## Formulaire

Pas de backend : le formulaire ouvre le client mail avec la demande pré-remplie.
CTA secondaire = DM Instagram `@mbsr_auto`. Pour un vrai envoi, brancher Formspree /
Web3Forms ou une fonction serverless.
