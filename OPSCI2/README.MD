### Etudiant : Kada ZIZANI 28708212

# Projet de Système Résilient avec Docker et Apache Kafka

## Description du Projet

Ce projet implémente un système résilient pour la gestion de grandes quantités de données issues de différents flux, utilisant Docker et Apache Kafka comme pierre angulaire. Kafka, en tant que message broker robuste, coordonne la communication entre plusieurs services pour assurer une efficacité optimale.

## Architecture de l'Application

Le système est composé de plusieurs conteneurs Docker configurés pour les différents composants de notre application :

- **Kafka** : Accessible via les ports `kafka:9092` ou `kafka:9093`.
- **Zookeeper** : Accessible via `zookeeper:2181`.
- **StrapiDB** : Base de données pour Strapi, accessible sur `localhost:5432`.
- **Strapi** : Application Strapi accessible sur `localhost:1337`.
- **db-dump** : Conteneur pour les sauvegardes de la base de données.
- **product-producer/consumer** : Conteneurs qui produisent et consomment des données relatives aux produits.
- **event-producer/consumer** : Conteneurs qui gèrent les événements associés aux produits.
- **stock-producer/consumer** : Conteneurs qui gèrent les stocks des produits.

## Configuration de Kafka

Les topics Kafka suivants ont été configurés pour assurer une communication efficace entre les producers et les consumers :

- **product** : Dédié à la création de nouveaux produits en masse.
- **event** : Dédié à la gestion des événements associés aux produits.
- **stock** : Utilisé pour enregistrer et gérer les mouvements de stock des produits.

Il est crucial que les noms des topics soient identiques dans les configurations de tous les producers et consumers pour garantir une communication sans faille.

## Démarrage du Projet

Pour démarrer le système, exécutez la commande suivante à la racine du projet :
```bash
docker-compose up -d

