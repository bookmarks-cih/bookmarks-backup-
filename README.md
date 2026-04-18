# Bookmarks Web - URL Status Monitor

A comprehensive web-based bookmarks manager with automated URL status monitoring using URLScan.io and GitHub Actions.

**Created by @morneface** - Open Source Project

## 📜 License

Ce projet est open source mais reste la propriété intellectuelle de son créateur @morneface. 

**Autorisé :**
- ✅ Utilisation personnelle et éducative
- ✅ Fork pour contribution 
- ✅ Apprentissage du code
- ✅ Modification pour usage personnel

**Interdit :**
- ❌ Reproduction commerciale sans autorisation
- ❌ Suppression des crédits de l'auteur
- ❌ Attribution du travail à quelqu'un d'autre
- ❌ Vente ou monétisation sans accord explicite

## 🤝 Contribuer

Les contributions sont bienvenues ! Veuillez respecter l'esprit du projet et conserver les crédits appropriés.

## 🌟 Fonctionnalités

- **Interface Moderne** : Design épuré et responsive avec thème sombre/clair
- **Monitoring URL** : Vérification automatique du statut toutes les 6 heures  
- **Intégration URLScan.io** : Analyse de sécurité et rapports détaillés
- **GitHub Actions** : Scanning automatisé sans intervention manuelle
- **Catégories** : Organisez vos favoris par catégories
- **Recherche** : Trouvez rapidement vos URLs
- **Tableau de Bord** : Vue d'ensemble de la santé de vos URLs

## 🚀 Instructions d'Installation

### 1. Configurer l'API URLScan.io

1. Inscrivez-vous sur [urlscan.io](https://urlscan.io/)
2. Récupérez votre clé API depuis votre dashboard
3. Ajoutez-la aux secrets de votre repository GitHub :
   - Allez dans votre repo → Settings → Secrets and variables → Actions
   - Cliquez sur "New repository secret"
   - Nom : `URLSCAN_API_KEY`
   - Value : Votre clé URLScan.io

### 2. Activer GitHub Actions

Le workflow est déjà configuré dans `.github/workflows/scan-urls.yml` et va :
- S'exécuter automatiquement toutes les 6 heures
- Peut être déclenché manuellement
- Mettre à jour le fichier `Bookmarks/data/results.json`
- Commiter les changements dans le repository

### 3. Personnaliser les URLs

Éditez les sources d'URLs :

1. **URLs Statiques** : Modifiez `STATIC_URLS` dans `.github/scripts/scan-urls.js`
2. **Données Bookmarks** : Mettez à jour `Bookmarks/data/bookmarks-data.js`

### 4. Développement Local

1. Clonez le repository
2. Servez les fichiers avec n'importe quel serveur web :
   ```bash
   # Avec Python
   python -m http.server 8000
   
   # Avec Node.js
   npx serve .
   
   # Avec PHP
   php -S localhost:8000
   ```
3. Ouvrez `Bookmarks/status.html` dans votre navigateur

## 📁 Structure des Fichiers

```
bookmarks.github.io/
├── .github/
│   ├── workflows/
│   │   ├── scan-urls.yml          # Workflow GitHub Actions
│   │   └── deploy-neocities.yml   # Déploiement Neocities
│   └── scripts/
│       ├── scan-urls.js           # Script de scanning
│       └── deploy-neocities.js    # Script de déploiement
├── Bookmarks/
│   ├── data/
│   │   ├── bookmarks-data.js      # Vos données de favoris
│   │   └── results.json           # Résultats des scans (auto-généré)
│   ├── status.html                # Page principale de monitoring
│   ├── index.html                 # Page principale des favoris
│   └── [autres fichiers HTML]
└── README.md
```

## ⚙️ Comment Ça Marche

1. **GitHub Actions** déclenche le scanner toutes les 6 heures
2. **Script Node.js** lit toutes les URLs de vos favoris
3. **URLScan.io API** scanne chaque URL pour la sécurité et la disponibilité
4. **Résultats** sont sauvegardés dans `results.json`
5. **Page de statut** affiche l'état actuel de toutes les URLs

## 🎨 Types de Statut

- **🟢 Healthy** : URL accessible et sécurisée
- **🟡 Warning** : URL accessible mais avec problèmes (codes 4xx)
- **🔴 Error** : URL inaccessible ou problèmes de sécurité détectés
- **⚪ Unknown** : Pas encore scanné

## ⚙️ Options de Configuration

### Paramètres du Scanner

Éditez `.github/scripts/scan-urls.js` pour personnaliser :

```javascript
const CONFIG = {
  maxConcurrentScans: 3,    // Limite URLScan.io
  scanDelay: 2000          // Délai entre scans (ms)
};
```

### Schedule GitHub Actions

Éditez `.github/workflows/scan-urls.yml` pour changer la fréquence :

```yaml
schedule:
  - cron: '0 */6 * * *'  # Toutes les 6 heures
```

## 🔐 Notes de Sécurité

- Les clés API sont stockées de manière sécurisée dans GitHub Secrets
- Tous les scans sont effectués dans le sandbox GitHub Actions
- Les résultats sont commités automatiquement dans le repository
- Aucune donnée sensible n'est exposée dans le frontend

## 🐛 Dépannage

### Problèmes Courants

1. **Limites de taux API** : URLScan.io a des limites. Le scanner inclut des délais pour les respecter.
2. **Scans échoués** : Vérifiez les logs des Actions pour les messages d'erreur détaillés.
3. **Résultats manquants** : Assurez-vous que le workflow a la permission de commiter dans le repository.

### Déclenchement Manuel

Vous pouvez déclencher un scan manuellement :
1. Allez dans Actions → URL Status Scanner
2. Cliquez sur "Run workflow"

## 🤝 Contribuer

1. Fork le repository
2. Créez une branche de fonctionnalité
3. Faites vos modifications
4. Soumettez une pull request

---

**Créé avec ❤️ par @morneface**  
*Projet Open Source - Tous droits réservés à l'auteur*
