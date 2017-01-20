# Présentation du projet et Mongoose

Avant de commencer le TP, voici ce que vous allez faire durant les 4 dernières semaines ensembles :

- TP 5 (celi-ci) :
    - Réaliser une API gérant des utilisateurs (ajout, modification, suppression, listage et récupération) au travers d'HAPI
    - Gestion de la persistance des données avec Mongoose
- TP 6 :
    - Envoi, par email à l'utilisateur, de ses identifiants de connexion à la création
    - Ajout d'un moteur de récupération de mot de passe
- TP 7 (sera plus un cours qu'un TP):
    - Présentation du debugger dans webstorm
    - Présentation des différents modes de mise en production
- TP 8 :
    - Présentation de Socket.io
    - Séparation en deux projets distincts la partie gestion des utilisateurs et envoie d'emails (approche micro-services)

Vous devrez donc avoir, à la fin de ces TP, deux projets présents sur Github que vous devrez me donner (avec le lien de chacun d'eux) afin que je puisse vous noter dessus.
La note prend en compte le fonctionnement des projets ainsi que l'organisation/apparence du code (bon respect du const/var/let, initialisation des plugins au bon endroit, ...)

Les TPs que vous allez avoir à partir de celui-ci seront que d'un seul par semaine englobant les deux séances que l'on a ensemble.

## Mongoose

Mongoose est une surcouche à MongoDB pour Node.JS permettant de valider ses données par rapport à des schémas préalablement définits.

Afin d'utiliser convenablement mongoose au sein d'Hapi et de pouvoir gérer facilement les connexions, nous allons passer par les modules `k7` et `k7-mongoose`. Si vous regardez bien `k7`, il s'agit en fait d'un client permettant de gérer de manière transparente, à la configuration, différents moteurs de base de donnée et d'en changer quand bon vous semble (à la manière de PDO en PHP).
