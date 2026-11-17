# MediQ

**Système de gestion des patients, des rendez-vous, des traitements et des paiements pour un cabinet médical individuel.**

MediQ est une application web qui centralise la gestion administrative et financière d'un cabinet médical composé d'un seul médecin. Elle est utilisée par la **secrétaire** et le **docteur**.

---

## État du projet

**Phase actuelle : analyse et conception** (dernière mise à jour : 17/11/2026)

### Livrables

| N° | Livrable | État |
|---|---|---|
| 01 | Cahier des charges | ✅ Terminé |
| 02 | Identification des besoins et du périmètre | ✅ Terminé |
| 03 | Diagramme de cas d'utilisation | ⬜ À faire |
| 04 | Diagramme de classes | ⬜ À faire |
| 05 | Diagrammes de séquence | ⬜ À faire |
| 06 | Maquettes des interfaces | ⬜ À faire |
| 07 | Application web MediQ | ⬜ À faire |
| 08 | Base de données | ⬜ À faire |
| 09 | Documentation technique | ⬜ À faire |
| 10 | Guide d'utilisation | ⬜ À faire |

### Modules

| Module | Conception | Développement |
|---|---|---|
| Authentification | ⬜ | ⬜ |
| Tableau de bord | ⬜ | ⬜ |
| Patients | ⬜ | ⬜ |
| Rendez-vous | ⬜ | ⬜ |
| Traitements | ⬜ | ⬜ |
| Consultations | ⬜ | ⬜ |
| Paiements | ⬜ | ⬜ |
| Salle d'attente | ⬜ | ⬜ |
| Utilisateurs | ⬜ | ⬜ |
| Paramètres | ⬜ | ⬜ |

Légende : ✅ terminé · 🔄 en cours · ⬜ à faire

### Prochaines étapes

1. Réaliser le diagramme de cas d'utilisation
2. Réaliser le diagramme de classes
3. Concevoir la base de données (schéma MySQL)
4. Créer les maquettes des interfaces
5. Démarrer le développement du backend puis du frontend

---

## Fonctionnalités (MVP)

- **Authentification** : connexion sécurisée, accès selon le rôle
- **Tableau de bord** : indicateurs clés adaptés au rôle
- **Patients** : dossier administratif, recherche, archivage, historiques
- **Rendez-vous** : planning, statuts, prévention des chevauchements
- **Traitements de longue durée** : suivi administratif et financier
- **Consultations** : enregistrement des visites réellement effectuées
- **Paiements** : paiements échelonnés, total payé et reste à payer calculés automatiquement
- **Salle d'attente** : file d'attente, numéros de passage, écran public sans données personnelles
- **Utilisateurs** : comptes, rôles et autorisations
- **Paramètres** : configuration du cabinet

### Hors périmètre

Diagnostic et prescription médicale, dossier médical électronique détaillé, prise de rendez-vous en ligne par les patients, notifications SMS/e-mail, application mobile, téléconsultation, gestion des stocks, assurances et remboursements, comptabilité avancée, multi-cabinets.

---

## Technologies

| Couche | Technologie |
|---|---|
| Frontend | React.js |
| Backend | Java / Spring Boot |
| Base de données | MySQL |
| Architecture | Client-serveur / API REST |
| Modélisation | UML |
| Versioning | Git / GitHub |

---

## Structure du projet

```
MediQ/
├── docs/          # Documentation et livrables (cahier des charges, UML, maquettes...)
├── database/      # Scripts SQL (schema.sql, data.sql)
├── backend/       # API REST Spring Boot
├── frontend/      # Interface React.js
├── README.md
└── .gitignore
```

---

## Prérequis

> ⚠️ Les dossiers `backend/`, `frontend/` et `database/` seront créés lors de la phase de développement. Les instructions ci-dessous s'appliqueront à ce moment-là.

- Java 17 ou supérieur
- Maven
- Node.js 18 ou supérieur et npm
- MySQL 8 ou supérieur
- Git

---

## Installation et lancement

### 1. Cloner le projet

```bash
git clone https://github.com/nora-elayane/MediQ.git
cd MediQ
```

### 2. Base de données

```bash
mysql -u root -p -e "CREATE DATABASE mediq CHARACTER SET utf8mb4;"
mysql -u root -p mediq < database/schema.sql
mysql -u root -p mediq < database/data.sql   # données de test (optionnel)
```

### 3. Backend

Configurer `backend/src/main/resources/application.properties` :

```properties
spring.datasource.url=jdbc:mysql://localhost:3306/mediq
spring.datasource.username=root
spring.datasource.password=VOTRE_MOT_DE_PASSE
```

Lancer l'API :

```bash
cd backend
mvn spring-boot:run
```

L'API est disponible sur `http://localhost:8080`.

### 4. Frontend

```bash
cd frontend
npm install
npm start
```

L'application est disponible sur `http://localhost:3000`.

---

## Règles de gestion principales

- Deux rendez-vous ne peuvent pas se chevaucher pour le médecin.
- Une consultation correspond à une visite effectivement réalisée (différente d'un rendez-vous planifié).
- Un traitement peut être réglé en plusieurs paiements.
- Le montant d'un paiement est strictement positif et le total des paiements ne dépasse pas le coût du traitement.
- Reste à payer = coût total du traitement − total payé.
- Un utilisateur désactivé ne peut pas accéder au système.
- La numérotation de la salle d'attente est réinitialisée chaque jour.

La liste complète (RG01 à RG20) se trouve dans `docs/02_Identification_des_besoins_et_perimetre.md`.

---

## Documentation

| N° | Document |
|---|---|
| 01 | Cahier des charges |
| 02 | Identification des besoins et du périmètre |
| 03 | Diagramme de cas d'utilisation |
| 04 | Diagramme de classes |
| 05 | Diagrammes de séquence |
| 06 | Maquettes des interfaces |
| 09 | Documentation technique |
| 10 | Guide d'utilisation |

---

## Sécurité et données personnelles

- Authentification obligatoire et autorisations selon les rôles
- Mots de passe stockés de façon sécurisée (hachage)
- Prise en compte de la loi marocaine **09-08** sur la protection des données personnelles

---

## Auteur

**Nora** — [github.com/nora-elayane](https://github.com/nora-elayane)
