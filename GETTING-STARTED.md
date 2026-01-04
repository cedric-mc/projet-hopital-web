# 🚀 Guide de Démarrage Rapide

## 📥 Installation

Aucune installation requise ! Le projet fonctionne en HTML/CSS pur.

### Prérequis
- Un navigateur moderne (Chrome, Firefox, Safari, Edge)
- Un éditeur de texte (VS Code, Sublime, etc.)

### Téléchargement
```bash
# Cloner ou télécharger le projet
git clone <repo-url>
cd projet-hopital-web
```

---

## 🎬 Démarrage

### Méthode 1 : Double-clic
1. Ouvrez le dossier `projet-hopital-web`
2. Double-cliquez sur `index.html`

### Méthode 2 : Navigateur
```
Fichier → Ouvrir → Sélectionnez index.html
```

### Méthode 3 : Terminal (macOS/Linux)
```bash
open index.html
# ou
xdg-open index.html
```

### Méthode 4 : Serveur Local (recommandé)
```bash
# Avec Python 3
python -m http.server 8000

# Avec Node.js (http-server)
npx http-server

# Avec PHP
php -S localhost:8000
```

Puis visitez `http://localhost:8000` dans votre navigateur.

---

## 🗺️ Navigation du Site

### Pages Principales
```
🏠 Accueil
├── 📊 Dashboard (index.html)
├── 👥 Patients
│   ├── 📋 Liste des patients
│   ├── ➕ Admission patient
│   ├── 📄 Dossier médical
│   └── 🚪 Sortie patient
├── 👨‍⚕️ Personnel
│   ├── 👥 Liste personnel
│   └── ➕ Ajouter personnel
├── 📅 Rendez-vous
│   ├── 📅 Planifier RDV
│   ├── 📋 Liste RDV
│   └── 📝 Consultation
├── 🛏️ Chambres
│   └── 🛏️ Gestion chambres
├── 💰 Facturation
│   ├── 🧾 Facturation
│   └── 💳 Historique paiements
└── 📈 Statistiques
    └── 📊 Tableau de bord
```

---

## 🎨 Fonctionnalités à Découvrir

### 1. Responsive Design
- Redimensionnez la fenêtre du navigateur
- Testez sur mobile (F12 → Device mode)
- Breakpoints: 768px, 1024px

### 2. Dark Mode
- Cliquez le bouton 🌙 en bas à droite
- Persiste en rechargeant
- Utilisez `data-theme="dark"` sur `<html>`

### 3. Navigation Mobile
- Cliquez le menu ☰ sur mobile
- Menu burger en CSS pur
- Navigation fluide

### 4. Guide de Style
```
Visitez → style-guide.html
```
- Tous les composants
- Palette de couleurs
- Typographie
- Formulaires

### 5. Validation
```
Visitez → validation.html
```
- Checklist du projet
- Vérification des critères
- Résumé complet

### 6. Page 404
```
Visitez → 404.html
```
- Design créatif
- Animations
- Navigation vers accueil

### 7. Impression
```
Appuyez → Ctrl+P (ou Cmd+P)
```
- Optimisée pour papier
- Couleurs préservées
- Layout adapté

---

## 📁 Structure du Projet

```
projet-hopital-web/
│
├── 📄 Fichiers Principaux
│   ├── index.html              ← Accueil/Dashboard
│   ├── style-guide.html        ← Composants
│   ├── validation.html         ← Vérification
│   ├── 404.html               ← Page erreur
│   └── README.md              ← Documentation
│
├── 📂 css/
│   ├── variables.css          ← Design tokens (IMPORTANT)
│   ├── reset.css              ← Normalisation
│   ├── style.css              ← Import principal
│   ├── responsive.css         ← Media queries
│   ├── dark-mode.css          ← Thème sombre
│   ├── print.css              ← Impression
│   └── components/            ← Composants modulaires
│       ├── header.css
│       ├── navigation.css
│       ├── buttons.css
│       ├── forms.css
│       ├── cards.css
│       ├── tables.css
│       └── modals.css
│
├── 📂 pages/
│   ├── patients/              ← 4 pages
│   ├── personnel/             ← 2 pages
│   ├── rendez-vous/          ← 3 pages
│   ├── chambres/             ← 1 page
│   ├── facturation/          ← 2 pages
│   └── statistiques/         ← 1 page
│
├── 📂 images/
│   ├── logo.png
│   └── icons/
│
├── 📂 docs/
│   ├── DOCUMENTATION.md       ← Guide technique
│   └── screenshots/           ← Captures d'écran
│
└── 📂 Configuration
    ├── README.md              ← Guide projet
    ├── PROJECT_SUMMARY.md     ← Résumé
    ├── FEATURES.md            ← Fonctionnalités
    ├── CHECKLIST_EVALUATION.md ← Évaluation
    └── GETTING-STARTED.md     ← Ce fichier
```

---

## 🛠️ Personnalisation

### Modifier les Couleurs
Éditez `css/variables.css` :

```css
:root {
    --primary-color: #3498db;      /* Changez cette valeur */
    --secondary-color: #2ecc71;    /* Changez cette valeur */
    /* ... */
}
```

