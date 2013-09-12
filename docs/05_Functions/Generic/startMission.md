## Description

[`AW_fnc_startMission`](/Functions/Generic/startMission) is a function designed to facilitate the running of missions within I&A 3 utilising the various parent FSMs provided.

When intending to trigger another mission, direct use of this function is not advised. Instead, it is advised that you use [the mission machine](#).

## Parameters

* **0: STRING**
The type of the mission. This is usually the name of the parent mission folder. By default, these are `tactical`, `sub`, `priority` and `ghost`.
* **1: STRING**
The mission to run within the type. This is the name of the mission folder / classname defined in the mission's configuration definition. Examples of this might be `getDocuments` or `mortarTeam`.
* **2: STRING**
The unique code to use for creating the mission. When spawning multiple objectives, a unique code must be provided to ensure the clean use of markers and the like. These are automatically generated when used through mission machines.
* **3: ARRAY**
The position to spawn the mission. This is, in the case of the mission machine, garnered through the mission's configuration file.

## Returns

* **INTEGER**
The ID of the FSM triggered.

## Examples

Triggering a `tactical` mission called `getDocuments`.

```sqf
["tactical", "getDocuments", "tactical_getDocuments_1", [215,514,12]] call AW_fnc_startMission;
```

## Source

<script src="http://gist-it.appspot.com/https://github.com/jpwilliams/I-A-3/blob/master/functions/generic/fn_startMission.sqf?footer=0">
</script>
