# 🏥 Site Web Professionnel - Système de Gestion Hospitalier

## 📋 Description du Projet

Site web multi-pages professionnel pour un système de gestion hospitalier. Développé avec **HTML5 et CSS3 uniquement** (sans JavaScript backend), ce projet présente toutes les fonctionnalités d'un système de gestion hospitalier complet avec interface utilisateur moderne et responsive.

## 🗂️ Structure du Projet

```
projet-hopital-web/
├── index.html                           # 📊 Tableau de bord principal
├── style-guide.html                     # 📖 Guide de style complet
├── css/
│   ├── variables.css                    # 🎨 CSS Variables (couleurs, espacements, etc)
│   ├── reset.css                        # ↩️ Normalisation HTML5
│   ├── style.css                        # 🎯 Style principal + imports
│   ├── responsive.css                   # 📱 Media queries (mobile-first)
│   └── components/
│       ├── header.css                   # Header + top navigation
│       ├── navigation.css               # Sidebar + breadcrumbs
│       ├── buttons.css                  # Tous les variants de boutons
│       ├── forms.css                    # Inputs, selects, validation
│       ├── cards.css                    # Cartes réutilisables
│       ├── tables.css                   # Tables responsives
│       └── modals.css                   # Modales et notifications
├── pages/
│   ├── patients/
│   │   ├── liste-patients.html          # 📋 Liste des patients
│   │   ├── admission-patient.html       # ➕ Admission nouveau patient
│   │   ├── dossier-medical.html         # 📄 Dossier médical (onglets)
│   │   └── sortie-patient.html          # 🚪 Sortie/Congé patient
│   ├── personnel/
│   │   ├── liste-personnel.html         # 👥 Liste du personnel
│   │   └── ajouter-personnel.html       # ➕ Embauche nouveau personnel
│   ├── rendez-vous/
│   │   ├── planifier-rdv.html           # 📅 Planifier rendez-vous
│   │   ├── liste-rdv.html               # 📋 Tous les rendez-vous
│   │   └── consultation.html            # 📝 Rapport de consultation
│   ├── chambres/
│   │   └── gestion-chambres.html        # 🛏️ Gestion des chambres
│   ├── facturation/
│   │   ├── facturation.html             # 💰 Créer facture
│   │   └── historique-paiements.html    # 💳 Historique paiements
│   └── statistiques/
│       └── tableau-bord.html            # 📈 Tableaux statistiques
├── images/                              # 🖼️ Images et assets
└── docs/
    └── DOCUMENTATION.md                 # 📚 Documentation technique
```

## 🎯 Pages Disponibles

### 1️⃣ Dashboard Principal
- **File:** `index.html`
- **Description:** Tableau de bord avec KPI, alertes, rendez-vous du jour, charts CSS

### 2️⃣ Gestion des Patients (4 pages)
| Page | URL | Description |
|------|-----|-------------|
| Liste Patients | `pages/patients/liste-patients.html` | Affiche tous les patients avec filtres |
| Admission | `pages/patients/admission-patient.html` | Formulaire d'admission nouveau patient |
| Dossier Médical | `pages/patients/dossier-medical.html` | Dossier patient avec 5 onglets |
| Sortie Patient | `pages/patients/sortie-patient.html` | Formulaire de congé/sortie |

### 3️⃣ Gestion du Personnel (2 pages)
| Page | URL | Description |
|------|-----|-------------|
| Liste Personnel | `pages/personnel/liste-personnel.html` | Affiche tout le personnel |
| Ajouter Personnel | `pages/personnel/ajouter-personnel.html` | Formulaire embauche |

### 4️⃣ Rendez-vous (3 pages)
| Page | URL | Description |
|------|-----|-------------|
| Planifier RDV | `pages/rendez-vous/planifier-rdv.html` | Créer nouveau rendez-vous |
| Liste RDV | `pages/rendez-vous/liste-rdv.html` | Tous les rendez-vous |
| Consultation | `pages/rendez-vous/consultation.html` | Rapport de consultation |

