---
- GuiCommand:/de
   Name:Part Compound‏‎
   Name/de:Formteil Verbund
   MenuLocation:Formteil → Erzeuge Verbund
   Workbenches:[Arbeitsbereich Part](Part_Workbench/de.md)
   Version:0.14
   SeeAlso:[Part Verschmelzung](Part_Fuse/de.md), [Part VerbundFilter](Part_CompoundFilter/de.md), [Part SprengeVerbund](Part_ExplodeCompound/de.md)
---

# Part Compound/de


</div>

## Beschreibung

Dieser Befehl erzeugt einen Verbund aus jeder Art topologischer Formen. Dies können Festkörper oder Polygonnetze oder jede andere Art topologischer Formen sein.

Ein Verbund ist ein Satz von Formen gruppiert in einem Objekt.

## Anwendung

1.  Markiere die topologischen Formen, die dem Verbund in der [Baumansicht](Tree_view/de.md)

hinzugefügt werden sollen

1.  Wähle den **Formteil → Verbund → Erzeuge Verbund** Eintrag im Part Menü oder klicke auf die <img alt="" src=images/Part_Compound.svg  style="width:24px;"> Schaltfläche.

## Hinweise

Ein Verbund, der sich berührende oder sich überschneidende Formen enthält, ist **ungültig** für Boolesche Operationen. Aufgrund von möglichen Ausführungsproblemen wird standardmäßig keine Prüfung der Formen auf Überschneidung durchgeführt. Automatische Geometrieprüfung (verfügbar für Boolesche Operationen) ist für den Part Verbund ebenfalls deaktiviert.

Um diese Prüfung einzuschalten, gehe zu {{MenuCommand/de|Werkzeuge → Parameter bearbeiten → Einstellungen..... → Mod → Teil → PrüfeGeometrie→ RunBOPCheck}} und setze den Parameter auf `true`.


<div class="mw-translate-fuzzy">





</div>



---
![](images/Right_arrow.png) [documentation index](../README.md) > [Part](Part_Workbench.md) > Part Compound/de
