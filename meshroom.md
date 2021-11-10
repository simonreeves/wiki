[< Wiki Index](/README.md)

# Meshroom

 - [UVs](#uvs)
 
 
## UVs
#### Make Uvs externally
Meshroom was making terrible uvs automatically but good geometry.
![image](https://user-images.githubusercontent.com/12150445/141107122-b9089bd2-05d9-4ec8-bfe3-593cd14f9417.png)

So I imported the obj into houdini did a little cleanup and exported an obj.
![image](https://user-images.githubusercontent.com/12150445/141107156-35ecbaf7-5ff5-4ac5-b9a9-33f1524d4f65.png)

  - Then back in meshroom, there is no 'import' but mehsroom is always saving objs and referencing them, so you can enter a path manually on many nodes.
  - 👎 Entering the path directly into 'texturing' didnt error when computed but just outputed black 
  - 👍 But! I found using 'ConvertMesh' node plugged into 'texturing' converts the obj to an expected format for 'texturing' node - so reprojects the source photos onto the new uvs nicely!

![image](https://user-images.githubusercontent.com/12150445/141106760-96d2a5f4-d57c-4570-9a61-487994f1ee01.png)

![image](https://user-images.githubusercontent.com/12150445/141108249-339309a7-35db-4838-b33d-a246c16da37b.png)
