# 📚 Documentation Technique - Système de Gestion Hospitalier

## Table des Matières
1. [Architecture du Projet](#architecture)
2. [Système de Design](#design-system)
3. [Méthodologie CSS](#css-methodology)
4. [Guide d'Utilisation](#usage-guide)
5. [Patterns et Bonnes Pratiques](#patterns)
6. [Défis et Solutions](#challenges)
7. [Évolutions Futures](#future)

---

## Architecture du Projet {#architecture}

### Structure Générale

```
projet-hopital-web/
├── index.html                       # Point d'entrée principal (dashboard)
├── style-guide.html                 # Guide de composants
├── css/
│   ├── variables.css                # Design tokens (SINGLE SOURCE OF TRUTH)
│   ├── reset.css                    # Normalisation HTML5
│   ├── style.css                    # Imports + styles globaux
│   ├── responsive.css               # Media queries centralisées
│   └── components/                  # Styles modulaires
│       ├── header.css
│       ├── navigation.css
│       ├── buttons.css
│       ├── forms.css
│       ├── cards.css
│       ├── tables.css
│       └── modals.css
└── pages/                           # Pages par domaine fonctionnel
    ├── patients/                    # 4 pages gestion patients
    ├── personnel/                   # 2 pages gestion personnel
    ├── rendez-vous/                 # 3 pages gestion RDV
    ├── chambres/                    # 1 page gestion chambres
    ├── facturation/                 # 2 pages facturation
    └── statistiques/                # 1 page statistiques
```

### Hiérarchie des Imports CSS

```
style.css (main)
├── variables.css        ← Design tokens
├── reset.css            ← Normalization
├── components/
│   ├── header.css
│   ├── navigation.css
│   ├── buttons.css
│   ├── forms.css
│   ├── cards.css
│   ├── tables.css
│   └── modals.css
└── responsive.css       ← Media queries
```

**Principe:** Chaque fichier CSS a une responsabilité unique. Variables au top, responsive en bas.

---

## Système de Design {#design-system}

### 1. Palette de Couleurs

**Couleurs Sémantiques:**
```css
--primary-color: #3498db          /* Bleu - Actions principales */
--secondary-color: #2c3e50        /* Gris foncé - Contexte */
--success-color: #2ecc71          /* Vert - Validations */
--danger-color: #e74c3c           /* Rouge - Erreurs/Alertes */
--warning-color: #f39c12          /* Orange - Avertissements */
--info-color: #3498db             /* Bleu - Informations */
```

**Couleurs Neutres:**
```css
--dark-color: #2c3e50             /* Fond foncé */
--light-color: #ecf0f1            /* Fond clair */
--gray-500: #95a5a6              /* Texte secondaire */
--white: #ffffff                  /* Blanc pur */
```

**Utilisation:**
- Primaire: Boutons actions, headers, focus states
- Succès: Badges validées, alerts positives, checkmarks
- Danger: Erreurs, suppression, états critiques
- Alerte: Avertissements, actions à risque

### 2. Système d'Espacement (8px Base)

```css
--spacing-xs: 5px      /* Minimal, spacing intra-composants */
--spacing-sm: 10px     /* Petit, entre éléments proches */
--spacing-md: 20px     /* Normal, entre sections */
--spacing-lg: 30px     /* Grand, entre blocs majeurs */
--spacing-xl: 50px     /* Extra large */
--spacing-2xl: 80px    /* Double grande page */
```

**Usage Pattern:**
- Padding card: `var(--spacing-lg)` (30px)
- Margin between sections: `var(--spacing-xl)` (50px)
- Gap in grid: `var(--spacing-md)` (20px)

### 3. Typographie

**Families:**
```css
--font-family-main: 'Segoe UI', Tahoma, sans-serif        /* Body */
--font-family-heading: 'Georgia', serif                    /* Titles */
```

**Sizes (Scale basé sur 16px base):**
```css
--font-size-xs: 12px
--font-size-sm: 14px
--font-size-base: 16px
--font-size-lg: 18px
--font-size-xl: 20px
--font-size-2xl: 24px
--font-size-3xl: 28px
--font-size-4xl: 32px
```

**Line Heights:**
```css
--line-height-tight: 1.2       /* Titles */
--line-height-normal: 1.5      /* Body */
--line-height-relaxed: 1.75    /* Lists */
```

### 4. Shadows (Depth System)

```css
--shadow-sm: 0 1px 2px rgba(0, 0, 0, 0.05)
--shadow-md: 0 4px 8px rgba(0, 0, 0, 0.1)
--shadow-lg: 0 8px 16px rgba(0, 0, 0, 0.15)
--shadow-xl: 0 12px 24px rgba(0, 0, 0, 0.2)
```

**Utilisation:**
- Cards au repos: `--shadow-md`
- Cards au hover: `--shadow-lg` ou `--shadow-xl`
- Modales: `--shadow-xl`

### 5. Border Radius

```css
--border-radius: 8px              /* Standard components */
--border-radius-lg: 12px          /* Large components */
--border-radius-sm: 4px           /* Small components */
--border-radius-pill: 9999px      /* Fully rounded */
```

### 6. Z-Index Scale

```css
--z-index-dropdown: 1000
--z-index-sticky: 1020
--z-index-fixed: 1030
--z-index-modal-backdrop: 1040
--z-index-modal: 1050
--z-index-popover: 1060
--z-index-tooltip: 1070
```

### 7. Breakpoints

```css
--breakpoint-mobile: 576px         /* Minimum tablette */
--breakpoint-tablet: 768px         /* Minimum desktop */
--breakpoint-desktop: 1024px       /* Minimum large */
--breakpoint-large: 1440px         /* Minimum extra-large */
```

---

## Méthodologie CSS {#css-methodology}

### Approche Mobile-First

**Principe:** Styles simples et mobiles d'abord, augmentez complexité pour desktop.

```css
/* DEFAULT: Mobile styles */
.grid {
    display: grid;
    grid-template-columns: 1fr;      /* Une colonne */
    gap: var(--spacing-md);
}

/* TABLET: +576px */
@media (min-width: 768px) {
    .grid {
        grid-template-columns: repeat(2, 1fr);  /* Deux colonnes */
    }
}

/* DESKTOP: +1024px */
@media (min-width: 1024px) {
    .grid {
        grid-template-columns: repeat(3, 1fr);  /* Trois colonnes */
    }
}
```

**Avantages:**
- Fichier CSS plus petit (pas de débordements)
- Performance mobile améliorée
- Progressive enhancement naturel

### Nommage: BEM Léger

**Syntaxe:** `block__element--modifier`

```css
/* Block */
.card { }

/* Element */
.card__header { }
.card__body { }
.card__footer { }

/* Modifier */
.card--primary { }
.card--secondary { }
.card--small { }
```

**Exemple dans HTML:**
```html
<div class="card card--primary">
    <div class="card__header">
        <h3 class="card__title">Title</h3>
    </div>
    <div class="card__body">
        Content
    </div>
</div>
```

### Utility-First Classes

Utilisation limitée de utility classes pour spacing et display:

```css
.mb-lg { margin-bottom: var(--spacing-lg); }
.mt-md { margin-top: var(--spacing-md); }
.p-xl { padding: var(--spacing-xl); }
.gap-md { gap: var(--spacing-md); }
.text-center { text-align: center; }
.text-muted { color: var(--gray-500); }
.sr-only { /* Screen reader only */ }
```

### CSS Grid Architecture

**Main Layout (Toutes les pages):**
```css
.main-layout {
    display: grid;
    grid-template-areas:
        "header header header"
        "sidebar main main"
        "footer footer footer";
    
    grid-template-columns: 250px 1fr;
    grid-template-rows: auto 1fr auto;
    min-height: 100vh;
}
```

**Responsive Adaptation:**
```css
@media (max-width: 1023px) {
    .main-layout {
        grid-template-columns: 1fr;
        grid-template-areas:
            "header"
            "main"
            "footer";
    }
    .sidebar {
        position: fixed;
        left: -100%;
        top: 80px;
        transition: left 0.3s ease;
    }
    .sidebar.active {
        left: 0;
    }
}
```

---

## Guide d'Utilisation {#usage-guide}

### Ajouter une Nouvelle Page

**Étape 1: Créer HTML**
```html
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Page Title - Hopital Central</title>
    <link rel="stylesheet" href="../../css/style.css">
</head>
<body>
    <div class="main-layout">
        <!-- Copier structure d'une autre page -->
        <header>...</header>
        <aside class="sidebar">...</aside>
        <main>
            <div class="page-content">
                <!-- Contenu ici -->
            </div>
        </main>
        <footer>...</footer>
    </div>
</body>
</html>
```

**Étape 2: Mettre à jour Navigation**
Ajouter lien dans sidebar de header.html/index.html:
```html
<a href="pages/nouvelle/page.html">📄 Nouvelle Page</a>
```

### Créer un Nouveau Composant

**Exemple: Nouvelle carte type**

**Étape 1: CSS (cards.css)**
```css
.card--custom {
    background-color: var(--light-color);
    border-left: 4px solid var(--primary-color);
    padding: var(--spacing-lg);
}

.card--custom:hover {
    box-shadow: var(--shadow-lg);
    transform: translateY(-2px);
}
```

**Étape 2: HTML (utilisation)**
```html
<div class="card card--custom">
    <h3>Custom Card Title</h3>
    <p>Card content here</p>
</div>
```

**Étape 3: Ajouter à style-guide.html**
```html
<div class="card card--custom">
    <h3>Custom Card Title</h3>
    <p>Card content example</p>
</div>
```

### Customiser les Couleurs Globales

**Avant (Défaut):**
```css
:root {
    --primary-color: #3498db;
}
```

**Après (Bleu foncé):**
```css
:root {
    --primary-color: #2c5aa0;
}
```

**Effet:** Tous les `.btn-primary`, `.card--primary`, `.card__header--primary` changent automatiquement.

### Ajouter un Breakpoint

**Éditer `responsive.css`:**
```css
/* Nouveau breakpoint XL */
@media (min-width: 1920px) {
    .container {
        max-width: 1400px;
    }
    
    .grid {
        grid-template-columns: repeat(4, 1fr);
    }
}
```

---

## Patterns et Bonnes Pratiques {#patterns}

### 1. Formulaires

**Pattern Standard:**
```html
<form class="form-grid-2">
    <fieldset>
        <legend>Personal Information</legend>
        
        <div class="form-group">
            <label for="nom" class="required">Nom</label>
            <input 
                type="text" 
                id="nom" 
                name="nom"
                placeholder="Entrer nom..."
                required
            >
        </div>

        <div class="form-group">
            <label for="email">Email</label>
            <input 
                type="email" 
                id="email" 
                name="email"
                placeholder="email@example.com"
            >
            <small class="help-text">Optionnel</small>
        </div>
    </fieldset>
    
    <div class="btn-group">
        <button type="submit" class="btn btn-primary">Soumettre</button>
        <button type="reset" class="btn btn-secondary">Réinitialiser</button>
    </div>
</form>
```

**Classes de Layout:**
- `.form-grid-2`: 2 colonnes
- `.form-grid-3`: 3 colonnes

### 2. Tables Responsives

**Pattern avec Data Labels:**
```html
<table>
    <thead>
        <tr>
            <th>Nom</th>
            <th>Email</th>
            <th>Status</th>
            <th>Actions</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td data-label="Nom">Jean Martin</td>
            <td data-label="Email">jean@example.com</td>
            <td data-label="Status">
                <span class="badge badge-success">Actif</span>
            </td>
            <td data-label="Actions">
                <a href="#" class="icon-btn">✎</a>
                <a href="#" class="icon-btn icon-btn--danger">✕</a>
            </td>
        </tr>
    </tbody>
</table>
```

**CSS Responsive Magic:**
```css
@media (max-width: 767px) {
    table {
        display: block;
        overflow-x: auto;
    }
    
    tbody tr {
        display: grid;
        gap: var(--spacing-sm);
        margin-bottom: var(--spacing-lg);
        border: 1px solid var(--border-color);
        padding: var(--spacing-md);
    }
    
    td:before {
        content: attr(data-label);
        font-weight: bold;
        display: block;
    }
}
```

### 3. Système d'Alertes

**Pattern:**
```html
<!-- Success -->
<div class="alert alert-success">
    ✓ Opération réussie
</div>

<!-- Danger -->
<div class="alert alert-danger">
    ✗ Une erreur est survenue
</div>

<!-- Warning -->
<div class="alert alert-warning">
    ⚠ Attention requise
</div>

<!-- Info -->
<div class="alert alert-info">
    ℹ Information importante
</div>
```

### 4. Validation de Formulaires

**HTML5 Native (Pas de JS):**
```html
<input 
    type="email" 
    required
    pattern="[a-z0-9._%+-]+@[a-z0-9.-]+\.[a-z]{2,}$"
>
```

**CSS Feedback:**
```css
input:valid {
    border-color: var(--success-color);
    box-shadow: inset 0 0 0 2px rgba(46, 204, 113, 0.1);
}

input:invalid {
    border-color: var(--danger-color);
    box-shadow: inset 0 0 0 2px rgba(231, 76, 60, 0.1);
}

input:invalid + .error-message {
    display: block;
    color: var(--danger-color);
}
```

---

## Défis et Solutions {#challenges}

### Défi 1: Responsive Table sans Framework

**Problème:** Tables pas responsives sur mobile par défaut.

**Solution:** Utiliser `data-label` attributes + CSS Grid
```css
@media (max-width: 767px) {
    tbody tr {
        display: grid;
        grid-template-columns: auto 1fr;
        column-gap: var(--spacing-md);
    }
    
    td::before {
        content: attr(data-label);
        font-weight: bold;
    }
}
```

### Défi 2: Sidebar Navigation Mobile

**Problème:** Sidebar prend trop d'espace sur mobile.

**Solution:** Fixed overlay + hamburger menu
```css
@media (max-width: 1023px) {
    .sidebar {
        position: fixed;
        left: -100%;
        top: 80px;
        width: 250px;
        height: calc(100vh - 80px);
        z-index: var(--z-index-fixed);
        transition: left 0.3s ease;
    }
    
    .sidebar.active {
        left: 0;
        box-shadow: var(--shadow-lg);
    }
}
```

### Défi 3: Charts CSS-Only

**Problème:** Afficher des graphiques sans JavaScript.

**Solution:** Utiliser `conic-gradient` et proportions

**Pie Chart:**
```html
<div style="
    width: 200px;
    height: 200px;
    border-radius: 50%;
    background: conic-gradient(
        #3498db 0deg 120deg,
        #2ecc71 120deg 240deg,
        #e74c3c 240deg
    );
"></div>
```

**Bar Chart:**
```html
<div style="display: flex; align-items: flex-end; gap: 10px;">
    <div style="width: 30px; height: 150px; background: #3498db;"></div>
    <div style="width: 30px; height: 200px; background: #2ecc71;"></div>
    <div style="width: 30px; height: 100px; background: #e74c3c;"></div>
</div>
```

### Défi 4: Formulaires Conditionnels

**Problème:** Afficher/masquer champs selon sélection (besoin JS minimal).

**Solution:** JavaScript simple
```javascript
document.getElementById('admission-type').addEventListener('change', (e) => {
    const hospitalSection = document.getElementById('hospitalization-section');
    hospitalSection.style.display = e.target.value === 'internal' ? 'block' : 'none';
});
```

---

## Évolutions Futures {#future}

### Court Terme
- [ ] Ajouter mode sombre (CSS variables dark theme)
- [ ] Animations micro-interactions
- [ ] Système de notification toast
- [ ] Pagination interactive
- [ ] Export PDF (CSS print optimization)

### Moyen Terme
- [ ] Multi-langage (i18n CSS + HTML)
- [ ] Support des plugins UI
- [ ] Système de thème personnalisable
- [ ] Dashboards customisables
- [ ] Offline support (Service Worker)

### Long Terme
- [ ] Backend API integration
- [ ] Database integration
- [ ] Authentication system
- [ ] Real-time notifications
- [ ] Analytics tracking
- [ ] Performance monitoring

---

## Checklist de Maintenance

- [ ] Vérifier toutes les pages sur mobile (575px)
- [ ] Vérifier toutes les pages sur tablet (768px)
- [ ] Vérifier toutes les pages sur desktop (1366px)
- [ ] Tester tous les formulaires
- [ ] Vérifier tous les liens de navigation
- [ ] Valider HTML avec W3C
- [ ] Valider CSS avec W3C
- [ ] Tester accessibility avec WAVE
- [ ] Vérifier contraste de couleurs (Contrast Checker)

---

## Ressources

- [MDN: CSS Variables](https://developer.mozilla.org/en-US/docs/Web/CSS/--*)
- [CSS-Tricks: Responsive Design](https://css-tricks.com/snippets/css/media-queries-for-standard-devices/)
- [A11y Project](https://www.a11yproject.com/)
- [Web.dev: CSS Performance](https://web.dev/css/)

---

**Version:** 1.0.0  
**Dernière mise à jour:** 2026  
**Maintenu par:** Équipe Développement
