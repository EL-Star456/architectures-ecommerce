# Architectures logicielles · Étude de cas e-commerce

Quatre travaux pratiques pour comparer différentes façons de structurer une application e-commerce. Le dépôt contient le code source et les rapports de chaque TP.

| TP | Architecture | À explorer | Rapport |
| --- | --- | --- | --- |
| 1 | Monolithe simple | API de catalogue avec Java 21, Spring Boot, Gradle et PostgreSQL | [PDF](TP1_Monolithe_Simple/TP1_Log.pdf) |
| 2 | Monolithe modulaire | Organisation du code par modules dans une seule application Spring Boot | [PDF](TP2_Monolithe_Modulaire/TP2_Log.pdf) |
| 3 | Architecture distribuée | Deux instances Node.js derrière Nginx, avec MongoDB, Redis et RabbitMQ | [PDF](TP3_Architecture_Distribuee/TP3_Log.pdf) |
| 4 | Architecture orientée services | Services produits et commandes distincts, avec Spring Boot et Eureka | [PDF](TP4_Architecture_SOA/TP4_Log.pdf) |

## Lancer la démonstration du TP 3

Prérequis · Docker et Docker Compose. Depuis la racine du dépôt, dans un terminal PowerShell, Bash ou zsh :

```sh
cd TP3_Architecture_Distribuee/code
docker compose up --build -d
docker compose ps
```

Ouvrir [l’état de l’API](http://localhost/health) puis [la liste des commandes](http://localhost/commandes). Les deux requêtes passent par Nginx. Redis sert de cache pour la lecture des commandes, et MongoDB stocke les données. RabbitMQ intervient dans le traitement asynchrone.

Pour arrêter la démonstration, exécuter `docker compose down` depuis le même dossier.

## Code source

- [TP 1 · Monolithe simple](TP1_Monolithe_Simple/code)
- [TP 2 · Monolithe modulaire](TP2_Monolithe_Modulaire/code/tp2)
- [TP 3 · Architecture distribuée](TP3_Architecture_Distribuee/code)
- [TP 4 · Services et découverte](TP4_Architecture_SOA/code)
