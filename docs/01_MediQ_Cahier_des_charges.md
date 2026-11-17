# CAHIER DES CHARGES
## Projet MediQ
**Système de gestion des patients, des rendez-vous, des traitements et des paiements**

---

## 1. Présentation générale du projet

### 1.1. Contexte

La gestion quotidienne d'un cabinet médical nécessite une organisation efficace des dossiers des patients, des rendez-vous, des traitements et des paiements.

L'utilisation de méthodes manuelles ou de plusieurs outils séparés peut entraîner des difficultés dans le suivi administratif et financier des patients.

Dans ce contexte, MediQ propose une solution web permettant de centraliser et de simplifier les différentes opérations administratives du cabinet.

### 1.2. Présentation de la solution

MediQ est une application web destinée à un cabinet médical composé d'un seul médecin.

Elle permet de :

- Gérer les dossiers des patients.
- Organiser les rendez-vous.
- Suivre les traitements de longue durée.
- Enregistrer les consultations réalisées.
- Gérer les paiements et les versements partiels.
- Organiser la salle d'attente.
- Suivre l'activité administrative et financière du cabinet.

### 1.3. Client cible

- Établissement : Cabinet médical individuel.
- Organisation : Un seul médecin.
- Utilisateurs : Secrétaire et Docteur.

---

## 2. Problématique

La gestion quotidienne d'un cabinet médical peut présenter plusieurs difficultés :

- Difficulté à retrouver les informations des patients.
- Manque d'organisation des rendez-vous.
- Difficulté à suivre les traitements de longue durée.
- Manque de visibilité sur les consultations déjà réalisées.
- Difficulté à suivre les paiements échelonnés.
- Absence d'une vision claire du montant payé et du reste à payer.
- Difficulté à organiser les patients présents dans la salle d'attente.

**Problématique principale :**

Comment développer une application web permettant de centraliser et d'améliorer la gestion administrative et financière d'un cabinet médical, notamment les patients, les rendez-vous, les traitements et les paiements ?

---

## 3. Objectifs du projet

### 3.1. Objectif général

Développer une application web centralisée permettant d'améliorer l'organisation administrative et financière d'un cabinet médical individuel.

### 3.2. Objectifs spécifiques

- Centraliser les informations des patients.
- Faciliter la gestion des dossiers administratifs.
- Organiser les rendez-vous médicaux.
- Assurer le suivi des traitements de longue durée.
- Enregistrer les consultations réalisées.
- Gérer les paiements partiels et complets.
- Calculer automatiquement les montants payés et les restes à payer.
- Organiser la file d'attente.
- Gérer les utilisateurs et leurs autorisations.
- Fournir un tableau de bord présentant les informations essentielles.

---

## 4. Identification des acteurs

### 4.1. Secrétaire

La secrétaire assure principalement la gestion administrative du cabinet.

Ses responsabilités :

- Se connecter à l'application.
- Consulter le tableau de bord.
- Ajouter, modifier et consulter les dossiers des patients.
- Gérer les rendez-vous.
- Créer et suivre les traitements.
- Enregistrer les consultations réalisées.
- Enregistrer les paiements.
- Consulter les historiques financiers.
- Gérer la salle d'attente.

### 4.2. Docteur

Le docteur utilise l'application pour consulter et suivre l'activité du cabinet.

Ses responsabilités :

- Se connecter à l'application.
- Consulter son tableau de bord.
- Consulter les dossiers des patients.
- Consulter les rendez-vous du jour.
- Consulter les traitements en cours.
- Consulter l'historique des consultations.
- Suivre la salle d'attente.
- Consulter les informations financières.
- Gérer les utilisateurs et les paramètres selon ses autorisations.

---

## 5. Besoins fonctionnels

### 5.1. Authentification

Le système doit permettre :

- La connexion avec identifiant et mot de passe.
- La vérification des informations de connexion.
- L'accès selon le rôle de l'utilisateur.
- La déconnexion sécurisée.
- La protection des pages contre les accès non autorisés.

### 5.2. Tableau de bord

Le système doit proposer un tableau de bord adapté au rôle de l'utilisateur.

Les informations affichées peuvent inclure :

- Nombre total de patients.
- Nombre de rendez-vous du jour.
- Nombre de consultations réalisées.
- Nombre de patients en attente.
- Nombre de traitements en cours.
- Total des paiements enregistrés.
- Total des montants restant à payer.

