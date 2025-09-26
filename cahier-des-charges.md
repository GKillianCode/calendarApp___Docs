# 📑 Cahier des charges – Calendar App

## 1. Objectifs du projet

L’application **Calendar App** vise à proposer une solution de gestion de calendriers personnels et collaboratifs.  
Elle doit permettre aux utilisateurs de gérer plusieurs agendas, d’organiser des rendez-vous, de réserver des salles et d’utiliser des fonctionnalités collaboratives comme le chat et les réunions avec invitations.

Le projet a également pour but de :

- Mettre en œuvre une architecture **backend Symfony / frontend Vue.js 3**.
- Expérimenter des cas d’usage réels (multi-tenant, gestion de conflits, rôles & droits).
- Démontrer mes compétences techniques via un projet concret documenté.

---

## 2. Périmètre fonctionnel

📄 [Roadmap détaillée](roadmap.md)

---

## 3. Exigences techniques

- **Backend** : Symfony (API REST)
- **Base de données** : PostgreSQL
- **Frontend** : Vue.js 3 + TailwindCSS
- **Temps réel** : Symfony Mercure ou Socket.io pour chat et notifications
- **Déploiement** : Hostinger (démo en ligne)

---

## 4. Exigences non fonctionnelles

- **Sécurité** : authentification JWT, rôles et permissions, protection contre les bots (captcha pour liens publics).
- **RGPD** : conformité prévue (droit à l’oubli, export) – intégration future.
- **Performances** : support du multi-tenant et optimisation pour montée en charge.
- **Accessibilité** : interface responsive, possibilité de dark mode (prévu dans le code).
- **Conservation des données** :
  - Chat : messages conservés 1 an puis purge auto.
  - Événements : historique selon règles à définir.

---

## 5. Livrables

- Code source backend (Symfony) et frontend (Vue.js 3)
- Documentation technique (API docs, architecture)
- Documentation utilisateur (guide rapide)
- Cahier des charges (ce document)
- Démo en ligne (sur Hostinger)

---

## 6. Phasage prévisionnel

- **Lot 1** : Calendrier simple – ✅ en cours
- **Lot 2** : Organisations et rendez-vous internes
- **Lot 3** : Réservation de salles
- **Lot 4** : Chat interne
- **Lot 5** : Partage public de rendez-vous
- **Lot 6** : Réunions avec invitations

---
