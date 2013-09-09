## Description

This is a function that is, ideally, run via a `killed` event handler when an AI unit is, unsurprisingly, killed. It adds the dead object's corpse (be it a vehicle or a body) to a global array that has a "limit" of sorts, definable via parameters. Once this limit is reached, the oldest item in the array is deleted. This way, the map can contain a limited number of dead objects and therefore doesn't "overload."

## Parameters

* **OBJECT**
The dead object to add to the array

## Returns

Nothing.

## Examples

Adding a soldier's (`aSoldier`) dead body to the array.

```sqf
aSoldier call AW_fnc_addDead;
```

## Source

<script src="http://gist-it.appspot.com/https://github.com/jpwilliams/I-A-3/blob/master/functions/garbage/fn_addDead.sqf?footer=0">
</script>