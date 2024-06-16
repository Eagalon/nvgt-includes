# script_detect
This class allows you to detect a script, .EXE, or .NVGT, to run without writing complex code.
This class automatically determines whether to run directly or run from nvgt script which is installed at your computer.

## Constructor

1. `script_detect();`
2. `script_detect(string mn);`

### Parameters
| Variable | Description |
|---|---|
| mn | An optional name for the script. Note, you must set the script correctly, for example using `SCRIPT_COMPILED` property to check to set .EXE or .NVGT. |

## Properties

* `string name;` : The name. This can be set or get. Note that if the name is exe file, it will return the location of your NVGT script installed file, so that command property can be given to run.
* `string command;` : Returns the command for running, usually empty on non exe files.

## Methods

### execute
This method will execute the script that is set in name.

`bool execute(bool wait_complete=false, bool background=false);`

### Parameters
| Variable | Description |
|---|---|
| wait_complete | An optional parameter to control whether the run function should wait while the given script is active. |
| background | An optional parameter to control whether background window will be active while running, usually you will know if you know run function. |

## Example

```
#include"script_detect.nvgt"
void main()
{
script_detect d((SCRIPT_COMPILED?"test.exe":"test.nvgt"));
alert("script returns",d.execute());
}
```