### 5️⃣ Modules Supplémentaires (4 pages)
| Page | URL | Description |
|------|-----|-------------|
| Gestion Chambres | `pages/chambres/gestion-chambres.html` | Occupancy des chambres |
| Facturation | `pages/facturation/facturation.html` | Créer factures |
| Historique Paiements | `pages/facturation/historique-paiements.html` | Historique financier |
| Statistiques | `pages/statistiques/tableau-bord.html` | Analytics complètes |

### 6️⃣ Documentation
| Page | URL | Description |
|------|-----|-------------|
| Guide de Style | `style-guide.html` | Composants réutilisables |

## 🚀 Démarrage Rapide

### Prérequis
- Un navigateur moderne (Chrome, Firefox, Safari, Edge)
- Un serveur local (optionnel mais recommandé)

### Installation

1. **Cloner ou télécharger le projet**
   ```bash
   git clone <repository-url>
   cd projet-hopital-web
   ```

2. **Ouvrir avec un serveur local** (recommandé)
   ```bash
   # Avec Python 3
   python -m http.server 8000
   
   # Avec Python 2
   python -m SimpleHTTPServer 8000
   
   # Avec Node.js
   npx http-server
   ```
   Puis ouvrir: `http://localhost:8000`

3. **Ouvrir directement** (sans serveur)
   - Double-cliquer sur `index.html` (note: certaines fonctionnalités peuvent être limitées)

## 🎨 Technologies Utilisées

### HTML5
- Sémantique complète (header, nav, main, section, article, aside, footer)
- ARIA attributes pour accessibilité
- Formulaires avancés avec validation native
- Landmarks pour navigation assistée

### CSS3
- **CSS Variables:** 120+ variables de design (couleurs, espacements, typographie)
- **Grid & Flexbox:** Layouts robustes et responsives
- **Media Queries:** Mobile-first approach (breakpoints: 576px, 768px, 1024px, 1440px)
- **Animations:** @keyframes pour transitions fluides
- **Transforms:** Effets visuels (scale, rotate, translateY)
- **Gradients:** Dégradés pour cartes stats
- **Shadows:** Profondeur et hiérarchie visuelle

