[< Wiki Index](/README.md)
# Nuke
 - [Official Nuke Developers Documentation](https://learn.foundry.com/nuke/content/misc/nuke_devs.html)
 - [Python Dev Guide](https://learn.foundry.com/nuke/developers/121/pythondevguide/)
 - Wish there was a attribute VOP for nuke, but in the mean time there is the [expression node](http://www.nukepedia.com/written-tutorials/expressions-101)
 
 #### Read every nth frame
 In a read (or write etc.) node's expression manipulate the frame value like this
 
 Eg. This example will read every 10th frame, 1001, 1011 etc. (without the `-1` would be 1000, 1010 etc.)
 
 ```
 frame - ((frame%10)-1)
 ```

## Python

 #### Run a python file with Nuke's python interpreter

```bash
/c/Program\ Files/Nuke12.1v1/python.exe ~/my_nuke_scripto.py
```

Open a nuke script file
```python
nuke.scriptOpen(script_file)
```

Loop through nodes with a type filter eg. `Write` `Read`
```
# loop through all write nodes
    for node in nuke.allNodes('Write'):
     print('Node name: {}.format(node.name())
```
Get value of a node's knob
```python
node['file'].getValue())
```

Version-up a node using Nuke's built in script
```python
# version up
nukescripts.version_up()
```

Save script - with warning if it didn't save! (need to provide filename while not IN nuke GUI I think)
```python
if not nuke.scriptSave(script_file):
    print('Script did not save for some reason')
```

Get nuke script's full file path
``python
nuke.root().name()
```

Get nuke script's frame start/end
```python
nuke.root()['first_frame'].value()
nuke.root()['last_frame'].value()
```


