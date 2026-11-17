# Identification des besoins et du périmètre
## Projet MediQ
**Système de gestion des patients, des rendez-vous, des traitements et des paiements**

| Élément | Détail |
|---|---|
| Document | 02 – Identification des besoins et du périmètre |
| Projet | MediQ |
| Document de référence | Cahier des charges MediQ |
| Version | 1.0 |

---

## 1. Introduction

### 1.1. Objet du document

Ce document identifie et structure les besoins du projet MediQ, définit précisément le périmètre du MVP et clarifie ce qui est exclu. Il constitue la base des livrables suivants : diagrammes UML (cas d'utilisation, classes, séquence), maquettes, base de données et développement.

### 1.2. Résumé du projet

MediQ est une application web destinée à un cabinet médical individuel (un seul médecin). Elle centralise la gestion administrative et financière : patients, rendez-vous, traitements de longue durée, consultations réalisées, paiements échelonnés et salle d'attente.

### 1.3. Problématique

Comment développer une application web permettant de centraliser et d'améliorer la gestion administrative et financière d'un cabinet médical, notamment les patients, les rendez-vous, les traitements et les paiements ?

---

## 2. Analyse du contexte et des problèmes

| Problème identifié | Besoin correspondant |
|---|---|
| Difficulté à retrouver les informations des patients | Dossier patient centralisé avec recherche rapide |
| Manque d'organisation des rendez-vous | Planning des rendez-vous avec statuts et anti-chevauchement |
| Difficulté à suivre les traitements de longue durée | Module de traitements rattachés au patient |
| Manque de visibilité sur les consultations réalisées | Historique des consultations par traitement et par patient |
| Difficulté à suivre les paiements échelonnés | Paiements multiples par traitement |
| Absence de vision claire du payé / reste à payer | Calcul automatique du total payé et du reste à payer |
| Difficulté à organiser la salle d'attente | File d'attente avec numéros de passage et écran public |

---

## 3. Objectifs

### 3.1. Objectif général

Améliorer l'organisation administrative et financière d'un cabinet médical individuel grâce à une application web centralisée.

### 3.2. Objectifs spécifiques

| Réf. | Objectif |
|---|---|
| OBJ01 | Centraliser les informations des patients |
| OBJ02 | Faciliter la gestion des dossiers administratifs |
| OBJ03 | Organiser les rendez-vous médicaux |
| OBJ04 | Assurer le suivi des traitements de longue durée |
| OBJ05 | Enregistrer les consultations réalisées |
| OBJ06 | Gérer les paiements partiels et complets |
| OBJ07 | Calculer automatiquement les montants payés et les restes à payer |
| OBJ08 | Organiser la file d'attente |
| OBJ09 | Gérer les utilisateurs et leurs autorisations |
| OBJ10 | Fournir un tableau de bord avec les informations essentielles |

---

## 4. Identification des parties prenantes et des acteurs

### 4.1. Client cible

- Établissement : cabinet médical individuel.
- Organisation : un seul médecin.
- Utilisateurs de l'application : secrétaire et docteur.

### 4.2. Acteurs du système

| Acteur | Rôle | Responsabilités principales |
|---|---|---|
| **Secrétaire** | Gestion administrative du cabinet | Patients, rendez-vous, traitements, consultations, paiements, historiques financiers, salle d'attente |
| **Docteur** | Consultation et suivi de l'activité | Consultation des dossiers, des rendez-vous du jour, des traitements, des consultations, de la salle d'attente et des informations financières ; gestion des utilisateurs et des paramètres selon ses autorisations |

### 4.3. Matrice acteurs / fonctionnalités

Légende : **G** = gérer (créer, modifier, supprimer ou archiver), **C** = consulter, **—** = non prévu au cahier des charges.

| Fonctionnalité | Secrétaire | Docteur |
|---|:---:|:---:|
| Authentification | G | G |
| Tableau de bord | C | C |
| Patients | G | C |
| Rendez-vous | G | C |
| Traitements | G | C |
| Consultations | G | C |
| Paiements | G | C (informations financières) |
| Salle d'attente | G | C |
| Utilisateurs | — | G (selon autorisations) |
| Paramètres du cabinet | — | G (selon autorisations) |

> Les droits exacts de chaque rôle restent paramétrables via la gestion des autorisations (BF-USR).

---

## 5. Identification des besoins fonctionnels

Chaque besoin est identifié par une référence unique pour permettre la traçabilité vers les cas d'utilisation, les maquettes et les tests.

### 5.1. Authentification (BF-AUT)

| Réf. | Besoin |
|---|---|
| BF-AUT-01 | Se connecter avec identifiant et mot de passe |
| BF-AUT-02 | Vérifier les informations de connexion |
| BF-AUT-03 | Donner l'accès selon le rôle de l'utilisateur |
| BF-AUT-04 | Se déconnecter de façon sécurisée |
| BF-AUT-05 | Protéger les pages contre les accès non autorisés |

### 5.2. Tableau de bord (BF-DSH)

| Réf. | Besoin |
|---|---|
| BF-DSH-01 | Afficher un tableau de bord adapté au rôle de l'utilisateur |
| BF-DSH-02 | Afficher le nombre total de patients |
| BF-DSH-03 | Afficher le nombre de rendez-vous du jour |
| BF-DSH-04 | Afficher le nombre de consultations réalisées |
| BF-DSH-05 | Afficher le nombre de patients en attente |
| BF-DSH-06 | Afficher le nombre de traitements en cours |
| BF-DSH-07 | Afficher le total des paiements enregistrés |
| BF-DSH-08 | Afficher le total des montants restant à payer |

### 5.3. Gestion des patients (BF-PAT)

| Réf. | Besoin |
|---|---|
| BF-PAT-01 | Ajouter un patient |
| BF-PAT-02 | Consulter la liste des patients |
| BF-PAT-03 | Rechercher un patient |
| BF-PAT-04 | Consulter le dossier administratif d'un patient |
| BF-PAT-05 | Modifier les informations d'un patient |
| BF-PAT-06 | Archiver un dossier |
| BF-PAT-07 | Consulter les rendez-vous d'un patient |
| BF-PAT-08 | Consulter les traitements d'un patient |
| BF-PAT-09 | Consulter l'historique des consultations d'un patient |
| BF-PAT-10 | Consulter l'historique des paiements d'un patient |

**Données d'un patient :** identifiant unique, nom, prénom, date de naissance, sexe, téléphone, adresse, date de création du dossier.

### 5.4. Gestion des rendez-vous (BF-RDV)

| Réf. | Besoin |
|---|---|
| BF-RDV-01 | Ajouter un rendez-vous |
| BF-RDV-02 | Associer le rendez-vous à un patient |
| BF-RDV-03 | Associer éventuellement le rendez-vous à un traitement |
| BF-RDV-04 | Consulter les rendez-vous du jour |
| BF-RDV-05 | Consulter les rendez-vous par date |
| BF-RDV-06 | Modifier un rendez-vous |
| BF-RDV-07 | Annuler un rendez-vous |
| BF-RDV-08 | Suivre le statut d'un rendez-vous |
| BF-RDV-09 | Organiser les rendez-vous par ordre chronologique |
| BF-RDV-10 | Empêcher les chevauchements de rendez-vous pour le même médecin |

**Données d'un rendez-vous :** identifiant, patient concerné, traitement associé (facultatif), date, heure, motif administratif, statut.

**Statuts :** En attente, Confirmé, En cours, Terminé, Annulé, Absent.

### 5.5. Gestion des traitements (BF-TRT)

| Réf. | Besoin |
|---|---|
| BF-TRT-01 | Créer un traitement pour un patient |
| BF-TRT-02 | Consulter les traitements d'un patient |
| BF-TRT-03 | Modifier les informations d'un traitement |
| BF-TRT-04 | Consulter le coût total d'un traitement |
| BF-TRT-05 | Consulter les consultations associées |
| BF-TRT-06 | Consulter les paiements associés |
| BF-TRT-07 | Suivre le statut du traitement |
| BF-TRT-08 | Consulter le montant payé et le reste à payer |

**Données d'un traitement :** identifiant, patient associé, nom du traitement, description administrative, coût total, date de début, date de fin éventuelle, statut.

**Statuts :** En cours, Terminé, Suspendu, Annulé.

> Le système assure uniquement le suivi **administratif et financier** des traitements. Il ne gère ni diagnostics, ni prescriptions, ni actes médicaux détaillés.

### 5.6. Gestion des consultations (BF-CSL)

| Réf. | Besoin |
|---|---|
| BF-CSL-01 | Enregistrer une consultation réellement effectuée |
| BF-CSL-02 | Associer la consultation à un traitement |
| BF-CSL-03 | Associer éventuellement la consultation au rendez-vous correspondant |
| BF-CSL-04 | Enregistrer la date et l'heure |
| BF-CSL-05 | Consulter l'historique des consultations d'un traitement |
| BF-CSL-06 | Consulter l'historique des consultations d'un patient |

**Données d'une consultation :** identifiant, traitement associé, rendez-vous associé (facultatif), date, heure, observation administrative éventuelle.

> Une consultation représente une visite effectivement réalisée ; elle ne doit pas être confondue avec un rendez-vous planifié.

### 5.7. Gestion des paiements (BF-PAY)

| Réf. | Besoin |
|---|---|
| BF-PAY-01 | Enregistrer un paiement |
| BF-PAY-02 | Associer un paiement à un traitement |
| BF-PAY-03 | Enregistrer le montant versé |
| BF-PAY-04 | Enregistrer la date du paiement |
| BF-PAY-05 | Enregistrer le mode de paiement |
| BF-PAY-06 | Accepter plusieurs paiements pour un même traitement |
| BF-PAY-07 | Consulter l'historique des paiements |
| BF-PAY-08 | Calculer le total payé |
| BF-PAY-09 | Calculer le reste à payer |
| BF-PAY-10 | Consulter la situation financière de chaque traitement |

**Données d'un paiement :** identifiant, traitement associé, montant, date du paiement, mode de paiement.

**Modes de paiement :** espèces, carte bancaire, autre mode à définir.

**Calcul financier :**
- Total payé = somme des paiements enregistrés.
- Reste à payer = coût total du traitement − total payé.

### 5.8. Gestion de la salle d'attente (BF-ATT)

| Réf. | Besoin |
|---|---|
| BF-ATT-01 | Afficher les patients présents au cabinet |
| BF-ATT-02 | Organiser la file d'attente |
| BF-ATT-03 | Attribuer un numéro de passage |
| BF-ATT-04 | Afficher le numéro du patient actuellement appelé |
| BF-ATT-05 | Appeler le patient suivant |
| BF-ATT-06 | Mettre à jour le statut d'un patient en attente |
| BF-ATT-07 | Afficher les patients encore en attente |
| BF-ATT-08 | Afficher sur l'écran public uniquement les numéros de passage, sans données personnelles |

### 5.9. Gestion des utilisateurs (BF-USR)

| Réf. | Besoin |
|---|---|
| BF-USR-01 | Ajouter un compte |
| BF-USR-02 | Consulter les utilisateurs |
| BF-USR-03 | Modifier les informations d'un compte |
| BF-USR-04 | Activer ou désactiver un compte |
| BF-USR-05 | Attribuer un rôle |
| BF-USR-06 | Gérer les autorisations |

### 5.10. Paramètres (BF-PRM)

| Réf. | Besoin |
|---|---|
| BF-PRM-01 | Configurer le nom du cabinet |
| BF-PRM-02 | Configurer les coordonnées du cabinet |
| BF-PRM-03 | Configurer les informations du médecin |
| BF-PRM-04 | Configurer la durée standard des rendez-vous |
| BF-PRM-05 | Configurer les paramètres de fonctionnement |
| BF-PRM-06 | Configurer les paramètres de la salle d'attente |

---

## 6. Identification des besoins non fonctionnels

| Catégorie | Réf. | Besoin |
|---|---|---|
| **Sécurité** | BNF-SEC-01 | Authentification obligatoire |
| | BNF-SEC-02 | Gestion des autorisations selon les rôles |
| | BNF-SEC-03 | Stockage sécurisé des mots de passe |
| | BNF-SEC-04 | Protection des données personnelles |
| | BNF-SEC-05 | Protection contre les accès non autorisés |
| **Ergonomie** | BNF-ERG-01 | Interface intuitive et navigation simple |
| | BNF-ERG-02 | Organisation claire des informations |
| | BNF-ERG-03 | Adaptation aux écrans d'ordinateur et de tablette |
| **Performance** | BNF-PER-01 | Temps de réponse raisonnable |
| | BNF-PER-02 | Recherche rapide des patients |
| | BNF-PER-03 | Chargement efficace des tableaux |
| | BNF-PER-04 | Gestion correcte des opérations simultanées |
| **Fiabilité** | BNF-FIA-01 | Validation des données avant enregistrement |
| | BNF-FIA-02 | Prévention des conflits de rendez-vous |
| | BNF-FIA-03 | Cohérence des paiements |
| | BNF-FIA-04 | Prévention des paiements dépassant le montant restant |
| | BNF-FIA-05 | Conservation de l'historique financier |
| **Maintenabilité** | BNF-MNT-01 | Code organisé |
| | BNF-MNT-02 | Séparation des responsabilités |
| | BNF-MNT-03 | Réutilisation des composants |
| | BNF-MNT-04 | Architecture évolutive |

---

## 7. Règles de gestion

| Référence | Règle de gestion |
|---|---|
| RG01 | Chaque patient possède un identifiant unique. |
| RG02 | Un patient peut avoir plusieurs traitements. |
| RG03 | Chaque traitement appartient à un seul patient. |
| RG04 | Un traitement peut comporter plusieurs consultations. |
| RG05 | Chaque consultation appartient à un seul traitement. |
| RG06 | Un patient peut avoir plusieurs rendez-vous. |
| RG07 | Un rendez-vous doit être associé à un patient existant. |
| RG08 | Un rendez-vous peut être associé à un traitement. |
| RG09 | Deux rendez-vous ne peuvent pas se chevaucher pour le médecin. |
| RG10 | Une consultation correspond à une visite effectivement réalisée. |
| RG11 | Un traitement peut être réglé en plusieurs paiements. |
| RG12 | Chaque paiement doit être associé à un traitement existant. |
| RG13 | Le montant d'un paiement doit être strictement positif. |
| RG14 | Le total des paiements ne doit pas dépasser le coût total du traitement. |
| RG15 | Le reste à payer est calculé à partir des paiements enregistrés. |
| RG16 | Les paiements enregistrés doivent être conservés dans l'historique. |
| RG17 | Chaque utilisateur possède un rôle et des autorisations définies. |
| RG18 | Un utilisateur désactivé ne peut pas accéder au système. |
| RG19 | Le numéro d'ordre de la salle d'attente est réinitialisé chaque jour. |
| RG20 | Un traitement terminé ne doit plus recevoir de nouvelles consultations sans réactivation ou correction autorisée. |

### 7.1. Traçabilité règles de gestion → besoins

| Règle | Besoins concernés |
|---|---|
| RG01 | BF-PAT-01 |
| RG02, RG03 | BF-TRT-01, BF-TRT-02 |
| RG04, RG05 | BF-CSL-02, BF-CSL-05 |
| RG06, RG07 | BF-RDV-01, BF-RDV-02, BF-PAT-07 |
| RG08 | BF-RDV-03 |
| RG09 | BF-RDV-10, BNF-FIA-02 |
| RG10 | BF-CSL-01 |
| RG11, RG12 | BF-PAY-02, BF-PAY-06 |
| RG13, RG14 | BF-PAY-03, BNF-FIA-04 |
| RG15 | BF-PAY-09, BF-TRT-08 |
| RG16 | BF-PAY-07, BNF-FIA-05 |
| RG17, RG18 | BF-USR-04, BF-USR-05, BF-USR-06, BF-AUT-03 |
| RG19 | BF-ATT-03 |
| RG20 | BF-CSL-01, BF-TRT-07 |

---

## 8. Périmètre du projet

### 8.1. Périmètre inclus (MVP)

| Module | Description |
|---|---|
| Authentification | Connexion, déconnexion, protection des accès par rôle |
| Tableau de bord | Indicateurs clés adaptés au rôle |
| Patients | Dossier administratif, recherche, archivage, historiques |
| Rendez-vous | Planning, statuts, prévention des chevauchements |
| Traitements de longue durée | Suivi administratif et financier |
| Consultations | Enregistrement des visites réellement effectuées |
| Paiements | Paiements échelonnés, total payé, reste à payer |
| Salle d'attente | File d'attente, numéros de passage, écran public |
| Utilisateurs | Comptes, rôles, autorisations |
| Paramètres du cabinet | Configuration générale |

### 8.2. Périmètre exclu

| Fonctionnalité exclue | Remarque |
|---|---|
| Diagnostic médical | Hors du suivi administratif |
| Prescription médicale | Hors du suivi administratif |
| Dossier médical électronique détaillé | Seule une observation administrative éventuelle est prévue |
| Prise de rendez-vous en ligne par les patients | Les rendez-vous sont saisis par le personnel |
| Notifications automatiques par SMS ou e-mail | Aucun rappel automatique |
| Application mobile | Application web uniquement (ordinateur et tablette) |
| Téléconsultation | Consultations au cabinet uniquement |
| Gestion des stocks médicaux | — |
| Gestion des assurances et remboursements | — |
| Comptabilité avancée | Suivi limité aux paiements des traitements |
| Gestion de plusieurs cabinets | Un seul cabinet, un seul médecin |

### 8.3. Frontières du système

- **Entrées :** saisies de la secrétaire et du docteur (patients, rendez-vous, traitements, consultations, paiements, utilisateurs, paramètres).
- **Sorties :** tableaux de bord, listes, historiques, situation financière, écran public de la salle d'attente.
- **Système externe :** aucun système externe n'est prévu dans le MVP.

---

## 9. Contraintes

### 9.1. Contraintes techniques

- Application accessible via un navigateur web.
- Base de données relationnelle.
- Architecture client-serveur avec communication via API REST.
- Protection des données.

### 9.2. Contraintes fonctionnelles

- Adaptation à un cabinet avec un seul médecin.
- Simplicité d'utilisation.
- Respect des règles de gestion des rendez-vous.
- Suivi financier précis des traitements.

### 9.3. Contraintes réglementaires

Prise en compte de la réglementation marocaine relative à la protection des données personnelles, notamment la **loi 09-08** et les obligations applicables aux traitements concernés.

### 9.4. Technologies envisagées

| Couche | Technologie |
|---|---|
| Frontend | React.js |
| Backend | Java / Spring Boot |
| Base de données | MySQL |
| Architecture | Client-serveur / API REST |
| Modélisation | UML |
| Gestion de versions | Git / GitHub |

---

## 10. Priorisation des besoins (proposition)

Proposition de priorisation selon la méthode MoSCoW, à valider avant la conception détaillée.

| Priorité | Modules / besoins |
|---|---|
| **Must have** (indispensable) | Authentification ; patients ; rendez-vous (dont anti-chevauchement) ; traitements ; consultations ; paiements (dont calcul du reste à payer) |
| **Should have** (important) | Salle d'attente et écran public ; tableau de bord ; gestion des utilisateurs et des autorisations |
| **Could have** (souhaitable) | Paramètres avancés du cabinet ; archivage des dossiers ; filtres et recherches avancés |
| **Won't have** (hors MVP) | Toutes les fonctionnalités exclues (section 8.2) |

---

## 11. Hypothèses et points à clarifier

### 11.1. Hypothèses

- Le cabinet ne compte qu'un seul médecin ; le planning est donc unique.
- La secrétaire et le docteur sont les seuls utilisateurs du système.
- Un paiement est toujours rattaché à un traitement (pas de paiement isolé).
- La salle d'attente est gérée au quotidien, avec numérotation réinitialisée chaque jour.

### 11.2. Points à clarifier

| N° | Point à clarifier |
|---|---|
| Q1 | Quel est le mode de paiement « autre » à prévoir (chèque, virement, etc.) ? |
| Q2 | Quels droits précis le docteur et la secrétaire ont-ils sur la gestion des utilisateurs et des paramètres ? |
| Q3 | Une consultation unique (sans traitement de longue durée) doit-elle passer par un traitement ? Le cahier des charges rattache chaque consultation à un traitement (RG05). |
| Q4 | Quelle est la durée standard d'un rendez-vous par défaut ? |
| Q5 | Comment la réactivation ou la correction d'un traitement terminé est-elle autorisée (RG20) et par qui ? |
| Q6 | Quelles données doivent être conservées lors de l'archivage d'un dossier patient ? |

---

## 12. Livrables associés

| N° | Livrable |
|---|---|
| 1 | Cahier des charges |
| **2** | **Document d'identification des besoins et du périmètre (le présent document)** |
| 3 | Diagramme de cas d'utilisation |
| 4 | Diagramme de classes |
| 5 | Diagrammes de séquence |
| 6 | Maquettes des interfaces |
| 7 | Application web MediQ |
| 8 | Base de données |
| 9 | Documentation technique |
| 10 | Guide d'utilisation |

---

## 13. Critères de validation

Le périmètre sera considéré comme couvert lorsque :

- Les utilisateurs peuvent se connecter selon leurs rôles.
- Les dossiers des patients peuvent être gérés.
- Les rendez-vous peuvent être créés et suivis.
- Les conflits de réservation sont empêchés.
- Les traitements peuvent être associés aux patients.
- Les consultations réalisées sont enregistrées.
- Plusieurs paiements peuvent être associés à un traitement.
- Le montant payé et le reste à payer sont calculés correctement.
- La salle d'attente fonctionne correctement.
- Les autorisations d'accès sont respectées.
- Les données sont correctement enregistrées et récupérées.

---

## 14. Glossaire

| Terme | Définition |
|---|---|
| **MVP** | Version minimale viable : ensemble des fonctionnalités indispensables livrées en premier |
| **Traitement** | Suivi administratif et financier de longue durée associé à un patient |
| **Consultation** | Visite effectivement réalisée au cabinet |
| **Rendez-vous** | Créneau planifié, pouvant ou non aboutir à une consultation |
| **Reste à payer** | Coût total du traitement moins le total des paiements enregistrés |
| **Numéro de passage** | Numéro attribué à un patient dans la file d'attente du jour |
| **API REST** | Interface de communication entre le client (frontend) et le serveur (backend) |
| **Loi 09-08** | Loi marocaine relative à la protection des personnes physiques à l'égard du traitement des données à caractère personnel |

---

**Fin du document – Identification des besoins et du périmètre – Projet MediQ**
