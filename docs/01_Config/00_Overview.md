Configuration files are present in I&A 3 as a key way of customising the bits and pieces of the mission that might otherwise be lost in a muddle of hard-set code. Using these files, any administrator/developer can change anything from marker appearences to base and mission behaviour, all from within the carefully-laid-out files.

## Where they are

The files are found within the mission `.pbo` in the `config` directory. Each file/folder is categorised according to its contents.

## What they're used for

Ideally, all changable appearence- and content-based content should be placed within these configuration files. As a rule of thumb, any variables that effect gameplay should be placed within the mission's parameters.

Here we see a single example of these configuration files, this time showing us how the details for a [Tactical Mission](/Tactical_Missions/Overview) are set. By using classes within Arma, we bypass the need to store useful, changable information at the top of core files or, really, anywhere near important code; administrators can change this stuff at their will and not worry about having to change it in ten different files.

```sqf
class getDocuments
{
	title = "Get Documents";
	description = "Your job is to get papers, like.";
	pos = "[""land"", true, 15] call AW_fnc_findSpace;";
};
```

## Format

Each configuration file has, at the top, an example of its usage. I&A 3's been written in a way that not all of these values are required and default settings will be used in the place of their absence, though the required settings are not shown be design. You are strongly encouraged to fill out as many options as you can, as this will help provide the deepest and most rewarding development experience (and the experience for your players, of course).

```sqf
/***********************************************************\
	class Rifleman
	{
		displayName = "Rifleman";
		vehicle = "B_Soldier_F";
		role = "none";
	};
\***********************************************************/
```