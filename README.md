# 📝 Gestionnaire de Tâches

Une application web moderne de gestion de tâches avec une interface intuitive et des fonctionnalités avancées.

## ✨ Caractéristiques

- 🎯 Gestion complète des tâches (CRUD)
- 📋 Système de sous-tâches et commentaires
- 🏷️ Catégorisation par priorité et statut
- 🔍 Filtrage et recherche avancés
- 📱 Design responsive et moderne

## 🚀 Démarrage Rapide

```bash
# Installation
git clone [url-du-repo]
cd [nom-du-projet]
npm install

# Configuration
echo "PORT=3000
MONGODB_URI=mongodb://localhost:27017/TP2" > .env

# Lancement
npm start
```

## 🛠️ Stack Technique

- **Backend**: Node.js + Express + MongoDB
- **Frontend**: HTML5 + CSS3 + JavaScript vanilla
- **Base de données**: MongoDB avec Mongoose

## 📊 Structure des Données

```javascript
{
  titre: String,
  description: String,
  dateCreation: Date,
  echeance: Date,
  statut: String,        // à faire, en cours, terminée, annulée
  priorite: String,      // basse, moyenne, haute, critique
  categorie: String,     // perso, travail, projet
  sousTaches: [{
    titre: String,
    statut: String,
    echeance: Date
  }],
  commentaires: [{
    auteur: { nom, prenom, email },
    date: Date,
    contenu: String
  }],
  historiqueModifications: [{
    champModifie: String,
    ancienneValeur: Mixed,
    nouvelleValeur: Mixed,
    date: Date
  }]
}
```

## 🔌 API REST

### Tâches
```
GET    /tasks              # Liste des tâches
GET    /tasks/:id         # Détails d'une tâche
POST   /tasks             # Création
PUT    /tasks/:id         # Modification
DELETE /tasks/:id         # Suppression
```

### Sous-tâches & Commentaires
```
POST   /tasks/:id/subtasks           # Ajouter une sous-tâche
PUT    /tasks/:id/subtasks/:id       # Modifier une sous-tâche
DELETE /tasks/:id/subtasks/:id       # Supprimer une sous-tâche
POST   /tasks/:id/comments           # Ajouter un commentaire
DELETE /tasks/:id/comments/:id       # Supprimer un commentaire
```

## 🔍 Filtres & Recherche

| Paramètre | Description | Exemple |
|-----------|-------------|---------|
| `statut` | Filtre par statut | `/tasks?statut=à faire` |
| `priorite` | Filtre par priorité | `/tasks?priorite=haute` |
| `categorie` | Filtre par catégorie | `/tasks?categorie=perso` |
| `q` | Recherche textuelle | `/tasks?q=rapport` |
| `avant/apres` | Filtre par date | `/tasks?avant=2024-12-31` |

## 📱 Interface Utilisateur

- Design moderne et épuré
- Navigation intuitive
- Filtres rapides et efficaces
- Visualisation claire des priorités
- Gestion simplifiée des sous-tâches
- Système de commentaires intégré

## 🔒 Sécurité

- Validation des données
- Protection contre les injections
- Gestion des erreurs
- Historique des modifications

## 📦 Prérequis

- Node.js ≥ v14
- MongoDB ≥ v4.4
- Navigateur moderne
