---
- GuiCommand:/ru
   Name:Sketcher ConstrainInternalAlignment
   Name/ru:Sketcher ConstrainInternalAlignment
   MenuLocation:Sketch → Ограничения эскиза → Привязать к внутренней геометрии
   Workbenches:[Sketcher](Sketcher_Workbench/ru.md)
   Shortcut:**Ctrl** + **A**
   SeeAlso:[Показать/скрыть внутреннюю геометрию](Sketcher_RestoreInternalAlignmentGeometry/ru.md), [Sketcher Ellipse by Center](Sketcher_CreateEllipseByCenter/ru.md)
---

## Description

The InternalAlignment constraint aligns lines and points to particular places of a complex sketcher element (there is just one \"complex\" element so far, the [Ellipse](Sketcher_CreateEllipseByCenter.md)).

For **<img src=images/Sketcher_CreateEllipseByCenter.svg style="width:16px"> <img src=images/Sketcher_CreateArcOfEllipse.svg style="width:Ellipse](Sketcher_CreateEllipseByCenter.md)** and **[16px"> <img src=images/Sketcher_CreatePoint.svg style="width:Arc of ellipse](Sketcher_CreateArcOfEllipse.md)**, it supports constraining lines to become major and minor diameters, and constraining **[16px"> [points](Sketcher_CreatePoint.md)** to positions of ellipse\'s foci.

The constraint is for experienced users because its usage is not as straight forward as for the other constraints. There is a helper tool called **<img src=images/Sketcher_RestoreInternalAlignmentGeometry.svg style="width:16px"> [Show/Hide internal geometry](Sketcher_RestoreInternalAlignmentGeometry.md)** to avoid the need to invoke the InternalAlignment constraint manually.

## Operation on Ellipse 

1.  Select elements to be aligned and an ellipse. The ellipse must be selected last. Accepted are up to two lines and up to two points.
2.  Invoking the constraint can be done several ways:
    -   Pressing the **<img src=images/Sketcher_ConstrainInternalAlignment.svg style="width:16px"> [Constrain internal alignment](Sketcher_ConstrainInternalAlignment.md)** button in the toolbar.
    -   Using the **Ctrl** + **A** keyboard shortcut.
    -   Using the **Sketch → Sketcher constraints → <img src=images/Sketcher_ConstrainInternalAlignment.svg style="width:16px"> Constrain InternalAlignment** entry from the top menu.

The first line that was selected gets aligned to become ellipse\'s major diameter (but if it is not occupied already by another line, otherwise it will become minor diameter). The second line is aligned to become minor radius. The lines are automatically switched to [construction](Sketcher_ToggleConstruction.md).

Likewise, the first point is constrained to become the first unoccupied focus, and the second point goes to the other focus.

**Note:** By default new ellipses have an internal construction geometry. When this defines the ellipse already completely, you cannot directly use the InternalAlignment constraint. You first need to delete the construction geometry or parts of it. In case you don\'t see the construction geometry, select the ellipse and use the tool **<img src=images/Sketcher_RestoreInternalAlignmentGeometry.svg style="width:16px"> [Show/Hide internal geometry](Sketcher_RestoreInternalAlignmentGeometry.md)** to make it visible.

## Scripting


```python
Sketch.addConstraint(Sketcher.Constraint('InternalAlignment:EllipseMajorDiameter', index_of_line, index_of_ellipse))
Sketch.addConstraint(Sketcher.Constraint('InternalAlignment:EllipseMinorDiameter', index_of_line, index_of_ellipse))
Sketch.addConstraint(Sketcher.Constraint('InternalAlignment:EllipseFocus1', index_of_point, 1, index_of_ellipse))
Sketch.addConstraint(Sketcher.Constraint('InternalAlignment:EllipseFocus2', index_of_point, 1, index_of_ellipse))
```

Remarks:

:   
    `Sketch`is a sketch object.

:   Number `1` in the focus calls stands for starting point of a point element (it is ignored).

:   The `index_of_point` argument must be a point, it cannot be used to e.g. denote an edge\'s extremity.

The [Sketcher scripting](Sketcher_scripting.md) page explains the values which can be used for `index_of_line`, `index_of_point` and `index_of_ellipse` and contains further examples on how to create constraints from Python scripts.





{{Sketcher Tools navi

}}  