### 5.3. Gestion des patients

Le système doit permettre :

- Ajouter un patient.
- Consulter la liste des patients.
- Rechercher un patient.
- Consulter son dossier administratif.
- Modifier ses informations.
- Archiver un dossier.
- Consulter ses rendez-vous.
- Consulter ses traitements.
- Consulter son historique de consultations.
- Consulter son historique de paiements.

**Informations d'un patient :**

- Identifiant unique.
- Nom.
- Prénom.
- Date de naissance.
- Sexe.
- Téléphone.
- Adresse.
- Date de création du dossier.

### 5.4. Gestion des rendez-vous

Le système doit permettre :

- Ajouter un rendez-vous.
- Associer le rendez-vous à un patient.
- Associer éventuellement le rendez-vous à un traitement.
- Consulter les rendez-vous du jour.
- Consulter les rendez-vous par date.
- Modifier un rendez-vous.
- Annuler un rendez-vous.
- Suivre son statut.
- Organiser les rendez-vous par ordre chronologique.

**Informations d'un rendez-vous :**

- Identifiant.
- Patient concerné.
- Traitement associé (facultatif).
- Date.
- Heure.
- Motif administratif.
- Statut.

**Statuts possibles :**

- En attente.
- Confirmé.
- En cours.
- Terminé.
- Annulé.
- Absent.

Le système doit empêcher les chevauchements de rendez-vous pour le même médecin.

### 5.5. Gestion des traitements

Le système doit permettre de gérer les traitements de longue durée associés aux patients.

Fonctionnalités :

- Créer un traitement pour un patient.
- Consulter les traitements d'un patient.
- Modifier les informations d'un traitement.
- Consulter le coût total du traitement.
- Consulter les consultations associées.
- Consulter les paiements associés.
- Suivre le statut du traitement.
- Consulter le montant payé et le reste à payer.

**Informations d'un traitement :**

- Identifiant.
- Patient associé.
- Nom du traitement.
- Description administrative.
- Coût total.
- Date de début.
- Date de fin éventuelle.
- Statut.

**Statuts possibles :**

- En cours.
- Terminé.
- Suspendu.
- Annulé.

Le système assure uniquement le suivi administratif et financier des traitements. Il ne gère pas les diagnostics, les prescriptions ou les actes médicaux détaillés.

### 5.6. Gestion des consultations

Le système doit permettre d'enregistrer les consultations réellement effectuées dans le cabinet.

Fonctionnalités :

- Enregistrer une consultation.
- Associer la consultation à un traitement.
- Associer éventuellement la consultation au rendez-vous correspondant.
- Enregistrer la date et l'heure.
- Consulter l'historique des consultations d'un traitement.
- Consulter l'historique des consultations d'un patient.

**Informations d'une consultation :**

- Identifiant.
- Traitement associé.
- Rendez-vous associé (facultatif).
- Date.
- Heure.
- Observation administrative éventuelle.

Une consultation représente une visite effectivement réalisée et ne doit pas être confondue avec un rendez-vous planifié.

### 5.7. Gestion des paiements

Le système doit permettre de gérer les paiements associés aux traitements.

Fonctionnalités :

- Enregistrer un paiement.
- Associer un paiement à un traitement.
- Enregistrer le montant versé.
- Enregistrer la date du paiement.
- Enregistrer le mode de paiement.
- Consulter l'historique des paiements.
- Calculer le total payé.
- Calculer le reste à payer.
- Consulter la situation financière de chaque traitement.

**Informations d'un paiement :**

- Identifiant.
- Traitement associé.
- Montant.
- Date du paiement.
- Mode de paiement.

**Modes de paiement :**

- Espèces.
- Carte bancaire.
- Autre mode à définir.

Le système doit accepter plusieurs paiements pour un même traitement.

**Calcul financier :**

Total payé = Somme des paiements enregistrés.

Reste à payer = Coût total du traitement − Total payé.

### 5.8. Gestion de la salle d'attente

Le système doit permettre :

- Afficher les patients présents au cabinet.
- Organiser la file d'attente.
- Attribuer un numéro de passage.
- Afficher le numéro du patient actuellement appelé.
- Appeler le patient suivant.
- Mettre à jour son statut.
- Afficher les patients encore en attente.

L'écran public doit afficher uniquement les numéros de passage, sans exposer les informations personnelles.

