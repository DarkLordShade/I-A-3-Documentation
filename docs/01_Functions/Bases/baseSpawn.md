## Description

[`AW_fnc_baseSpawn`](/Functions/Bases/baseSpawn) is a function creating to aid in the creation, spawning and management of friendly vehicles in I&A 3. Specific use cases were designed to be mission vehicles / rewards, though may extend in the future to creating respawn-enabled vehicles in bases rather than having the FSM itself handle that via [`AW_fnc_createVehicle`](/Functions/Units/createVehicle).

When cycling through bases and no specific base has been defined via parameters (i.e. nothing has been specified or a position array / object has), the search will continue to fan out either randomly in the case of nothing being given and second, third, fourth nearest (etc) in the case of an array / object being given.

## Parameters

* **0: STRING**
Vehicle type / classname. Either provide a specific classname to spawn a particular vehicle, or to spawn a specific type use either one of `land`, `air` or `sea`
* **1: STRING / ARRAY / OBJECT**
Base to spawn vehicle at / find nearest base to given position / find nearest base to given object

## Returns

* **OBJECT / BOOL**
The vehicle that has been created. If a vehicle has failed to spawn, `false` is returned

## Examples

Create a vehicle of any type using available spawn markers at any base.

```sqf
[] call AW_fnc_baseSpawn;
```

Create a land vehicle using available spawn markers at any base.

```sqf
["land"] call AW_fnc_baseSpawn;
```

Create an air vehicle using available spawn markers at the base with the codename `base_alpha`.

```sqf
["air", "base_alpha"] call AW_fnc_baseSpawn;
```

Create a vehicle of any type using available spawn markers at the base with the codename `base_alpha`.

```sqf
["", "base_alpha"] call AW_fnc_baseSpawn;
```

Create a sea vehicle using available spawn markers at the base nearest the player.

```sqf
["sea", player] call AW_fnc_baseSpawn;
```

## Source

<script src="http://gist-it.appspot.com/https://github.com/jpwilliams/I-A-3/blob/master/functions/bases/fn_baseSpawn.sqf?footer=0">
</script>