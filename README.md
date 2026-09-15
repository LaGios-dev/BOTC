[![Release](https://img.shields.io/github/v/release/LaGios-dev/BOTC?color=blue&label=Release)](https://github.com/LaGios-dev/BOTC/releases/latest)
![Minecraft Version](https://img.shields.io/badge/Minecraft-1.20.1-brightgreen)
![Server Engine](https://img.shields.io/badge/Server-Paper%20%7C%20Purpur-blue)
![Java](https://img.shields.io/badge/Java-17%2B-orange)  
![Players](https://img.shields.io/badge/Players-5--15-8A2BE2)
![License](https://img.shields.io/badge/License-All%20Rights%20Reserved-red)
[![Discord](https://img.shields.io/badge/Discord-Playtest%20%26%20Support-5865F2?logo=discord&logoColor=white)](https://discord.gg/jvVhcMtA3h)

# Blood On The Clocktower (BOTC)

[FR]  
Ce plugin adapte le premier scénario **Trouble Brewing** du jeu de déduction sociale **Blood on the Clocktower** sur **Minecraft** en automatisant intégralement le rôle du Maître du Jeu.

[EN]  
This plugin adapts the first script, **Trouble Brewing**, from the social deduction game **Blood on the Clocktower** into **Minecraft**, fully automating the Storyteller role.
  
*Note: The plugin is currently available in French only (v1.0.0). However, English and other language localizations can be implemented if requested by the community, feel free to open a suggestion ticket on [GitHub Issues](https://github.com/LaGios-dev/BOTC/issues)!*

> [!IMPORTANT]
> 📖 **First time setting up the plugin or playing the game?**  
> Check out the **[Complete Setup & How to Play Guide](https://github.com/LaGios-dev/BOTC/blob/main/HOW_TO_PLAY.md)** for a full step-by-step tutorial (server hosting with playit.gg, proximity chat setup, and game rules).

---
## Sommaire / Contents
- **[Français](#fr)**
  - [Présentation du Jeu](#présentation-du-jeu)
  - [Fonctionnalités du Plugin](#fonctionnalités-du-plugin)
  - [Configuration](#configuration)
  - [Communauté et Amélioration](#communauté-et-amélioration)
- **[English](#en)**
  - [Game Overview](#game-overview)
  - [Plugin Features](#plugin-features)
  - [Settings](#settings)
  - [Community and Feedback](#community-and-feedback)
---

# FR

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

## Configuration

| Commande | Description |
| :--- | :--- |
| `/botc add <player>` | Ajoute un joueur à la liste des participants de la prochaine partie |
| `/botc kick <player>` | Retire un joueur de la partie en préparation |
| `/botc configset prepTime <value>` | Définit en secondes le temps entre le lancement de la partie et le début de la première nuit |
| `/botc configset actionTime <value>` | Définit en secondes le temps maximum d'interaction dans les GUI pour les pouvoirs nocturnes et les votes |
| `/botc configset dayTime <value>` | Définit en secondes le temps de la phase diurne |
| `/botc configset councilTime <value>` | Définit en secondes le temps des débats au Conseil |
| `/botc start` | Lance la partie (génère la composition et distribue les rôles) |

## Communauté et Amélioration

Si vous souhaitez améliorer ce plugin, un formulaire de report de bug et un formulaire de suggestions sont à votre disposition : [GitHub Issues](https://github.com/LaGios-dev/BOTC/issues).  
Rejoignez le [serveur Discord](https://discord.gg/jvVhcMtA3h) pour organiser des parties de playtest, poser vos questions ou faire vos retours.

---
# EN

## Game Overview

### Origin and Credits
Created by **Steven Medway** and published by [**The Pandemonium Institute**](https://bloodontheclocktower.com/) in 2022, Blood on the Clocktower has become an essential reference in modern social deduction games. The game revolutionizes the classic mechanics of this genre, notably by allowing eliminated players to keep talking and voting until the very end.

This adaptation is directly inspired by the format popularized by [**Fukano**](https://www.youtube.com/@FukanoLIVE), who brought the game to Minecraft by leveraging open-map movement and proximity voice chat.

### Game Rules
- **Objective:** Two opposing sides clash. Good players must unmask and execute the Demon. The Evil team must lie, sow chaos, and eliminate all the living Townsfolk.
- **No Vanilla Villagers:** Every single player possesses a unique role with distinct abilities.
- **Death is Not the End:** If you are killed, you are never out of the game. You become a Ghost: your role stays secret, you continue to actively debate on voice chat, and you retain one final, decisive vote.
- **Conspiracies & Proximity Chat:** During the Day phase, wander freely across the map to trade private whispers and forge secret alliances before the public Council gathering.
- **Deep Strategy & Misinformation:** No information is 100% reliable. Evil abilities can poison your senses, and one player (the Drunk) truly believes they are another Townsfolk and receives false info without knowing it. You must cross-reference deductions constantly to separate truth from deceit!
- **Bluffing is King:** The exact roster of roles in play is hidden from the players, giving the Demon and Minions total freedom to craft convincing fake identities.

## Plugin Features

This plugin specifically aims to fully automate the Storyteller (Game Master) role. It includes:
- Random setup generation
- Full ability interaction management
- Parallelized night phases to speed up the pace of the game
- Interactive GUI system for active abilities and casting votes
- Commands for spontaneous actions
- In-game guide book listing all available roles and their mechanics

## Settings

| Command | Description |
| :--- | :--- |
| `/botc add <player>` | Adds a player to the participant list for the upcoming game |
| `/botc kick <player>` | Removes a player from the game in preparation |
| `/botc configset prepTime <value>` | Sets the duration (in seconds) between game start and the first night |
| `/botc configset actionTime <value>` | Sets the maximum interaction time (in seconds) in GUIs for night actions and voting |
| `/botc configset dayTime <value>` | Sets the duration (in seconds) of the Day phase |
| `/botc configset councilTime <value>` | Sets the duration (in seconds) for Council debates |
| `/botc start` | Starts the game (generates the role composition and assigns roles) |

## Community and Feedback

The plugin is currently available **in French only**. However, if there is enough interest from the international community, a full localization update (English translations for GUIs, role books, and system messages) will gladly be prioritized!
If you would like to see this happen, please let me know by opening a suggestion ticket on [GitHub Issues](https://github.com/LaGios-dev/BOTC/issues).
