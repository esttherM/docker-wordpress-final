# 🐳 WordPress Dockerisé avec Nginx et MariaDB

Ce projet permet de déployer une infrastructure **WordPress** complète, sécurisée et isolée en utilisant **Docker Compose**. L'architecture repose sur un serveur Web **Nginx** servant de Reverse Proxy, un moteur **PHP 8.2** et une base de données **MariaDB**.

---

## 🏗️ Architecture du Projet

Le schéma ci-dessous illustre le flux de données entre l'utilisateur et les différents services Docker :

```mermaid
graph LR
    User((Utilisateur)) ---|Port 8085| Nginx[Serveur Nginx]
    
    subgraph Docker_Network [Réseau Interne Docker]
        Nginx ---|FastCGI:9000| WP[WordPress PHP-FPM]
        WP ---|MySQL:3306| DB[(MariaDB)]
    end

    style Nginx fill:#f9f,stroke:#333,stroke-width:2px
    style WP fill:#bbf,stroke:#333,stroke-width:2px
    style DB fill:#dfd,stroke:#333,stroke-width:2px
