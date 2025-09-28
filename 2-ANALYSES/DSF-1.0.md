# 📄 Document des Spécifications Fonctionnelles

## 🗓️ Calendar App

---

## 🌍 1. Présentation générale

**Calendar App** est une application web de gestion de calendriers personnels et collaboratifs.  
Elle vise à offrir une expérience proche de Google Calendar et Apple Calendar, tout en explorant des problématiques avancées comme la gestion multi-organisation, la réservation de salles, les réunions collaboratives et les liens publics de prise de rendez-vous.

Ce projet a une double vocation :

- Servir de **side project technique** pour approfondir les compétences backend (Symfony), frontend (Vue.js 3 + TailwindCSS) et gestion de projet.
- Constituer une **démonstration concrète dans un portfolio professionnel**, avec une démo en ligne accessible.

---

## ⚙️ 2. Stack technique

- **Backend** : Symfony (API REST), PostgreSQL
- **Frontend** : Vue.js 3 + TailwindCSS
- **Communication** : API REST + WebSockets (Mercure / Socket.io) pour le temps réel
- **Déploiement** : Hostinger (démonstration)
- **Architecture** : multi-tenant, multi-organisation, rôles et sous-rôles
- **Roadmap** : approche incrémentale par lots fonctionnels

---

## 👤 3. Profils utilisateurs

### 3.1 Rôles globaux

Il existe trois rôles principaux, attribués au niveau de l’application dans son ensemble :

| Rôle                     | Code interne   | Description                                                                                             | Accès aux fonctionnalités                |
| ------------------------ | -------------- | ------------------------------------------------------------------------------------------------------- | ---------------------------------------- |
| **Admin**                | `usr_sa`       | Gère l’ensemble de la plateforme, les utilisateurs et la configuration globale.                         | Accès complet (technique et fonctionnel) |
| **Utilisateur Premium**  | `usr_premium`  | Compte ayant débloqué les fonctionnalités avancées (ex. : multi-organisations, réservation publique…).  | Accès étendu                             |
| **Utilisateur Standard** | `usr_standard` | Compte gratuit avec accès aux fonctionnalités de base (calendrier simple, événements personnels, etc.). | Fonctionnalités limitées                 |

👉 Le passage de standard à premium se fera **par simulation de paiement**, afin de tester le comportement freemium sans intégrer de véritable passerelle de paiement.

---

### 3.2 Sous-rôles organisationnels

Lorsqu’un utilisateur crée ou rejoint une organisation, il se voit attribuer un sous-rôle propre à cette organisation. La hiérarchie est la suivante :

| Sous-rôle          | Code interne  | Description                                                                                                                       |
| ------------------ | ------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| **Propriétaire**   | `orga_owner`  | Créateur initial de l’organisation. Dispose de tous les droits (paramétrage, gestion des membres, suppression de l’organisation). |
| **Administrateur** | `orga_admin`  | Peut gérer les ressources, les événements, les membres (mais pas supprimer l’organisation).                                       |
| **Membre**         | `orga_member` | Peut consulter et créer des événements, réserver des salles, mais ne gère pas les paramètres globaux.                             |

---

## 🔐 4. Authentification

| Fonctionnalité                       | Description                                                                                                                      |
| ------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------- |
| **Inscription**                      | Par email et mot de passe uniquement. Confirmation par email.                                                                    |
| **Connexion**                        | Email + mot de passe. Aucune authentification externe (Google / Microsoft) prévue pour le MVP.                                   |
| **Gestion du compte**                | L’utilisateur peut modifier ses informations personnelles et mot de passe depuis l’espace personnel.                             |
| **Passage Premium**                  | Simulé via un bouton d’upgrade (visible uniquement pour les utilisateurs standard). L’activation Premium est validée côté admin. |
| **Réinitialisation du mot de passe** | Envoi d’un lien sécurisé par email.                                                                                              |

---

## 🧭 5. Liste des lots fonctionnels

| Lot | Nom                                  | Description synthétique                                           |
| --- | ------------------------------------ | ----------------------------------------------------------------- |
| 1   | Calendrier personnel                 | Création/affichage d’événements simples pour un utilisateur       |
| 2   | Organisations & rendez-vous internes | Gestion des organisations, membres, et événements enrichis        |
| 3   | Réservation de salles                | Réservation avec priorisation automatique et gestion des conflits |
| 4   | Chat interne                         | Messagerie temps réel dans une organisation                       |
| 5   | Partage public de créneaux           | Lien public pour prise de rendez-vous externe                     |
| 6   | Réunions collaboratives              | Organisation et invitations à des réunions                        |

