## Description

This function "cleans up" objects by deleting both them and (if applicable) their groups.

If an empty array is provided, the function will delete all dead bodies (including vehicles) along with, if possible, their groups. If a populated array is provided, however, all units in the array (along with their groups, if possible) will be deleted, even if they are alive.

This function will never delete players or playable units.

## Parameters

* **ARRAY**
An array of objects / groups that are to be deleted. If an empty array is provided, objects in `allDead` are deleted along with their groups (if possible).

## Returns

Nothing.

## Examples

Deleting all units in the array `_attackers`.

```sqf
_attackers call AW_fnc_collectGarbage;
```

Deleting all units; a global purge.

```sqf
[] call AW_fnc_collectGarbage;
```

## Source

<script src="http://gist-it.appspot.com/https://github.com/jpwilliams/I-A-3/blob/master/functions/garbage/fn_collectGarbage.sqf?footer=0">
</script>