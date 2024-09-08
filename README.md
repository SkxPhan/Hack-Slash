# Hack and Slash/Dungeon Crawler Game (Zelda like)
## 1. Introduction
As part of the INFO-H-200 project at the École Polytechnique de Bruxelles in 2016, we developed a Hack and Slash/Dungeon Crawler game in Java with a graphical interface. The project aimed to practice object-oriented programming and introduce us to video game development. This README summarizes the game's implementation and design patterns. More details are available in the ![rapport-info.pdf](docs/rapport-info.pdf) file (French).
![Game demo](docs/zelda.png)

## 2. Game Overview
### 2.1 Characters
Characters, including the hero and monsters, inherit from an abstract Character class. They all have health and mana, with mana used for attacks and regenerating over time. A collision system manages interactions between characters and the environment, using the visitor design pattern to trigger actions based on the type of collision.

#### 2.1.1 Hero
The hero, controlled by the player, engages in melee or ranged attacks (using mana). The hero can store health and mana potions in an inventory, while invincibility bonuses activate on contact.

#### 2.1.2 Monsters
Monsters are loaded from a file and attack the player when in range and with enough mana. When killed, they have a 50% chance to drop a potion.

### 2.2 Items
Health, mana, and invincibility potions are generated on the map, with a 1 in 4 chance of appearing. Health and mana potions can be stored, while invincibility potions are used instantly.

### 2.3 Map
The map, consisting of obstacles and doors, is generated from a text file. Players can move between rooms by interacting with doors.

### 2.4. Gameplay
The game’s main loop checks for collisions between entities and triggers actions based on the visitor design pattern. Players attack with the spacebar, switch attacks with "A," and use health or mana potions with "H" and "M."