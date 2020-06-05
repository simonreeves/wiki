# CG Guide
A collection of examples, guides, tips.

### Other Resources
  - [Matt Estela's cgwiki](http://www.tokeru.com/cgwiki/?title=Houdini) An inspiration and a valuable learning resource
  - [toadstorm.com/blog/](https://www.toadstorm.com/blog/)
  - [I have a bunch of gists for houdini/python/vex here](https://gist.github.com/simonreeves)

# ZBrush[#](#zbrush)
Here is a good intro to zbrush [Michael Wilde zbrush](https://www.youtube.com/watch?v=SKvPIkND1yI) a good refresher for zbrush is helpful when you don't use it often!


# Houdini[#](#houdini)

## Rigging
Just watch these Sidefx tutorials by Michael Goldfarb
Scripts are included on the sidefx page (youtube better than vimeo for resuming etc.)
https://www.sidefx.com/tutorials/rigging-series-01-hda-spine/

## HDAs
 - rigging tutorials have good guides of how to create HDAs
 - [enable asset bar to show versions](https://youtu.be/jxpb36URQ9M?t=471)

## Retopo
 - Clear [simple quick video](https://www.youtube.com/watch?v=yAF3HtIFiVc) about using the retopo tool !
 
 
## Houdini Cloth[#](#houdini-cloth)
 - As if H18 Always set substeps to [at least 5](https://youtu.be/1ztATWCOwn8?t=94), fixes initial stretching - then consider reducing collision passes.
 - Really useful section of [Sidefx Jeff Laits vellum cloth tutorial](
https://youtu.be/4nC-L19400I?t=12200), he shows a (complicated!) way to extract the holes after using create planar patch
 - [Help initially intersecting collisions](https://youtu.be/4nC-L19400I?t=2344)
 - [unpin using stopped(vellum H17)](https://youtu.be/NwabG-znu9Y?t=3113)

## Houdini Python[#](#houdini-python)
Create `null` objects from `transform SOPs`.
This can be useful to re-create transforms at object level instead of 'deforming' geometry which is much heavier.

```python
def nulls_from_x():
    for node in hou.selectedNodes():
        print(node.name())
        t = node.parmTuple('t').eval()
        r = node.parmTuple('r').eval()
        s = node.parmTuple('s').eval()
        scale = node.parm('scale').eval()

        new_null = hou.node('obj/').createNode('null')
        new_null.parmTuple('t').set(t)
        new_null.parmTuple('r').set(r)
        new_null.parmTuple('s').set(s)
        new_null.parm('scale').set(scale)
```

## VEX[#](#vex)
vex wrangle examples
```c
// get nearest point index of second input
int np = nearpoint(1, @P);

// get that point's position
vector np_pos = point(1, 'P', np);

// measure distance
float dist = distance(@P, np_pos);

// normalise distance
dist = fit(dist, ch('in_min'), ch('in_max'), ch('out_min'), ch('out_max'));

// remap with ramp
dist = chramp('remap', dist);

// set attribute
f@dist = dist;
```

## Houdini Redshift[#](#houdini-redshift)
Not well documented, how to enable console log
```python
# Toggle Redshift console log
hou.hscript("Redshift_setLogLevel -L 5")

# Set log level
hou.hscript("Redshift_switchConsoleLog")
```
