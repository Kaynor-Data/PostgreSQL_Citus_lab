# PostgreSQL_Citus_lab
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

