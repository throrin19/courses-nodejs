<!-- $theme: gaia -->

# Node.JS

---
# Sommaire

1. Qu'est-ce que Node.JS
2. Utilisations
3. Gestionnaire de paquet et package.json
4. EventLoop
5. Plan de travail

---
# Qu'est-ce que Node.JS

- Javascript côté server
- Moteur V8 de Webkit
- Open Source
- Multiplateforme (ou presque)
- Mono thread
- Asynchrone
- I/O non bloqués

---
# Qu'est-ce que Node.js

- Versions standards et LTS
	![version](https://github.com/nodejs/LTS/raw/master/schedule.png)
    
---
# Qu'est-ce que Node.JS

- serveur http

```javascript
var http = require('http');

http.createServer(function (req, res) {
    res.writeHead(200, {'Content-Type': 'text/html'});
    res.end('Hello World!');
}).listen(8080);
```

---
Utilisation

- scripts bash
- compilations diverses (babel, ...)
- applications multiplateformes desktop (electron, NW)
- applications mobiles (react-native, ionic, native-script)
- serveurs web (express, hapi, koa)

---
# Gestionnaire de paquets

- NPM
	- officiel
	- npmjs.org

```
npm install -S hapi
```

- Yarn
	- facebook
	- plus rapide

```
yarn add hapi
```

---
# Package.json

- coeur de l'application
- paquets utilisés
- commandes de lancement
- version Node.JS requise

---

```
{
  "private": true,
  "name": "Test APP",
  "description": "This is an example package.json",
  "version": "0.0.0-this-does-not-matter",
  "license": "MIT",
  "scripts": {
    "dev": "npx poi",
  },
  "devDependencies": {
    "less": "2.7.2",
    "less-loader": "4.0.5",
  },
  "dependencies": {
    "lodash": "4.17.4",
    "moment": "2.18.1",
  }
}

```
---
# EventLoop

```
   ┌───────────────────────┐
┌─>│        timers         │
│  └──────────┬────────────┘
│  ┌──────────┴────────────┐
│  │     I/O callbacks     │
│  └──────────┬────────────┘
│  ┌──────────┴────────────┐
│  │     idle, prepare     │
│  └──────────┬────────────┘      ┌───────────────┐
│  ┌──────────┴────────────┐      │   incoming:   │
│  │         poll          │<─────┤  connections, │
│  └──────────┬────────────┘      │   data, etc.  │
│  ┌──────────┴────────────┐      └───────────────┘
│  │        check          │
│  └──────────┬────────────┘
│  ┌──────────┴────────────┐
└──┤    close callbacks    │
   └───────────────────────┘
```
---
# EventLoop
   
   - **timers** : lance les callbacks programmés par `setTimeout` et `setIntervale`
   - **I/o callbacks** : lance tous les autres callbacks
   - **idle, prepare** : utilisé par le coeur de Node.JS
   - **poll** : Créer de nouveauc événements d'entrée/sortie. Le cas échéant, peut bloquer l'exécution du script.
   - **check** : invoque les callbacks de `setImmediate`
   - **close callbacks** : `socket.on('close')`, ...

---
# EventLoop

- **Attention** : tous les callbacks ne sont pas asynchrones de base :

```javascript
const a = [1, 2, 3, 4];

a.forEach((value) => {
    console.log(value);
});

console.log('after forEach');
```
- Les fonctions des types de base (String, Object, Array, ...) sont toujours synchrones.

---
# EventLoop

