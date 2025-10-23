# 🚀 Déploiement Rapide

## Fichiers à copier sur votre serveur web

Copiez ces fichiers à la racine de votre hébergement web (généralement dans `public_html/` ou `www/`) :

### ✅ Fichiers obligatoires

```
📄 index.html       → Page principale du site
📄 styles.css       → Feuille de styles
📄 script.js        → JavaScript (animations et interactions)
```

### ✅ Fichiers optionnels mais recommandés

```
📄 .htaccess        → Configuration Apache (cache, compression, sécurité)
📄 robots.txt       → Pour les moteurs de recherche (SEO)
📄 favicon.ico      → Icône du site (à créer/ajouter)
```

### 📁 Dossier à créer

```
📁 images/          → Pour toutes vos photos
   ├── about.jpg    → Votre photo ou celle de votre salon
   ├── gallery-1.jpg → Photos de vos réalisations
   ├── gallery-2.jpg
   ├── gallery-3.jpg
   ├── gallery-4.jpg
   ├── gallery-5.jpg
   └── gallery-6.jpg
```

## 📋 Structure finale sur votre serveur

```
public_html/  (ou www/)
│
├── index.html          ← Page d'accueil
├── styles.css          ← Design et animations
├── script.js           ← Interactivité
├── .htaccess          ← Configuration serveur
├── robots.txt         ← SEO
├── favicon.ico        ← Icône du site
│
└── images/            ← Dossier des photos
    ├── about.jpg
    ├── gallery-1.jpg
    ├── gallery-2.jpg
    ├── gallery-3.jpg
    ├── gallery-4.jpg
    ├── gallery-5.jpg
    └── gallery-6.jpg
```

## 🎯 Étapes d'installation (5 minutes)

### 1️⃣ Connectez-vous à votre hébergement

Par FTP avec :
- **FileZilla** (gratuit) : https://filezilla-project.org/
- **Cyberduck** (gratuit) : https://cyberduck.io/

Ou via le **Gestionnaire de fichiers** de votre hébergeur (cPanel, Plesk, etc.)

### 2️⃣ Uploadez les 3 fichiers principaux

Glissez-déposez dans votre serveur :
- `index.html`
- `styles.css`
- `script.js`

### 3️⃣ Uploadez les fichiers optionnels

- `.htaccess` (si vous avez Apache)
- `robots.txt`

### 4️⃣ Créez le dossier images

- Créez un nouveau dossier nommé `images`
- Uploadez-y vos photos

### 5️⃣ Testez votre site

Ouvrez votre navigateur et allez sur : `http://votre-domaine.com`

✅ **C'est terminé !**

## 🎨 Personnalisation rapide

### Changer vos coordonnées

Ouvrez `index.html` avec un éditeur de texte et cherchez :

```html
<p>123 Rue de la Beauté<br>75000 Paris</p>
```

Remplacez par vos vraies informations.

### Ajouter vos photos

1. **Optimisez vos photos** avec https://tinypng.com/
2. **Nommez-les** : `gallery-1.jpg`, `gallery-2.jpg`, etc.
3. **Uploadez-les** dans le dossier `images/`
4. **Modifiez `index.html`** pour utiliser vos images :

Cherchez :
```html
<div class="image-placeholder">Photo 1</div>
```

Remplacez par :
```html
<img src="images/gallery-1.jpg" alt="Nail art réalisé par CD Nails">
```

## 💡 Solutions d'hébergement recommandées

### Gratuit (pour débuter)

- **GitHub Pages** : Gratuit, illimité
- **Netlify** : Gratuit, très simple
- **Vercel** : Gratuit, rapide

### Payant (professionnel)

- **OVH** : À partir de 2-3€/mois
- **O2Switch** : 5€/mois (hébergement français illimité)
- **Hostinger** : À partir de 2€/mois

## 🆘 Problèmes fréquents

### ❌ Le site ne s'affiche pas

➡️ Vérifiez que `index.html` est bien à la racine (pas dans un sous-dossier)

### ❌ Les images ne s'affichent pas

➡️ Vérifiez que le dossier `images/` existe et contient vos photos

### ❌ Le design est cassé

➡️ Vérifiez que `styles.css` est dans le même dossier que `index.html`

### ❌ Les animations ne fonctionnent pas

➡️ Vérifiez que `script.js` est uploadé et dans le bon dossier

## 📞 Support

Consultez le fichier `INSTALLATION.md` pour des instructions détaillées.

---

**🎉 Félicitations, votre site est en ligne !**
