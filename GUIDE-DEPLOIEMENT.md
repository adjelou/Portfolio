# 🚀 Guide — Portfolio ADJELOU Jean Eudes
## Personnalisation + Déploiement Vercel

---

## 📁 Structure du projet

```
portfolio/
├── index.html          ← Votre portfolio (tout-en-un)
├── vercel.json         ← Config Vercel (optionnel)
└── assets/             ← Créez ce dossier
    └── photo.jpg       ← Votre photo de profil
```

---

## ✏️ Les 10 choses à modifier dans index.html

Cherchez ces textes (Ctrl+F) et remplacez :

| Ce qu'il faut chercher | Ce qu'il faut mettre |
|---|---|
| `adjeloujeaneudes@gmail.com` | Votre vrai email |
| `+228 XX XX XX XX` | Votre numéro WhatsApp |
| `github.com/adjelou` | Votre vrai profil GitHub |
| `linkedin.com/in/adjeloujeaneudes` | Votre vrai LinkedIn |
| `YOUR_FORM_ID` | Votre ID Formspree (voir section formulaire) |
| `3+` (années d'exp.) | Le bon nombre d'années |
| `10+` (projets livrés) | Le bon nombre de projets |
| Textes des certifications | Vos vraies certifications |
| Dates dans le parcours | Vos vraies dates |
| Texte "Projet académique & missions freelance" | Votre vrai employeur |

### Ajouter votre photo
Remplacez le bloc `.about-img-placeholder` par :
```html
<img src="assets/photo.jpg" alt="ADJELOU Jean Eudes" 
     style="width:100%;aspect-ratio:4/5;object-fit:cover;border-radius:12px;border:1px solid var(--border);" />
```

---

## 📬 Formulaire de contact — Formspree (gratuit)

1. Allez sur **https://formspree.io**
2. Créez un compte gratuit
3. Cliquez "New Form" → entrez votre email
4. Copiez l'ID (ex: `xpwzqabc`)
5. Dans `index.html`, remplacez `YOUR_FORM_ID` par votre ID :
   ```
   https://formspree.io/f/xpwzqabc
   ```
6. C'est tout ! Les messages arrivent dans votre boîte email.

---

## 🌐 Déploiement sur Vercel — Étape par étape

### Méthode 1 : GitHub + Vercel (recommandée)

#### Étape 1 — Créer le dépôt GitHub
```bash
# Créez un dossier "portfolio"
mkdir portfolio
cd portfolio

# Copiez index.html dedans, puis :
git init
git add .
git commit -m "Initial portfolio"

# Sur github.com, créez un nouveau dépôt "portfolio"
# Puis connectez-le :
git remote add origin https://github.com/VOTRE_USERNAME/portfolio.git
git branch -M main
git push -u origin main
```

#### Étape 2 — Connecter Vercel
1. Allez sur **https://vercel.com**
2. Cliquez **"Sign Up"** → connectez-vous avec GitHub
3. Cliquez **"Add New Project"**
4. Sélectionnez votre dépôt **"portfolio"**
5. Laissez tous les paramètres par défaut
6. Cliquez **"Deploy"**
7. ✅ Votre site est en ligne en 30 secondes !

#### Étape 3 — Obtenir votre URL
Vercel génère automatiquement :
```
https://portfolio-VOTRE_USERNAME.vercel.app
```

#### Étape 4 — Déploiements automatiques
À chaque `git push`, Vercel redéploie automatiquement :
```bash
# Modifier votre fichier index.html, puis :
git add .
git commit -m "Mise à jour projets"
git push

# → Vercel déploie en ~30 secondes automatiquement !
```

---

### Méthode 2 : Vercel CLI (sans GitHub)

```bash
# Installer Vercel CLI
npm install -g vercel

# Dans votre dossier portfolio
vercel login
vercel

# Suivez les instructions, votre site est en ligne !
```

---

### Méthode 3 : Drag & Drop (la plus simple)

1. Allez sur **https://vercel.com/new**
2. Faites glisser votre dossier `portfolio/` dans la page
3. C'est déployé ! ✅

---

## 🔧 Fichier vercel.json (optionnel)

Créez un fichier `vercel.json` pour des redirections :

```json
{
  "version": 2,
  "routes": [
    { "src": "/(.*)", "dest": "/index.html" }
  ],
  "headers": [
    {
      "source": "/(.*)",
      "headers": [
        { "key": "X-Frame-Options", "value": "SAMEORIGIN" },
        { "key": "X-Content-Type-Options", "value": "nosniff" }
      ]
    }
  ]
}
```

---

## 🌍 Domaine personnalisé (ex: jeaneudes.dev)

1. Achetez un domaine sur **Namecheap, GoDaddy, ou OVH**
2. Dans Vercel → votre projet → **"Domains"**
3. Ajoutez votre domaine
4. Vercel vous donne les enregistrements DNS à configurer
5. Attendez 5-30 minutes → votre site est sur votre domaine !

---

## 💡 Conseils pour aller plus loin

- **Analytics** : Vercel Analytics (gratuit dans le dashboard)
- **Performance** : Le site est déjà optimisé (HTML pur, pas de framework)
- **SEO** : Ajoutez ces balises dans le `<head>` :
  ```html
  <meta name="description" content="Portfolio de ADJELOU Jean Eudes, développeur Full-Stack à Lomé, Togo. Python, Flask, Django, Java, MySQL." />
  <meta property="og:title" content="ADJELOU Jean Eudes — Full-Stack Developer" />
  <meta property="og:image" content="https://votre-site.vercel.app/assets/photo.jpg" />
  ```

---

## ❓ Problèmes fréquents

| Problème | Solution |
|---|---|
| Formulaire ne fonctionne pas | Vérifiez que `YOUR_FORM_ID` est remplacé |
| Photo ne s'affiche pas | Vérifiez le chemin `assets/photo.jpg` |
| Vercel dit "no framework detected" | C'est normal, choisissez "Other" |
| Site lent sur mobile | C'est déjà optimisé, vérifiez votre connexion |

---

*Portfolio généré pour ADJELOU Jean Eudes Victoire — Lomé, Togo 🇹🇬*
