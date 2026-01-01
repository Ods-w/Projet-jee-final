## Rapport du Projet : Gestion de Comptes Bancaires avec Agent AI

## 1. Introduction
#### J’ai réalisé une application permettant de gérer des comptes bancaires avec l’aide d’un agent intelligent (AI). Cette application permet de gérer des clients,
#### leurs comptes et les opérations effectuées sur ces comptes (débit ou crédit).
#### L’objectif est de créer un outil fonctionnel pour comprendre la gestion des comptes bancaires et la programmation des web services sécurisés.

## 2. Architecture du projet
<img width="1918" height="1020" alt="image" src="https://github.com/user-attachments/assets/3044a143-817d-491a-a3cf-5c61f9f9790a" />

#### L’application est organisée en trois grandes parties :

### Backend (Spring Boot) :

#### Gère les entités, la logique métier et les web services REST.
<img width="1918" height="832" alt="image" src="https://github.com/user-attachments/assets/eb706a6d-fd89-405c-824e-15bf224e6547" />

#### Création des interfaces Repository avec Spring Data JPA
#### Après avoir défini mes entités JPA, j’ai mis en place des interfaces Repository pour chacune afin de simplifier l’accès aux données et la gestion de la persistance.
#### L’utilisation de Spring Data JPA me permet de profiter automatiquement des méthodes CRUD de base sans avoir besoin de les coder manuellement.
#### Repository pour les clients
#### J’ai créé CustomerRepository pour gérer les opérations liées à l’entité Customer.
#### Cette interface étend JpaRepository<Customer, Long> et offre la possibilité de :
#### Enregistrer un client
#### Mettre à jour un client
#### Supprimer un client
<img width="1890" height="595" alt="image" src="https://github.com/user-attachments/assets/3fa63416-dbff-43ce-a50b-3cb4cd54d638" />


## 3 Repositories
#### Pour gérer l’accès aux données et la persistance, j’ai créé des interfaces Repository en utilisant Spring Data JPA. Ces interfaces permettent d’effectuer facilement des opérations CRUD sans implémentation manuelle.
##### CustomerRepository : permet de gérer les clients et inclut une méthode personnalisée searchCustomer pour rechercher des clients par nom.
#### BankAccountRepository : gère les comptes bancaires, qu’ils soient courants ou d’épargne.
#### AccountOperationRepository : gère les opérations bancaires (CRÉDIT / DÉBIT) et offre des méthodes pour récupérer les opérations par compte, avec ou sans pagination et tri par date décroissante.
#### Ces repositories simplifient l’interaction avec la base de données et facilitent l’implémentation du backend.
<img width="1911" height="387" alt="image" src="https://github.com/user-attachments/assets/59eda1c5-8f59-46cc-954a-b5fee6d3be67" />

### Frontend (Angular) :
#### Après avoir développé le backend avec Spring Boot, j’ai créé le frontend avec Angular, qui constitue l’interface utilisateur de l’application. Le frontend récupère et affiche les donnée
#### s (clients, comptes et opérations bancaires)directement depuis la base de données via l’API REST du backend. Il permet aux utilisateurs de gérer facilement les clients et leurs comptes, 
#### de consulter les opérations de type CRÉDIT ou DÉBIT en temps réel, et assure la communication sécurisée avec le backend. Le frontend inclut l’authentification et l’autorisation côté client,
#### une navigation fluide entre les pages, ainsi que l’utilisation de DTO pour ne présenter que les informations nécessaires.. Il offre également une interface graphique intuitive pour la création et la consultation des clients,
#### la gestion des comptes courants et d’épargne,et l’enregistrement des opérations bancaires. À titre d’illustration, j’ai ajouté une capture de la page de connexion affichant le formulaire d’authentification.
<img width="1033" height="548" alt="image" src="https://github.com/user-attachments/assets/4f85ab34-d631-4c5c-8320-5e60cc6d8527" />

#### Liste des clients : affichage des clients
<img width="1037" height="547" alt="image" src="https://github.com/user-attachments/assets/4f08259e-8cc2-420f-bcda-4af973eb5008" />

#### Formulaire de création de compte 
<img width="1033" height="542" alt="image" src="https://github.com/user-attachments/assets/dad3491c-d252-40d7-a5ac-3c1a1d3a6d7a" />

### Sécurité:
#### La sécurité de l’application est assurée avec Spring Security et des tokens JWT. J’ai configuré des utilisateurs en mémoire pour le développement,
#### avec des mots de passe encodés en BCrypt. Le backend utilise une authentification stateless : chaque requête vers les endpoints sécurisés nécessite un JWT,
#### généré lors de la connexion via /auth/login. Les rôles des utilisateurs sont inclus dans le token pour gérer les autorisations.
#### e frontend Angular communique avec l’API en incluant ce token dans l’en-tête Authorization. Un endpoint /auth/profile permet de récupérer les informations de l’utilisateur connecté.
#### La configuration inclut également le CORS, pour permettre l’accès depuis le frontend.

<img width="1907" height="596" alt="image" src="https://github.com/user-attachments/assets/63afc985-e610-4c51-8d5b-7349c243d882" />

<img width="1902" height="858" alt="image" src="https://github.com/user-attachments/assets/31ad1834-47a7-4e72-89de-5b0a43703a3a" />


## 5. Conclusion 
### Ce projet m’a permis de mettre en pratique plusieurs compétences en développement logiciel :
#### La conception d’une application full-stack avec Spring Boot et Angular.
#### La modélisation des données bancaires avec JPA et la gestion des relations entre entités.
#### La création et la sécurisation d’APIs REST grâce à Spring Security et JWT.
#### L’intégration d’une interface utilisateur fonctionnelle et intuitive.
#### Grâce à ce projet, j’ai mieux compris le fonctionnement d’un système bancaire simplifié et l’importance de la sécurité et de la structuration des données.
#### Il offre une base solide pour évoluer vers une application plus complète, par exemple en ajoutant :
#### Des fonctionnalités d’analyse automatique des opérations.
#### Des rapports détaillés sur les comptes et transactions.
#### Une interface utilisateur plus interactive et responsive.
#### Ce projet constitue donc une bonne introduction au développement d’applications bancaires sécurisées et à l’utilisation des technologies modernes de développement web.
