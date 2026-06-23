# 📦 Guide d'Installation — Doctor Mind

> Ce guide permet au jury/comité d'évaluation de lancer le projet complet en local.

---

## ✅ Prérequis

| Outil | Version minimale | Vérification |
|-------|-----------------|--------------|
| Node.js | 16+ | `node --version` |
| npm | 8+ | `npm --version` |
| Python | 3.9+ | `python --version` |
| pip | dernière version | `pip --version` |
| Git | any | `git --version` |

---

## 📥 Étape 1 — Cloner le projet

```bash
git clone https://github.com/MAN198/-doctor-mind.git
cd -doctor-mind
```

---

## 🤖 Étape 2 — Télécharger les modèles IA

Les modèles sont hébergés sur Google Drive (trop lourds pour GitHub).

1. Ouvrir : **[Google Drive — Modèles Doctor Mind](https://drive.google.com/LIEN_A_COMPLETER)**
2. Télécharger tous les fichiers `.h5`, `.pkl` et le dossier `tfjs_model(dermatologie)/`
3. Les placer dans le dossier `AI_server/`

Structure attendue après téléchargement :
```
AI_server/
├── server.py
├── requirements.txt
├── liste_symptomes.txt
├── ecg_cnn_model4.h5
├── model_brain_tumor15(irm).h5
├── optimized_pcg_cnn1.h5
├── lgbm_disease_model.pkl
├── model_3_lgbm.pkl
├── label_encoder.pkl
├── label_3_encoder.pkl
├── symptoms_3_list.pkl
└── tfjs_model(dermatologie)/
```

---

## 🐍 Étape 3 — Lancer le serveur IA (Python)

```bash
cd AI_server

# Créer un environnement virtuel
python -m venv venv

# Activer l'environnement
# Windows :
venv\Scripts\activate
# Linux/Mac :
source venv/bin/activate

# Installer les dépendances
pip install -r requirements.txt

# Lancer le serveur Flask
python server.py
```

✅ Serveur IA disponible sur : **http://localhost:5000**

---

## ⚛️ Étape 4 — Lancer l'application React

> Ouvrir un **nouveau terminal**

```bash
cd doctormind_v2

# Installer les dépendances
npm install

# Configurer Firebase
cp .env.example .env
# Ouvrir .env et remplir avec les clés Firebase

# Lancer l'application
npm start
```

✅ Application disponible sur : **http://localhost:3000**

---

## 🌐 Étape 5 — Landing Page

Site HTML statique, aucune installation requise.
Ouvrir directement : `landing_page/index.html`

---

## 🔐 Comptes de démonstration

| Rôle | Email | Mot de passe |
|------|-------|--------------|
| Médecin | `demo.doctor@doctormind.dz` | `Demo1234!` |
| Patient | `demo.patient@doctormind.dz` | `Demo1234!` |

---

## 🗺️ Navigation

```
http://localhost:3000/               ← Connexion
http://localhost:3000/register       ← Inscription
http://localhost:3000/dashboard      ← Tableau de bord médecin
                                        ├── ECG
                                        ├── IRM
                                        ├── PCG
                                        ├── Dermatologie
                                        └── Symptômes
http://localhost:3000/patientsymptoms ← Interface patient
```

---

## ❓ Problèmes fréquents

**`npm install` échoue :**
```bash
npm install --legacy-peer-deps
```

**Serveur Python ne démarre pas :**
```bash
pip install --upgrade pip
pip install -r requirements.txt --no-cache-dir
```

**Erreur Firebase :** Vérifier les clés dans le fichier `.env`

---

## 📞 Contact

**Sekkal Soria** — Université de Belhadj Bouchaib, Aïn Témouchent
