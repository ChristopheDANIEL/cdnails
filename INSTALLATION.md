# Guide d'Installation - CD Nails

## 📋 Prérequis

- Un serveur web (Apache, Nginx, ou hébergement web)
- Accès FTP/SFTP ou panneau de contrôle (cPanel, Plesk, etc.)
- Optionnel : Nom de domaine

## 🚀 Installation

### Option 1 : Hébergement Web Classique (cPanel, etc.)

1. **Connectez-vous à votre hébergement**
   - Via FTP (FileZilla, Cyberduck, etc.)
   - Ou via le gestionnaire de fichiers de votre hébergeur

2. **Uploadez les fichiers suivants dans le dossier `public_html` ou `www`** :
   ```
   ✅ index.html
   ✅ styles.css
   ✅ script.js
   ✅ .htaccess (si Apache)
   ✅ robots.txt
   ✅ favicon.ico (si vous en avez un)
   ```

3. **Créez un dossier `images`** dans le même répertoire

4. **Vérifiez les permissions** :
   - Fichiers : 644
   - Dossiers : 755

5. **Testez votre site** : `http://votre-domaine.com`

### Option 2 : Serveur VPS/Dédié

#### Pour Apache

1. **Placez les fichiers dans `/var/www/html/`** :
   ```bash
   cd /var/www/html/
   # Copiez vos fichiers ici
   ```

2. **Vérifiez qu'Apache est installé** :
   ```bash
   sudo systemctl status apache2
   ```

3. **Activez les modules nécessaires** :
   ```bash
   sudo a2enmod deflate expires headers rewrite
   sudo systemctl restart apache2
   ```

#### Pour Nginx

1. **Placez les fichiers dans `/usr/share/nginx/html/`** :
   ```bash
   cd /usr/share/nginx/html/
   # Copiez vos fichiers ici
   ```

2. **Configuration Nginx** (`/etc/nginx/sites-available/default`) :
   ```nginx
   server {
       listen 80;
       server_name votre-domaine.com;
       root /usr/share/nginx/html;
       index index.html;

       location / {
           try_files $uri $uri/ /index.html;
       }

       # Compression Gzip
       gzip on;
       gzip_types text/css application/javascript image/svg+xml;

       # Cache
       location ~* \.(jpg|jpeg|png|gif|ico|css|js|svg|woff|woff2|ttf)$ {
           expires 1y;
           add_header Cache-Control "public, immutable";
       }
   }
   ```

3. **Redémarrez Nginx** :
   ```bash
   sudo systemctl restart nginx
   ```

### Option 3 : Hébergement Gratuit (GitHub Pages, Netlify, Vercel)

#### GitHub Pages (Gratuit)

1. **Créez un repository sur GitHub**
2. **Uploadez les fichiers** : `index.html`, `styles.css`, `script.js`, et le dossier `images`
3. **Activez GitHub Pages** dans Settings > Pages
4. **Votre site sera disponible** à : `https://votre-username.github.io/nom-repo/`

#### Netlify (Gratuit)

