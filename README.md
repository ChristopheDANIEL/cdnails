# CD Nails - Site Web Prothésiste Ongulaire

Site web moderne et responsive pour une micro-entreprise de prothésiste ongulaire.

## Fonctionnalités

- **Design moderne et élégant** avec des couleurs rose/fuchsia adaptées au domaine de la beauté
- **Responsive** - S'adapte à tous les écrans (mobile, tablette, desktop)
- **Navigation fluide** avec menu mobile hamburger
- **Sections complètes** :
  - Hero section avec appel à l'action
  - Section À propos
  - Services détaillés (6 services)
  - Galerie de photos
  - Grille de tarifs
  - Témoignages clients
  - Formulaire de contact
  - Footer complet

## Structure du projet

```
cdnails/
├── index.html      # Page principale
├── styles.css      # Feuille de style CSS
├── script.js       # JavaScript pour l'interactivité
└── README.md       # Ce fichier
```

## Utilisation

1. **Ouvrir le site** : Double-cliquez sur `index.html` ou ouvrez-le dans votre navigateur web préféré

2. **Personnalisation** :
   - Modifiez les textes dans `index.html`
   - Changez les couleurs dans `styles.css` (variables CSS en haut du fichier)
   - Ajoutez vos propres images en remplaçant les placeholders

3. **Ajout d'images** :
   - Créez un dossier `images/`
   - Remplacez les `.image-placeholder` dans le HTML par vos photos
   - Format recommandé : JPG ou PNG, taille optimisée pour le web

## Personnalisation des couleurs

Les couleurs sont définies en haut du fichier `styles.css` :

```css
:root {
    --primary-color: #e91e63;      /* Rose principal */
    --secondary-color: #ff4081;    /* Rose secondaire */
    --dark-color: #2c2c2c;         /* Couleur foncée */
    --light-color: #f8f9fa;        /* Couleur claire */
}
```

## Sections à personnaliser

1. **Informations de contact** (ligne 262 de index.html) :
   - Adresse
   - Téléphone
   - Email
   - Horaires

2. **Tarifs** (ligne 159 de index.html) :
   - Ajustez les prix selon vos prestations
   - Ajoutez ou supprimez des formules

3. **Services** (ligne 91 de index.html) :
   - Personnalisez les descriptions
   - Ajoutez vos propres services

4. **Réseaux sociaux** :
   - Ajoutez les liens Facebook et Instagram

## Déploiement

### Option 1 : Hébergement gratuit avec GitHub Pages
1. Créez un compte sur GitHub
2. Créez un nouveau repository
3. Uploadez les fichiers
4. Activez GitHub Pages dans les paramètres

### Option 2 : Hébergement web classique
1. Uploadez tous les fichiers via FTP
2. Configurez votre nom de domaine
3. Le site est prêt !

## Technologies utilisées

- HTML5
- CSS3 (avec variables CSS, Flexbox, Grid)
- JavaScript vanilla (pas de framework)

## Compatibilité

- ✅ Chrome, Firefox, Safari, Edge (versions récentes)
- ✅ Mobile iOS et Android
- ✅ Tablettes

## Améliorations futures possibles

- [ ] Système de réservation en ligne
- [ ] Intégration Google Maps
- [ ] Galerie photo interactive (lightbox)
- [ ] Blog/actualités
- [ ] Multilingue
- [ ] Connexion avec calendrier de rendez-vous
- [ ] Paiement en ligne

## Support

Pour toute question ou amélioration, n'hésitez pas à me contacter.

---

**Version** : 1.0
**Date** : Octobre 2024
**Licence** : Libre d'utilisation pour usage personnel
