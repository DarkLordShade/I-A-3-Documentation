## Description

[`AW_fnc_addJIPmarker`](/Functions/Markers/addJIPmarker) is used mainly internally to facilitate the creation of JIP-compatible markers. In particular, this function manages the array created to ensure the synchronisation of markers from server to client.

[`AW_fnc_createJIPstateMarker`](/Functions/Markers/createJIPstateMarker) uses this function after markers have been created/manipulated.

## Parameters

* **0: STRING**
The marker to be added
* **1: STRING**
The marker type, usually along the lines of `tactical`, `base` or the like
* **2: STRING**
The state of the marker. If not specified, will default to `init`
* **3: ARRAY**
The position of the marker
* **4: STRING** (optional)
The text to display on the marker

## Returns

Nothing.

## Examples

Adding the `base` marker `base_bimbo` at the position `[512, 124]` to be a JIP-compatible marker.

```sqf
["base_bimbo", "base", "init", [512, 124]] call AW_fnc_addJIPmarker;
```

## Source

<script src="http://gist-it.appspot.com/https://github.com/jpwilliams/I-A-3/blob/master/functions/markers/fn_addJIPmarker.sqf?footer=0">
</script>