# Portfolio BTS SIO — Alex-Junior Gross

Portfolio professionnel pour l'épreuve E6 du BTS Services Informatiques aux
Organisations, option SISR — session 2026.

Ce site centralise la documentation des réalisations professionnelles afin de
permettre au jury d'y accéder via une URL publique.

## Contenu

- `index.html` — page d'accueil du portfolio
- `realisation-1.html` — Mise en place d'un contrôleur de domaine Active Directory
- `realisation-2.html` — Mise en place d'un routage Inter-VLAN
- `style.css` — feuille de style
- `assets/serveur-active-directory.pdf` — documentation technique réalisation 01
- `assets/routage-inter-vlan.pdf` — documentation technique réalisation 02
- `.nojekyll` — désactive le traitement Jekyll par GitHub Pages

---

## Déployer sur GitHub Pages — pas à pas

### 1. Créer un compte GitHub

Si tu n'en as pas déjà un, rends-toi sur https://github.com et crée un compte
gratuit. Ton nom d'utilisateur apparaîtra dans l'URL finale du site, donc
choisis quelque chose de propre, par exemple `alex-junior-gross` ou `ajgross`.

### 2. Créer un nouveau dépôt (repo)

1. Une fois connecté, clique sur le `+` en haut à droite, puis **New repository**.
2. **Repository name** : `bts-sio-portfolio` (ou `portfolio`, comme tu veux).
3. Coche **Public** (obligatoire pour GitHub Pages avec un compte gratuit).
4. NE coche PAS « Add a README file » (on a déjà tout).
5. Clique sur **Create repository**.

### 3. Uploader les fichiers

Sur la page du dépôt fraîchement créé, clique sur **uploading an existing file**
(le lien apparaît au milieu de la page).

Glisse-dépose tous les fichiers ET le dossier `assets` dans la zone d'upload.
Important : il faut bien que la structure soit conservée :

```
ton-repo/
├── .nojekyll
├── README.md
├── index.html
├── realisation-1.html
├── realisation-2.html
├── style.css
└── assets/
    ├── serveur-active-directory.pdf
    └── routage-inter-vlan.pdf
```

Si l'interface web n'accepte pas les dossiers en glisser-déposer, tu peux aussi :
- Cliquer sur **Add file → Create new file**, taper `assets/placeholder.txt`
  pour créer le dossier, puis uploader les PDF dedans.
- Ou utiliser GitHub Desktop (https://desktop.github.com/) qui gère ça
  beaucoup plus facilement.

Une fois tout en place, écris un message de commit (par exemple
« Initial commit ») puis clique sur **Commit changes**.

### 4. Activer GitHub Pages

1. Sur la page du dépôt, va dans l'onglet **Settings** (en haut à droite).
2. Dans le menu de gauche, clique sur **Pages**.
3. Sous **Source**, sélectionne :
   - Branch : `main`
   - Folder : `/ (root)`
4. Clique sur **Save**.

GitHub te dira « Your site is live at … ». L'URL aura cette forme :

```
https://TON-PSEUDO.github.io/bts-sio-portfolio/
```

Le premier déploiement prend en général 1 à 2 minutes. Si tu vois une page 404
au début, c'est normal, attends un peu et rafraîchis.

### 5. Mettre cette URL dans ton dossier de réalisations

Une fois le site en ligne, modifie ton dossier BTS pour remplacer les anciennes
URL `https://ajgbtssio.fr/...` par les nouvelles :

- Réalisation 01 → `https://TON-PSEUDO.github.io/bts-sio-portfolio/realisation-1.html`
- Réalisation 02 → `https://TON-PSEUDO.github.io/bts-sio-portfolio/realisation-2.html`

---

## Mettre à jour le site plus tard

Si tu veux ajouter une réalisation ou corriger un détail :

1. Va sur ton repo GitHub.
2. Clique sur le fichier à modifier puis sur l'icône crayon (éditer).
3. Fais tes modifications, puis **Commit changes**.

GitHub Pages se met à jour automatiquement (1-2 minutes).

Tu peux aussi uploader de nouveaux fichiers via **Add file → Upload files**.

---

## Tester en local avant de publier

Pour vérifier que le site fonctionne avant de le déployer, tu peux l'ouvrir
en local. Comme les iframes pour les PDF nécessitent un vrai serveur
(et pas juste un double-clic sur le fichier HTML), le plus simple est
d'utiliser Python :

```bash
cd portfolio/
python3 -m http.server 8000
```

Puis ouvre http://localhost:8000 dans ton navigateur.

---

## Points à vérifier avant le passage devant le jury

- [ ] Le site est accessible depuis une connexion publique (test sur ton tél en 4G)
- [ ] Les deux PDF s'affichent bien dans l'iframe
- [ ] Les boutons « Ouvrir dans un nouvel onglet » et « Télécharger » fonctionnent
- [ ] L'URL est notée correctement dans le dossier de réalisations papier
- [ ] Le site s'affiche correctement sur mobile (test au moins une fois)
