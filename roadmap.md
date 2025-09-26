# Roadmap – Application de calendrier

## Liste des lots

- Lot 1 : Calendrier simple (utilisateur individuel)
- Lot 2 : Organisations et rendez-vous internes
- Lot 3 : Réservation de salles (organisations)
- Lot 4 : Chat interne
- Lot 5 : Partage public de rendez-vous
- Lot 6 : Réunions avec invitations

---

## Détails des lots et sous-lots

### **Lot 1 – Calendrier simple (utilisateur individuel)**

- 1.1 – Création de compte et authentification (email + mot de passe)
- 1.2 – Gestion d’un espace personnel (profil utilisateur)
- 1.3 – Création, modification et suppression d’événements (CRUD)
- 1.4 – Affichage du calendrier en vues **année / mois / semaine / jour**
- 1.5 – **Recherche avancée** : recherche d’événements par mots-clés et paramètres (date, type d’événement, participants, organisation sélectionnée, plage horaire, etc.)

---

### **Lot 2 – Organisations et rendez-vous internes**

- 2.1 – Création et gestion d’une organisation
- 2.2 - Création de compte d'organisation et authentification
- 2.2 - Création de rendez-vous dans l'agenda personnel (organisation)
- 2.2 – Association d’utilisateurs à une organisation (invitation / ajout)
- 2.3 – Gestion des rôles et droits (admin organisation, membre, etc.)
- 2.4 – Création de réunions internes (visibles uniquement par les membres de l’organisation)
- 2.5 – **Sélecteur d’organisation** : menu permettant de basculer d’une organisation à l’autre

---

### **Lot 3 – Réservation de salles (organisations)**

- 3.1 – Création et gestion des salles (nom, capacité, localisation)
- 3.2 – Association d’une réservation de salle à un événement
- 3.3 – Vérification des disponibilités (contrôle temps réel pour éviter les doublons)
- 3.4 – Gestion des conflits de réservation (alerte, proposition d’alternatives)
- 3.5 – **Système de poids / priorisation pour la réservation**
  - Priorisation en fonction de la capacité vs nombre de participants
  - Pondération selon l’importance de l’événement ou rôle de l’organisateur
- 3.6 – Suggestions automatiques de salles alternatives en cas de conflit
- 3.7 – Journalisation / audit des réservations et modifications
- 3.8 – Interface admin pour override manuel des priorités

---

### **Lot 4 – Chat interne**

- 4.1 – Messagerie simple (direct messages) entre utilisateurs d’une organisation
- 4.2 – Conversations de groupe dans une organisation
- 4.3 – Notifications temps réel pour nouveaux messages
- 4.4 – Historique des conversations conservé **1 an** (purge auto ensuite)
- 4.5 – Recherche dans l’historique des messages

---

### **Lot 5 – Partage public pour réservation de créneaux**

- 5.1 – Lien public de réservation (token unique, durée configurable)
- 5.2 – Page publique de réservation (créneau + infos contact)
- 5.3 – Paramètres de validité et activation + ajout de salle / distancielle
- 5.4 – Notifications et confirmations (email externe + notification interne) + si distanciel envoie du lien de la visio conférence
- 5.5 – Historique des réservations
- 5.6 – Révocation des liens publics

---

### **Lot 6 – Réunions avec invitations**

- 6.1 – Création d’événements de type « réunion »
- 6.2 – Envoi d’invitations aux membres de l’organisation
- 6.3 – Gestion des statuts de participation (accepté / refusé / en attente)
- 6.4 – Vue récapitulative des participants et statuts
- 6.5 – **Système de poids / priorisation pour les réunions**
  - Pondération des types d’événements (`client_meeting` > `daily_meeting`)
  - Gestion automatique des conflits via priorités
  - Règles de fallback : ordre de création, rôle de l’organisateur, override admin
- 6.6 – Notifications et propositions d’alternatives en cas de conflit
- 6.7 – Gestion des récurrences et impact sur les conflits

---