---

## 📝 6. Détail des lots fonctionnels

### **Lot 1 – Calendrier personnel**

- 1.1 – Vue calendrier (année / mois / semaine / jour)
- 1.2 – Création, édition, suppression d’événements simples
- 1.3 – Gestion multi-calendriers personnels
- 1.4 – Recherche avancée avec paramètres (titre, dates, tags…)
- 1.5 – Import/export ICS (évolution ultérieure)

---

### **Lot 2 – Organisations & rendez-vous internes**

- 2.1 – Création / gestion d’une organisation
- 2.2 – Invitation et gestion des membres (avec sous-rôles)
- 2.3 – Vue calendrier d’organisation
- 2.4 – Création d’événements enrichis (rendez-vous internes)
- 2.5 – Changement d’organisation via menu utilisateur
- 2.6 – Gestion des types d’événements spécifiques à l’organisation

---

### **Lot 3 – Réservation de salles**

- 3.1 – Création et paramétrage des salles (capacité, équipement…)
- 3.2 – Réservation d’une salle depuis un calendrier
- 3.3 – Système de priorisation automatique en cas de conflit
  - Ex. grande salle priorisée pour grand groupe.
- 3.4 – Gestion manuelle des conflits et notifications

---

### **Lot 4 – Chat interne**

- 4.1 – Conversations privées entre membres d’une organisation
- 4.2 – Canaux de groupe internes
- 4.3 – Notifications temps réel (WebSockets)
- 4.4 – Suppression automatique des messages après 1 an
- 4.5 – Historique et modération basique

---

### **Lot 5 – Partage public de créneaux**

- 5.1 – Génération de liens publics (token unique, expiration configurable)
- 5.2 – Page publique de réservation (créneaux, infos contact, captcha)
- 5.3 – Paramètres de contrôle (activation, durée, quotas)
- 5.4 – Association à un calendrier ou une salle
- 5.5 – Notifications et confirmations (email externe + interne)
- 5.6 – Journalisation des réservations
- 5.7 – Révocation et gestion des liens

---

### **Lot 6 – Réunions collaboratives**

- 6.1 – Création de réunions avec ordre du jour et durée
- 6.2 – Invitation des membres d’une organisation
- 6.3 – Gestion des conflits avec système de priorités (ex : client > daily)
- 6.4 – Affichage consolidé dans les calendriers
- 6.5 – Notifications automatiques (email, interne)

---

## 🎨 7. Contraintes UX/UI transversales

- Interface responsive (desktop & mobile).
- Navigation fluide entre calendrier personnel et organisations via menu latéral ou supérieur.
- Charte graphique homogène inspirée de Google Calendar + Apple Calendar.
- Accessibilité de base : contrastes lisibles, taille de police suffisante, interactions claires.
- Préparation au dark mode (non activé par défaut).
- Design minimaliste et épuré, favorisant la lisibilité.

---

## 🛡️ 8. Sécurité & RGPD

- Gestion des comptes conforme au droit à l’oubli (suppression sur demande).
- Données conservées 1 an max pour les chats internes.
- Partages publics sécurisés par token et captcha.
- Gestion CNIL/RGPD prévue comme évolution future.

---

## 🚀 9. Performances & scalabilité

- Application pensée pour un usage réel multi-utilisateurs.
- Architecture multi-tenant dès la conception.
- Sauvegardes automatiques PostgreSQL envisagées (hors périmètre MVP).

---

## 📝 10. Documentation & livrables

- **README** clair dans chaque repo (backend / frontend / docs).
- **Documentation technique** (API, structure BDD).
- **Guide utilisateur rapide** pour la démo.
- **Roadmap détaillée** dans `roadmap.md`.
- **Cahier des charges** et **présent document** versionnés dans le repo documentation.

---

## 👤 11. Auteur

Développé par **Killian GODET**  
Backend developer spécialisé Symfony  
🌐 [https://killiangodet.fr](https://killiangodet.fr)
