# 🚀 Guide de Déploiement Vercel

## ✅ Repository GitHub Prêt

**Repository:** https://github.com/medch24/KIS-Calendrier-Evaluations

Le code est maintenant sur GitHub et prêt pour le déploiement!

---

## 📋 DÉPLOIEMENT SUR VERCEL (2 méthodes)

### **Méthode 1: Interface Web Vercel (Recommandé)**

#### **Étape 1: Importer le Projet**
1. Allez sur: **https://vercel.com/new**
2. Connectez-vous avec votre compte GitHub
3. Cliquez sur: **Import Git Repository**
4. Recherchez: `KIS-Calendrier-Evaluations`
5. Cliquez sur: **Import**

#### **Étape 2: Configuration du Projet**
Dans la page de configuration:

- **Project Name:** `kis-calendrier` (ou laissez par défaut)
- **Framework Preset:** Sélectionnez **"Other"**
- **Root Directory:** `.` (par défaut)
- **Build Command:** Laisser vide
- **Output Directory:** `public`
- **Install Command:** `npm install`

#### **Étape 3: Variables d'Environnement**
Cliquez sur **"Environment Variables"** et ajoutez:

| Name | Value |
|------|-------|
| `MONGODB_URI` | `mongodb+srv://username:password@cluster.mongodb.net/kis-calendrier?retryWrites=true&w=majority` |

⚠️ **Important:** Remplacez `username`, `password`, et `cluster` par vos vraies informations MongoDB Atlas.

#### **Étape 4: Déployer**
1. Cliquez sur: **Deploy**
2. Attendez 1-2 minutes
3. Votre site sera accessible sur: `https://kis-calendrier.vercel.app`

---

### **Méthode 2: Via CLI Vercel**

```bash
# Installer Vercel CLI globalement
npm install -g vercel

# Se connecter à Vercel
vercel login

# Aller dans le projet
cd /home/user/KIS-Calendrier

# Déployer (mode développement)
vercel

# Suivre les instructions:
# ? Set up and deploy "~/KIS-Calendrier"? [Y/n] Y
# ? Which scope do you want to deploy to? [Votre compte]
# ? Link to existing project? [N/y] N
# ? What's your project's name? kis-calendrier
# ? In which directory is your code located? ./

# Une fois déployé, aller sur le dashboard Vercel
# Ajouter la variable MONGODB_URI dans Settings → Environment Variables

# Déployer en production
vercel --prod
```

---

## 🗄️ CONFIGURATION MONGODB ATLAS

### **Étape 1: Créer un Compte**
1. Allez sur: https://www.mongodb.com/cloud/atlas/register
2. Créez un compte gratuit

### **Étape 2: Créer un Cluster**
1. Cliquez sur: **Build a Database**
2. Choisissez: **M0 Free** (gratuit)
3. Sélectionnez une région (ex: AWS / Europe-West)
4. Nom du cluster: `Cluster0` (par défaut)
5. Cliquez sur: **Create**

### **Étape 3: Créer un Utilisateur Database**
1. Dans **Database Access**, cliquez: **Add New Database User**
2. Choisissez: **Password** authentication
3. Username: `kisadmin`
4. Password: **Générer un mot de passe fort** (notez-le!)
5. Database User Privileges: **Read and write to any database**
6. Cliquez sur: **Add User**

### **Étape 4: Whitelist IP pour Vercel**
1. Dans **Network Access**, cliquez: **Add IP Address**
2. Cliquez sur: **Allow Access from Anywhere**
3. Cela ajoutera: `0.0.0.0/0`
4. Cliquez sur: **Confirm**

### **Étape 5: Obtenir la Connection String**
1. Retournez dans **Database**
2. Cliquez sur: **Connect** pour votre cluster
3. Choisissez: **Connect your application**
4. Driver: **Node.js** / Version: **5.5 or later**
5. Copiez la connection string:
   ```
   mongodb+srv://kisadmin:<password>@cluster0.xxxxx.mongodb.net/?retryWrites=true&w=majority
   ```
6. Remplacez `<password>` par votre vrai mot de passe
7. Ajoutez le nom de la database à la fin: `/kis-calendrier`

**Exemple final:**
```
mongodb+srv://kisadmin:MonMotDePasseSecurise123@cluster0.ab1cd.mongodb.net/kis-calendrier?retryWrites=true&w=majority
```

### **Étape 6: Ajouter dans Vercel**
1. Dans votre projet Vercel: **Settings** → **Environment Variables**
2. Cliquez: **Add New**
3. Key: `MONGODB_URI`
4. Value: Collez votre connection string MongoDB
5. Environment: Cochez **Production**, **Preview**, **Development**
6. Cliquez: **Save**
7. Redéployez: **Deployments** → **Redeploy**

---

## 🧪 TESTER LE DÉPLOIEMENT

Une fois déployé:

1. **Ouvrir le site:** Cliquez sur le lien Vercel (ex: `https://kis-calendrier.vercel.app`)

2. **Vérifier le design:**
   - ✅ Header bleu IB avec logo
   - ✅ 9 onglets de navigation
   - ✅ Calendrier avec 42 semaines
   - ✅ Formulaires d'ajout par semaine

3. **Tester les fonctionnalités:**
   - Changer la classe (PEI1-5, DP1-2)
   - Ajouter une évaluation
   - Supprimer une évaluation
   - Changer d'onglet matière
   - Exporter (ZIP, Matière, Complet)

4. **Vérifier MongoDB:**
   - Dans MongoDB Atlas → Database → Browse Collections
   - Vous devriez voir: `kis-calendrier` → `evaluations`

---

## 🔧 DÉPANNAGE

### **Erreur 500 ou "Cannot connect to MongoDB"**
- Vérifiez que `MONGODB_URI` est bien configurée dans Vercel
- Vérifiez que `0.0.0.0/0` est whitelisté dans MongoDB Network Access
- Vérifiez que le mot de passe ne contient pas de caractères spéciaux (sinon, URL-encodez)

### **Site ne s'affiche pas correctement**
- Videz le cache du navigateur (Ctrl+Shift+R)
- Vérifiez les logs dans Vercel Dashboard → Deployments → Logs

### **Fonctions ne marchent pas**
- Ouvrez la console du navigateur (F12)
- Vérifiez les erreurs JavaScript
- Vérifiez que JSZip est bien chargé

---

## 📊 STATISTIQUES DU PROJET

| Métrique | Valeur |
|----------|--------|
| **Fichiers** | 9 |
| **Lignes de code** | 1,614 |
| **Taille totale** | ~45KB |
| **HTML** | 3.9KB |
| **CSS** | 12KB |
| **JavaScript** | 19KB |
| **Backend** | 3.7KB |

---

## 🎯 URLS IMPORTANTES

- **GitHub Repository:** https://github.com/medch24/KIS-Calendrier-Evaluations
- **Vercel Dashboard:** https://vercel.com/dashboard
- **MongoDB Atlas:** https://cloud.mongodb.com/
- **Documentation Vercel:** https://vercel.com/docs

---

## 🎉 FÉLICITATIONS!

Votre application est maintenant:
- ✅ Sur GitHub (version control)
- ✅ Déployée sur Vercel (hosting gratuit)
- ✅ Connectée à MongoDB Atlas (database cloud)
- ✅ Accessible 24/7 avec HTTPS
- ✅ Prête pour la production!

**Bon déploiement! 🚀**
