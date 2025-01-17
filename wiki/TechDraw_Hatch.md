---
- GuiCommand:
   Name:TechDraw Hatch
   MenuLocation:TechDraw → Hatch a Face using Image File
   Workbenches:[TechDraw](TechDraw_Workbench.md)
   SeeAlso:[TechDraw Geometric Hatch](TechDraw_GeometricHatch.md), [TechDraw Hatching](TechDraw_Hatching.md)
---

# TechDraw Hatch

## Description

The Hatch tool fills a closed region in a View with a hatch pattern, which can be [SVG](SVG.md) or [bitmap](bitmap.md) files. In contrary the <img alt="" src=images/TechDraw_GeometricHatch.svg  style="width:24px;"> [Geometric Hatch](TechDraw_GeometricHatch.md) tool uses a specific PAT pattern file, see [Hatching](TechDraw_Hatching.md) for details.

 <img alt="" src=images/TechDraw_Hatch_example.png  style="width:300px;"> 



*SVG hatch pattern on a face*

## Usage

1.  Select an closed region in a View.
2.  Press the **<img src="images/TechDraw_Hatch.svg" width=16px> [Hatch a Face using Image File](TechDraw_Hatch.md)** button
3.  A dialog will open where you can select the pattern file, the scale and color.

## Notes

-   Hatching objects are vulnerable to the \"[topological naming problem](Topological_naming_problem.md)\". See [TechDraw LengthDimension](TechDraw_LengthDimension.md) for more information. It is recommended that hatching be one of the last steps in your drawing process.
-   Sample [SVG](SVG.md) patterns are available locally in

 
```python
$INSTALL_DIR/data/Mod/TechDraw/Patterns
``` where  
```python
/usr/share/freecad/data/Mod/TechDraw/Patterns
``` and also on [GitHub](https://github.com/FreeCAD/FreeCAD/tree/master/src/Mod/TechDraw/Patterns).

## Properties

-    **Source**: The View and Face to receive the hatch pattern.

-    **Hatch Pattern**: Full path and filename to an SVG pattern file.

-    **Hatch Color**: Hatch pattern will be displayed in this color.

-    **Hatch Scale**: Hatch pattern size modifier.

## Scripting


**See also:**

[TechDraw API](TechDraw_API.md) and [FreeCAD Scripting Basics](FreeCAD_Scripting_Basics.md).

The Hatch tool can be used in [macros](Macros.md) and from the [Python](Python.md) console by using the following functions:

 
```python
hatch = FreeCAD.ActiveDocument.addObject('TechDraw::DrawHatch','Hatch')
hatch.Source = (view1,["Face0"])
hatch.HatchPattern = hatchFileSpec
rc = page.addView(hatch)
```




 {{TechDraw Tools navi}}



---
![](images/Right_arrow.png) [documentation index](../README.md) > [TechDraw](TechDraw_Workbench.md) > TechDraw Hatch
