# PivotTool
## Description
This tool extends transform functionality, allowing for temporary custom pivots for objects and groups of objects, without the hassle involved with creating empty GameObjects. The pivot can be repositioned and rotated independent of the selected objects.

<img src="https://i.imgur.com/ZbPeKu3.gif" width="32%" /> <img src="https://i.imgur.com/UTjgxJm.gif" width="32%" /> <img src="https://i.imgur.com/ZwMU7iG.gif" width="32%" />

## Getting Started
If you have the Custom Tools panel enabled, the Pivot Tool icon will be available as long as you have at least one scene object selected. Alternately, you can click on the Custom Tool icon (next to the Transform tool in the left of the main toolbar).
## Instructions
With the tool active, a transform gizmo will be present at the current pivot location. This gizmo allows you to move, rotate, and scale the selected object[s]. All operations occur relative to the pivot.

While holding **A**, or by toggling the `Adjust Pivot` button, the gizmo will move and rotate the pivot, independent of the selected objects. If you're a Blender user, this is similar to the functionality offered by the cursor. 

Holding **S**, or toggling the `Snap Pivot` button, will allow you to snap the object to scene geometry. While Snap is active, a white sphere will indicate where the pivot will be placed when you click. The cursor will snap to nearby vertices, edges, and edge midpoints.

Combining **A** and **S** allows you to snap just the cursor to scene geometry.
## Hotkeys
Hotkeys make use of the Shortcut API, so the following are rebindable via *Edit->Shortcuts*.
* **A** `PivotTool/Adjust Pivot` : Hold to move/rotate the pivot point
* **S** `PivotTool/Snap Pivot` : Hold and click in the scene to snap the pivot to the clicked point (tests against geometry). Snaps to vertices, edges, and edge midpoints.
## Todo
* Keyboard entry for position, rotation, scale
  * Should respect `adjustPivot` mode
  * Probably just a GUI overlay like the adjust/snap pivot indicators
* Respect local/global pivot mode
  * Currently only uses local
* Save/restore pivots?
  * Either via bookmarks, or automatically by selection
* Create concrete pivot on demand via empty GameObject
  * Could be tricky to manage in the sense that a user could easily end up with a ridiculous chain of empties if not careful
* Option to change hotkey behaviour from press-and-hold to toggle (in preferences)
* ~~Snap could instead snap the object[s] to the position. Combining Snap with Adjust would snap the pivot independent of the object[s].~~ *Done*
* ~~Either add a **Snap to Vertex** mode, or optionally allow the existing Snap mode to snap to vertices within a configurable threshold~~ *Done*
* Configurable threshold for vertex/edge snapping (either Scene View UI or in preferences)
