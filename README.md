# D-D-5ed.-lite-gobGrinder
Dungeons and Dragons 5e. Lite - Goblin Meatgrinder - bash
Goblin Meat Grinder
A relentless, terminal-based combat simulator written in Bash, inspired by the unforgiving spirit of Dark Souls. Face an ever-growing horde of goblins with no victory in sight—just fight until "You died" echoes across the screen.

Overview
In Goblin Meat Grinder, you create a character with rolled stats, arm them with a Longsword, and plunge into combat. Each round, a new goblin spawns, wielding a club and fueled by a desire to grind you down. Initiative determines turn order, and combat rages until your health points (HP) hit zero. There’s no escape, no victory condition—just survival for as long as you can.

Features
Character Creation: Roll 3d6 stats (Strength, Dexterity, Constitution) and assign them interactively.
Dynamic Combat: Initiative (1d20 + Dex modifier) sets the turn order each round; attack rolls (1d20 + Str modifier) vs. Armor Class determine hits.
File-Based System: Player and goblin stats are stored in text files, updated in real-time as HP changes.
Goblin Horde: A new goblin spawns each round, with stats pulled from a template (goblin.txt).
Modifiers: A lookup table (modifier.txt) calculates ability modifiers for AC and damage.
Dark Souls Ending: Combat ends with "You died" when your HP reaches 0 or below.
Prerequisites
Bash: Tested on Bash 5.x (should work on 4.x+).
Unix-like Environment: Runs on Linux, macOS, or WSL on Windows.
Text Files: Requires goblin.txt (goblin template) and modifier.txt (modifier table) in the same directory.
Required Files
Create these files before running the script:

goblin.txt (Goblin Template):
text

Collapse

Wrap

Copy
Name: Goblin
Strength: 8
Dexterity: 14
Constitution: 10
Health Points: 15
Challenge Rating: 0.25
Defines the base stats for each spawned goblin.
modifier.txt (Modifier Table):
text

Collapse

Wrap

Copy
1:-5
2-3:-4
4-5:-3
6-7:-2
8-9:-1
10-11:0
12-13:1
14-15:2
16-17:3
18-19:4
20:5
Maps stat scores to modifiers (e.g., Dex 14 = +2).
Installation
Clone the repository:
bash

Collapse

Wrap

Copy
git clone https://github.com/yourusername/goblin-meat-grinder.git
cd goblin-meat-grinder
Ensure goblin.txt and modifier.txt are in the directory (see above).
Make the script executable:
bash

Collapse

Wrap

Copy
chmod +x goblin_meat_grinder.sh
Usage
Run the script:

bash

Collapse

Wrap

Copy
./goblin_meat_grinder.sh
How to Play
Enter your character’s name when prompted.
Assign your rolled stats (Strength, Dexterity, Constitution) by choosing from a menu.
Combat begins automatically:
Each round, a new goblin spawns (e.g., goblin0.txt, goblin1.txt).
Initiative is rolled for you and all goblins.
Attacks resolve in initiative order: you swing a Longsword (1d8 + Str mod), goblins swing Clubs (1d4 + Str mod).
Goblins die at 0 HP (files are deleted); you die at 0 HP, ending with "You died."
Game Mechanics
Stats: Rolled as 3d6 (3–18 range).
Health Points (HP): Player = Constitution + 10; Goblin = 15 (from template).
Armor Class (AC): Player = 11 (leather armor) + Dex mod; Goblin = 12 (hide armor) + Dex mod.
Initiative: 1d20 + Dex modifier.
Attack: 1d20 + Str modifier vs. AC.
Damage: Player = 1d8 + Str mod; Goblin = 1d4 + Str mod.
Files Generated
charactersheet.txt: Stores your character’s stats, HP, AC, and weapon.
goblinX.txt: Temporary files for each goblin (e.g., goblin0.txt), deleted when HP ≤ 0.
Future Enhancements
Add multiple monster types (e.g., orc.txt, dragon.txt) with Challenge Rating selection.
Implement an escape mechanic or victory condition (currently none by design).
Track rounds survived as a high score.
Contributing
Feel free to fork, submit pull requests, or report issues via GitHub. Ideas for new features or bug fixes are welcome!

License
This project is licensed under the MIT License—see the  file for details.

Acknowledgments
Built with help from Grok (xAI) for iterative design and debugging.
Inspired by Dark Souls’ unforgiving gameplay.
