### Introduction

**LAMP** désigne un ensemble de 4 choses:
1) Linux
2) Un serveur web **Apache** 
3) My-sql
4) Le langage de programmation **php**

Ces 4 technologies forment une **pile** (stack en anglais) vous permettant l'hebergement de vos *sites* ou de vos *applications web dynamiques*.

Dans ce tuto, nous allons voir comment mettre en place ces 4 outils et installer PhpMyAdmin afin de gérer notre Base De Données grâce à une interface graphique.


### L'installation

## Etape 1: la mise à jour du système

Commençons par nous connecter à l'utilisateur "root" via la commande `su`.
Afin d'être sur que tous les packages puissent être installés, il faut mettre à jour votre système via cette commande:
`apt update && apt upgrade -y`

Maintenant, nous sommes sur qu'aucun problème en rapport avec des packages ne surviendra !


## Etape 2: créer un nouvel utilisateur avec les privilèges **sudo**

Pour des raisons pratiques mais également de sécurités, nous allons créer un nouvel utilisateur où nous gérerons et installerons notre serveur.
Pour créer l'utilisateur, il vous suffit de taper cette commande dans votre terminal:
`adduser mynewuser`
Ici, *mynewuser* sera notre nom d'utilisateur. Vous pouvez le remplacer par celui voulu.

Il vous sera demander plusieurs informations.
Certaines optionnelles tels que votre numéro de téléphone ou votre nom par exemple, d'autres seront obligatoires, votre mot de passe par exemple.

Une fois notre utilisateur crée, il nous faut le rajouter au groupe **sudo**.
Pour cela, tapez cette commande:
`usermod -aG sudo mynewuser`
*mynewuser* étant mon nom d'utilisateur, remplacez le par celui crée.

Enfin, connectons nous à ce compte grâce à cette commande:
`su - mynewuser`


## Etape 3: installation du serveur web **Apache**
