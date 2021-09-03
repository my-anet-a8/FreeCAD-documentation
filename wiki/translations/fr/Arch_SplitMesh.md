---
- GuiCommand:/fr
   Name:Arch SplitMesh
   Name/fr:Arch Séparer un objet Mesh
   MenuLocation:Arch → Utilitaires → Diviser une maille
   Workbenches:[Atelier Arch](Arch_Module/fr.md)
   SeeAlso:[Arch Sélection de maillages non-manifold](Arch_SelectNonSolidMeshes/fr.md), [Arch Maillage vers un objet shape](Arch_MeshToShape/fr.md)
---


</div>

## Description

Cet outil sépare les composants d\'un objet [Mesh](Mesh_Workbench/fr.md) sélectionné.

## Utilisation

1.  Sélectionnez un objet mesh.
2.  Cliquez sur le bouton **<img src="images/Arch_SplitMesh.svg" width=16px>  [Diviser une maille](Arch_SplitMesh/fr.md)** dans **Arch → Utilitaires → Diviser une maille**.

## Script


**Voir aussi :**

[Arch API](Arch_API/fr.md) et [FreeCAD Scripts de Base](FreeCAD_Scripting_Basics/fr.md).

L\'outil Séparer un objet Mesh est utilisable dans une [macro](macros/fr.md) et dans la console [Python](Python/fr.md) en utilisant la fonction suivante :


```python
new_list = splitMesh(obj, mark=True)
```

-   Divise l\'objet maillé donné (`obj`) en composants séparés.

-   Si `mark` est mis à `True`, les composants [Variété non-manifold](https://fr.wikipedia.org/wiki/Vari%C3%A9t%C3%A9_(g%C3%A9om%C3%A9trie)) seront peints en rouge.

-    `new_list`est une liste de tous les composants individuels qui composent le maillage.

Exemple:


```python
import FreeCAD, Draft, Arch, Mesh, MeshPart

Line = Draft.makeWire([FreeCAD.Vector(0, 0, 0),FreeCAD.Vector(2000, 2000, 0)])
Wall = Arch.makeWall(Line, width=150, height=3000)
FreeCAD.ActiveDocument.recompute()

Shape = Wall.Shape.copy(False)
Shape.Placement = Wall.getGlobalPlacement()

mesh_obj = FreeCAD.ActiveDocument.addObject("Mesh::Feature", "Mesh")
mesh_obj.Mesh = MeshPart.meshFromShape(Shape=Shape, MaxLength=520)
mesh_obj.ViewObject.DisplayMode = "Flat Lines"

new_list = Arch.splitMesh(mesh_obj)
```


<div class="mw-translate-fuzzy">





</div>





