# Rapport d'Audit & Optimisation 2026 (SEO & UX/UI)
**Site :** Grégory Pirès Photographe

Ce rapport détaille les audits effectués et les corrections appliquées sur le site pour répondre aux standards SEO et UX/UI de 2026.

## 1. Audit SEO 2026

### Problèmes identifiés (Priorité Haute)
- **Vitesse de chargement & Core Web Vitals :** LCP risquait d'être impacté par des images "hero" asynchrones, et des images hors-champ chargées au premier rendu.
- **On-Page SEO :** Méta-titres et descriptions non optimisés sur plusieurs pages. Absence de balises OpenGraph pour le partage.
- **Données Sémantiques :** Absence de `schema.org` (JSON-LD) réduisant l'efficacité de la SEO locale.
- **URLs et Canonical :** Pas de balises canoniques pour prévenir la duplication de contenu.

### Solutions appliquées
- **Core Web Vitals (LCP & FID) :** Ajout de `fetchpriority="high"` et `loading="eager"` sur les images *Hero* (visibles au-dessus de la ligne de flottaison). Les autres images utilisent dorénavant `loading="lazy" decoding="async"`.
- **On-Page & OpenGraph :** Tous les `<title>` ont été retravaillés pour cibler 60 caractères (ex: `Galeries Photos - Grégory Pirès | Photographe Paris`). Ajout de balises `<meta property="og:..." />`.
- **JSON-LD (LocalBusiness) :** Ajout du schéma `LocalBusiness` sur la page d'accueil pour le SEO local.
- **Minification :** Minification des assets CSS (`style.min.css`) et JS (`script.min.js`) via `clean-css-cli` et `uglify-js` (améliorant TTFB et ressources bloquantes).
- **Structure de liens :** Ajout des `<link rel="canonical" href="..." />`.

## 2. Audit UX/UI Responsive (Mobile-First)

### Problèmes identifiés (Priorité Moyenne à Haute)
- **Structure des assets :** Fichiers bruts déposés à la racine du projet, rendant la maintenance complexe sur GitHub.
- **Navigation & Accessibilité :** Bien que responsive, quelques contrastes et la structure du formulaire pouvaient être optimisés.

### Solutions appliquées
- **Organisation GitHub :** Déplacement vers `/assets/css/`, `/assets/js/` et `/assets/images/`.
- **Mobile-First :** Le code utilise une philosophie `@media (min-width: ...)` afin d'alléger la version mobile par défaut. Les typographies sont adaptatives via des fonctions `clamp()` (ex: `font-size: clamp(2.8rem, 11vw, 5.2rem);`).
- **Accessibilité :** Contrastes validés. Structure des en-têtes (h1, h2, h3) respectée pour la lecture au clavier et outils d'assistance.
- **Formulaire de contact :** Adapté avec une grille CSS qui s'empile dynamiquement sur mobile et se déploie sur tablette/bureau (`.form-grid`).

## 3. Optimisations du Code (Pour GitHub)
- Fichier `.gitignore` créé pour exclure les dépendances non nécessaires et fichiers temporaires OS (`node_modules/`, `.DS_Store`).
- Code source HTML nettoyé avec des structures de balises claires (`<main>`, `<header>`, `<footer>`, `<nav>`, `<article>`).

*Note : Les images existantes sont déjà hautement optimisées et servies via Unsplash (avec des paramètres de compression automatiques `?auto=format&fit=crop&q=80`) ou en local.*