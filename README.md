# PostgreSQL_Citus_lab

Laboratoire pratique consacré à l'installation, la configuration et à l'utilisation de **PostgreSQL et Apache Citus** dans un environnement Data Engineering.

---

## 1. Présentation du projet

`PostgreSQL_Citus_lab` est un laboratoire technique destiné à apprendre à déployer et exploiter une base de données PostgreSQL avec l'extension Citus.

L'objectif est de comprendre le fonctionnement d'une architecture PostgreSQL distribuée, depuis l'installation des composants jusqu'à la création de tables distribuées, l'importation de données et l'exécution de requêtes analytiques.

Ce laboratoire servira également de documentation technique et de référence pour les prochaines missions Data Engineering.

## 2. Objectifs

**Construire un mini Data Warehouse avec Citus.**

Les objectifs techniques sont les suivants :

1. Installer PostgreSQL et Citus.
2. Configurer l'environnement de travail.
3. Créer une base de données `dwh_ventes`.
4. Créer les tables `clients`, `commandes` et `ventes`.
5. Définir les clés de distribution (*Distribution Keys*).
6. Distribuer les tables avec Citus.
7. Importer des données depuis des fichiers CSV.
8. Réaliser des jointures et des agrégations SQL.
9. Observer et comprendre la répartition des fragments (*Shards*).
10. Vérifier le fonctionnement de l'architecture distribuée.

## 3. Technologies utilisées

| Technologie | Utilisation |
|---|---|
| PostgreSQL | Système de gestion de base de données relationnelle |
| Apache Citus | Extension PostgreSQL pour le traitement distribué |
| Docker | Conteneurisation des services |
| Ubuntu Server | Environnement Linux pour le déploiement |
| DBeaver | Interface graphique pour administrer les bases de données |
| SQL | Création, manipulation et interrogation des données |
| MobaXterm | Accès SSH aux serveurs Linux |

*Les technologies seront utilisées selon le plan de déploiement retenu.*

## 4. Choix de l'environnement

Plusieurs configurations sont envisagées pour réaliser ce laboratoire.

### 4.1 Environnement de déploiement

- Docker sur Windows.
- Ubuntu Server (Linux).
- PostgreSQL installé directement sur une machine, avec DBeaver comme client d'administration.

### 4.2 Architecture Citus

Deux architectures sont envisagées :

**Architecture 1 — Serveur unique**

Un seul serveur héberge PostgreSQL et Citus. Cette configuration permet de commencer par comprendre les fonctionnalités de Citus sans gérer plusieurs machines.

**Architecture 2 — Cluster distribué**

Un coordinateur et deux Workers.

- Coordinator : reçoit les requêtes SQL et coordonne leur exécution.
- Worker 01 : héberge une partie des données distribuées.
- Worker 02 : héberge une autre partie des données distribuées.

Cette architecture permet de comprendre le fonctionnement d'un cluster Citus distribué.

## 5. Plans de déploiement envisagés

### Plan 1 — Docker + serveur unique

- Environnement : Docker sur Windows.
- Architecture : un seul serveur Citus.
- Objectif : découvrir PostgreSQL et les fonctionnalités de Citus.

### Plan 2 — Docker + cluster distribué

- Environnement : Docker sur Windows.
- Architecture : un coordinateur et deux Workers.
- Objectif : comprendre la distribution des données entre plusieurs instances PostgreSQL.

### Plan 3 — Ubuntu Server + serveur unique

- Environnement : Ubuntu Server.
- Architecture : un seul serveur Citus.
- Objectif : installer et configurer Citus directement sous Linux.

### Plan 4 — Ubuntu Server + cluster distribué

- Environnement : trois serveurs Ubuntu.
- Architecture : un coordinateur et deux Workers.
- Accès et administration : SSH avec MobaXterm.
- Objectif : reproduire une architecture Citus distribuée sur plusieurs machines.

### Plan 5 — PostgreSQL + DBeaver sans Docker

- Environnement : PostgreSQL installé directement sur le système.
- Interface d'administration : DBeaver.
- Objectif : apprendre à administrer PostgreSQL et Citus sans conteneurisation.

### Plan 6 — PostgreSQL + DBeaver avec Docker

- Environnement : PostgreSQL et Citus exécutés dans Docker.
- Interface d'administration : DBeaver.
- Objectif : administrer les bases de données conteneurisées avec une interface graphique.

## 6. Plan retenu

**Statut : À définir.**

Le choix définitif de l'environnement et de l'architecture sera indiqué dans cette section.

| Élément | Choix |
|---|---|
| Plan sélectionné | À définir |
| Environnement | À définir |
| Système d'exploitation | À définir |
| Version PostgreSQL | À définir |
| Version Citus | À définir |
| Architecture | À définir |
| Interface d'administration | À définir |

## 7. Travaux pratiques

Les exercices seront réalisés progressivement.

### TP 01 — Installation

- Installation de PostgreSQL.
- Installation de l'extension Citus.
- Vérification des versions.
- Activation de l'extension.

