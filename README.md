# 🧠 Doctor Mind
### Plateforme Intelligente d'Aide au Diagnostic Médical

> **Projet de Fin d'Études — PROJET START UP**  
> Université de Belhadj Bouchaib — Aïn Témouchent, Algérie  
> Année universitaire 2024–2025

---

## 📌 Présentation du projet

**Doctor Mind** est une plateforme web médicale basée sur l'Intelligence Artificielle, conçue pour assister les médecins dans l'analyse de signaux biomédicaux et le diagnostic de pathologies. Elle intègre plusieurs modèles de deep learning entraînés sur des données réelles, accessibles via une interface web moderne et intuitive.

Le projet se compose de **trois modules complémentaires** :

| Module | Technologie | Description |
|--------|-------------|-------------|
| 🌐 **Application Web** | React 19 + Firebase | Interface médecin/patient avec authentification |
| 🤖 **Serveur IA** | Python + Flask | API REST exposant les modèles de deep learning |
| 🏠 **Landing Page** | HTML/CSS/JS | Site de présentation public du projet |

---

## 🩺 Fonctionnalités médicales

### 🫀 Analyse ECG (Électrocardiogramme)
- Modèle CNN entraîné sur signaux ECG réels
- Détection de pathologies cardiaques
- Modèle embarqué côté client via **TensorFlow.js**

### 🧲 Analyse IRM Cérébrale
- Modèle de classification de tumeurs cérébrales
- Basé sur **model_brain_tumor15(irm).h5**
- Précision validée sur dataset public

### 🔊 Analyse PCG (Phonocardiogramme)
- Classification de sons cardiaques anormaux
- Modèle **optimized_pcg_cnn1.h5**

### 🩹 Dermatologie
- Analyse d'images de lésions cutanées
- Modèle TensorFlow.js + serveur Python

### 🤒 Diagnostic par Symptômes
- Moteur de diagnostic basé sur **LightGBM**
- Base de données de 300+ symptômes

### 👤 Gestion des rôles
- Interface **Médecin** : tableau de bord complet, accès à tous les modules
- Interface **Patient** : saisie des symptômes, consultation des résultats

---

## 🏗️ Architecture du système

```
┌─────────────────────────────────────────────────────┐
│                   DOCTOR MIND                        │
│                                                      │
│  ┌──────────────┐    ┌──────────────────────────┐   │
│  │  Landing     │    │   React App (Front-end)   │   │
│  │  Page        │    │   React 19 + Bootstrap    │   │
│  │  HTML/CSS    │    │   Firebase Auth + Firestore│  │
│  └──────────────┘    └──────────┬───────────────┘   │
│                                 │ API REST           │
│                      ┌──────────▼───────────────┐   │
│                      │   AI Server (Back-end)    │   │
│                      │   Python + Flask          │   │
│                      │   Modèles: CNN, LGBM      │   │
│                      └──────────────────────────┘   │
│                                 │                    │
│                      ┌──────────▼───────────────┐   │
│                      │   Firebase (Cloud)        │   │
│                      │   Auth + Firestore DB     │   │
│                      └──────────────────────────┘   │
└─────────────────────────────────────────────────────┘
```

---

## 🛠️ Technologies utilisées

### Frontend
- React 19, React Router v7
- Firebase (Authentication + Firestore)
- TensorFlow.js (modèle ECG embarqué)
- Bootstrap 5, Framer Motion, Font Awesome
- ApexCharts, Recharts
- jsPDF, html2canvas, XLSX (exports)

### Backend (AI Server)
- Python 3.10+, Flask
- TensorFlow / Keras (modèles `.h5`)
- LightGBM (modèles `.pkl`)
- scikit-learn, pandas, numpy
- Pillow (traitement d'images)

---

## 📁 Structure du dépôt

```
-doctor-mind/
│
├── 📁 doctormind_v2/          ← Application React principale
│   ├── src/
│   │   ├── pages/             ← ECG, IRM, PCG, Dermatologie, Symptômes
│   │   ├── styles/
│   │   ├── utils/
│   │   ├── App.js
│   │   └── firebase.js
│   ├── public/
│   │   └── model/ecg/         ← Modèle ECG TensorFlow.js
│   ├── .env.example
│   └── package.json
│
├── 📁 AI_server/              ← Serveur Python + API IA
│   ├── server.py
│   ├── requirements.txt
│   ├── liste_symptomes.txt
│   ├── MODEL_USAGE_SUMMARY.md
│   └── [modèles sur Google Drive → voir lien ci-dessous]
│
├── 📁 landing_page/           ← Site de présentation
│   ├── index.html
│   ├── about-elements.html
│   ├── contact.html
│   └── assets/
│
└── 📄 INSTALLATION.md         ← Guide de démarrage complet
```

---

## 🤖 Modèles IA — Téléchargement

> Les modèles entraînés (`.h5` et `.pkl`) sont hébergés sur Google Drive
> en raison de leur taille totale (~2.3 Go).

### 📥 [Télécharger les modèles IA — Google Drive](https://drive.google.com/LIEN_A_COMPLETER)

| Fichier | Description |
|---------|-------------|
| `ecg_cnn_model4.h5` | Modèle CNN — Analyse ECG |
| `model_brain_tumor15(irm).h5` | Modèle CNN — Tumeurs IRM |
| `optimized_pcg_cnn1.h5` | Modèle CNN — Sons cardiaques PCG |
| `lgbm_disease_model.pkl` | Modèle LGBM — Diagnostic symptômes |
| `model_3_lgbm.pkl` | Modèle LGBM v3 — Symptômes |
| `label_encoder.pkl` | Encodeur de labels |
| `tfjs_model(dermatologie)/` | Modèle Dermatologie TF.js |

> ⚠️ Placer tous les fichiers dans le dossier `AI_server/` après téléchargement.

---

## 🚀 Démarrage rapide

Voir **[INSTALLATION.md](./INSTALLATION.md)** pour le guide complet.

```bash
# 1. Cloner le projet
git clone https://github.com/MAN198/-doctor-mind.git
cd -doctor-mind

# 2. Lancer le serveur IA
cd AI_server
pip install -r requirements.txt
python server.py

# 3. Lancer l'application React (nouveau terminal)
cd ../doctormind_v2
npm install
npm start
```

---

## 👩‍💻 Auteure

**Sekkal mansouria**  
MCA 
Université de Belhadj Bouchaib — Aïn Témouchent, Algérie

---


---

## 📄 Droits

Ce projet est réalisé dans un cadre académique. Tous droits réservés.  
© 2025 — Université de Belhadj Bouchaib, Aïn Témouchent.
