# create
This method will setup the menu. You should call this after the menu items have been added.

`bool create(string ctitle,bool saydialog=false,bool allowoverrun=false, bool is_tts=true);`

## Parameters
| Variable | Description |
|---|---|
| ctitle | The title for the menu. If is_tts is set to true, this is the filename for the title. |
| saydialog | Determines whether the title should also speak the word "dialog". |
| allowoverrun | Toggles whether the menu can run multiple times. if this is set to false, which is default, the menu cannot run if the menu is already active. |
| is_tts | Toggles whether the menu title should be set as TTS speech, or audio. Default is false. |

## Return value
true on success, false on failure.

## Remarks
You can check error using `error` and `error_info` properties if the function returns false.