### TP 02 — Création du Data Warehouse

- Création de la base `dwh_ventes`.
- Création des schémas si nécessaire.
- Création des tables `clients`, `commandes` et `ventes`.

### TP 03 — Distribution des données

- Comprendre les tables distribuées.
- Choisir les clés de distribution.
- Utiliser `create_distributed_table()`.
- Comprendre les tables de référence.
- Vérifier la distribution des fragments.

### TP 04 — Importation des données

- Préparation des fichiers CSV.
- Vérification de la structure des fichiers.
- Importation des données dans PostgreSQL.
- Contrôle du nombre de lignes importées.

### TP 05 — Requêtes analytiques

- Jointures entre les tables.
- Agrégations.
- Fonctions SQL.
- Analyse des résultats.

### TP 06 — Observation et administration

- Inspection des Workers.
- Observation des Shards.
- Vérification de la répartition des données.
- Analyse de l'exécution des requêtes.
- Vérification du fonctionnement du cluster.

## 8. Organisation du projet

```text
PostgreSQL_Citus_lab/
│
├── README.md
│
├── docs/
│   ├── architecture.md
│   ├── installation.md
│   ├── configuration.md
│   └── commandes.md
│
├── docker/
│   ├── docker-compose.yml
│   └── config/
│
├── sql/
│   ├── 01_create_database.sql
│   ├── 02_create_tables.sql
│   ├── 03_distribute_tables.sql
│   ├── 04_insert_data.sql
│   └── 05_analytics.sql
│
├── data/
│   ├── clients.csv
│   ├── commandes.csv
│   └── ventes.csv
│
├── scripts/
│
├── screenshots/
│
└── tests/
    └── validation.sql
```

*Cette structure est une proposition initiale. Les dossiers seront adaptés au plan de déploiement retenu.*

## 9. Documentation officielle

- [Apache Citus — Documentation officielle](https://docs.citusdata.com/)
- [Citus — Créer et modifier des tables distribuées](https://learn.microsoft.com/en-us/postgresql/citus/reference-ddl?view=citus-14)
- [PostgreSQL — Documentation officielle](https://www.postgresql.org/docs/)
- [Docker — Documentation officielle](https://docs.docker.com/)
- [DBeaver — Documentation officielle](https://dbeaver.com/docs/)

## 10. Suivi de progression

- [ ] Choisir le plan de déploiement.
- [ ] Préparer l'environnement.
- [ ] Installer PostgreSQL.
- [ ] Installer Citus.
- [ ] Vérifier le fonctionnement de Citus.
- [ ] Créer la base `dwh_ventes`.
- [ ] Créer les tables.
- [ ] Définir les clés de distribution.
- [ ] Distribuer les tables.
- [ ] Importer les fichiers CSV.
- [ ] Réaliser les requêtes analytiques.
- [ ] Vérifier la répartition des Shards.
- [ ] Documenter les résultats et les difficultés rencontrées.

---

**Nom du projet :** `PostgreSQL_Citus_lab`  
**Domaine :** Data Engineering / Distributed Databases  
**Objectif final :** disposer d'un environnement PostgreSQL-Citus fonctionnel, documenté et réutilisable pour les travaux pratiques et les futures missions.





<!--

# PostgreSQL_Citus_lab

Laboratoire pratique consacré à l'installation, la configuration et à l'utilisation de PostgreSQL et Apache Citus dans un environnement Data Engineering.

installation de PostgreSQL et de Citus.

---

# **Objectif : construire un mini Data Warehouse avec Citus.**


1. Installer PostgreSQL et Citus.
2. Créer une base dwh_ventes.
3. Créer les tables clients, commandes et ventes.
4. Choisir les clés de distribution.
5. Distribuer les tables avec Citus.
6. Importer un fichier CSV.
7. Réaliser des jointures et agrégations SQL.
8. Observer la répartition des shards.


**Documentation officielle : Créer et modifier des tables distribuées avec Citus** : https://learn.microsoft.com/en-us/postgresql/citus/reference-ddl?view=citus-14&utm_source=chatgpt.com

---

# **plan**

## 1. Environnement : 

- Docker (sur Windows)
- Ubuntu Server (Linux)
- PostgreSQL + DBeaver, sans Docker

## 2. Architecture


- Un seul serveur Citus pour commencer
- Un coordinateur et deux workers, comme GS2E


---

# Plan sélectionner : 

## Plan 1

- Docker (sur Windows) + - Un seul serveur Citus pour commencer

---

## Plan 2

- Docker (sur Windows) + - UUn coordinateur et deux workers, comme GS2E

---

## Plan 3

- Ubuntu Server (Linux) + Un seul serveur Citus pour commencer

---

## Plan 4

- Ubuntu Server (Linux) + Un coordinateur et deux workers, comme GS2E

---

## Plan 5

- PostgreSQL + DBeaver, sans Docker

---

## Plan 6

- PostgreSQL + DBeaver, avec Docker
-->


