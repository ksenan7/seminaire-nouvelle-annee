# 🚀 Déploiement GitHub Pages — Séminaire « Nouvelle Année, Nouvelle Vie »
**Setonwe Finances & KDIEX**

Ce dossier contient l'ensemble autonome du site prêt à être déployé immédiatement sur **GitHub Pages** (ou tout autre hébergement web comme Vercel, Netlify, Cloudflare Pages ou cPanel).

---

## 📂 Contenu du dossier
* `index.html` : La Landing Page complète (responsive, typographie Cinzel / Plus Jakarta Sans, minuteurs Header & Footer, basculement automatique des tarifs, modale FedaPay sécurisée).
* `confirmation.html` : La Page de Remerciement / Confirmation post-paiement (sécurisée par `tx_id`, intégration WhatsApp direct).
* `images setonwe/` : Tous les visuels officiels optimisés (photos réelles de Julien et Hermionne, kit participant, ateliers, logo).
* `robots.txt` : Référencement SEO configuré (indexation de la page principale et protection de la page de confirmation).
* `.gitignore` : Fichiers systèmes ignorés.

---

## 🛠️ Instructions de déploiement sur GitHub Pages (3 étapes simples)

### Étape 1 : Créer un nouveau dépôt sur GitHub
1. Connectez-vous sur votre compte [GitHub](https://github.com).
2. Cliquez sur le bouton vert **« New »** pour créer un dépôt (repository).
3. Nommez-le par exemple : `seminaire-nouvelle-annee` (ou le nom de votre choix).
4. Choisissez la visibilité **Public** (nécessaire pour GitHub Pages gratuit).
5. Ne cochez pas "Add a README" (nous avons déjà tout préparé).
6. Cliquez sur **« Create repository »**.

---

### Étape 2 : Publier ce dossier sur GitHub

Ouvrez un terminal PowerShell ou une invite de commande dans ce dossier `deploy-github` et exécutez les commandes suivantes :

```bash
# 1. Se placer dans le dossier de déploiement
cd "c:\Users\KDIEX\OneDrive\Desktop\Google Antigravity\BRAIN\08_Formations_Ateliers\Seminaire Janvier\deploy-github"

# 2. Initialiser le dépôt git
git init

# 3. Ajouter tous les fichiers
git add .

# 4. Enregistrer le commit initial
git commit -m "Initial commit - Tunnel de vente Setonwe Finances"

# 5. Définir la branche principale sur main
git branch -M main

# 6. Relier votre dépôt GitHub (remplacez VOTRE-UTILISATEUR et VOTRE-DEPOT par vos informations)
git remote add origin https://github.com/VOTRE-UTILISATEUR/VOTRE-DEPOT.git

# 7. Envoyer les fichiers sur GitHub
git push -u origin main
```

---

### Étape 3 : Activer GitHub Pages
1. Sur votre dépôt GitHub, allez dans l'onglet **Settings** (en haut à droite).
2. Dans le menu de gauche, cliquez sur **Pages** (sous la section *Code and automation*).
3. Sous **Build and deployment** :
   * **Source :** Sélectionnez `Deploy from a branch`.
   * **Branch :** Sélectionnez `main` et laissez le dossier sur `/ (root)`.
4. Cliquez sur **Save**.
5. Après 1 à 2 minutes, votre site sera en ligne à l'adresse :  
   `https://VOTRE-UTILISATEUR.github.io/VOTRE-DEPOT/`

---

### 🌐 (Optionnel) Lier un Nom de Domaine Personnalisé
Si vous souhaitez utiliser un sous-domaine de marque (ex : `seminaire.setonwefinances.com`) :
1. Dans GitHub > **Settings** > **Pages** > **Custom domain**, renseignez votre domaine.
2. Chez votre registraire de domaine (DNS), ajoutez un enregistrement `CNAME` :
   * **Nom / Hôte :** `seminaire`
   * **Valeur / Cible :** `VOTRE-UTILISATEUR.github.io`
3. Cochez **Enforce HTTPS** sur GitHub Pages.

---

### 💳 Rappel Configuration FedaPay
Votre clé publique FedaPay live (`pk_live_thmZxJF1sTikTpyP3bf29axk`) est déjà configurée et active dans `index.html`. Les paiements sont prêts à être encaissés directement.
