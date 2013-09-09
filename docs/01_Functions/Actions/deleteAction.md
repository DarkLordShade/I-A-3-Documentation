## Description

To be used with either the returned array from [`AW_fnc_createAction`](/Functions/Actions/createAction) or the returned ID from an `addAction` command, [`AW_fnc_deleteAction`](/Functions/Actions/deleteAction) is used to globally remove an action from existence from all clients connected both presently and in the future.

This function also uses the same `BIS_fnc_MP` usage as [`AW_fnc_createAction`](/Functions/Actions/createAction), facilitating the deletion of actions across both client and server.

## Parameters

If using data gathered from [`AW_fnc_createAction`](/Functions/Actions/createAction), use:

* **0: ARRAY**
The value returned from [`AW_fnc_createAction`](/Functions/Actions/createAction) in the form of `[_id, _obj]`
* **1: BOOL** (not recommended)
Whether or not the action should be deleted locally (`true`) or not (`false`)

<hr/>

Otherwise, use:

* **0: INTEGER**
The ID of the action you wish to remove
* **1: OBJECT**
The object you wish to remove the action from
* **2: BOOL** (not recommended)
Whether or not the action should be deleted locally (`true`) or not (`false`)

It is worth noting that, in both instances, the specification of the locality `bool` is not recommended, as the value is set internally when removing actions globally.

## Returns

Nothing.

## Examples

Adding the action via `addAction` and using the returned variables to delete that action globally.

```lua
_id = mySoldier addAction ["Do Something", { hint "Woohoo!"; }];
[_id, mySoldier] call AW_fnc_deleteAction;
```

Adding the action globally via [`AW_fnc_createAction`](/Functions/Actions/createAction) and using the returned variables to delete said action globally.

```lua
_action = [mySoldier, ["Do Something", { hint "Woohoo!"; }]] call AW_fnc_createAction;
[_action] call AW_fnc_deleteAction;
```

As noted above, the specification of the locality `bool` is not recommended, though if you do wish to delete an action on the client running [`AW_fnc_deleteAction`](/Functions/Actions/deleteAction) only, you could do so by simple specifying `true` at the end of the passed array.

```lua
/* Using the above example for the creation of the action */
[_action, true] call AW_fnc_deleteAction;
```

## Source

<script src="http://gist-it.appspot.com/https://github.com/jpwilliams/I-A-3/blob/master/functions/actions/fn_deleteAction.sqf?footer=0">
</script>