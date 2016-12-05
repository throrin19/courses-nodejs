# TP3 : Hapi

<center>
![hapi](../resources/hapi.jpg)
<br><br>
</center>

## Introduction

Hapi est un framework Node.JS développé par la société Wallmart et ayant comme philosophie que tout est plugin à l'intérieur des projets Hapi.

Hapi, tout comme ExpressJS ou Koa rajoute une surcouche au module Http pour permettre un meilleur découpage du code et une facilité de déclaration des différentes routes.

Avant de rentrer plus en détail avec un *boilerplate* tout prêt pour la suite des TP, vous avez, comme d'habitude, un tutoriel nodeschool pour bien comprendre son fonctionnement :

- Si vous n'avez pas eu le temps de le faire lors du TP1, je vous recommande vivement de faire `learnyounode` pour bien comprendre le fonctionnement de base de NodeJS et du module Http.
- `makemehapi`

## Boilerplate

Un boilerplate est un projet de base que vous prenez pour commencer un nouveau projet. Afin que tout le monde parte sur une base commune pour la suite des TP, vous devrez vous baser sur le boilerplate trouvable à cette adresse :

```
https://github.com/throrin19/hapi-boilerplate
```

Il est préférable, pour plus de facilité dans les TP futurs, de faire un fork de ce projet sur votre repository.

Vous trouverez toute la documentation quand à son fonctionnement directement sur son repo git.

### Plugins de base

Les plugins installés de base sur ce projet sont les suivants :

- **Good** : Permet de logger facilement du contenu au sein du serveur en lieu et place du traditionnel `console.log` : https://github.com/hapijs/good
- **Blipp** : Affiche dans la console, lors du démarrage du serveur, les routes disponibles : https://github.com/danielb2/blipp
- **Boom** : Permet d'uniformiser les retours d'erreur aux requêtes : https://github.com/hapijs/boom
- **Boom decorators** : Permet d'utiliser facilement Hapi Boom dans le projet : https://github.com/brainsiq/hapi-boom-decorators
