# add_audio

custom_menu object

This adds the item to the menu as audio.

`bool add_audio(string i, string ref);`

## Parameters

| Variable| Description |
|---|---|
| i | The specified item as filename. |
| ref | The reference name for the item. |

## Return Value

True on success, false on failure.

## Remarks

This function adds the item into the menu as audio file. Make sure that the reference names are not the same as each other, as this will make the references unusable. The reference will be returned with the value after the menu is run (e.g., result == "back").