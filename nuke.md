[< Wiki Index](/README.md)
# Nuke
 - [Official Nuke Developers Documentation](https://learn.foundry.com/nuke/content/misc/nuke_devs.html)
 - [Python Dev Guide](https://learn.foundry.com/nuke/developers/121/pythondevguide/)
 - Wish there was a attribute VOP for nuke, but in the mean time there is the [expression node](http://www.nukepedia.com/written-tutorials/expressions-101)
 
 #### Read every nth frame
 In a read (or write etc.) node's expression manipulate the frame value like this
 Eg. this will read every 10th frame, 1001, 1011 etc.
 
 ```
 frame - ((frame%10)-1)
 ```
