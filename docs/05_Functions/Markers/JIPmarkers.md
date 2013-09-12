## Description

[`AW_fnc_JIPmarkers`](/Functions/Markers/JIPmarkers) is used when a player joins the server. Utilising an array created and managed mainly via [`AW_fnc_createJIPstateMarker`](/Functions/Markers/createJIPstateMarker), this function grabs details for created markers and creates them locally for the client until they are no longer needed.

Essentially, this provides the functionality to maintain easy-to-create JIP-compatible markers.

## Parameters

None.

## Returns

Nothing.

## Examples

Calling in the client's `init.sqf`.

```sqf
[] call AW_fnc_JIPmarkers;
```

## Source

<script src="http://gist-it.appspot.com/https://github.com/jpwilliams/I-A-3/blob/master/functions/markers/fn_JIPmarkers.sqf?footer=0">
</script>
