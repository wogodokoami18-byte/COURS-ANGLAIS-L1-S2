# ⚙️ Configuration et Variables du Système

## 🔑 Clés et mots de passe

### Mot secret pour les étudiants
```
SOWAH
```
**Usage** : Entré par l'étudiant lors de l'authentification  
**Donné par** : Le professeur d'anglais en classe  
**Vérification** : Normalisée (majuscules, sans accents)

### Mot de passe administrateur (par défaut)
```
WJ2026admin
```
**⚠️ IMPORTANT** : Changer ce mot de passe immédiatement après test !

---

## 📱 Intégration WhatsApp (CallMeBot)

### Numéro d'enregistrement CallMeBot
```
+34 644 57 87 08
```

### Processus d'enregistrement
1. Ajouter ce numéro dans vos contacts
2. Envoyer exactement ce message :
   ```
   I allow callmebot to send me messages
   ```
3. Recevoir une clé API par retour

### Clé API CallMeBot
```
Remplacer par votre clé reçue
```

### Variables de code
```javascript
const CMBOT_KEY = "VOTRE_CLE_API";    // Clé API de CallMeBot
const WA_NUM = "22891195432";          // Numéro WhatsApp de l'admin
```

---

## 🌐 Déploiement

### URL du site (à remplir après déploiement)
```
https://anglais01.netlify.app
```

### Options de déploiement

#### Option 1 : Netlify (Recommandé)
- Créer un compte sur [netlify.com](https://netlify.com)
- Deploy manually le fichier HTML
- URL générée automatiquement

#### Option 2 : GitHub Pages
- Activer GitHub Pages dans les settings du dépôt
- URL : `https://wogodokoami18-byte.github.io/COURS-ANGLAIS-L1-S2/`

---

## 👥 Base de données étudiants

### Structure des groupes

| Groupe | Nom | Nombre d'étudiants |
|--------|-----|-------------------|
| 1 | Groupe 1 | 10 |
| 2 | Groupe 2 | 10 |
| 3 | Groupe 3 | 10 |
| 4 | Groupe 4 | 10 |
| 5 | Groupe 5 | 10 |
| 6 | Groupe 6 | 10 |
| 7 | Groupe 7 | 11 |
| 8 | Groupe 8 | 11 |
| 9 | Groupe 9 | 11 |
| 10 | Groupe 10 | 11 |
| 11 | Groupe 11 | 11 |

**Total** : 118 étudiants

### Format des données dans le HTML
```javascript
const STUDENTS = [
  {
    id: 1,
    nom: "AFANVI",
    prenom: "Afi Vénissa",
    groupe: 1,
    contact: "+228XXXXXXXXX"  // Numéro WhatsApp
  },
  // ... autres étudiants
];
```

---

## 🔐 Clé d'accès étudiant

### Format
```
WJ-[2 initiales][6 caractères aléatoires]
```

### Exemples
- `WJ-KM7X2P`
- `WJ-AB4K9L`
- `WJ-XY2D8R`

### Caractéristiques
- ✅ Unique par étudiant
- ✅ Générée lors de l'approbation par l'admin
- ✅ Stockée dans `localStorage` du navigateur
- ✅ Non transférable entre navigateurs
- ✅ Expire après une durée définie (configurable)

---

## 📊 Quiz de vérification

### Questions (à extraire du cours)

**Format recommandé** : 5 questions sur le contenu du cours

```javascript
const QUIZ_QUESTIONS = [
  {
    id: 1,
    question: "Question 1 du cours",
    options: ["Réponse A", "Réponse B", "Réponse C"],
    correct: 0  // Index de la réponse correcte
  },
  // ... autres questions
];
```

**Seuil de passage** : Minimum 2/3 bonnes réponses

---

## 📁 Structure des fichiers

### Dossier racine
```
COURS-ANGLAIS-L1-S2/
├── CoursAnglais_L1S2_V4.html    # Fichier principal (HTML autonome)
├── README.md                     # Vue d'ensemble du projet
├── DOCUMENTATION.md              # Guide complet
├── CONFIG.md                     # Ce fichier
├── /groupes/                     # Dossiers organisés par groupe
├── /assets/                      # Ressources (images, QR codes)
├── /admin/                       # Documentation pour l'admin
└── /dev/                         # Documentation pour les développeurs
```

### Dossier `/assets/`
```
/assets/
├── qr-code.png                  # QR code à scanner
├── logo-isica.png               # Logo de l'établissement
└── screenshots/                 # Captures d'écran du système
```

---

## 🔧 Checklist avant mise en production

- [ ] Créer le fichier HTML avec le PDF du cours encodé en Base64
- [ ] Mettre à jour la liste complète des 118 étudiants
- [ ] Changer le mot de passe admin (`WJ2026admin`)
- [ ] Enregistrer auprès de CallMeBot
- [ ] Remplacer `VOTRE_CLE_API` par la vraie clé
- [ ] Mettre à jour le numéro WhatsApp de l'admin (`WA_NUM`)
- [ ] Configurer le mot secret (`SOWAH`)
- [ ] Ajouter les 5 questions du quiz
- [ ] Déployer sur Netlify ou GitHub Pages
- [ ] Générer le QR code
- [ ] Tester avec au moins 3 étudiants différents
- [ ] Vérifier les notifications WhatsApp
- [ ] Imprimer et distribuer le QR code en classe

---

## 🚀 Variables d'environnement (optionnel)

Si vous utilisez un système avec variables d'environnement :

```env
ADMIN_PASSWORD=WJ2026admin
CMBOT_API_KEY=votre_cle_api
WHATSAPP_ADMIN_NUMBER=22891195432
SECRET_WORD=SOWAH
SITE_URL=https://anglais01.netlify.app
```

---

## 📞 Support

Pour modifier ces configurations :
1. Éditer ce fichier `CONFIG.md`
2. Mettre à jour le code HTML correspondant
3. Re-déployer sur Netlify/GitHub Pages

---

**⚠️ Document interne confidentiel — Ne pas diffuser**  
© 2026 · ISICA · Cours d'Anglais L1-S2
