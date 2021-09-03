---
- GuiCommand:   Name:TechDraw  Dimension Horizontal   Workbenches:[[TechDraw_Workbench   TechDraw]]|MenuLocation:TechDraw → Dimension Horizontal   Shortcut:   SeeAlso:---


</div>


<div class="mw-translate-fuzzy">

## Descriere

Instrumentul pentru cote orizontale adaugă o cotă orizontală unei imagini. Cota poate fi între două vârfuri, lungimea unei muchii sau distanța verticală dintre două margini. Distanța va fi inițial distanța proiectată(adică așa cum este reprezentată în desen), dar această distanță poate fi înlocuită prin distanța 3D reală utilizând instrumentul Link Dimension <img alt="" src=images/LinkDimension.png  style="width:24px;">. <img alt="" src=images/HorizontalSample.png  style="width:200px;">


</div>

The Dimension Horizontal tool adds a horizontal dimension to a View. The dimension may be between two vertices, the length of one edge or the horizontal distance between 2 edges. The distance will initially be the projected distance (ie as shown on the drawing), but this may be changed to the actual 3D distance using the **<img src="images/TechDraw_Dimension_Link.svg" width=16px> [Link Dimension](TechDraw_Dimension_Link.md)** tool.

<img alt="" src=images/TechDraw_Dimension_Horizontal_example.png  style="width:200px;"> 
*Length dimension taken from two arbitrary nodes of the view; the distance is measured horizontally*


<div class="mw-translate-fuzzy">

## Cum se folosește 

1.  Selectați punctele sau muchiile care definesc măsurarea dvs.
2.  Apăsați butonul **<img src="images/Dimension_Horizontal.png" width=24px> [Dimension Horizontal](TechDraw_Dimension_Horizontal.md)
**
3.  O cotă va fi adăugată la View. Cota poate fi glisată în poziția dorită.


</div>

1.  Select the points or edge which define your measurement.
2.  Press the **<img src="images/TechDraw_Dimension_Horizontal.svg" width=16px> [Dimension Horizontal](TechDraw_Dimension_Horizontal.md)** button
3.  A dimension will be added to the View. The dimension may be dragged to the desired position.
4.  If needed, add tolerances as described in [this page](TechDraw_Geometric_dimensioning_and_tolerancing#Tolerances.md).

To change the properties of a dimension object either double-clicking it in the drawing or in the [Tree view](Tree_view.md). This will open the [dimension dialog](TechDraw_Dimension_Length#Dimension_dialog.md).

## Limitations

Dimension objects are vulnerable to \"topological naming\" issues. See the information in the [TechDraw Dimension Length](TechDraw_Dimension_Length.md) tool for more information.


<div class="mw-translate-fuzzy">

## Proprietăți

This object has the same properties as the [TechDraw Dimension Length](TechDraw_Dimension_Length/ro.md) tool. See that tool for details.


</div>

This object has the same properties as the [TechDraw Dimension Length](TechDraw_Dimension_Length.md) tool. See that tool for details.


<div class="mw-translate-fuzzy">

## Script

Cotele orizontale pot fi adăugate la Pages utilizând Python.


</div>


**See also:**

[TechDraw API](TechDraw_API.md) and [FreeCAD Scripting Basics](FreeCAD_Scripting_Basics.md).

The Dimension Horizontal tool can be used in [macros](Macros.md) and from the [Python](Python.md) console by using the following functions:


```python
dim1 = FreeCAD.ActiveDocument.addObject('TechDraw::DrawViewDimension','Dimension')
dim1.Type = "DistanceX"
dim1.References2D=[(view1, 'Edge1')]
rc = page.addView(dim1)
```





{{TechDraw Tools navi

}}  