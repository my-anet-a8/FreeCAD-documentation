---
- GuiCommand:/cs
   Name:Constraint PointOnObject
   Name/cs:Constraint PointOnObject
   Workbenches:[Náčrt](Sketcher_Workbench/cs.md), [Návrh dílu](PartDesign_Workbench/cs.md)
   MenuLocation:Sketch → Sketcher constraints → Constrain point onto object
   SeeAlso:[Vazba totožnosti](Sketcher_ConstrainCoincident/cs.md)
---

# Sketcher ConstrainPointOnObject/cs


</div>

## Description


<div class="mw-translate-fuzzy">

#### Popis


</div>


<div class="mw-translate-fuzzy">

#### Použití


</div>

1.  Select the point you want to affix onto a line/arc/etc. (**Result:** Once selected the point will become green).
2.  Select the line you want affixed onto the point you have just selected (**Result:** Once selected the line becomes green).
3.  Invoke the **Constrain point onto object** tool using several methods:
    -   Press the **[<img src=images/Sketcher_ConstrainPointOnObject.svg style="width:16px"> [Point on object](Sketcher_ConstrainPointOnObject.md)** button in the toolbar.
    -   Use the **Shift** + **O** keyboard shortcut.
    -   Use the **Sketch → Sketcher constraints → Constrain point onto object** entry in the top menu.

**Note:** The order you select the line and point does not matter. The point will always move to line. In other words, the line remains fixed.

## Scripting

The constraint can be created from [macros](Macros.md) and from the [Python](Python.md) console by using the following command:


`Sketch.addConstraint(Sketcher.Constraint('PointOnObject',LineMoving,PointOfLineMoving,LineFixed))`

-    `Sketch`is a sketch object.

-    `LineMoving`is the number that designates the line, which contains the point that has to be moved onto the `LineFixed` (the line which is fixed).

-    `PointOfLineMoving`is the number of the vertex of line `LineMoving`, that has to be moved onto the `LineFixed`.

-    `LinedFixed`is the number of the line to be affixed onto the point `PointOfLineMoving`.

The [Sketcher scripting](Sketcher_scripting.md) page explains how to identify the numbers that designate lines and points.





{{Sketcher Tools navi

}}



---
![](images/Right_arrow.png) [documentation index](../README.md) > [Sketcher](Sketcher_Workbench.md) > Sketcher ConstrainPointOnObject/cs
