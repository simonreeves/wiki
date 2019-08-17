# wiki

hello
here is some code
```python
# not complete but an example

def n():
    
    # get child nodes from a node
    prop_nodes = hou.node('/obj/action/props/').children()
    
    # loop through children
    for prop in prop_nodes:
        # filter by name
        if 'lens' not in prop.name():
            continue
        
        # get a parm on node
        mat_parm = hou.parm(prop.path() + '/material1/shop_materialpath1')
        print(prop.name() + ': ' + mat_parm.eval())
    
```
## another
here is some code
```python
# not complete but an example

def n():
    
    # get child nodes from a node
    prop_nodes = hou.node('/obj/action/props/').children()
    
    # loop through children
    for prop in prop_nodes:
        # filter by name
        if 'lens' not in prop.name():
            continue
        
        # get a parm on node
        mat_parm = hou.parm(prop.path() + '/material1/shop_materialpath1')
        print(prop.name() + ': ' + mat_parm.eval())
    
```
[a relative link](another-page.md)