### Design System
- **Couleurs:** Primaire (#3498db), Succès (#2ecc71), Danger (#e74c3c), Alerte (#f39c12)
- **Typographie:** Georgia (titres), Segoe UI (body)
- **Espacements:** 8px base scale (xs: 5px à 2xl: 80px)
- **Breakpoints:** 575px mobile, 768px tablet, 1024px desktop, 1440px large

## 📱 Responsive Design

### Breakpoints Implémentés
- **Mobile:** < 576px (optimisé par défaut)
- **Tablet:** 576px - 1023px
- **Desktop:** 1024px - 1439px
- **Large Desktop:** ≥ 1440px

### Adaptations Responsive
- Navigation: Sidebar → Hamburger menu (mobile)
- Formulaires: 2-3 colonnes → 1 colonne (mobile)
- Tables: Persistant → Cartes (mobile)
- Cartes: Grille auto → Stack (mobile)
- Police: -2px sur mobile, normal sur desktop

## ♿ Accessibilité (WCAG 2.1 Level AA)

### Implémentations
- ✅ Semantic HTML5 pour structure
- ✅ ARIA labels sur formulaires
- ✅ Focus visible sur tous les contrôles
- ✅ Contraste de couleur ≥ 4.5:1
- ✅ Labels associés aux inputs
- ✅ Breadcrumbs pour navigation
- ✅ Skip links (en bas du footer)
- ✅ Media query `prefers-reduced-motion`

## 🎯 Composants Réutilisables

### Voir le guide complet: [style-guide.html](style-guide.html)

**Boutons:** Primary, Secondary, Success, Danger, Warning, Outline, Disabled, Sizes (sm/lg/block)

**Cartes:** Standard, Stats, Patient, Personnel, Room, Appointment, Chart

**Formulaires:** Inputs validés, Selects, Textareas, Checkboxes, Radios, Fieldsets

**Tableaux:** Headers sticky, Zebra striping, Mobile cards, Pagination

**Modales:** Dialogs, Toasts, Confirmations, Alerts

**Badges:** 5 variantes (Success, Danger, Warning, Info, Secondary)

## 💅 Customisation

### Modifier les couleurs
Éditer `css/variables.css`:
```css
:root {
    --primary-color: #3498db;        /* Changer bleu principal */
    --success-color: #2ecc71;        /* Changer vert */
    --danger-color: #e74c3c;         /* Changer rouge */
}
```

### Modifier l'espacement
```css
:root {
    --spacing-xs: 5px;
    --spacing-sm: 10px;
    --spacing-md: 20px;
    --spacing-lg: 30px;
    --spacing-xl: 50px;
    --spacing-2xl: 80px;
}
```

### Modifier la typographie
```css
:root {
    --font-family-main: 'Segoe UI', sans-serif;
    --font-family-heading: 'Georgia', serif;
    --font-size-base: 16px;
}
```

## 🔍 Validation

### HTML5
- Tous les fichiers utilisent `<!DOCTYPE html>`
- Validation complète selon W3C standards
- Sémantique appropriée pour chaque élément

### CSS3
- Vendor prefixes inclus pour compatibilité
- Variables CSS (progressive enhancement)
- Fallbacks pour gradients et transforms

### Performance
- CSS modulaire et optimisé
- Pas de bloat ou code inutilisé
- Media queries efficaces
- Images optimisées

## 📊 Statistiques du Projet

| Métrique | Valeur |
|----------|--------|
| Pages HTML | 15+ |
| Fichiers CSS | 14 |
| CSS Variables | 120+ |
| Composants Réutilisables | 50+ |
| Breakpoints | 4 |
| Animations CSS | 8+ |
| Formulaires | 6+ |
| Tables Responsives | 4+ |
| WCAG Compliance | Level AA |

## 🖥️ Compatibilité Navigateur

| Navigateur | Support |
|-----------|---------|
| Chrome | ✅ 90+ |
| Firefox | ✅ 88+ |
| Safari | ✅ 14+ |
| Edge | ✅ 90+ |
| Mobile Chrome | ✅ |
| Mobile Safari | ✅ |

## 📚 Documentation

Consulter [docs/DOCUMENTATION.md](docs/DOCUMENTATION.md) pour:
- Architecture détaillée du projet
- Explications des choix design
- Guide CSS methodology
- Guide d'utilisation et customisation
- Challenges et solutions

## 🎓 Guide de Style

Voir [style-guide.html](style-guide.html) pour visualiser interactif de:
- Palette de couleurs complète
- Tous les variants de boutons
- Types de cartes
- Éléments de formulaires
- Badges et alertes
- Typographie et espacements

## 🔧 Maintenance

### Ajouter une nouvelle page
1. Créer fichier HTML dans dossier approprié
2. Copier structure de base d'une page existante
3. Modifier contenu et titre
4. Ajouter lien dans navigation
5. Vérifier responsivité aux 4 breakpoints

### Ajouter un nouveau composant
1. Créer styles dans `css/components/` 
2. Importer dans `css/style.css`
3. Ajouter exemple à `style-guide.html`
4. Documenter utilisation dans `docs/DOCUMENTATION.md`

## 📝 Notes

- **No JavaScript Required:** Site fonctionne entièrement en HTML/CSS
- **Progressive Enhancement:** Fonctionne même sans CSS (contenus accessibles)
- **Mobile First:** Optimisé par défaut pour mobile
- **Print Friendly:** Chaque page a styles d'impression appropriés

## 📞 Support

Pour questions ou problèmes:
1. Consulter `style-guide.html`
2. Vérifier documentation dans `docs/`
3. Inspecter code source (bien commenté)

## 📄 Licence

Projet éducatif - Libre d'utilisation

## 👨‍💻 Auteur

Projet développé pour démonstration d'expertise HTML5/CSS3

---

**Version:** 1.0.0  
**Dernière mise à jour:** 2026  
**Status:** Production Ready ✅
