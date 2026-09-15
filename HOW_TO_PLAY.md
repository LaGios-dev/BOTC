# HOW TO PLAY BOTC

## Contents
- [Game Rules](#game-rules)
- [Complete Setup Guide](#complete-setup-guide)
  - [Server Side](#server-side)
  - [Client Side](#client-side)
- [Host a Game](#host-a-game)

---

## Game Rules

Blood on the Clocktower is a game of murder, deception, logic, and deduction for **5 to 15 players**. The Storyteller role is completely automated by the plugin.

### 1. Teams & Objectives

Every player is secretly assigned a character belonging to one of two teams:

#### 🟢 The Good Team
* **Townsfolk (Citadins):** Good players with beneficial abilities used to gather information, protect villagers, or counter evil.
* **Outsiders (Étrangers):** Good players whose abilities cause negative drawbacks or introduce confusion to the village.
* **Objective:** Find and execute the **Imp** during the daily Town Council vote.

#### 🔴 The Evil Team
* **Minions (Sbires):** Evil players who know the Imp's identity. Their job is to disrupt good abilities, mislead debates, and shield their leader.
* **The Imp (Diablotin):** The head of the evil faction. Strikes and kills one player each night.
* **Objective:** Achieve numerical superiority (living Evil players outnumber living Good players).

> 💡 **Role Guide:** Exact abilities and role interactions are detailed in-game in your **Role Guide Book** (use `/botc roles`).

---

### 2. The Game Cycle

The game alternates between two main phases: **Night** and **Day**.

```
     ┌─────────────────────────┐
     ▼                         │
 [ Night ] ──► [ Day ]  ──► [ Council ]
(Abilities)   (Whispers)    (Executions)
```

#### 🌙 Phase 1: The Night
1. Players must return to their personal houses.
2. The plugin opens private **GUI menus** for characters whose abilities wake up during the night.
3. Make your choice before the interaction timer runs out (`actionTime`). Independent night actions run in parallel to keep nights fast.
4. Any clues, visions, or night feedback are delivered to you privately in the chat.

#### ☀️ Phase 2: The Day (Whispers & Investigation)
1. The sun rises, reveals who died during the night, and players are free to move.
2. Use **Simple Voice Chat** to roam the village, form private circles, whisper secrets, test alibis, or spread misinformation.
3. **Keep an ear out:** Anyone can lie about who they are and what information they received!

#### ⚖️ Phase 3: The Town Council (Accusations & Execution)
1. When the day timer expires, all players gather at the central Council area.
2. **Public Debate:** Players share clues, cross-reference stories, and accuse suspects.
3. **Nominations:** Any living player can publicly nominate a suspect for execution using:
   ```text
   /botc nommer <playername>
   ```
4. **Voting (GUI):** When a nomination opens, an interactive voting interface appears for eligible players to cast their vote (*Yes* or *No*).
5. If an accused player receives a majority of votes among living players (and exceeds any prior nomination that day), they are **executed** at the end of the day.

---

### 3. Core Mechanics

#### 👻 Death is Not Elimination (The Ghost System)
* When you die, your role is **never revealed**.
* You become a **Ghost**: you continue to roam, discuss, share theories, and participate fully in debates on proximity voice chat.
* **Ghost Vote Token:** Every dead player keeps **one single vote token** for the remainder of the game. Use it wisely, as dead votes often decide the fate of the living!

#### 🍷 Poison & Drunkenness (Misinformation)
* Information in Blood on the Clocktower is **never guaranteed to be 100% true**.
* A **Poisoner (Empoisonneur)** can poison an ability, forcing the plugin to return false or arbitrary results to the target.
* The **Drunk (Ivrogne)** genuinely believes they are a specific Townsfolk, but secretly receives inaccurate information from the plugin.

#### 🎭 Bluffing & Deduction
* The exact list of roles in play is kept secret. Good players must deduce which characters actually exist, while Evil players are free to fabricate fake claims to blend in.

---

### 4. Player Commands

| Command | Role / Phase | Description |
| :--- | :--- | :--- |
| `/botc roles` | Any | Gives you the in-game role manual listing every character in the edition |
| `/botc nommer <player>` | Council Phase | Nominates the specified player for execution |
| `/botc pourfendre <player>` | Council Phase | Publicly attempts to strike down the target. Kills them instantly if they are the Demon (only effective for the Slayer, but can be bluffed by any player once per game) |

---

## Complete Setup Guide

### Server Side

#### 1. Create the Server
1. Create a dedicated empty folder on your machine to host the server.
2. Download the [Paper build for version 1.20.1](https://fill-ui.papermc.io/projects/paper/version/1.20.1), place it in your folder, and rename it to `server.jar`.
3. In the same folder, create a file named `start.bat` with the following content:
   ```bat
   @echo off
   java -Xms2G -Xmx4G -jar server.jar nogui
   pause
   ```
4. Run `start.bat` once to generate server files, open `eula.txt`, change `eula=false` to `eula=true`, and save.

#### 2. Install Plugins & Map
1. Download both the [BOTC plugin](https://github.com/LaGios-dev/BOTC/releases/latest) and [Simple Voice Chat (Paper 1.20.1)](https://modrinth.com/plugin/simple-voice-chat?version=1.20.1&loader=paper#download), then place them into the `/plugins/` folder.
2. *(Optional)* If using a custom village map, delete the generated `world` folders, paste your map folder, and rename it to `world`.  
*Note: If any builders want to create an official map for the project, reach out to me on Discord!*
3. Run `start.bat` to generate the default configuration files. Once the console displays `Done!`, type `stop` and press Enter to shut down cleanly.

#### 3. Configure Network Tunnels (playit.gg)
1. Download and run [playit.gg](https://playit.gg/download/).
2. Link the agent to your account via the terminal link, or manage it directly on the [playit dashboard](https://playit.gg/account) if already claimed.
3. **Create Tunnel 1 — Game Server:**
   * **Tunnel Type:** `Minecraft Java`
   * **Local Port:** `25565`
   * *The generated domain is the server IP players will use to connect.*
4. **Create Tunnel 2 — Proximity Voice Chat:**
   * **Tunnel Type:** `Custom`
   * **Protocol:** `UDP` *(must be UDP, do not select TCP)*
   * **Local Port:** `24454`
   * *Note down both the generated address and external port (e.g., `voice.auto.playit.gg:38412`).*
5. Open `plugins/voicechat/voicechat-server.properties` and bind the UDP tunnel coordinates to `voice_host`:
   ```properties
   voice_host=voice.auto.playit.gg:38412
   ```
   *(Leave `port=24454` unchanged).*
6. Run `start.bat` to put the server and proximity voice chat online.

---

### Client Side

Every participant must install the **Simple Voice Chat** client mod to hear other players and participate in proximity discussions.

#### 1. Prerequisites
* **Minecraft Java Edition** running on version **`1.20.1`**.
* A functional microphone and headphones.

#### 2. Install Mod Loader
If you are not already using a modded profile, install **Fabric** (recommended):
1. Download and run the [Fabric Installer](https://fabricmc.net/use/installer/).
2. Select Minecraft version **`1.20.1`** and click **Install**.

#### 3. Install Client Mods
1. Download [Fabric API (1.20.1)](https://modrinth.com/mod/fabric-api/versions?g=1.20.1&version=1.21.1&loader=fabric#download).
2. Download [Simple Voice Chat for Fabric 1.20.1](https://modrinth.com/plugin/simple-voice-chat/versions?g=1.20.1&l=fabric&version=1.20.1&loader=fabric#download).
3. Place both `.jar` files into your `mods` folder:
   * **Windows:** Press `Win + R`, type `%appdata%\.minecraft\mods`, and press Enter.
   * **macOS:** `~/Library/Application Support/minecraft/mods`
   * **Linux:** `~/.minecraft/mods`

#### 4. Connect to the Server
1. Launch Minecraft using your **Fabric 1.20.1** profile.
2. Go to **Multiplayer** > **Direct Connection** (or **Add Server**).
3. Enter the server IP provided by the host and click **Join Server**.

#### 5. Configure Voice Chat
1. Once in-game, verify the voice status icon in the **bottom-left corner**:
   * 🎙️ **Microphone icon:** Connected and functional.
   * ❌ **Red slash icon:** Disconnected (check your network or host UDP setup).
2. Press **`V`** to open the Voice Chat settings menu:
   * Select your input and output audio devices.
   * Choose between **Voice Activation** or **Push-to-Talk**.
   * Run the microphone test to check your volume level.
3. Bind the **Whisper** key in your Minecraft Controls, as whispering is essential for sharing private information during discussions.

---

## Host a Game

Follow this step-by-step guide to configure the timers, register players, and start a game.

### 1. Launch Services
1. Run `playit.gg` to ensure your external tunnels are active.
2. Run `start.bat` to launch the Minecraft server.
3. Have all players connect using the assigned server IP.

### 2. Configure Game Durations (Optional)
You can customize the pacing of the game using the following configuration commands (times are in seconds):

| Command | Description | Default |
| :--- | :--- | :--- |
| `/botc configset prepTime <seconds>` | Preparation time before the first night (reading the role book) | `15` |
| `/botc configset actionTime <seconds>` | Timeout for GUI night interactions and council votes | `15` |
| `/botc configset dayTime <seconds>` | Free-roaming discussion & whisper phase duration | `240` |
| `/botc configset councilTime <seconds>` | Public town council debate duration | `120` |

### 3. Register Players & Seating Order ⚠️

In Blood on the Clocktower, **neighbor relationships are vital** for many role abilities (e.g., the Empath checking their adjacent living neighbors). In this plugin, physical neighbors are determined by the registration order.

1. Register each participant using:
   ```text
   /botc add <playername>
   ```
2. *(Optional)* If you make a mistake, remove a player with:
   ```text
   /botc kick <playername>
   ```
3. **Mandatory Seating Rule:**  
   Instruct your players to sit (or position themselves) around the Council circle **in the exact order they were added**.  
   *The first registered player sits next to the second, the second next to the third, and the last registered player loops back next to the first.*

---

### 4. Start the Game
Once all players (5 to 15) are registered and seated in order:
```text
/botc start
```
The plugin will automatically:
* Balance the team composition (Citadins, Outsiders, Sbires, Démon) based on player count.
* Assign roles secretly.
* Begin the `prepTime` countdown before plunging the village into the first night.

At this point, players can claim their role manual using:
```text
/botc roles
```