### 5.9. Gestion des utilisateurs

Le système doit permettre à l'utilisateur autorisé :

- Ajouter un compte.
- Consulter les utilisateurs.
- Modifier les informations d'un compte.
- Activer ou désactiver un compte.
- Attribuer un rôle.
- Gérer les autorisations.

### 5.10. Paramètres

Le système doit permettre de configurer :

- Nom du cabinet.
- Coordonnées du cabinet.
- Informations du médecin.
- Durée standard des rendez-vous.
- Paramètres de fonctionnement.
- Paramètres de la salle d'attente.

---

## 6. Besoins non fonctionnels

### 6.1. Sécurité

- Authentification obligatoire.
- Gestion des autorisations selon les rôles.
- Stockage sécurisé des mots de passe.
- Protection des données personnelles.
- Protection contre les accès non autorisés.

### 6.2. Ergonomie

- Interface intuitive.
- Navigation simple.
- Organisation claire des informations.
- Adaptation aux écrans d'ordinateur et de tablette.

### 6.3. Performance

- Temps de réponse raisonnable.
- Recherche rapide des patients.
- Chargement efficace des tableaux.
- Gestion correcte des opérations simultanées.

### 6.4. Fiabilité

- Validation des données avant enregistrement.
- Prévention des conflits de rendez-vous.
- Cohérence des paiements.
- Prévention des paiements dépassant le montant restant.
- Conservation de l'historique financier.

### 6.5. Maintenabilité

- Code organisé.
- Séparation des responsabilités.
- Réutilisation des composants.
- Architecture évolutive.

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

---

## 8. Périmètre du projet

### 8.1. Fonctionnalités incluses dans le MVP

- Authentification.
- Tableau de bord.
- Gestion des patients.
- Gestion des rendez-vous.
- Gestion des traitements de longue durée.
- Gestion des consultations.
- Gestion des paiements.
- Gestion de la salle d'attente.
- Gestion des utilisateurs.
- Paramètres du cabinet.

### 8.2. Fonctionnalités exclues

- Diagnostic médical.
- Prescription médicale.
- Dossier médical électronique détaillé.
- Prise de rendez-vous en ligne par les patients.
- Notifications automatiques par SMS ou Email.
- Application mobile.
- Téléconsultation.
- Gestion des stocks médicaux.
- Gestion des assurances et remboursements.
- Comptabilité avancée.
- Gestion de plusieurs cabinets.

---

## 9. Contraintes du projet

### 9.1. Contraintes techniques

- Application accessible via un navigateur web.
- Utilisation d'une base de données relationnelle.
- Architecture Client-Serveur.
- Communication via API REST.
- Protection des données.

### 9.2. Contraintes fonctionnelles

- Adaptation à un cabinet avec un seul médecin.
- Simplicité d'utilisation.
- Respect des règles de gestion des rendez-vous.
- Suivi financier précis des traitements.

### 9.3. Contraintes réglementaires

Le système doit prendre en considération la réglementation marocaine relative à la protection des données personnelles, notamment la loi 09-08 et les obligations applicables aux traitements concernés.

---

## 10. Technologies envisagées

| Couche | Technologie |
|---|---|
| Frontend | React.js |
| Backend | Java / Spring Boot |
| Base de données | MySQL |
| Architecture | Client-Serveur / API REST |
| Modélisation | UML |
| Gestion de versions | Git / GitHub |

---

## 11. Livrables du projet

1. Cahier des charges.
2. Document d'identification des besoins et du périmètre.
3. Diagramme de cas d'utilisation.
4. Diagramme de classes.
5. Diagrammes de séquence.
6. Maquettes des interfaces.
7. Application web MediQ.
8. Base de données.
9. Documentation technique.
10. Guide d'utilisation.

---

## 12. Critères de validation

Le projet sera considéré comme fonctionnel lorsque :

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

## 13. Conclusion

MediQ est une solution web destinée à améliorer la gestion administrative et financière d'un cabinet médical individuel.

L'application permet de centraliser les dossiers des patients, de gérer les rendez-vous, de suivre les traitements de longue durée, d'enregistrer les consultations réalisées et de gérer les paiements échelonnés.

Le projet sera développé progressivement selon les besoins identifiés, les règles de gestion définies et les exigences de sécurité et de qualité.

**Fin du cahier des charges – Projet MediQ**
