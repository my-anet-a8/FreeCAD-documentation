---
- GuiCommand:/de
   Name:Part ElementKopie
   MenuLocation:Part → Erzeuge eine Kopie → Erzeuge Formelement Kopie
   Workbenches:[Arbeitsbereich Part](Part_Workbench/de.md)
   Version:0.19
   SeeAlso:[EinfacheKopie](Part_SimpleCopy/de.md), [TransformierteKopie](Part_TransformedCopy/de.md), [FormVerfeinern](Part_RefineShape/de.md)
---


</div>

## Beschreibung

[Part ElementKopie](Part_ElementCopy/de.md) erzeugt eine nichtparametrische Kopie eines Sub Elements eines bestimmten Objekts, d.h. eines Knotens, einer Kante oder einer Fläche.


<div class="mw-translate-fuzzy">

Um vollständige nicht-parametrische Kopien der Objekte zu erstellen, verwenden Sie [EinfacheKopie](Part_SimpleCopy/de.md), [TransformierteKopie](Part_TransformedCopy/de.md) oder [FormVerfeinern](Part_RefineShape/de.md).


</div>


<div class="mw-translate-fuzzy">

## Anwendung


</div>


<div class="mw-translate-fuzzy">

1.  Wähle einen Knoten, eine Kante oder eine Fläche eines Objekts, für das du eine Kopie erstellen möchtest.
2.  Gehe zum Menü {{MenuCommand/de|Teil → Erstelle eine Kopie → <img src=images/Part_ElementCopy.svg style="width:16px"> [Formularelementkopie erstellen](Part_ElementCopy/de.md)}}.


</div>

## Eigenschaften

### Daten


<div class="mw-translate-fuzzy">

Die Kopie hat eine einfache {{PropertyData/de|Positionierung}} Eigenschaft wie jede andere [Part Funktion](Part_Feature/de.md).


</div>

### Ansicht


<div class="mw-translate-fuzzy">

Die Kopie hat einfache Ansichtseigenschaften wie jede andere [Teilfunktion](Part_Feature/de.md).


</div>

## Scripting

The **Part ElementCopy** command can be applied after selecting one or more objects in the [Tree view](Tree_view.md):


```python
FreeCADGui.runCommand('Part_ElementCopy')
```

The selection can be manual (by using the mouse), or via the [Python console](Python_console.md).
To know more about selecting objects programmatically, refer to [Selection methods](Selection_methods.md).





 