# Guide d'Upload sur GitHub

## 🎯 Étape 1: Upload des fichiers

1. **Allez sur** https://github.com/bookmarks-cih/bookmarks.github.io
2. **Cliquez sur "Add file" → "Upload files"**
3. **Téléchargez ces dossiers/fichiers :**

### 📁 Structure à uploader :
```
bookmarks.github.io/
├── .github/
│   ├── workflows/
│   │   ├── scan-urls.yml
│   │   └── deploy-neocities.yml
│   └── scripts/
│       ├── scan-urls.js
│       └── deploy-neocities.js
├── Bookmarks/
│   ├── data/
│   │   ├── bookmarks-data.js
│   │   └── results.json
│   ├── status.html
│   ├── index.html
│   ├── about.html
│   ├── hub.html
│   ├── files.html
│   ├── jobs.html
│   ├── news.html
│   ├── privacy.html
│   ├── terms.html
│   ├── docs.html
│   ├── docs-data.js
│   ├── favicon.svg
│   ├── links.txt
│   ├── robots.txt
│   ├── cheatsheet/
│   ├── for_maitenance/
│   ├── resources/
│   └── scripts/
└── README.md
```

## 🎯 Étape 2: Activer GitHub Pages

1. **Dans votre repo**, allez dans **Settings**
2. **Cherchez "Pages"** dans le menu de gauche
3. **Source**: Sélectionnez "Deploy from a branch"
4. **Branch**: Choisissez "main"
5. **Folder**: / (root)
6. **Cliquez sur "Save"**

## 🎯 Étape 3: Activer GitHub Actions

1. **Allez dans Settings → Actions → General**
2. **Workflow permissions**: 
   - ✅ Cochez "Read and write permissions"
   - ✅ Cochez "Allow GitHub Actions to create and approve pull requests"
3. **Cliquez sur "Save"**

## 🎯 Étape 4: Vérifier les secrets

1. **Allez dans Settings → Secrets and variables → Actions**
2. **Vérifiez que vous avez :**
   - `URLSCAN_API_KEY` ✅
   - `NEOCITIES_API_KEY` ✅

## 🎯 Étape 5: Tester les workflows

1. **Allez dans l'onglet "Actions"**
2. **Cliquez sur "URL Status Scanner"**
3. **Cliquez sur "Run workflow" → "Run workflow"**
4. **Attendez que le scan se termine**

## 🎯 Étape 6: Accéder à votre site

**URL de votre site :**
- 🏠 **Page principale**: https://bookmarks-cih.github.io
- 📊 **Status Monitor**: https://bookmarks-cih.github.io/Bookmarks/status.html

## ✅ Checklist de vérification

- [ ] Tous les fichiers uploadés
- [ ] GitHub Pages activé
- [ ] GitHub Actions permissions configurées
- [ ] Secrets API configurés
- [ ] Workflow testé manuellement
- [ ] Site accessible via l'URL

---

**Une fois tout uploadé, votre status.html sera automatiquement mis à jour toutes les 6 heures !**
