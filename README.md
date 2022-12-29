# Material Batch Tools
Addon for [Blender](https://www.blender.org/) (3.4+) that can perform batch modifications of many materials and nodes simultaneously, automating common repetitive tasks on models with many materials. The addon dramatically speeds up the process of preparing models for baking, especially when baking many textures into one - such as with megatextures, texture atlases, etc.

## Features:
- **Node Unify** - Set a selected node as a template, and then apply its settings to all other nodes of the same type, in all materials, in all selected objects.
- **Bake Target Node** - Copy / paste your own customized Image Texture node into all materials on all selected objects.
	- The created Image Texture node is set as "active" automatically, making it ready as a target for baking
	- The node is always positioned automatically to the right of the Material Output node, for easy finding
	- Optional color setting allows you to add a color decoration to the node, making it easier to identify
- **Batch rename** of UV maps and vertex colors on all selected objects at once
- Automatically add and connect a **UV Map node** (with a specific UV Map set) to all Image Texture nodes, in all materials in all selected objects at once
	- The UV Map node is selectively added based on a user-specified image format (ie. PNG, HDR). This allows you to, for example, selectively add a "lightmap" UV Map node **only** to any HDR Image Texture nodes.
- Switch between **Opaque, Alpha Clip, and Alpha Blend**, in all materials on all selected objects, with an optional filter based on the shader (Principled BSDF or Transparent BSDF) present in the material
- **Shader Switch** - instantly swap any Principled BSDF shader with the Emission shader, and vise versa, in all materials in all selected objects.

## Installation
1. Download [mat_batch_tools.py](https://github.com/theanine3D/mat-batch-tools/raw/main/mat_batch_tools.py) (right click this link and Save As...)
2. Go into Blender's addon preferences (File → Preferences → Addons)
3. Click the "Install..." button and browse to mat_batch_tools.py, select it, and press "Install Add-on"

## Notes
- Not every function in this addon is undoable. Keep a backup copy of your blend file just in case you need to restore something.
- Every single function in this addon affects *all* currently selected mesh objects, not just one object. Make sure you double check which objects you have selected before running any of them.
- The addon was coded for Blender 3.4, but you may be able to run it in older versions, at least as far back as 3.0 or so. Try modifying the "version" code at the top of the py file to force it to run on older versions.

## Previews:
#### The interface - found in the Material Properties tab
![image](https://user-images.githubusercontent.com/88953117/209483586-7d90c484-d886-4b2d-8013-164ac2dcd735.png)

#### Node Unify
![node unify](https://user-images.githubusercontent.com/88953117/209483715-d8592e98-56a3-4a8d-aa3f-aaf95896e1bb.gif)

#### Automatic creation, assignment, and linking of UV Map nodes for all Image Textures:
![uvmap](https://user-images.githubusercontent.com/88953117/209455488-7ef92550-09c1-439a-ae89-39ad8fc48348.gif)

#### Bake Target
![bake target](https://user-images.githubusercontent.com/88953117/209455528-a3690ce7-2004-47b0-acf5-56c7c9eac398.gif)
