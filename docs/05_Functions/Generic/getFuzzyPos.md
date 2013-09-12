## Description

[`AW_fnc_getFuzzyPos`](/Functions/Generic/getFuzzyPos) retrives and returns a (potentially un-safe) position within the given radius of supplied position. Mainly utilised for making markers appear vague rather than supplying soldiers with pin-point accuracy regarding their objectives, the use of this function is encouraged to aid in the dynamic, tactical nature of I&A 3.

## Parameters

* **0: ARRAY**
The position with which to start
* **1: INTEGER**
The radius in which to search for a new position

## Returns

* **ARRAY**
Returns the position gathered with no Z axis.

```sqf
_fuzzyPos = [234, 713, 0];
```

## Examples

Get a position within 300m of the player.

```sqf
_pos = [player, 300] call AW_fnc_getFuzzyPos;
```

Get a position within 1,000m of the given position.

```sqf
_pos= [[104,22,1], 1000] call AW_fnc_getFuzzyPos;
```

## Source

<script src="http://gist-it.appspot.com/https://github.com/jpwilliams/I-A-3/blob/master/functions/generic/fn_getFuzzyPos.sqf?footer=0">
</script>
