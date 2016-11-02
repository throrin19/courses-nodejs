# TP 1 : Introduction

<center>
![yknjs](/resources/yknjs.jpg)
<br>
<br>
</center>

Tous les TP se présenteront de la manière suivante :

+ Une introduction de la technologie/module utilisés sur le TP via l'utilisation des cours fournis par nodeschool.io.
+ Un projet à réaliser durant toute la durée du module.

Ce TP a pour but de faire un rappel bref aux base javascript pour la partie ES6, asynchrone et clojures.
Vous verrez ensuite l'utilisation de l'éditeur Webstorm.

**Attention** : tous les TP seront fait sur la dernière version LTS (long support) de NodeJS disponible. Il s'agit de la version `6.9.1` au moment de la rédaction de ce TP.

```
nvm install v6.9
nvm use v6.9
```

Dans le doute, pensez à mettre cette version en version par défaut :

```
nvm alias default v6.9
```

## NodeSchool.io

Le site [nodeschool.io](https://nodeschool.io/fr-fr/) répertorie plusieurs exercices interractifs afin de vous apprendre l'utilisation d'un concept, d'un module nodeJS ou d'une technologie javascript directement dans votre terminal.

Pour tous les "turorials", vous aurez une *installation globale* d'un module nodeJS à installer sur votre poste de la manière suivante :

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

**Attention** : De base, les "tutoriels" sont en anglais. Heureusement, ceux que vous ferez au travers de ces TP sont disponibles en français. Pensez-bien à changer la langue si celle de Shakespear vous rebute un peu.

## ES6, Asynchrone et Clojures

Nous allons commencer ce TP avec la réalisation des *tutoriels* suivants :

- `javascripting` : Si vous voulez vous rappeler les bases du développement javascript, faites le, sinon passez au suivant.
- `scope-chains-closures` : Apprenez le détaildes Scope, Scope Chains, Closures, et Garbage Collection.
- `count-to-6` : Apprenez comment utiliser les caractéristiques de ES6.
- `learnyounode` : Apprenez les bases de node : asynchronous i/o, http.

Tous ces tutoriels vous serviront à comprendre le fonctionnement fondamental de javascript et de Node.JS e, bien entendu, ils sont nécessaires pour la suite du module.

## Webstorm

Webstorm est l'un des IDE fournit par Jetbrains. Bien entendu, vu la base qu'ont tous les éditeurs de Jetbrains, cette partie marchera aussi, dans les grandes lignes, pour PHPstorm, Pycharm, ...

### Installation

Pour l'installation/lancement de Webstorm, je vous conseille de passer par le logiciel JetBrains toolbox permettant de facilement accéder à un projet particulier mais aussi de gérer l'installation/maj/lancement de tous les éditeurs que Jetbrains fournit.

Vous trouverez la toolbox via le lien suivant :

```
https://www.jetbrains.com/toolbox/app/
```

**Attention** : Selon votre système d'exploitation, l'installation de la toolbox n'est pas du tout la même partout. Je pars du principe que vous savez installer une application sous Windows, Linux, macOS sans aucun problème.

<center>
![hackerman](/resources/hackerman.tb.jpg)
<br>
<br>
</center>

Ensuite quand vous lancez la toolbox, voud devriez avoir cette fenêtre :

<center>
![toolbox](/resources/tp1/toolbox-001.png)
<br>
<br>
</center>

Vous n'avez plus qu'à installer le(s) éditeur(s) de votre choix. Dans notre cas : **Webstorm**.

### Utilisation

Pour l'utilisation de webstorm, dans le cadre du projet du TP, je vous conseille de commencer par un *empty project* :

<center>
![toolbox](/resources/tp1/webstorm-001.png)
<br>
<br>
</center>

Et là, vous devriez arriver sur la fenêtre suivante :

<center>
![toolbox](/resources/tp1/webstorm-002.png)
<br>
<br>
</center>

1. Barre de contrôle pour créer un fichier, accéder aux settings, ...
2. Fenêtre d'exploration du projet.
3. Barre de lancement de votre application et de debug.
4. Barre d'accès aux différents outils (terminal, VCS, ...)
5. Fenêtre d'édition

### Réglages de base pour un projet NodeJS :

1. Allez dans les Settings (**File => Default Settings...**)
2. Allez dans l'onglet **Languages and Frameworks => Javascript**.
3. Passez *Javascript language version* à **ECMAScript 6**.
4. Cochez **Prefer Strict Mode**
5. Allez dans **Languages and Frameworks => Node.JS and NPM**.
6. Choisissez le binaire de node v6.9.1 qui devrait être dans `~/.nvm/versions/node/v6.9.1/bin/node`
7. Activez l'assistance du code de Node.JS
8. Appliquez les changements

Normalement après ces réglages par défaut, tous vos projets devraient prendre en compte ES6 et nodeJS 6.9.1
