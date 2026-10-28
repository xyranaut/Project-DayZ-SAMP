# Project DayZ SA-MP

**GTA SA: DayZ Survival [ZOMBIE AI]**, version 15.0. A DayZ-style survival gamemode for SA-MP 0.3.7: find food, water and medicine, keep your blood up, fight off hundreds of AI zombies and decide whether other survivors are friends or targets.

The project started in 2012 on the Pro Gaming Arena server. It was written by **Kitten (AldenJ)**, and this repository is a fork of [AaronNader96/Project-DayZ-SAMP](https://github.com/AaronNader96/Project-DayZ-SAMP). Licensed under GPL-3.0.

## Features

### Staying alive
- **Blood, hunger and thirst.** All three drop over time and faster when you run, swim or get hurt. Low blood darkens and shakes the screen and cuts your stamina.
- **Temperature.** Swimming and jumping chill you, while sprinting or a heat pack warms you up.
- **Bleeding.** Gunshots and zombie hits make you bleed until you use a bandage.
- **Broken legs.** A bad fall breaks a leg, and morphine fixes it.
- **Infection.** Some zombie attacks infect you. Antibiotics cure it.
- **Status indicators** in the bottom-right corner change colour from light green (safe) to red (near death). `/survival` prints your blood, hunger and thirst.
- **Alive time, kills and headshots** are tracked on the stats panel along with zombies killed, murders and bandits killed.

### Zombies
- **Up to 400 AI zombies** run as FCNPC bots (set by `MAX_ZOMBIES`). They spawn on San Andreas' path nodes, chase you with MapAndreas pathfinding and attack in melee.
- **Noise and sight.** Running, shooting and driving make you easier to spot. Your name tag shows from further away the more noise you make.
- **Loot on zombies.** Dead zombies can be searched for supplies.

### Loot and items
- **World loot** sits in buildings and on streets across the state. Press **N** to loot it. Admins can respawn all of it with `/lootres`.
- **Hospital loot.** Each hospital holds medical supplies to take.
- **Military crates.** Airdropped crates with high-tier gear, placed with `DayZSA_CreateAirdrop` or `/spawncratem`.
- **Weapons:** Pistol, Silenced Pistol, Desert Eagle, Shotgun, SPAZ-12, MP5, AK-47, M4, Country Rifle, Sniper Rifle, Katana and Baseball Bat. Ammo comes by type (Pistol, Shotgun, SMG, Assault and Sniper Ammo). Use `/dropgun` and `/pickupgun` to leave a gun on the ground or take one.
- **Food and drink:**
  - Can of Beans, Packet of Cereals, Burger, Pizza Slice, Apple, Banana, Orange and Tomato.
  - Raw Meat and Cooked Meat.
  - Milk, Fresh Juice, Soda Bottle, Whiskey, Rum and Gin.
  - Water Bottles (empty, dirty or full).
- **Medical:** Bandage, Painkiller, Morphine, Antibiotics, Blood Bag and Medical Kit.
- **Tools and gear:**
  - Map (`/map` shows the radar) and GPS.
  - Binoculars, Flashlight (`/flashoff`), Road Flare and Lighter.
  - Toolbox, Rope and Wood.
  - Heat Pack, Radio Device, and Empty and Full Jerry Cans.
- **Clothing:** Civilian, Army and Sniper skins, plus male or female characters.

### Inventory and backpacks
- **Inventory:** a dialog-based inventory (`/inv`) with stacking items, saved per player.
- **Backpacks:** Czech Vest Pouch, Alice Pack, Coyote Patrol Pack and Coyote Backpack, each adding carrying space.

### Tents and storage
- **Tents.** Pitch a tent anywhere and store items in it. Tents persist, and admins can reset them with `/tentres`.
- **Vehicle storage.** Each vehicle has a 4-slot trunk for items.

### Vehicles
- **Repairs.** Vehicles spawn damaged across the map. Fit an engine and four tyres with a toolbox to get one running.
- **Fuel.** Fill an empty jerry can, then pour it into a vehicle.
- **Respawning.** Wrecks respawn on a timer. Admins can respawn them with `/respawncars` and `/respawnallcars`.

### Humanity, bandits and heroes
- **Humanity.** Killing other survivors lowers it and killing bandits raises it.
- **Bandits and heroes.** A red skull marks a bandit, who may be killed on sight. A green skull marks a hero or a normal survivor.

### Groups
- **Survivor groups**, up to 750, each with its own leader and members.
- **Group commands:** `/makegroup`, `/invitegroup`, `/acceptgroup`, `/denygroup`, `/kickgroup`, `/leavegroup`, `/destroygroup`, `/groupinfo` and `/groupfind`.

### Chat and radio
- **Chat channels:**
  - Local chat (`/l`, `/local`), shouting (`/s`, `/shout`) and `/me` actions.
  - Global chat (`/g`), switched with `/gon` and `/goff`.
  - Out-of-character chat (`/o`, `/ooc`, `/b`).
- **Private messages:** `/pm`, `/blockpm` and `/unblockpm`.
- **Radio device:** tune to low, medium, normal or high frequency and talk with `/r`.
- **Help channel:** `/ask`, which helpers answer with `/respond`, and `/report` to reach staff.

### Player options
- **Gender:** a default gender selection.
- **Ambient background:** toggle the ambient sound, or stop it with `/stopambient`.
- **First-person camera** with `/firstperson`.
- **Animations:** `/handsup`, `/sit`, `/wave`, `/smoke`, `/clearanim` and `/stopanim`.
- **Coins shop:** cosmetic headwear (Police Cap, Red Hockey Mask, Army Helmet) bought with coins.

### Accounts and staff
- **MySQL accounts** with Whirlpool-hashed passwords. Stats, inventory, position and survival state are all saved (`/savestats`, `/stats`).
- **Staff:** admin levels 1 to 6 and helpers.
- **Premium players** with their own chat (`/pchat`) and a `/premiums` list.
- **Admin tools:**
  - Moderation: `/kick`, `/ban`, `/tban`, `/unbanname`, `/unbanip`, `/warn`, `/mute`, `/unmute`, `/slap`, `/wslap` and `/akill`.
  - Watching and moving players: `/spec`, `/specoff`, `/get`, `/gotop`, `/ip` and `/weaps`.
  - Server: `/ann`, `/ann2`, `/setweather`, `/saveall`, `/cc` and `/nuke`.
  - Accounts: `/setadmin`, `/sethelper`, `/setpremium`, `/setscore`, `/sethumanity`, `/giveallitems` and `/resetinv`.
- **Bans** are stored in MySQL (the `samp_ban` table) by name and IP.
- **Anti-cheat** (`DayZ_AntiG`) stops passengers warping into moving vehicles (the "G-bug").
- **Weather and time:** a day and night cycle with weather changes, plus fog.

### Maps
- **State-wide wreckage map** (`dayzmap.inc` / `TWD_Map.inc`, about 12,400 objects): abandoned cars, debris and barricades across Los Santos, San Fierro, Las Venturas and the countryside.
- **Military base map** (`dayzmap2.inc`, about 850 objects) around the Area 69 base in Bone County.

### Help in game
- `/help` and `/cmds` list the commands by topic: general, animation and group.
- The help menu also has survival tips, and `/basickeys`, `/rules`, `/info` and `/version` cover the basics.

## Requirements

- SA-MP 0.3.7 server
- Plugins (included in `plugins/`): Streamer, FCNPC, MapAndreas, MySQL, sscanf and Whirlpool
- A MySQL database

## Installation

1. Download the SA-MP 0.3.7 server package: http://files.sa-mp.com/samp037_svr_R2-1-1_win32.zip
2. Download the project files and copy them into the server folder.
3. Create a MySQL database. You can run one locally with XAMPP, or use a hosted one. Put the connection details in the settings at the top of `dayz.pwn`.

   The tables are created automatically the first time the server starts with a working database connection.

4. Compile `dayz.pwn`.
5. Start `samp-server.exe`.

## Server settings

These are all `#define`s at the top of `dayz.pwn`:

| Setting | What it is |
|---|---|
| `mysql_host` | IP of the MySQL host, or `127.0.0.1` if it runs locally |
| `mysql_user` | MySQL user name (`root` for a local install) |
| `mysql_password` | MySQL password |
| `mysql_database` | Name of the database |
| `MAX_ZOMBIES` | Number of zombies (400 by default). Set `maxnpc` in `server.cfg` to at least this. |
| `Name` | Server name |

Everything else is self-explanatory.

## Making yourself an admin

1. Log in to phpMyAdmin or the MySQL command prompt.
2. Set the `pAdminLevel` field of your account to 5.
3. Optional: to use SA-MP's RCON login instead, replace `if(pInfo[playerid][pAdminLevel] >= 5)` with `if(IsPlayerAdmin(playerid))` in `dayz.pwn` (around line 9120). You then log in with `/rcon login <password>`.

## Military crates

Administrators place a crate with `/spawncratem`. To add permanent crate spawns, call:

```pawn
DayZSA_CreateAirdrop(x, y, z);
```

## Credits

- **Kitten (AldenJ)**, Pro Gaming Arena: the gamemode
- [AaronNader96/Project-DayZ-SAMP](https://github.com/AaronNader96/Project-DayZ-SAMP): the upstream repository
- Plugin and include authors: Incognito (Streamer), the FCNPC team, Kalcor and RyDeR (MapAndreas), BlueG and maddinat0r (MySQL), Y_Less (sscanf, YSI, y_timers, foreach) and Zeex (zcmd)
