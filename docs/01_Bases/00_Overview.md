## Purpose
Bases in I&A 3 are present to supply players with two major requirements: respawn points and transport vehicles.

Bases should provide a system whereby players will fight for resources (vehicles and respawn points) whilst simultaneously having to ensure that they don't get too greedy (managing the defense of 10 bases will be near impossible; they have to focus their efforts on the vehicles they want).

## The problem they resolve
When playing older game-types such as Domination, I've always found the game so much more fun when travelling to the AO meant actually travelling there as opposed to just clicking a flagpole. It helps you feel more immersed in the mission and makes you care for your player's life a hell of a lot more too; if you've just spent 15 minutes getting to the location, surviving's going to matter a lot more than if you just instantly teleported there.

So, the idea of bases was to preserve the travelling in Arma 3 whilst simultaneously reducing the annoyance of long-distance travel when the action is so far away. Ergo, bases act as respawn points for players and offer specific transport vehicles at each one. They don't, however, come without a cost.

## How it works
There should be multiple bases spread out across a map, offering players a multitude of points to choose from. Each one will offer different advantages in the form of vehicles and positioning, but owning more than one base will leave all bases vulnerable to attack. Periodically, when more than one base is owned by BLUFOR, bases will be attacked by OPFOR forces. To keep your respawn points and vehicles you must fight to defend your bases.

Let's go through how a base might react to player iteraction from the beginning of a game. In this instance, our base starts off as not being owned by players and therefore guarded by OPFOR AI.

1. OPFOR AI is spawned to defend the base. Some patrol while others stay and defend.
2. Players start engaging the base from 500m. If they eliminate an entire group, that group will respawn within five minutes.
3. Players move within 200m (double the radius) of the base. A notification is shown globally to announce that we are now attacking the base.
4. Players get within 100m of the centre of the base and have now entered the base. Enemies can no longer respawn while players are present.
5. All enemies are eliminated. The base switches to being owned by BLUFOR and vehicles spawn in relevant positions. Also, a notification is shown globally conveying the success, a hint is shown describing the base and players can now respawn at the base whenever they wish.

```text
Let's assume that the base radius is 100m, 5 groups of enemies spawn to defend it, 1 of which respawns every 5 minutes.
```

## Customisation
Any base, new or existing, can be created/modified through the use of one marker and one config entry, though more thought-through set-ups are encouraged. These thought-through bases would include markers for vehicle respawns as well as barricades and generic defenses.