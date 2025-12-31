# 🐳 Infrastructure WordPress avec Docker & Nginx

Ce projet déploie une solution WordPress complète et sécurisée en utilisant **Docker Compose**. Elle inclut un serveur web Nginx faisant office de reverse proxy.

## 🏗️ Architecture du Projet

```mermaid
graph TD
    User([Utilisateur]) -->|Port 80| Nginx[Serveur Nginx]
    subgraph Docker_Network [Réseau Docker]
        Nginx -->|Proxy| WordPress[Conteneur WordPress]
        WordPress -->|Lien| MariaDB[(Base de données MariaDB)]
    end
