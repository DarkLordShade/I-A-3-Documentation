## Description

A simple function that uses `BIS_fnc_taskCompleted` to test whether all the children of a parent task have been completed.

This is utilised mainly for Main AO sub-objective completion, though can be used for many different purposes.

## Parameters

* **STRING** (required)
The task name to check

## Returns

* **BOOL**
`true` if all child tasks have been completed, otherwise `false`

## Examples

Checking whether all tasks under the task "myTask" have been completed.

```sqf
_childrenComplete = "myTask" call AW_fnc_childrenComplete;
```

## Source

<script src="http://gist-it.appspot.com/https://github.com/jpwilliams/I-A-3/blob/master/functions/generic/fn_childrenComplete.sqf?footer=0">
</script>