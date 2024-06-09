# get_list_selections

custom_menu object


This method returns an array with the list of selected list items in a given list.

`uint[] get_list_selections(string ref);`

## Parameters

| Variable| Description |
|---|---|
| ref | The reference of the menu item to the list. |

## Return Value

An array with the list of selected items on success, an empty array otherwise.

## Remarks

This method returns an array with the list of selected list items in a given list, assuming that the list is multiselect enabled.
