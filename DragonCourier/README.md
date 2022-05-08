# Game Overview

Players control a courier who rides a dragon. Basic core of the game is:
1. choose a job
2. plan a path
3. survive the path
4. complete the job

The first prototype I'll focus on is **Survive**.

Dragon Courier is an RPG game that's a cross between Oregon Trail and Final Fantasy 2. 

## Entities

### Courier
The Courier is charged with taking packages, messages and people over long distances across the land. They're responsible for choosing the jobs, managing the resources and accepting the money. Couriers have access to a basic inventory that will include medicines, food, and the package in question.

Couriers have **Will** skills:
* Negotiate - This is short hand for people skills. Couriers can use this skill to bring down prices for food, bring up prices for jobs, or even gain more position in the guild.
* Cunning - Short hand for survival skills. This is used to determine a player's ability to camp out in the wilderness in various conditions.
* Evoke - Magic. mainly support skills

### Dragon

The Dragon is the courier's partner. They actually carry the courier and their packages to their destination. Dragons are mysterious creatures whose origins are a closely kept secret by the guilds. Couriers are paired with dragons when they are very young and grow up with them. There are different kinds of dragons with different kinds of skills.

Dragons have **Instinct** skills:
* Impress - This skill can be used to show off, intimidate hostile creatures, and to aid in negotiation.
* Forage - This skill is used to find food and shelter for the dragon. modified by the dragon's innate abilities
* Breath - Magic, mainly attack

### Guild
TBD

## Survive

### Basics
The courier and their dragon is challenged to survive and endure various encounters in order to continue their journey.
Players will be charged with maintaining the following resources:
* Health - Both courier and dragon will have HP.
  * things that can damage HP: attacks, illness, falls, acid, not enough or bad water
  * ways to recover: time, magic, medicine
  * penalties for low HP: reduced energy/vigilance recovery
  * result if depleted: job failure
* Energy - The dragon needs energy to fly/run/etc
  * things that can damage energy: not enough or bad food, poison
  * ways to recover: brimstone, food, human magic
  * penalties for low energy: reduced speed, loss of access to special skills
  * result if depleted: required hunt/forage session
* Vigilance - Couriers need to remain alert to ride their dragons
  * things that can damage vigilance: not enough or bad shelter (leads to bad sleep), poison
  * ways to recover: rest, "coffee", dragon magic
  * penalties for low: chances to go off course, special skills may fail
  * result if depleted: forced rest



### Game Loop

Players will be presented with a **Field**, **environmental** conditions, and necessary **resources** to gather. The game will award stars for each kind of resource found. Players only have a set number of actions to perform.

The **resources** that players will gather are:
* Shelter - Based on environmental conditions, players will be charged with gathering enough points to count as shelter. If they fail, then they take a penalty to Vigilance
* Food - Based on tomorrow's journey, players will be charged with gathering enough food points for the dragon to count as fed. If they fail, they take a penalty to Energy
* Medicine - bonus resource. Can be used to recover health
* Brimstone - bonus resource. Can be used to recover Energy
* "Coffee" - bonus resource. Can be used to recover Vigilance.

The **Field** is made of *spaces* that the player needs to send the courier and the dragon to. When the courier or dragon enters the field there's a chance that it'll "attack" with either an animal attack or poison or something like quicksand.
* Brush - bright green
  * good - food, medicine, shelter
  * bad - poison
* Meadow - yellow-green
  * good - shelter+, medicine
  * bad - raids
* Tree - dark green
  * good - food, shelter++, "coffee"
  * bad - poison, raids
* Cave - black
  * good - shelter+++, water, medicine
  * bad - raids
* River bank - blue-gray
  * good - water, food
  * bad - floods
* Swamp - brown
  * good - food, brimstone
  * bad - shelter-, bugs
* Cliff - white
  * good - easy takeoff
  * bad - shelter---
* Bare Rock - Gray
  * good - brimstone
  * bad - shelter--, 
* Sand Beach - yellow
  * good - food
  * bad - tide
* Rock Beach - TBD
  * good - food, medicine
  * bad - tide, shelter--
* Water - dark blue
  * good - food
  * bad - no shelter

The **environmental conditions** will increase/decrease the shelter points required and modify the chances to find food.
These follow for temperate climates.
* Spring - no rainstorm
  * shelter points: 2
  * food chances: high
  * attack chances: medium
* Spring - Rainstorm
  * shelter points: 4
  * food chances: low
  * attack chances: low
* Summer - hot
  * shelter points: 3
  * food chances: med
  * attack chances: low
* Summer - thunderstorm
  * shelter points: 5
  * food chances: low
  * attack chances: low
* Autumn - no rain
  * shelter points: 3
  * food chances: high
  * attack chances: high
* Autumn - rain
  * shelter points: 4
  * food chances: med
  * attack chances: med
* Winter - no snow
  * shelter points: 4
  * food chances: low
  * attack chances (outside of caves): low
  * in caves: high
* Winter - snowing
  * shelter points: 5
  * food chances: low
  * attack chances (outside of caves): low
  * in caves: high
* Winter - Blizzard
  * shelter points: 6
  * food chances: nil
  * attack chances (outside of caves): nil
  * in caves: high