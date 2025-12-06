# 📅 Calendrier des Évaluations - KIS

## 🎓 Kawthar International School - Programme PEI/DP

Application web moderne pour gérer le calendrier des évaluations scolaires pour les classes PEI (1-5) et DP (1-2).

---

## ✨ Fonctionnalités

### 📊 **Interface Multi-Vues**
- **Vue Générale**: Visualiser toutes les matières ensemble
- **Vues par Matière**: 8 onglets individuels pour chaque matière
  - 🇫🇷 Français LL
  - 🇬🇧 Anglais AL
  - 📐 Mathématiques
  - 🔬 Sciences
  - 🌍 Individus et Sociétés (IS)
  - 🎨 Arts
  - 💡 Design

### 📅 **Calendrier Complet**
- **42 Semaines** de l'année scolaire 2025-2026
- **Types de périodes:**
  - 🗓️ Orientation
  - 🏖️ Vacances (incluant Eid-ul-Fitr et Eid-ul-Adha)
  - 📝 Examens finaux

### ⚙️ **Gestion des Évaluations**
- ✏️ Ajouter des évaluations par semaine
- 🗑️ Supprimer des évaluations avec confirmation
- 📑 Saisie: Matière, Unité/Thème, Critère (A, B, C, D)
- 🎓 Sélection de classe (PEI1-5, DP1-2)

### 📦 **Export Professionnel**
- **ZIP**: Génération d'un fichier par matière dans une archive ZIP
- **Par Matière**: Export de la matière sélectionnée
- **Complet**: Toutes les matières en un seul document
- **Format**: Documents HTML stylisés prêts pour impression

### 🎨 **Design Ultra-Moderne**
- **Header IB Professionnel**: Gradient bleu IB avec logo animé
- **Animations CSS3**: Transitions fluides et effets hover
- **Couleurs par Matière**: Gradients uniques pour chaque matière
- **Responsive**: Adapté desktop, tablette, mobile
- **Toast Notifications**: Feedback visuel pour toutes les actions

---

## 🚀 Déploiement

### **Vercel** (Recommandé)

1. **Importer le projet sur Vercel:**
   ```bash
   vercel import
   ```

2. **Configurer les variables d'environnement:**
   - Aller dans: **Settings → Environment Variables**
   - Ajouter: `MONGODB_URI` avec votre URL MongoDB Atlas

3. **Déployer:**
   ```bash
   vercel --prod
   ```

### **Local**

1. **Installer les dépendances:**
   ```bash
   npm install
   ```

2. **Créer un fichier `.env`:**
   ```
   MONGODB_URI=mongodb+srv://username:password@cluster.mongodb.net/kis-calendrier
   PORT=3000
   ```

3. **Lancer le serveur:**
   ```bash
   npm start
   ```

4. **Accéder à l'application:**
   ```
   http://localhost:3000
   ```

---

## 🛠️ Technologies

### **Frontend**
- HTML5
- CSS3 (Variables, Animations, Grid, Flexbox)
- JavaScript Vanilla (ES6+)
- JSZip (Génération ZIP)

### **Backend**
- Node.js
- Express.js
- MongoDB avec Mongoose
- RESTful API

### **Déploiement**
- Vercel (Serverless)
- MongoDB Atlas (Database Cloud)

---

## 📂 Structure du Projet

```
KIS-Calendrier-Evaluations/
├── public/
│   ├── index.html      # Structure HTML
│   ├── style.css       # Styles et animations
│   └── script.js       # Logique frontend
├── index.js            # Backend Express + API
├── package.json        # Dépendances
├── vercel.json         # Configuration Vercel
└── README.md           # Documentation
```

---

## 🎨 Palette de Couleurs

| Matière | Couleur Principale | Gradient |
|---------|-------------------|----------|
| Français LL | Rose | #FFE5F0 → #FFD0E5 |
| Anglais AL | Bleu | #E0F0FF → #C0E0FF |
| Mathématiques | Violet | #F0E5FF → #E0D0FF |
| Sciences | Vert | #D0FFE0 → #B0FFD0 |
| IS | Orange | #FFE5C0 → #FFD0A0 |
| Arts | Rose Vif | #FFE0F0 → #FFD0E8 |
| Design | Cyan | #D0F0FF → #B0E0FF |

---

## 📡 API Endpoints

### **POST** `/api/evaluations`
Ajouter une nouvelle évaluation

**Body:**
```json
{
  "classe": "PEI1",
  "semaine": "S2",
  "matiere": "Mathématiques",
  "unite": "Algèbre",
  "critere": "A"
}
```

### **GET** `/api/evaluations?classe=PEI1`
Récupérer toutes les évaluations d'une classe

### **DELETE** `/api/evaluations/:id`
Supprimer une évaluation par ID

---

## 🔧 Configuration MongoDB

1. **Créer un compte MongoDB Atlas**: https://www.mongodb.com/cloud/atlas
2. **Créer un cluster gratuit**
3. **Créer un utilisateur database**
4. **Whitelist IP**: `0.0.0.0/0` (pour Vercel)
5. **Copier la connection string**
6. **Ajouter dans Vercel Environment Variables**

---

## 📝 Licence

Ce projet est développé pour Kawthar International School.

---

## 👨‍💻 Développement

**Version:** 1.0.0  
**Dernière mise à jour:** Décembre 2024  
**Année scolaire:** 2025-2026
