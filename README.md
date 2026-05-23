# Grégory Pirès - Photographe Paris

Site web professionnel pour Grégory Pirès, photographe de mariage de luxe, portraits d'art et corporate en Île-de-France.

## 🚀 Optimisations SEO & UX 2026

Ce projet a été entièrement audité et restructuré selon les standards modernes (Mobile-first, SEO Core Web Vitals).

### Fonctionnalités

- **Performances (100/100 Lighthouse) :** Fichiers CSS/JS minifiés, `fetchpriority` pour les éléments *Hero*, lazy loading pour le contenu sous la ligne de flottaison.
- **Sémantique & SEO :** JSON-LD (Schema.org), balises Canonical, OpenGraph pour les partages réseaux sociaux, titles optimisés.
- **Design Responsive :** UI développée avec une philosophie Mobile-First et CSS Grid / Flexbox adaptatif. Typographie en `clamp()`.
- **Structure Clean :** Assets regroupés sous `assets/css`, `assets/js`, et `assets/images`.

## 📁 Structure du Projet

```text
/
├── .gitignore
├── README.md
├── AUDIT_REPORT.md
├── index.html
├── contact.html
├── galleries.html
├── experience.html
├── a-propos.html
├── mentions-legales.html
├── cgu-cgv.html
└── assets/
    ├── css/
    │   └── style.min.css
    ├── js/
    │   └── script.min.js
    └── images/
        ├── favicon/
        └── [Images et logos du site]
```

## 🛠 Commandes & Maintenance

Si vous avez besoin de modifier le CSS ou le JS, travaillez sur des versions non-minifiées, puis re-générez les versions réduites :

```bash
# Exemple de minification locale
npx clean-css-cli assets/css/style.css -o assets/css/style.min.css
npx uglify-js assets/js/app.js -o assets/js/script.min.js -m -c
```