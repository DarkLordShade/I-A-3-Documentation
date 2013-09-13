## Purpose

Fixed positions with a small degree of military defences, Emplacements in I&A 3 are designed to give players the excitement of being and calling in support from a-far. Learning from the reactions of players regarding previous hints at Emplacements (in the form of "HayMaker" in I&A 2, thanks to razgriz33), these positions in I&A 3 are intended to give the support roles a more team-wide focus, having them rely on friendlies for protection and ammunition as well as raining fire on enemies.

## The problem they resolve

The aforementioned "HayMaker" base was, to an extent, a success; people liked the idea of owning and guarding more than one important position on the map (hence the reason [Bases](/Bases/Overview) were introduced), though being there was a largely solitary experience that only ever involved one-to-two players.

Emplacements in I&A 3 bring the excitement to the entire team, allowing them to be responsible for the protection and stock of each one. While this sounds like some sort of logistical drag, these tasks are presented in the form of [Missions](/Missions/Overview) that reward players for their actions when participating. Ergo, the needs of Emplacements slot into the rest of the game as if it was just another duty.

## How it works

We'll go through using a numbered list as it's easier to visualise.

1. By default, a [Ghost Mission](/Missions/Mission_Types/Ghost_Missions) is completed and rewards the team with an Emplacement. It is either randomly selected or the nearest available one is, depending on parameters set.
2. The Emplacement spawns with a random `type` and set of defences and is displayed on the map. It is now vulnerable to attack.
3. Assuming that it has not yet been attacked, any player can man the static guns at an Emplacement and fire away.
4. When ammunition is depleted to nothing, a team-wide mission is created to go and re-supply the Emplacement. This spawns a special (and specially marked) ammunition truck on the map which will need to be driven to the Emplacement.
5. Upon driving, the truck is vulnerable to attack by OPFOR "patrols". If it is destroyed before it reaches the Emplacement, a new truck will spawn after a small grace period.
6. When the truck reaches the Emplacement, ammunition is returned to full for all Emplacement weapons.
7. The Emplacement could, at any time, be attacked by OPFOR forces. This is the same as [Base](/Bases/Overview) attacks with one difference; if OPFOR forces take the Emplacement, it is not "taken over" by OPFOR forces and is instead simply lost until re-acquired via a [Ghost Mission](/Missions/Mission_Types/Ghost_Missions).

## Customisation

In their current state, Emplacement customisation is actually fairly limited as there aren't really any important variables you may want to change. We can, however, do two things:

1. [Create new Emplacements](/Emplacements/Creating_an_Emplacement)
2. [Create new Emplacement types](/Emplacements/Adding_an_Emplacement_type)
 
The former is rather self-explanatory, but I'll explain the latter. As aforementioned, an Emplacement is created using a random `type`. This type could, for example, be `mortar` or `scorcher'. So, creating a new Emplacement type refers to adding new pieces of weaponry to potential Emplacements.
