---
- GuiCommand:/de
   Name:TechDraw Dimension Landmark   Name/de:TechDraw Leitbemaßung
   MenuLocation:TechDraw → Bemaßungen → Leitmaß einfügen
   Workbenches:[TechDraw](TechDraw_Workbench/de.md)
   Version:0.19
   SeeAlso:[TechDraw Horizontalbemaßung](TechDraw_HorizontalDimension/de.md), [TechDraw Vertikalbemaßung](TechDraw_VerticalDimension/de.md)
---

# TechDraw LandmarkDimension/de


</div>

## Beschreibung


<div class="mw-translate-fuzzy">

Das Leitbemaßungswerkzeug fügt einer Ansicht eine lineare Dimension hinzu. Die Bemaßung basiert auf zwei Punkten **Funktion** (Draft.Point oder Part.Vertex) aus dem 3D Modell. Beachte, daß es sich bei den Punkten um **Funktion**s Objekte handeln muß, die in der Modell [Baumansicht](Tree_view/de.md) erscheinen. Zufällige Knoten aus einer Form funktionieren nicht.


</div>

Der Zweck dieses Werkzeugs ist es, eine Abhilfe gegen das Korrumpieren der Bemaßung zu schaffen, die durch \"[topologische Benennung](topological_naming_problem/de.md)\" Themen verursacht wird. Die Quellpunkte sollten [Ausdrücke](Expressions/de.md) oder andere enthaltenden Mechanismen verwenden, um ihre Position zu bestimmen. Da es sich bei den Punkten um [Dokumentobjekte](App_DocumentObject/de.md) und nicht um Formkomponenten handelt, ändert sich ihr Name bei Neuberechnungen nicht, so dass sie leicht gefunden werden können.


<div class="mw-translate-fuzzy">

Siehe die Begrenzung und Abhilfeabschnitte der [TechDraw Bemaßungslänge](TechDraw_LengthDimension/de.md) für Weiteres über Bemaßungen und topologische Benennung.


</div>


<div class="mw-translate-fuzzy">

Die Leitbemaßung verhält sich im Allgemeinen wie jede andere Bemaßung


</div>

## Anwendung


<div class="mw-translate-fuzzy">

1.  Wähle 2 Punktobjekte in der [Baumansicht](Tree_view/de.md) oder der [3D Ansicht](3D_view/de.md).
2.  Wähle auch die Ansicht, zu der die Bemaßung hinzugefügt werden soll.
3.  Drücke die **<img src="images/TechDraw_LandmarkDimension.svg" width=20px> [Leitbemaßung](TechDraw_LandmarkDimension/de.md)** Schaltfläche oder {{MenuCommand/de|TechDraw → Leitbemaßung}}
4.  Eine Bemaßung wird der Ansicht hinzugefügt. Der Bemaßungstext kann an die gewünschte Position gezogen werden.


</div>

## Begrenzungen

Das Leitbemaßungswerkzeug ist zunächst auf die \"Abstand\" Bemaßung beschränkt. Andere Typen könnten hinzugefügt werden, wenn die Nachfrage dies rechtfertigt.

## Eigenschaften

Leitbemaßung führt keine neuen Eigenschaften ein.

## Skripten


**Siehe auch:**

[TechDraw API](TechDraw_API/de.md) und [FreeCAD Grundlagen Skripten](FreeCAD_Scripting_Basics/de.md).


<div class="mw-translate-fuzzy">

Das Leitbemaßungswerkzeug kann in [Makros](Macros/de.md) und aus der [Python](Python/de.md) Konsole mit den folgenden Funktionen verwendet werden:


</div>


```python
dim1 = FreeCAD.ActiveDocument.addObject('TechDraw::LandmarkDimension','Landmark')
dim1.Type = "Distance"
dim1.References2D=[(TDView, 'Vertex1')]
dim1.References3D=[(Point3d1, 'Vertex1')]
dim1.References3D=[(Point3d2, 'Vertex1')]
rc = page.addView(dim1)
```


<div class="mw-translate-fuzzy">





</div>


{{TechDraw Tools navi

}}



---
![](images/Right_arrow.png) [documentation index](../README.md) > [TechDraw](TechDraw_Workbench.md) > TechDraw LandmarkDimension/de
