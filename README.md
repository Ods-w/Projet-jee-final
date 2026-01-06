## Rapport du Projet : Gestion de Comptes Bancaires avec Agent AI

## 1. Introduction
#### J’ai réalisé une application permettant de gérer des comptes bancaires avec l’aide d’un agent intelligent (IA). Cette application permet de gérer les clients, leurs comptes ainsi que les opérations effectuées sur ces comptes. L’objectif principal est de créer un outil fonctionnel et pédagogique, permettant de comprendre la gestion bancaire, la modélisation des données et le développement de web services sécurisés. Le projet met également en pratique les concepts fondamentaux des applications distribuées, tels que la persistance des données, l’architecture client-serveur, la communication via API REST, et l’intégration d’un frontend web moderne pour offrir une interface utilisateur intuitive et sécurisée.
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
### Base de donnees
<img width="1887" height="788" alt="image" src="https://github.com/user-attachments/assets/f2b940ae-2bde-43b6-9580-5ae2465a59a9" />

### Frontend (Angular) :
#### Après avoir développé le backend avec Spring Boot, j’ai créé le frontend avec Angular, qui constitue l’interface utilisateur de l’application. Le frontend récupère et affiche les donnée
#### s (clients, comptes et opérations bancaires)directement depuis la base de données via l’API REST du backend. Il permet aux utilisateurs de gérer facilement les clients et leurs comptes, 
#### de consulter les opérations de type CRÉDIT ou DÉBIT en temps réel, et assure la communication sécurisée avec le backend. Le frontend inclut l’authentification et l’autorisation côté client,
#### une navigation fluide entre les pages, ainsi que l’utilisation de DTO pour ne présenter que les informations nécessaires.. Il offre également une interface graphique intuitive pour la création et la consultation des clients,
#### la gestion des comptes courants et d’épargne,et l’enregistrement des opérations bancaires. À titre d’illustration, j’ai ajouté une capture de la page de connexion affichant le formulaire d’authentification.
  <img width="1915" height="511" alt="image" src="https://github.com/user-attachments/assets/fe92da68-a701-4b14-acae-59487f7c86e2" />

  <img width="1908" height="487" alt="image" src="https://github.com/user-attachments/assets/9383eb3e-e643-4c91-9dbe-a4ead4019df6" />

#### Liste des clients : affichage des clients
<img width="1918" height="367" alt="image" src="https://github.com/user-attachments/assets/d300b608-7270-499d-af29-1daa19964264" />

<img width="1917" height="698" alt="image" src="https://github.com/user-attachments/assets/d130c26b-6278-4b09-b5bc-8bbaf0dbe449" />

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