### Modifier les Espacements
Éditez dans `variables.css` :

```css
--spacing-md: 15px;     /* Changez la valeur */
--spacing-lg: 20px;     /* Changez la valeur */
```

### Modifier la Typographie
Éditez dans `reset.css` ou `variables.css` :

```css
--font-main: 'Arial', sans-serif;    /* Changez la police */
--font-size-md: 16px;                /* Changez la taille */
```

### Ajouter des Pages
1. Créez `pages/nouvellepage/page.html`
2. Copiez la structure d'une page existante
3. Mettez à jour les imports CSS
4. Ajoutez le lien dans la navigation

---

## 🔍 Inspections et Tests

### Tester la Responsivité
```
1. Appuyez F12 (DevTools)
2. Cliquez l'icône mobile
3. Testez sur 375px, 768px, 1024px
```

### Vérifier l'Accessibilité
```
1. Installez WAVE Extension
2. Testez chaque page
3. Vérifiez le contraste avec WebAIM
```

### Valider le HTML
```
1. Visitez validator.w3.org
2. Collez l'URL ou le code
3. Vérifiez les erreurs
```

### Valider le CSS
```
1. Visitez jigsaw.w3.org/css-validator
2. Collez l'URL ou le code
3. Vérifiez les avertissements
```

---

## 🎯 Cas d'Utilisation

### Cas 1 : Parcourir le Dashboard
```
1. Ouvrez index.html
2. Consultez les statistiques
3. Naviguez dans les sections
4. Testez le responsive (F12)
```

### Cas 2 : Créer un Nouveau Patient
```
1. Allez à "Admission Patient"
2. Remplissez le formulaire
3. Observez la validation HTML5
4. Cliquez "Admettre Patient"
```

### Cas 3 : Consulter les Statistiques
```
1. Allez à "Statistiques"
2. Consultez les graphiques CSS
3. Observez les cartes KPI
4. Testez les animations
```

### Cas 4 : Imprimer une Facture
```
1. Allez à "Facturation"
2. Appuyez Ctrl+P
3. Consultez l'aperçu
4. Téléchargez en PDF
```

---

## 🐛 Dépannage

### Le site ne s'ouvre pas
- ✅ Vérifiez le chemin du fichier
- ✅ Utilisez un serveur local (recommandé)
- ✅ Vérifiez les permissions des fichiers

### Les styles ne s'appliquent pas
- ✅ Videz le cache du navigateur (Ctrl+Shift+Delete)
- ✅ Vérifiez les chemins des imports CSS
- ✅ Ouvrez la console (F12) pour les erreurs

### Les formulaires ne valident pas
- ✅ C'est normal ! C'est une validation HTML5 côté client
- ✅ Les données ne sont pas envoyées (pas de backend)
- ✅ Utilisez les validations pour le feedback utilisateur

### Pas de dark mode
- ✅ Vérifiez que `dark-mode.css` est importé
- ✅ Assurez-vous que le bouton est visible (F12)
- ✅ Vérifiez localStorage (F12 → Application)

---

## 📚 Ressources Utiles

### Documentation Officielle
- [MDN Web Docs](https://developer.mozilla.org/)
- [W3C HTML](https://html.spec.whatwg.org/)
- [W3C CSS](https://www.w3.org/Style/CSS/)

### Outils de Test
- [W3C HTML Validator](https://validator.w3.org/)
- [W3C CSS Validator](https://jigsaw.w3.org/css-validator/)
- [WebAIM Contrast Checker](https://webaim.org/resources/contrastchecker/)
- [WAVE Accessibility](https://wave.webaim.org/)

### DevTools
- Chrome DevTools (F12)
- Firefox Inspector (F12)
- Safari Inspector (Cmd+Option+I)
- Edge DevTools (F12)

---

## 💬 Support

Pour toute question ou problème :

1. **Consultez la documentation** : `docs/DOCUMENTATION.md`
2. **Vérifiez le checklist** : `CHECKLIST_EVALUATION.md`
3. **Explorez les exemples** : `style-guide.html`
4. **Lire le code** : Les commentaires CSS sont explicites

---

## 🎓 Points d'Apprentissage

Ce projet vous enseigne :

- ✅ HTML5 sémantique et accessible
- ✅ CSS3 avancé (Grid, Flexbox, Animations)
- ✅ Responsive design mobile-first
- ✅ Système de design avec variables CSS
- ✅ Méthodologie CSS (BEM)
- ✅ Accessibilité web (WCAG)
- ✅ Performance et optimisation
- ✅ Organisation et documentation

---

## 🚀 Prochaines Étapes

### Pour Améliorer le Projet
1. Ajouter JavaScript pour interactivité
2. Créer un backend avec API
3. Ajouter une base de données
4. Déployer en ligne
5. Ajouter l'authentification

### Pour Apprendre
1. Lire toute la documentation
2. Modifier les variables CSS
3. Créer de nouvelles pages
4. Ajouter des animations
5. Implémenter une API

---

**Bon début ! Le projet est prêt à être utilisé et exploré. 🎉**
