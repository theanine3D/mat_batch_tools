# Material Batch Tools
Addon for [Blender](https://www.blender.org/) (3.x+ / 4.x+) that can perform batch modifications of many materials and nodes simultaneously, automating common repetitive tasks on models with many materials. The addon dramatically speeds up the process of preparing models for baking, especially when baking many textures into one - such as with megatextures, texture atlases, etc.

Finding this addon useful? Please consider starring it ⭐, [leaving a review](https://extensions.blender.org/add-ons/matbatchtools/reviews/new/) on the Blender repository, or [donating](https://ko-fi.com/theanine3d) 🙂<br>

## Features:
- **Node Unify** - Set a selected node as a template, and then apply its settings to all other nodes of the same type, in all materials, in all selected objects.
	- Optional filter allows you to restrict Node Unify's effect to only nodes that have a specific label set on them. 
- **Bake Target Node** - Copy / paste your own customized Image Texture node into all materials on all selected objects, for use with baking
	- The created Image Texture node is set as "active" automatically, making it ready as a target for baking
	- The node is always positioned automatically to the right of the Material Output node, for easy finding
	- Optional color setting allows you to add a color decoration to the node, making it easier to identify
- **Batch rename** of UV maps and vertex colors on all selected objects at once
- Automatically add and connect a **UV Map node** (with a specific UV Map set) to all Image Texture nodes, in all materials in all selected objects at once
	- The UV Map node is selectively added based on a user-specified image format (ie. PNG, HDR). This allows you to, for example, selectively add a "lightmap" UV Map node **only** to any HDR Image Texture nodes.
- Switch between **Opaque, Alpha Clip, and Alpha Blend**, in all materials on all selected objects, with an optional filter based on the shader (Principled BSDF or Transparent BSDF) present in the material In Blender 4.2 and higher, this feature will toggle the "Render Method" setting between Dithered and Blended.
- **Material Templates** - Replace the entire node setups in all materials in all selected objects, with common node setups. For example, if you bake your scene's lighting into vertex colors, there is a material template that you can apply that automatically blends the baked vertex colors onto the albedo textures in all materials.
- **Shader Switch** - instantly swap the Principled BSDF shader with the Emission shader, or vise versa, in all materials in all selected objects. Useful for instantly toggling fullbright on/off on a model. The first input/output connections for the original shader are preserved.
- **Isolate by Material Trait** - Separates faces that have assigned materials with certain traits, in all selected meshes, to a separate object automatically. Currently, three are supported - Emissive, Transparent, and Animated. An optional setting can automatically move geometry to a dedicated collection for easier finding.
- **Find/Copy/Paste Active Face Texture** - Allows you to quickly find, copy, and paste the diffuse texture of the currently active or last selected face. The Find operator loads the texture in the Image Editor. All 3 operators be found by search and assigned to your Quick Favorites for easy access, or accessed via Blender's Image Editor's "Image" menu
- **Copy Diffuse Texture to Material Name** - Finds the diffuse texture in all materials, in all selected objects, and if one is found, the diffuse texture's name is copied to its material's name. Can be accessed from the UV Editor's "Image" menu. If multiple textures are found in the material, all of their names are appended to the material's name.
- **Rename All Textures by Hash** - Renames ALL textures in the Blender file by generating a unique MD5-based hash for each texture. Can be found in the "Image" menu of the UV Editor or Image Editor.


## Installation
- If you are using Blender 4.2 or higher, you can install the addon via Blender's official [online extension repository](https://extensions.blender.org/add-ons/matbatchtools/), which can also be accesed via Blender's Preferences.
- Otherwise, for the newest, bleeding edge version, press the big green Code button near the top of this page, and choose Download ZIP.
- If you want a more stable release, check the [Releases](https://github.com/theanine3D/mat-batch-tools/releases).
- After downloading either of the above, go into Blender's addon preferences (File → Preferences → Addons)
- Click the "Install..." button and browse to the ZIP file you downloaded, select it, and press "Install Add-on"

(Note: The .PY file is installed directly, without a ZIP file)

## Notes
- Not every operator in this addon is undoable. Keep a backup copy of your blend file just in case you need to restore something.
- Most operators in this addon affect *all* currently selected mesh objects, not just one object. Make sure you double check which objects you have selected before running any of them.

## Previews:
#### The interface - found in the Material Properties tab
![image](https://github.com/user-attachments/assets/6db25d56-e53d-4c76-aef4-9f5956741eaa)

#### Material Templates ####
![material templates](https://github.com/theanine3D/mat-batch-tools/assets/88953117/56ec9b27-e3c5-4f90-aa13-68e6ae8bcc0c)

#### Node Unify
![node unify](https://user-images.githubusercontent.com/88953117/209483715-d8592e98-56a3-4a8d-aa3f-aaf95896e1bb.gif)

#### Automatic creation, assignment, and linking of UV Map nodes for all Image Textures:
![uvmap](https://user-images.githubusercontent.com/88953117/209455488-7ef92550-09c1-439a-ae89-39ad8fc48348.gif)

#### Bake Target
![bake target](https://user-images.githubusercontent.com/88953117/209455528-a3690ce7-2004-47b0-acf5-56c7c9eac398.gif)

#### Shader Switch
![shader switch](https://user-images.githubusercontent.com/88953117/209982952-27bddc61-4a7b-4780-a849-b3f85af73a4e.gif)


### Gallery
The projects below were created using Material Batch Tools. They are great examples of what this addon makes possible.
- #### Destiny Islands - Garry's Mod map by Theanine3D
  - [![YouTube Video](https://github.com/user-attachments/assets/57a5d834-cf59-41b4-ba26-dbfc92e0772a)](https://www.youtube.com/watch?v=bWywVC6aR9M)


