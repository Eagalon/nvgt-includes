# Downloader

downloader object

This object allows you to download files easily as possible with the customization.
This object has multiple constructors, so you can use the one you like. You can also use with no parameters for default if you don't want to specify any of the options.

1. `downloader(string url, string filename, bool silent=false);`
2. `downloader(string url, string filename, bool silent, string msg);`

## Parameters

| Variable | Description |
|---|---|
| url | The URL to download. |
| filename | The name for the file on the disk to save as. |
| silent | Toggle whether the download started message should speak or not. |
| msg | The message to speak as the download is started. |

## Remarks

Since downloader has multiple constructors, the parameters of each will depend.

In constructor 1, you cannot specify the msg parameter. Also in that constructor, the silent parameter is optional.

In constructor 2, you can specify the msg parameter as required. Also, the silent parameter is no longer optional and thus required in this constructor.

## Example
```
#include"downloader.nvgt"
void main()
{
string u=clipboard_get_text();
if(!u.empty())
{
int q=question("URL","There is an URL on your clipboard. Do you want to use it instead?");
if(q!=1) u=input_box("URL","Download URL");
}
if(u=="") exit();
string uf=input_box("Disk file","Disk file");
if(uf=="") exit();
show_window("test");
downloader d(u,uf);
d.finished="Download success";
string st=d.start();
alert("ok",st);
exit();
}
```

## Methods

### start
This method starts the download

`string start();`

#### Return value

A string with the message, returning whether the finish or cancel message on success, an empty string otherwise.

### reset
This method resets the values.

`void reset();`

## Properties

| Property | Description | Type |
|---|---|---|
| url | The URL to download. | string |
| filename | The name for the file on the disk to save as. | string |
| silent | Toggle whether the download started message should speak or not. | bool |
| message | The message to speak as the download is started. | string |
| round_to | Specifies the round place for the percentages and sizes, default is 2. | int |
| finished | The message of the download finished. | string |
| canceled | The message of the download canceled. | string |