# setonwefinances.com : site du séminaire + tunnel masterclass

Ce dossier est le dépôt GitHub Pages. Tout ce qu'il contient est publié tel quel.

## Pages

| Adresse | Fichier | Rôle |
|---|---|---|
| `/` | `index.html` | Page de vente du séminaire du 5 décembre (paiement FedaPay) |
| `/confirmation.html` | `confirmation.html` | Confirmation après paiement |
| `/masterclass/` | `masterclass/index.html` | Inscription à la masterclass gratuite du 15 novembre |
| `/masterclass/merci/` | `masterclass/merci/index.html` | Confirmation d'inscription : Zoom, agenda, groupe WhatsApp |

Autres fichiers :
- `images setonwe/` et `masterclass/img/` : les visuels.
- `CNAME` : le domaine personnalisé.
- `.nojekyll` : désactive Jekyll pour que GitHub publie les fichiers tels quels.
- `robots.txt` : bloque l'indexation des deux pages de confirmation.

## Lien avec n8n
Le formulaire `/masterclass/` envoie les inscriptions à :
`https://kdiex-n8n.srzxap.easypanel.host/webhook/masterclass-inscription`

Cette adresse se règle dans `WEBHOOK_URL`, en bas de `masterclass/index.html`.

Workflows (instance kdiex-n8n) :
- **Masterclass Cap 2027-2036 – Inscription** : enregistre l'inscrit dans le Google Sheet, puis envoie l'e-mail de confirmation.
- **Masterclass Cap 2027-2036 – Relances e-mail** : envoie les e-mails 2 à 12 aux dates prévues.

Les deux workflows doivent être **actifs** (bouton « Publish » dans n8n). Sinon le formulaire tombe en erreur.

Google Sheet des inscrits : https://docs.google.com/spreadsheets/d/1lYxKNUzWMtqaJ-nnwRMPwqmnV1skIBml3PreRsD5hyE/edit

## Mise en ligne (première fois)

```bash
cd "C:\Users\KDIEX\OneDrive\Desktop\Google Antigravity\BRAIN\08_Formations_Ateliers\Seminaire Janvier\deploy-github"
git init
git add .
git commit -m "Site séminaire + tunnel masterclass"
git branch -M main
git remote add origin https://github.com/VOTRE-COMPTE/setonwefinances.git
git push -u origin main
```

Ensuite, sur GitHub, ouvrez Settings → Pages et réglez :
- **Source :** Deploy from a branch.
- **Branche :** `main`, dossier `/ (root)`.
- **Custom domain :** `setonwefinances.com`. Le fichier `CNAME` le renseigne déjà.
- Cochez **Enforce HTTPS** dès que la case est disponible.

## DNS chez LWS (domaine racine setonwefinances.com)
Supprimez les anciens enregistrements A et AAAA de la racine, puis ajoutez :

| Type | Nom | Valeur |
|---|---|---|
| A | @ | 185.199.108.153 |
| A | @ | 185.199.109.153 |
| A | @ | 185.199.110.153 |
| A | @ | 185.199.111.153 |
| CNAME | www | VOTRE-COMPTE.github.io |

La propagation prend de quelques minutes à 24 h. Le certificat HTTPS arrive ensuite automatiquement.

## Mises à jour suivantes
```bash
git add .
git commit -m "Mise à jour"
git push
```

## FedaPay
La clé publique live FedaPay est intégrée dans `index.html`.
