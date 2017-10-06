# TP 1 : Introduction

<center>
![yknjs](/resources/yknjs.jpg)
<br>
<br>
</center>

Tous les TP se présenteront de la manière suivante :

+ Une introduction de la technologie/module utilisés sur le TP via l'utilisation des cours fournis par nodeschool.io.
+ Un projet à réaliser durant toute la durée du module.

Ce TD réalise les objectifs suivants :

- Installation de NVM
- Prise en main de nodeschool.io
- Revue des bases de Javascripts et des normes ES6
- Installation de l'environnement de développement
- Utilisation du debugger

## Installation de NVM

Selon que vous êtes sous Linux/Mac ou Windows, l'installation sera quasiment identique. Sauf que pour windows, vous devez **absolument** passer par le bash Ubuntu. Je prends pour acquis que tout le monde est sur une base Linux/MacOS n'ayant pas de post windows à disposition.

Pour l'installation de nvm, je vous recommande de voir tout ce qui est indiqué sur le sujet directement sur le site du projet : https://github.com/creationix/nvm

**Attention** : tous les TP seront fait sur la dernière version LTS (long support) de NodeJS disponible. Il s'agit de la version `8.6.0` au moment de la rédaction de ce TD.

```
nvm install v8
nvm use v8
```

Dans le doute, pensez à mettre cette version en version par défaut :

```
nvm alias default v8
```

## NodeSchool.io

Le site [nodeschool.io](https://nodeschool.io/fr-fr/) répertorie plusieurs exercices interractifs afin de vous apprendre l'utilisation d'un concept, d'un module nodeJS ou d'une technologie javascript directement dans votre terminal.

Pour tous les "turoriels", vous aurez une *installation globale* d'un module nodeJS à faire sur votre poste de la manière suivante :

```
npm install -g <module>
```

Et pour le lancer, vous aurez juste la commande suivante à taper :

```
<votremodule>
```

Normalement vous devriez arriver sur un écran de ce genre :

<center>
![nodeschool-001](/resources/tp1/nodeschool-001.png)
<br>
<br>
</center>

**Attention** : De base, les "tutoriels" sont en anglais. Heureusement, ceux que vous ferez au travers de ces TP sont disponibles en français (sauf rares exceptions). Pensez-bien à changer la langue si celle de Shakespear vous rebute un peu.

## ES6, Asynchrone et Clojures

Nous allons commencer ce TP avec la réalisation des *tutoriels* suivants :

- `javascripting` : Si vous voulez vous rappeler les bases du développement javascript, faites le, sinon passez au suivant.
- `scope-chains-closures` : Apprenez le détail des Scope, Scope Chains, Closures, et Garbage Collection.
- `learnyounode` : Apprenez les bases de node : asynchronous i/o, http.
- `async-you` : Appenez à utiliser la library async.
- `count-to-6` : Apprenez comment utiliser les caractéristiques de ES6.

Tous ces tutoriels vous serviront à comprendre le fonctionnement fondamental de javascript et de Node.JS ,et , bien entendu, ils sont nécessaires pour la suite du module.

## Atom

Atom est un éditeur développé par gitHub et tournant sous Electron. Ce qui veut dire qu'il tourne grâce à NodeJS. Quoi de plus normal de développer du NodeJS sur un éditeur codé avec la même chose ?
Vous trouverez l'installateur d'Atom à cette adresse : https://atom.io/

### Plugins de base

De base, Atom est assez sommaire et aussi basique que gEdit. Afin de l'enrichir, vous devrez installer des modules complémentaires. Nous allons installer tous ceux qu'il vous faut afin d'avoir un environnement au poil.

Pour celà allez dans les préférences (`CTRL` + `,`) puis dans la rubrique `install` et installez les packages suivants :

- advanced-open-file
- atom-ide-ui
- auto-update-plus
- autocomplete-modules
- emmet@2.4.3
- file-icons
- git-plus
- git-time-machine
- ide-json
- ide-typescript
- linter-eslint
- linter-npm-missing
- open-recent
- platformio-ide-terminal

Normalement après ceci vous devriez avoir tout de fonctionnel pour les TPs à venir.


### Lancement de son application

Vous allez créer dans votre projet un fichier `server.js` contenant le code suivant :

```javascript
'use strict';

const http = require('http');

let server = http.createServer((request, response) => {
  response.writeHead(200, {"Content-Type": "text/plain"});
  response.end("Hello World\n");
});

server.listen(8000);

console.log("Server running at http://127.0.0.1:8000/");
```

1. Dans la barre de lancement de votre application, cliquez sur la flèche descendante puis sur *Edit configuration*.
2. Cliquez sur l'icône **+** puis sur **Node.js**
3. Dans la ligne *Node Interpreter*, vérifiez que vous êtes bien sur la v6.9.1 sinon mettre le bon chemin (`~/.nvm/versions/node/v6.9.1/bin/node`)
4. Dans *Working directory*, ciblez votre projet
5. Dans *Javascript File*, mettez bien `server.js`.
6. Mettez le nom que vous voulez dans *Name*.
7. Validez

Vous devriez normalement vous retrouver avec ceci :

<center>
![toolbox](/resources/tp1/webstorm-003.png)
<br>
<br>
</center>

+ Le bouton *play* représenté par la flèche verte sert à lancer l'application normalement.
+ Le bouton *Debug* représenté par l'insect vert permet de lancer l'application en mode Debug (merci captain Obvious).

La partie Debug sera traité dans un TP propre plus tard. Pour le moment clquez uniquement sur la flèche verte. Vous devriez voir une fenêtre s'ouvrir avec la phrase "Server running at http://127.0.0.1:8000/".

Et si vous ouvrez le navigateur pour aller à l'adresse indiquée, vous devriez avoir le message "Hello World".
