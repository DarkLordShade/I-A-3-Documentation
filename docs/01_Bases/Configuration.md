Bases use a number of parameters in I&A 3's configuration files to function properly and all of a base's properties can be managed from the `config\base.hpp` file. Certain numbers, such as the `groups` variable, effect both the defending and attacking AI, so it's of great importance that you are mindful of game balance when assigning these values.

## Formatting & Syntax

* **Class name**    -   The marker on the map that signifies where the base will be created
* **name**			-	The full name to show for the base on the map
* **image**			-	The `.paa` image to show on the hint letting players know the base has been captured
* **description**	-	A description of the base that players will see upon capturing the base - should also contain a list of vehicles using bullet points (`%1%2`)
* **tip**			-	A helpful tip for defending the base
* **isOwned**		-	Is the base owned by BLUFOR at the beginning of the game? `1` for yes, `0` for no
* **radius**		-	The radius in metres that the base covers. Keep this rather limited as it majorly impacts how easy bases are to capture
* **groups**		-	If owned by the enemy, how many squads (each consisting of 10 infantry by default) should protect the base?
* **respawnGroups**	-	How many groups should respawn each respawn tick?
* **repsawnTime**	-	The amount of time in seconds that each enemy respawn is triggered
* **vehicles**		-	List of vehicles which should spawn at the base when owned by BLUFOR. Formatting TBD

```hpp
class base_fortknox
{
	name = "Fort Knox";
	image = "images\bases\fort_knox.paa";
	description = "A description of our base goes here";
	tip = "Here's a tip for defending the base!";
	isOwned = 0;
	radius = 100;
	groups = 3;
	respawnGroups = 1;
	respawnTime = 600;
	vehicles[] = {};
};
```
