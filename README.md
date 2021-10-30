# AoE_ECG_Squire

## Home View

### Find game

Textbox: [Enter game code]

Button: Find Game

if valid --> Game View

if invalid --> "Game not found"

### Create game

Button: Create Game --> Create Game View

### Admins only: list games

List all ongoing games by timestamp created/updated

## Create Game View

Create game with random code

Number of teams

For each team,

add player name

## Game View

### Title: game code

### List players by team

age

resources

Button: Select --> Player View

## Player View

### Title: game code and player name

### List other players by team

age

resources

Collapsible: technologies/upgrades

### Your resources

Food / Wood / Gold / Stone

counts

update counts

Button: Collect

Button: Spend

### Your stats (shows delta for unsubmitted changes)

Age +-

Villagers +-

Units

list of units +-

Dropdown: list of valid units

Button: Add Unit

Technologies

list of technologies

Dropdown: list of valid technologies

Button: Add Technology

Button: Submit changes (resets battle sim deltas)

Button: Discard changes

### Battle Simulation

Each column is a unit from your team, grouped by player starting with you

Each row is a unit from opposing teams, grouped by team, then by player

Each unit shows their Range, Attack, and Health with +- options on each.

Each cell holds information about battle outcomes for each round of combat in a turn

A range round if applicable, with the ability to negate the range round

Each round will show the number of units remaining per player after that round, or if a unit was destroyed the previous round, the remaining building damage

Options to hide battles are available on each player (collapse), unit (collapse), and battle (gray out)

### Database

Units: name, civ, age, type (enum), range attack, attack, hitpoints, max tokens

Unit Bonus: unit (fk), bonus damage, type (enum), unique(unit, type)

Unit Upgrade: unit (fk), name, civ, age, range attack, attack, hitpoints, predecessor

Upgrade Bonus: upgrade (fk), bonus damage, type (enum), unique(upgrade, type)

Tech: name, civ, age, predecessor

Tech Bonus: tech (fk), bonus amount, attribute (attack/health/etc. enum), unit type (enum), unique(tech, attribute, unit type)

Game: creation time, update time, code, complete (bool)

Team: game (fk), name

Player: team (fk), name, civ, age, villagers, food, wood, gold, stone

Player Unit: player (fk), unit (fk), number of tokens

Player Upgrade: player (fk), upgrade (fk), unique(player, upgrade)

Player Tech: player (fk), tech (fk), unique(player, tech)
