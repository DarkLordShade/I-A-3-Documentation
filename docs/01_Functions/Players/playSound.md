## Description

## Parameters

## Returns

## Examples

Play the sound `mySound` from the object `_unit` to all players within `50` metres of `_unit`.

```sqf
["mySound", _unit, 50] call AW_fnc_playSound;
```

Play the sound `mySound` from the object `_unit` to all players within the default radius of `30` metres from `_unit`.

```sqf
["mySound", _unit] call AW_fnc_playSound;
```

Play the sound `mySound` to all players as if it were coming through their ear-piece.

```sqf
["mySound"] call AW_fnc_playSound;
```

## Source

<script src="http://gist-it.appspot.com/https://github.com/jpwilliams/I-A-3/blob/master/functions/players/fn_playSound.sqf?footer=0">
</script>