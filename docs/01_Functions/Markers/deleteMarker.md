## Description

This function deletes markers whilst being concious of JIP compatibility provided by [`AW_fnc_createJIPstateMarker`](/Functions/Markers/createJIPstateMarker) and [`AW_fnc_JIPmarkers`](/Functions/Markers/JIPmarkers).

## Parameters

* **0: STRING / ARRAY**
A marker name or array of marker names to delete
* **1: BOOL** (default `false`)
Are we deleting local markers? While you can utilise this parameter, it is recommended you don't; it's mainly for internal use only.

## Returns

Nothing.

## Examples

Deleting the marker `base_lima`.

```sqf
["base_lima"] call AW_fnc_deleteMarker;
```

Deleting the markers `base_tango` and `slim_jim`.

```sqf
[["base_tango", "slim_jim"]] call AW_fnc_deleteMarker;
```

Creating a marker using [`AW_fnc_createJIPstateMarker`](/Functions/Markers/createJIPstateMarker) and then deleting the markers returned instantly.

```sqf
_markers = [["base", "under_attack"], "base_latvia", _pos, "(Under Attack) Latvia"] call AW_fnc_createMarker;
[_markers] call AW_fnc_deleteMarker;
```

## Source

<script src="http://gist-it.appspot.com/https://github.com/jpwilliams/I-A-3/blob/master/functions/markers/fn_deleteMarker.sqf?footer=0">
</script>
