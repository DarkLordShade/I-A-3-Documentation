## Description

Roles within I&A 3 are designed to free up the heavy-handed approach of selecting your role before the mission starts. One of the core concepts of I&A was to ensure that nobody was restricted and that everybody could play the role they wanted to. This obviously comes with certain drawbacks, one good example being that everyone will then carry around a sniper, an RPG and a backpack full of satchel charges and ammo. Every soldier becomes a jack of all trades, able to use anything at any time.

The way role selection works in Arma by default, however, means that restricting people to their roles can be more limiting than other games where role selection is a more free, easy-to-change experience. So, roles in I&A 3 allow the player to change what weapons, items, backpacks and uniforms players can use by choosing either the same or a different role every time they respawn. Upon respawning, they are presented with a menu which will allow them to choose from a wide variety of classes. These could be classes such as Marksman or Ammo Bearer to Medics and Engineers. With this system, players can be locked to specific gear and specific roles without having the key thrown away.

## Parameters

Using the example below / to the right, let's go through what each of the settings means and how we can manipulate them to get exactly what we want!

* **Class Name**
The name of the class will be the role code used when setting the role variable on the player. Keep this code to one lowercase word using only A-Z.
* **displayName**
This is how the class will appear when players are picking it from the respawn screen.
* **vehicle**
Vehicle can be used to attain a pre-set load-out using an existing character profile. Alternatively, use the example below to fully customise the player's original load-out when spawning as this class.
* **show**
This should be a statement that returns either `true` or `false`, deciding whether or not the slot should be available for players to spawn in. By default, this allows players to spawn in the spot if they are already in it or if the amount of others in that class is below the cap (in this 5).
* **restrictions**
This is a list of weapons/backpacks that should be exclusive to this class. If items are listed across multiple classes, all of those classes will still be able to access their "exclusive" weaponry.

```sqf
	class sniper
	{
		displayName = "Marksman";
		icon = "\A3\Ui_f\data\GUI\Cfg\Ranks\sergeant_gs.paa";
		vehicle = "B_sniper_F";
		show = "(player getVariable [""role"", ""none""]) == ""sniper"" || ({ (_x getVariable [""role"", ""none""]) == ""sniper"" } count playableUnits) < 5";
		restrictions[] = { /* some sniper example classnames here */ };
	};
```

Instead of using the `vehicle` parameter in our class, we can customise our default load-out by defining `weapons[]`, `magazines[]`, `items[]`, `linkedItems[]`, `uniformClass` and `backpack`. An example is below / to the right.

```sqf
	class sniper
	{
		displayName = "Marksman";
		icon = "\A3\Ui_f\data\GUI\Cfg\Ranks\sergeant_gs.paa";
		weapons[] =
		{
			"arifle_MXC_F",
			"Binocular"
		};
		magazines[] =
		{
			"30Rnd_65x39_caseless_mag",
			"30Rnd_65x39_caseless_mag",
			"SmokeShell"
		};
		items[] = {"FirstAidKit"};
		linkedItems[] =
		{
			"V_Chestrig_khk",
			"H_Watchcap_blk",
			"optic_Aco",
			"acc_flashlight",
			"ItemMap",
			"ItemCompass",
			"ItemWatch",
			"ItemRadio"
		};
		uniformClass = "U_B_CombatUniform_mcam_tshirt";
		backpack = "B_AssaultPack_mcamo";
		show = "(player getVariable [""role"", ""none""]) == ""sniper"" || ({ (_x getVariable [""role"", ""none""]) == ""sniper"" } count playableUnits) < 5";
		restrictions[] = { /* some sniper example classnames here */ };
	};
```
