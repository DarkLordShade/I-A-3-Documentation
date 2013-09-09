## Description

[`AW_fnc_createMarker`](/Functions/Markers/createMarker) is a function used to facilitate the creation of JIP-compatible markers that persist until removed from the system using [`AW_fnc_deleteMarker`](/Functions/Markers/deleteMarker).

To ensure all missions of the same type have a singular style that is unique to them, markers created this way require a `type` and a `state`.

The `type` parameter requires a lowercase string of the mission type the marker is being created/modified for. For example, `base`, `main`, `priority`, `tactical` and so on.

The `state` parameter signifies which state the marker should be in. For example, bases have the `init`, `friendly`, `enemy` and `contested` states. Tactical Missions, like most of the mission types, have two main states: `init` and `update`.

Every `type` will have an `init` state. If an array in the form of `[_type, _state]` is instead replaced with a simple `type` in the parameters passed, the function will assume the intended state is `init`.

## Parameters

* **0: ARRAY or STRING**
Either an array in the format `[_type, _state]` or a string containing the intended `type`. In the latter case, the `init` state will be assumed.
* **1: STRING**
The name being given to the marker. If the name is unique, a blank marker is created prior to modification.
* **2: POSITION ARRAY**
The position of the marker.
* **3: STRING** (optional)
The text the marker should display. If text has been specified in the marker's state configuration, it will be prefixed to the text given here.
* **4: BOOL** (not recommended)
Whether or not the created marker sure should local (`true`) or global (`false`). Be default, this is set to false. I'd recommened not touching this option as it is most often internally, and automatically, set.

## Returns

* **ARRAY**
An array of two marker names is always returned; a marker and an icon. An example might be `["base_connor_marker", "base_connor_icon"]` if `"base_connor"` was provided as a name. This returned value is usable with [`AW_fnc_deleteMarker`](/Functions/Markers/deleteMarker).

## Examples

Creating a new base marker for a friendly base with the name `base_connor`, assuming that `_pos` is a pre-set position array.

```sqf
[["base", "friendly"], "base_connor", _pos, "LZ Connor"] call AW_fnc_createMarker;
```

Creating a default Main AO marker and then instantly deleting it using [`AW_fnc_deleteMarker`](/Functions/Markers/deleteMarker).

```sqf
_markers = ["main", "main_latvia", _pos, "Latvia"] call AW_fnc_createMarker;
[_markers] call AW_fnc_deleteMarker;
```

## Source

<script src="http://gist-it.appspot.com/https://github.com/jpwilliams/I-A-3/blob/master/functions/markers/fn_createMarker.sqf?footer=0">
</script>