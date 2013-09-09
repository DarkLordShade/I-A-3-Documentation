## Description

[`AW_fnc_createAction`](/Functions/Actions/createAction) is a function that facilitates the creation of global actions, allowing developers to create an action that is added and managed through JIPPs (Join-In-Progress Players) as well are currently-connected clients.

The function will, in certain circumstances, call itself via `BIS_fnc_MP` to create actions globally.

## Parameters
* **0: OBJECT**
The object that the action should be added to. Does not have to be a globally-accessible reference
* **1: ARRAY**
The parameters to create the action with. Use the exact same parameters as [the addAction command](http://community.bistudio.com/wiki/addAction)
* **2: BOOL**
Whether or not the action should be deleted locally (`true`) or not (`false`)

## Returns
* **0: INTEGER**
The ID of the added action
* **1: OBJECT**
The object the action is added to

```sqf
[_id, _obj]
```

## Examples
Adding a simple "Talk to the Man" action.

```sqf
[myMan, ["Talk to the Man", "scripts\talk.sqf"]] call AW_fnc_createAction;
```

Adding an action that has a few extra parameters for the `addAction` command.

```sqf
[myMan, ["Talk to the Man", "scripts\talk.sqf", "", 1, true, false]] call AW_fnc_createAction;
```

Grabbing the ID and object returned to use with [`AW_fnc_deleteAction`](/Functions/Actions/deleteAction) later.

```sqf
_id = [myMan, ["Talk to the Man", "scripts\talk.sqf"]] call AW_fnc_createAction;
```

Adding an action that deletes the action as part of the code run when activated.

```sqf
[myMan, ["Talk to the Man", { hint "Ye-argh!"; [(_this select 2), (_this select 0)] call AW_fnc_deleteAction; }]] call AW_fnc_createAction;
```

Or a tidier version of the above example...

```sqf
[
	myMan,
	[
		"Talk to the Man",
		{
			hint "Ye-argh!";
			[(_this select 2), (_this select 0)] call AW_fnc_deleteAction;
		}
	]
] call AW_fnc_createAction;
```

## Source

<script src="http://gist-it.appspot.com/https://github.com/jpwilliams/I-A-3/blob/master/functions/actions/fn_createAction.sqf?footer=0">
</script>