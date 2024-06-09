# savedata

savedata object

The savedata object allows you to manage your game progresses to load and save.

`savedata(string filename, string enckey);`

## parameters

| Variable | Description |
|---|---|
| filename | The filename to save and load. |
| key | An optional key to the file to be encrypted. |

## remarks

This class provides saving and loading data, probably used on games to save the progress.

## example

```
#include"savedata.nvgt"
#include"form.nvgt"
savedata sd("config.dat","testkey");
double s=-1;
timer f;
#include"instance.nvgt"
instance j("savedata");
string name;
void main()
{
if(j.is_already_running)
{
alert("error","active");
exit();
}
s=-1;
loadsd();
if(name=="")
{
name=input_box("Name","Name, so we will have string value to test");
if(name=="") name="user";
}
show_window("test data");
if(s>-1) alert("previously","the timer is "+s);
wait(2000);
speak("Hello "+name+", you can press escape to exit");
while(true)
{
wait(5);
if(key_pressed(KEY_ESCAPE))
{
savesd();
alert("ok","saved");
exit();
}
}//while
exit();
}
void loadsd()
{
sd.load();
if(sd.exists("time")) s=sd.read("time");
if(sd.exists("username")) name=sd.read("username");
}
void savesd()
{
sd.clear();
sd.add("time",f.elapsed);
sd.add("username",name);
sd.save();
}
```