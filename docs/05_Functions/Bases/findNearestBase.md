## Description

[`AW_fnc_findNearestBase`](/Functions/Bases/findNearestBase) is used to, believe it or not, find the nearest base to a given `position` or `object`. Any base can be found as well as, specifically, OPFOR- or BLUFOR-controlled bases.

## Parameters

* **0: Position (`array`/`object`)** - The position to find the nearest base to. If an `object` is provided, the position of the `object` is used.
* **1: Blacklist (`array`)** - An array of bases that should be ignored when finding a base.
* **2: Side (`side`)** - The side who should own the found base. Defaults to finding all bases regardless of side.

## Returns

* **Base Code (`string`)** - The original marker for the base.

## Examples

Finding the nearest base to the player.

```sqf
_base = [player] call AW_fnc_findNearestBase;
```

Find the second-nearest base to the player.

```sqf
_nearest = [player] call AW_fnc_findNearestBase;
_secondNearest = [player, [_nearest]] call AW_fnc_findNearestBase;
```

Find the nearest OPFOR base to the position `[514,221,0.2]`.

```sqf
_base = [[514,221,0.2], [], EAST] call AW_fnc_findNearestBase;
```

## Source

<script src="http://gist-it.appspot.com/https://github.com/jpwilliams/I-A-3/blob/master/functions/bases/fn_findNearestBase.sqf?footer=0">
</script>
