## Description

[`AW_fnc_restrictWeapons`](/Functions/Players/restrictWeapons) is the function used internally to restrict weapon usage to that of the player's class. By defining which weaponry should be exclusive to each class within the `CfgRespawnInventory` configuration entries, developers can easily specify which equipment should be limited without having to write long lists.

## Parameters

None.

## Returns

Nothing.

## Examples

As called in the client `init.sqf`.

```sqf
[] call AW_fnc_restrictWeapons;
```

## Source

<script src="http://gist-it.appspot.com/https://github.com/jpwilliams/I-A-3/blob/master/functions/players/fn_restrictWeapons.sqf?footer=0">
</script>