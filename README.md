[![Release](https://img.shields.io/github/v/release/LaGios-dev/BOTC?color=blue&label=Release)](https://github.com/LaGios-dev/BOTC/releases/latest)
![Minecraft Version](https://img.shields.io/badge/Minecraft-1.20.1-brightgreen)
![Server Engine](https://img.shields.io/badge/Server-Paper%20%7C%20Purpur-blue)
![Java](https://img.shields.io/badge/Java-17%2B-orange)
![License](https://img.shields.io/badge/License-All%20Rights%20Reserved-red)
[![Discord](https://img.shields.io/badge/Discord-Playtest%20%26%20Support-5865F2?logo=discord&logoColor=white)](https://discord.gg/jvVhcMtA3h)

# Blood On The Clocktower (BOTC)

Ce plugin adapte le premier scénario **Trouble Brewing** du jeu de déduction sociale **Blood on the Clocktower** sur **Minecraft** en automatisant intégralement le rôle du Maitre du Jeu

## Sommaire

- [Présentation du Jeu](#présentation-du-jeu)
- [Fonctionnalités du Plugin](#fonctionnalités-du-plugin)
- [Installation et Prérequis](#installation-et-prérequis)
- [Configuration](#configuration)
- [Communauté et Amélioration](#communauté-et-amélioration)

## Présentation du jeu

### Origine et Crédits
Créé par **Steven Medway** et édité par [**The Pandemonium Institute**](https://bloodontheclocktower.com/) en 2022, Blood on the Clocktower est devenu la référence incontournable du jeu de déduction sociale moderne. Le jeu révolutionne les mécaniques classiques de ce type de jeux en permettant notamment aux joueurs éliminés de continuer à parler et voter jusqu'au bout.

Cette adaptation s'inspire directement du format popularisé par [**Fukano**](https://www.youtube.com/@FukanoLIVE), qui a transposé le jeu sur Minecraft en tirant parti du déplacement libre sur la carte et du chat vocal de proximité.

### Règles du jeu
- **Objectif :** Deux camps s'affrontent. Les Humains doivent démasquer et exécuter le chef des Démons. Les Démons, eux, doivent mentir, semer le chaos et éliminer tous les Humains.
- **Fini le Simple Villageois :** Ici, tout le monde possède un rôle unique avec des pouvoirs spécifiques.
- **La mort n'est plus une fin :** Si vous êtes tué, vous n'êtes pas éliminé. Vous devenez un Fantôme : votre rôle reste secret, vous continuez de participer aux débats, et vous conservez un vote ultime et décisif.
- **Complots et Chat de proximité :** Pendant la phase de Jour, vous vous déplacez librement sur la carte. C'est le moment d'échanger des informations en privé et de créer des alliances secrètes avant le grand Conseil public.
- **Un jeu beaucoup plus stratégique :** Aucune information n'est fiable à 100%. Les Démons peuvent empoisonner vos capacités, et un joueur (l'Ivrogne) se prend carrément pour un rôle qu'il n'est pas et reçoit de fausses informations sans le savoir. Il faudra croiser vos déductions en permanence pour démêler le vrai du faux !
- **Le bluff est roi :** Les rôles présents dans la partie ne sont pas connus par les joueurs. Les Démons ont donc une liberté totale pour s'inventer une fausse identité.

## Fonctionnalités du Plugin

Ce plugin tout particulièrement vise à automatiser la tâche de Maître du jeu. C'est à dire :
- Génération de composition aléatoire
- Gestion de toutes les interactions entre les capacités de chaque rôle
- Parallélisation des pouvoirs nocturnes sans dépendances pour une accélération du rythme
- Système de GUI pour l'utilisation des capacités actives et pour les votes au Conseil
- Commandes pour actions spontanées comme le fait de nommer un joueur au vote ou de pourfendre un joueur
- Présence sur commande d'un livre listant tous les rôles du jeu et leurs particularités

## Installation et Prérequis

### Prérequis Serveur
- **Moteur :** [Paper](https://papermc.io/) ou [Purpur](https://purpurmc.org/)
- **Version Minecraft :** `1.20.1`
- **Java :** Version `17` ou supérieure

### Plugins Recommandés / Dépendances
- **Obligatoire pour l'immersion :** [Simple Voice Chat](https://modrinth.com/plugin/simple-voice-chat) *(nécessaire pour le chat de proximité)*

### Installation
1. Téléchargez la [dernière version](https://github.com/LaGios-dev/BOTC/releases/latest) du plugin.
2. Glissez le fichier dans le dossier `/plugins/` de votre serveur.
3. Redémarrez le serveur.

## Configuration

| Commande | Description |
| :--- | :--- |
| `/botc add <pseudo>` | Ajoute un joueur à la liste des participants de la prochaine partie |
| `/botc kick <pseudo>` | Retire un joueur de la partie en préparation |
| `/botc configset prepTime <value>` | Définit en secondes le temps entre le lancement de la partie et le début de la première nuit |
| `/botc configset actionTime <value>` | Définit en secondes le temps maximum d'interaction dans les GUI pour les pouvoirs nocturnes et les votes |
| `/botc configset dayTime <value>` | Définit en secondes le temps de la phase diurne |
| `/botc configset councilTime <value>` | Définit en secondes le temps des débats au conseil |
| `/botc start` | Lance la partie (génère la composition et distribue les rôles) |

les autres commandes admin sont plutot orientées tests et debug

## Communauté et Amélioration

Si vous souhaitez améliorer ce plugin, un formulaire de report de bug et un formulaire de suggestions sont à votre disposition.  
Rejoignez le [serveur Discord](https://discord.gg/jvVhcMtA3h) pour organiser des parties de playtest, poser vos questions ou faire vos retours.
