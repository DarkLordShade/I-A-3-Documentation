## Requirements

Creating a base in I&A 3 is really, really simple. In its most basic form, you only require:

1. One configuration entry detailing the properties of the base
2. One map marker signifying the area of the base
3. A respawn marker for the base
4. Relevant vehicle respawn markers

That's it. You can go ahead and customise a lot more, but establishing your base is bloomin' easy. Good, eh?

## Location

When creating a base, you must first consider its location. A base should be, ideally, a military compound within which soldiers can safely reside and defend its walls. Blah.

## 1. Configuration

I&A 3 handles most of its fixed configuration through the use of C#-style `.hpp` files. These files use classes to determine various values, much like the large config files that Arma 3 itself uses.

To create a base, we'll need to create a new class in `config\base.hpp`. An example of a new base is shown to the right. Let's go through the parameters given here and briefly explain them.

* **name**			-	The full name to show for the base on the map
* **image**			-	The `.paa` image to show on the hint letting players know the base has been captured
* **description**	-	A description of the base that players will see upon capturing the base - should also contain a list of vehicles using bullet points (`%1%2`)
* **tip**			-	A helpful tip for defending the base
* **isOwned**		-	Is the base owned by BLUFOR at the beginning of the game? `1` for yes, `0` for no
* **radius**		-	The radius in metres that the base covers. Keep this rather limited as it majorly impacts how easy bases are to capture
* **groups**		-	If owned by the enemy, how many squads (each consisting of 10 infantry by default) should protect the base?
* **respawnGroups**	-	How many groups should respawn each respawn tick?
* **repsawnTime**	-	The amount of time in seconds that each enemy respawn is triggered
* **vehicles**		-	List of vehicles which should spawn at the base when owned by BLUFOR

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

## 2. Building the base / Marker

After the configuration is done, we'll need to create our base on the map. You can be as detailed or as lazy as you like when it comes to base creation, but there is still one necessity.

Using the editor, create a blank marker with the `Name` the same as the class name you created and the `Text` the same as the base's display name. That's all you have to do, really. You can go ahead and add whatever objects you want to the base such as tank traps, barriers or outposts, but the base will now be created and will work in I&A 3.

In our example above, I to create my base on the map I would create a marker called `base_fortknox` which covered the area that I wished to be my base.

## 3. Respawning

While it would be easier to assume that we want to spawn all players in the middle of a base, this isn't always the case. So, to mark where you'd like players to respawn, place a marker with a `_respawn` suffix. Again using the above example, our player respawn marker would be called `base_fortknox_respawn`.

## 4. Vehicles

If you've specified vehicles to respawn when your base is owned by players, you'll need to create some more blank markers in the correct position and pointing in the right direction. These markers are encouraged to be, in the case of this example, in the format on the right in the `Name` field; the `Text` field is not required. Please note that this is only required if you intend for vehicles to respawn at your base when BLUFOR possess it. Regardless of if this is your intention, it's still recommended that you add special spawn markers in the next step.

```sqf
base_fortknox_vehrespawn_1
...
base_fortknox_vehrespawn_2 etc
```

## Special Vehicle Spawns

Special spawn markers are markers placed in and around bases in which mission-related or rewarded vehicles can spawn. To ensure that there is always room for these vehicles to spawn, it is strongly encouraged that you add a good number of these markers wherever possible in your base. It will go a long way to helping how I&A 3 functions.

To do this, you'll need to add a marker with the suffix of `_spawn_1_land`. There are three vehicle types: `land`, `air` and `sea`. Only specify as many special air spawns as you have helipads / hangars. Examples of a collection of markers for our Fort Knox base are displayed below / on the right.

```sqf
base_fortknox_spawn_1_land
base_fortknox_spawn_2_land
base_fortknox_spawn_3_land
base_fortknox_spawn_4_air
base_fortknox_spawn_5_sea
base_fortknox_spawn_6_sea
base_fortknox_spawn_7_land
```