## Description

[`AW_fnc_setFSMVariable`](/Functions/Generic/setFSMVariable) sets / changes variables within FSMs from either the server or the client. This is useful for assigning objects or changing holding statuses for mission FSMs and the like.

## Parameters

* **0: INTEGER**
The ID of the FSM you wish to effect
* **1: STRING**
In the form of a string, give the variable you wish to change/create
* **2: ANY**
Supply the value you wish the variable to be

## Returns

Nothing.

## Examples

Setting the variable `_canContinue` in the FSM with an ID of `24` to `true`.

```sqf
[24, "_canContinue", true] call AW_fnc_setFSMVariable;
```

Setting the variable `_manPos` in the FSM with an ID of `11` to the position of our player.

```sqf
[11, "_manPos", (getPos player)] call AW_fnc_setFSMVariable;
```

## Source

<script src="http://gist-it.appspot.com/https://github.com/jpwilliams/I-A-3/blob/master/functions/generic/fn_setFSMVariable.sqf?footer=0">
</script>