1. **Inscrivez-vous sur** [netlify.com](https://netlify.com)
2. **Glissez-déposez** votre dossier contenant tous les fichiers
3. **Votre site est en ligne** en quelques secondes !
4. Vous obtenez un domaine gratuit : `votre-site.netlify.app`

#### Vercel (Gratuit)

1. **Inscrivez-vous sur** [vercel.com](https://vercel.com)
2. **Importez votre projet** depuis GitHub ou uploadez les fichiers
3. **Déploiement automatique** en quelques secondes

## 📸 Ajouter vos images

1. **Créez le dossier `images/`** à la racine

2. **Préparez vos images** :
   - Format recommandé : JPG pour les photos, PNG pour les logos
   - Taille recommandée :
     - Photos de galerie : 800x800px
     - Photo "À propos" : 600x750px
   - Compression : utilisez [TinyPNG](https://tinypng.com/) ou [Squoosh](https://squoosh.app/)

3. **Modifiez `index.html`** pour remplacer les placeholders :

   ```html
   <!-- Exemple : Section À propos -->
   <div class="image-placeholder">
       <span>Photo</span>
   </div>

   <!-- Remplacez par : -->
   <img src="images/about.jpg" alt="Prothésiste ongulaire CD Nails">
   ```

   ```html
   <!-- Exemple : Galerie -->
   <div class="gallery-item">
       <div class="image-placeholder">Photo 1</div>
   </div>

   <!-- Remplacez par : -->
   <div class="gallery-item">
       <img src="images/gallery-1.jpg" alt="Nail art rose et blanc">
   </div>
   ```

## 🔒 Configurer HTTPS (Recommandé)

### Avec Let's Encrypt (Gratuit)

```bash
# Installation Certbot
sudo apt-get update
sudo apt-get install certbot python3-certbot-apache

# Obtenir un certificat SSL
sudo certbot --apache -d votre-domaine.com -d www.votre-domaine.com

# Renouvellement automatique
sudo certbot renew --dry-run
```

Une fois SSL configuré, décommentez les lignes HTTPS dans `.htaccess`.

## ⚙️ Personnalisation

### 1. Informations de contact

Éditez `index.html` ligne ~305 :
```html
<p>123 Rue de la Beauté<br>75000 Paris</p>  <!-- Votre adresse -->
<p>06 12 34 56 78</p>                        <!-- Votre téléphone -->
<p>contact@cdnails.fr</p>                    <!-- Votre email -->
```

### 2. Réseaux sociaux

Ajoutez vos liens Facebook et Instagram ligne ~330 :
```html
<a href="https://facebook.com/votre-page" class="social-link">Facebook</a>
<a href="https://instagram.com/votre-compte" class="social-link">Instagram</a>
```

### 3. Tarifs

Modifiez les prix ligne ~232 selon vos prestations.

### 4. Couleurs

Pour changer les couleurs, éditez `styles.css` lignes 14-18 :
```css
--primary: #d63384;        /* Couleur principale */
--secondary: #8b5cf6;      /* Couleur secondaire */
```

## 🔍 Optimisation SEO

### 1. Meta tags

Ajoutez dans `<head>` de `index.html` :
```html
<meta name="keywords" content="prothésiste ongulaire, manucure, nail art, vernis semi-permanent, [votre ville]">
<meta property="og:title" content="CD Nails - Prothésiste Ongulaire">
<meta property="og:description" content="Prothésiste ongulaire professionnelle - Manucure, nail art et soins des ongles">
<meta property="og:image" content="https://votre-domaine.com/images/preview.jpg">
<meta property="og:url" content="https://votre-domaine.com">
```

### 2. Google Analytics (optionnel)

Ajoutez avant `</head>` :
```html
<!-- Google tag (gtag.js) -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-XXXXXXXXXX"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'G-XXXXXXXXXX');
</script>
```

### 3. Google My Business

Inscrivez votre entreprise sur Google My Business pour apparaître dans les résultats locaux.

## 📧 Formulaire de contact fonctionnel

Le formulaire actuel affiche juste une notification. Pour le rendre fonctionnel :

### Option 1 : Formspree (Gratuit, facile)

1. Inscrivez-vous sur [formspree.io](https://formspree.io)
2. Créez un formulaire et obtenez l'URL
3. Modifiez la balise `<form>` :
   ```html
   <form action="https://formspree.io/f/VOTRE_ID" method="POST">
   ```

### Option 2 : EmailJS (Gratuit)

1. Inscrivez-vous sur [emailjs.com](https://emailjs.com)
2. Configurez votre service email
3. Suivez leur documentation pour intégrer dans `script.js`

### Option 3 : PHP (si votre hébergeur le supporte)

Créez un fichier `contact.php` - je peux vous fournir le code si nécessaire.

## 🧪 Tester votre site

Avant de mettre en ligne :

- ✅ Testez sur différents navigateurs (Chrome, Firefox, Safari, Edge)
- ✅ Testez sur mobile et tablette
- ✅ Vérifiez tous les liens
- ✅ Testez le formulaire
- ✅ Vérifiez les images
- ✅ Testez la vitesse avec [PageSpeed Insights](https://pagespeed.web.dev/)

## ❓ Besoin d'aide ?

- **Problème de fichiers** : Vérifiez les permissions (644 pour fichiers, 755 pour dossiers)
- **Page blanche** : Vérifiez les logs d'erreur du serveur
- **CSS ne s'applique pas** : Videz le cache du navigateur (Ctrl+F5)
- **Formulaire ne fonctionne pas** : Vérifiez la console du navigateur (F12)

## 🎉 Checklist de mise en ligne

- [ ] Tous les fichiers uploadés
- [ ] Dossier `images/` créé
- [ ] Photos ajoutées et optimisées
- [ ] Informations de contact personnalisées
- [ ] Liens réseaux sociaux ajoutés
- [ ] Tarifs mis à jour
- [ ] Favicon ajouté
- [ ] HTTPS configuré
- [ ] Test sur mobile
- [ ] Google Analytics configuré (optionnel)
- [ ] Formulaire de contact fonctionnel

---

**Votre site est maintenant prêt à recevoir vos clientes ! 🎊**
