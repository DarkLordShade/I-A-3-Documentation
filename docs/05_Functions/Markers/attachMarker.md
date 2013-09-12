## Description

[`AW_fnc_attachMarker`](/Functions/Markers/attachMarker) is used to have a marker follow an object until a specific condition is broken. By default, this condition is `{ alive _obj }`, though a custom one can be specified.

Currently, this function creates a marker and then attaches it, though in the future I may well change it to instead simply use a marker given.

## Parameters

* **0: OBJECT**
The object to attach the marker to
* **1: STRING / ARRAY**
The type of marker to create, usually of type `base`, `misc`, `tactical` or the like. If a string is provided, the marker state will be automatically set to `init`. If you wish to define the state as well as the type, provide an array in the format `[type, state]`
* **2: CODE**
The condition to keep the marker attached and visible. By default, this is `{ alive _obj }`

## Returns

* **ARRAY**
The markers (icon and marker) created to be attached to the object

## Examples

Attaching a `misc` `ammo_truck` marker to the object `_truck` until the obj dies.

```sqf
[_truck, ["misc", "ammo_truck"]] call AW_fnc_attachMarker;
```

Attaching a `base` `init` marker to the object `player` until `rosesRed` == `true`.

```sqf
[player, "base", { !rosesRed }] call AW_fnc_attachMarker;
```

## Source

<script src="http://gist-it.appspot.com/https://github.com/jpwilliams/I-A-3/blob/master/functions/markers/fn_attachMarker.sqf?footer=0">
</script>