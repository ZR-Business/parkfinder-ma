# 🅿️ ParkFinder MA

Application web de recherche de parking en temps réel.

## 📁 Structure
```
parkfinder/
├── index.html        ← Landing page + Login/Signup
├── agent.html        ← Dashboard Agent (gérer les parkings)
├── client.html       ← Carte + Liste des parkings + Réservation
└── README.md
```

## 🚀 Étapes pour lancer le projet

### 1. Créer un projet Firebase
1. Va sur https://console.firebase.google.com
2. Clique "Ajouter un projet" → donne un nom (ex: parkfinder-ma)
3. Désactive Google Analytics (pas nécessaire) → Créer

### 2. Activer Authentication
1. Dans Firebase Console → Authentication → Commencer
2. Onglet "Sign-in method" → Activer "E-mail/Mot de passe"

### 3. Activer Firestore
1. Firestore Database → Créer une base de données
2. Choisir "Mode test" (pour commencer)
3. Choisir une région (europe-west1)

### 4. Récupérer la config Firebase
1. Firebase Console → ⚙️ Paramètres du projet → Vos applications
2. Cliquer l'icône "</>" (Web)
3. Enregistrer l'application → copier le firebaseConfig

### 5. Remplacer la config dans les 3 fichiers HTML
Chercher dans chaque fichier :
```js
const firebaseConfig = {
  apiKey: "VOTRE_API_KEY",
  ...
};
```
Et remplacer par ta vraie config.

### 6. Règles Firestore (mode test)
```
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /{document=**} {
      allow read, write: if true;
    }
  }
}
```

### 7. Déployer sur GitHub Pages
1. Crée un repo GitHub (ex: parkfinder-ma)
2. Upload les 3 fichiers HTML
3. Settings → Pages → Source: main branch
4. Ton site sera sur: https://TON_USERNAME.github.io/parkfinder-ma

## 👥 Utilisateurs
- **Agent** : s'inscrit, ajoute ses parkings, met à jour les places
- **Client gratuit** : voit la carte et les places disponibles
- **Client premium** : peut réserver une place (50 DH/mois simulé)

## 🛠️ Technologies
- HTML/CSS/JS vanilla
- Firebase Auth + Firestore
- Leaflet.js (carte OpenStreetMap)
- Google Fonts (Syne + DM Sans)
