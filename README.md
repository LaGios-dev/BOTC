[![Release](https://img.shields.io/github/v/release/LaGios-dev/BOTC?color=blue&label=Release)](https://github.com/LaGios-dev/BOTC/releases/latest)
![Minecraft Version](https://img.shields.io/badge/Minecraft-1.20.1-brightgreen)
![Server Engine](https://img.shields.io/badge/Server-Paper%20%7C%20Purpur-blue)
![Java](https://img.shields.io/badge/Java-17%2B-orange)  
![Players](https://img.shields.io/badge/Players-5--15-8A2BE2)
![Languages](https://img.shields.io/badge/Languages-English%20%7C%20French-db2777)
![License](https://img.shields.io/badge/License-All%20Rights%20Reserved-red)
[![Discord](https://img.shields.io/badge/Discord-Playtest%20%26%20Support-5865F2?logo=discord&logoColor=white)](https://discord.gg/jvVhcMtA3h)

# Blood On The Clocktower (BOTC)

This plugin adapts the first script, **Trouble Brewing**, from the social deduction game **Blood on the Clocktower** into **Minecraft**, fully automating the Storyteller role.

> [!IMPORTANT]
> 📖 **First time setting up the plugin or playing the game?**  
> Check out the **[Complete Setup & How to Play Guide](https://github.com/LaGios-dev/BOTC/blob/main/HOW_TO_PLAY.md)** for a full step-by-step tutorial (server hosting with playit.gg, proximity chat setup, and game rules).

---
## Contents
- [Game Overview](#game-overview)
- [Plugin Features](#plugin-features)
- [Settings](#settings)
- [Community and Feedback](#community-and-feedback)

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

## Commands & Configuration

### Storyteller (Admin/OP) Setup Commands
| Command | Description |
| :--- | :--- |
| `/botc add <player>` | Adds a player to the participant list for the upcoming game |
| `/botc kick <player>` | Removes a player from the preparation list |
| `/botc configset prepTime <seconds>` | Sets the duration between game start and the first night |
| `/botc configset actionTime <seconds>` | Sets the maximum GUI interaction time allowed for night actions and voting |
| `/botc configset dayTime <seconds>` | Sets the duration of the Day phase |
| `/botc configset councilTime <seconds>` | Sets the duration of Council debates and nominations |
| `/botc configset language <en/fr>` | Changes the game language (**English** or **French**) |
| `/botc start` | Starts the game (generates composition and secretly assigns roles) |
| `/botc stop` | Ends the game prematurely and resets the game state |

### Player Commands (In-Game)
| Command | Description |
| :--- | :--- |
| `/botc roles` | Gives you the in-game role guide book |
| `/botc nominate <player>` | Nominates the target player for execution (Council phase only) |
| `/botc slay <player>` | Publicly attempts to strike down the target (Council phase only). Instantly kills them if they are the Demon (only effective for the Slayer, but can be bluffed once per game by anyone) |

### Admin/OP Debugging & Testing Commands
| Command | Description |
| :--- | :--- |
| `/botc fake <name1> <name2> ...` | Add fake players to easily test setups with fewer people |
| `/botc setrole <player> <role>` | Manually assigns a specific role to a player |
| `/botc list` | Displays real-time game status (players, roles, poisoned/drunk states, protections, alive status) |
| `/botc review` | Gives the post-game summary review book at any time |

## Community and Feedback

If you wish to help improve this plugin, feel free to report issues or suggest new features via [GitHub Issues](https://github.com/LaGios-dev/BOTC/issues).

Join our [Discord Server](https://discord.gg/jvVhcMtA3h) to organize playtests, ask questions, or share your feedback directly with the team!
