## Description

A simple way to find empty space using a series of parameters. Designed for Side Mission / Priority Target creators who wish to easily find space without having to faff around with findSafePos, randomPos and isFlatEmpty.

As a way to force the I&A 3 design, developers using this function cannot search for a position within a specific area and must instead search across the entirety of the game map.

## Parameters

* **0: STRING** (required)
The area to search for. Can be any one of the following:
	* "water" // ignores "must be flat" `bool`
	* "shore"
	* "land"
	* "civilisation"
	* "anywhere"
	* "main"
* **1: BOOL** (default `false`)
Should the area found be flat? Essential for artillery pieces and the like
* **2: OBJECT/INTEGER/CLASSNAME** (optional, default `1`)
If this is an object, it'll get the size of the object. Otherwise, it'll just find an empty space with the radius given. Useful for spawning large buildings when size is unknown.

## Returns

* **ARRAY**
Position array in the format `[x,y,z]`.

## Examples

Finding a flat, inland position large enough to accomodate a mortar.

```sqf
_pos = ["inland", TRUE, "O_Mortar_F"] call AW_fnc_findSpace;
```

Finding a position in water.

```sqf
_pos = ["water"] call AW_fnc_findSpace;
```

Finding a position anywhere on any surface where the surface is the same for at least 50m. Does not have to be flat.

```sqf
_pos = ["anywhere", FALSE, 50] call AW_fnc_findSpace;
```

## Source

<script src="http://gist-it.appspot.com/https://github.com/jpwilliams/I-A-3/blob/master/functions/generic/fn_findSpace.sqf?footer=0">
</script>