# TP 6 : Envoie d'email

<center>
![email](../../resources/email.jpg)
<br>
<br>
</center>

Dans le TP de cette semaine, vous allez voir comment envoyer un email à l'utilisateur selon les cas suivants :

- Lors de l'ajout pour lui donner ses informations de login et de mot de passe
- Lors de la modification si le login ou le mot de passe ont changé (juste un email lui disant que ses informations ont changées)
- Après avoir lancé une requête de récupération de mot de passe : Effectivement, vu que les mots de passe sont cryptés en BDD, vous devrez être en mesure de changer uniquement celui-ci via une route prévue à cet effet.
- Rajouter la route `/authent` prenant en `POST` les paramètres login/password et retournant `{ msg : 'ok' }` si les informations sont bonnes et `{ msg : 'ko' }` si les informations sont incorrectes.

<br>

Pour réaliser ces emails, vous allez utiliser les modules suivants :

- [`nodemailer`](https://community.nodemailer.com/) : library permetant d'envoyer facilement un ou plusieurs emails au travers de Node.JS
- [`mailgen`](https://github.com/eladnava/mailgen) : Moteur de templating d'email compatible tout client (ou presque).

<br>

**Attention** : Lors de l'édition de l'utilisateur (route `PUT`), si jamais le mot de passe n'est pas saisit ou bien s'il s'agit du mot de passe crypté, veillez à ne pas le recrypter sous peine de vous retrouver avec un résultat invalide en base de donnée.

**Attention** : Penser la partie d'envoie d'email (qui devrait être une fonction propre) réutilisable facilement et configurable via ses paramètres d'entrée vu que vous devrez en faire un service hapi indépendant au dernier TP.

## Compléments

Niveau organisation du code : Un handler/route pour une partie métier. Par exemple à partir de ce TP vous devriez avoir les routes et handlers suivants :
    - default
    - users
    - mails (uniquement en handler pour le moment)
