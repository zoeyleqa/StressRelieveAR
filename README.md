# Stress Relieve AR

---------------------

## Overview

Feeling stressed? Want to let off steam with no cost? Break things without consequences? 

This is an ***Augmented Reality*** Application (intended for ***Microsoft HoloLens***) developed on Unity with code written in C#. The user can hold porcelain objects and break or throw them into pieces with voice commands. 


## How It Works

The game starts out with a table with a collection of porcelain consist of a teapot, teacup and saucer, plates, mug, etc. In the `Assets` folder, there are broken version of each porcelain item as prefabs. Each broken item was made from its regular porcelain object, cut into random pieces with the [fracture-voronoi](http://www.scriptspot.com/3ds-max/scripts/fracture-voronoi) script in Autodesk 3ds Max. 

<p align="center">
  <img  src="pictures/brokenpieces.gif">
</p>

The player can gaze towards an item, airtap and hold to drag it made possible with `HandDragable` script in the MixedRealityToolkit. While holding the item, the player can use voice commands `crush`, `toss` or `throw`. 
* `crush` command will shatter the porcelain into pieces right in front of the player by `Destroy` the object (make it disapear) and `Instantiate` the broken version at the same place. Since each piece of the broken prefab is affected by gravity, the whole object falls apart and looks like it was crushed.  
* `toss` command will put a ***light*** force onto the item on hand of the forward direction of the Mixed Reality Camera which is the forward direction from the player view. On impact with anything (`OnCollisionEnter`  function), the object will be `Destroy` and `Instantiate` broken version like how `crush` command function. 
* `throw` command basically operates exactly like `toss` with a much larger force so that it looks like an actual throwing.

The script that's responsible for this functiontality is in `Assets/destroyOnCollision.cs`

<p align="center">
  <img width="500" height="350" src="pictures/action_code.png">
</p>

## Demo
This is a quick demo of the Stress Relieve AR app. 3 keywords of voice command were used: `crush`, `toss`, and `throw`. 
***Note***: In this demo, `throw` command was designed with too much force (7000) which makes it look like the object disappeared. Spatial mapping was activated so that the porcelain objects can interact with objects in the room. As it was dropped in the video, the porcelain shattered on the floor or on real objects in the room.

<p align="center">
  <a href="https://youtu.be/Y7KxHFcewhE
  " target="_blank"><img src="http://img.youtube.com/vi/Y7KxHFcewhE/0.jpg" 
  alt="IMAGE ALT TEXT HERE" width="500" height="350" border="10" /></a>
</p>

---------------------
ヾ(｡･ω･｡)
