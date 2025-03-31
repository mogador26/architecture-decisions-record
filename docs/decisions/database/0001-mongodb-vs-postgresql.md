# Choix de MongoDB par rapport à PostgreSQL

## Statut

Brouillon

## Date

2025-03-24

## Participants

- équipe produit SIAF

## Contexte et Problème

Le projet actuel implique la reprise d'une base de données existante qui utilise PostgreSQL. Cette base de données relationnelle a été conçue pour stocker des informations bien structurées et interconnectées, mais la structure du modèle de données ne montre pas d'utilisation de clés étrangères entre les tables.

Toutefois, avec l'évolution du projet, de nouveaux besoins sont apparus :

**Flexibilité du schéma** : les données deviennent plus hétérogènes et requièrent une structure plus souple.

**Scalabilité** : besoin d'une montée en charge horizontale efficace.

**Performance sur des données semi-structurées** : forte présence de données JSON imbriquées et variabilité dans les attributs.

## Options Considérées

Continuer avec PostgreSQL, en exploitant JSONB pour stocker des documents semi-structurés.

Migrer vers MongoDB, une base de données NoSQL orientée document.

## Décision

Nous avons décidé d'adopter MongoDB comme nouvelle base de données principale pour les raisons suivantes :

**Flexibilité du schéma** :

MongoDB permet de stocker des documents JSON sans schéma fixe, facilitant l'adaptation aux évolutions des données.

PostgreSQL supporte JSONB, mais impose des contraintes supplémentaires pour l'indexation et la requête.

**Scalabilité horizontale** :

MongoDB est conçu pour une scalabilité horizontale native via le sharding.

PostgreSQL se scale principalement verticalement et requiert des solutions externes (ex: Citus) pour une répartition efficace.

**Performance pour les données semi-structurées** :

MongoDB optimise l'indexation et les recherches sur des structures JSON imbriquées.

PostgreSQL demande une configuration avancée pour obtenir des performances similaires sur de gros volumes de JSONB.

**Modélisation des données imbriquées** :

Dans MongoDB, les relations peuvent être gérées via des documents imbriqués plutôt que des jointures complexes.

PostgreSQL exige des jointures qui peuvent dégrader la performance lorsque les relations sont nombreuses.

## Conséquences

**Migration des données** :

Une phase de transformation sera nécessaire pour adapter les données relationnelles à un modèle document.

**Compétences et outillage** :

L'équipe devra monter en compétence sur MongoDB. Une petite attention toutefois, MongoDB n'est plus inscrit au [SILL](https://code.gouv.fr/sill).


**Simplicité d'évolution** :

Ajout de nouvelles données plus rapide sans modification du schéma global.





## Liens et Références

[Documentation PostgreSQL sur JSONB](https://www.postgresql.org/docs/current/datatype-json.html)

[Documentation MongoDB](https://www.mongodb.com/docs/)