---
- GuiCommand:/de
   Name:TechDraw Dimension Length
   Name/de:TechDraw Längenbemaßung
   MenuLocation:TechDraw → Bemaßung Länge
   Workbenches:[TechDraw](TechDraw_Workbench/de.md)
   SeeAlso:[TechDraw Bemaßung Horizontal](TechDraw_Dimension_Horizontal/de.md), [TechDraw Bemaßung Vertikal](TechDraw_Dimension_Vertical/de.md)
---

## Beschreibung

Das Werkzeug »Längenbemaßung« fügt ein lineares Maß in einer Ansicht hinzu. Das Längenmaß kann der Abstand zwischen zwei Ecken, die Länge einer Kante oder der Abstand zwischen zwei Kanten sein. Der Abstand ist zuerst der projizierte Abstand (wie in der Zeichnung dargestellt), aber dieser kann unter Verwendung des **<img src="images/TechDraw_Dimension_Link.svg" width=16px> [Bemaßungen verlinken](TechDraw_Dimension_Link/de.md)**-Werkzeugs zum eigentlichen 3D-Abstand geändert werden.

<img alt="" src=images/TechDraw_Dimension_Length_example.png  style="width:220px;"> 
*Längenbemaßung zweier beliebiger Knoten der Ansicht*

## Anwendung

1.  Wähle die Punkte oder die Kante, die deine Messung definieren.
2.  Drücke die **<img src="images/TechDraw_Dimension_Length.svg" width=20px> [Bemaßung Länge](TechDraw_Dimension_Length/de.md)** Schaltfläche
3.  Eine Bemaßung wird der Ansicht hinzugefügt. Die Bemaßung kann an die gewünschte Position gezogen werden.
4.  Falls erforderlich, füge Toleranzen, wie in [diese Seite](TechDraw_Geometric_dimensioning_and_tolerancing/de#Toleranzen.md) beschrieben, hinzu.

Um die Eigenschaften eines Bemaßungsobjekts zu ändern, doppel-klicke sie entweder in der Zeichnung oder in der [Baumansicht](Tree_view/de.md). Dadurch wird der Bemaßungsdialog geöffnet.

## Bemaßungsdialog

Der Bemaßungsdialog bietet die folgenden Einstellungen:

![](images/TechDraw_DimensionDialog.png )

### Tolerierung

-   **Theoretisch genau**: Wenn diese Option aktiviert ist, wird das Maß als theoretisch genaues Maß angegeben. Als solches darf es keine Toleranzen aufweisen. Das Maß wird durch einen Rahmen um den Wert dargestellt: <img alt="" src=images/TechDraw_theoretically_exact.png  style="width:100px;">

-   **Gleiche Toleranz**: Falls aktiviert, sind Über- und Untertoleranz gleich und der negierte Wert der Übertroleranz wird als Untertoleranz benutzt. Die Anzeige zeigt <img alt="" src=images/TechDraw_equal-tolerance.png  style="width:100px;">, anderenfalls <img alt="" src=images/TechDraw_Non-equal-tolerance.png  style="width:80px;">.

-   **Übertoleranz**: Der Wert, um den die Bemaßung größer sein kann.

-   **Untertoleranz**: Der Wert, um den die Bemaßung kleiner sein kann.

### Formatierung

-   **Formatspezifizierer**: Wie der Bemaßungswert formatiert werden soll. Standardspezifizierer ist*%.xf*, wobei *x* die Anzahl der Dezimalstellen angibt. Details zur Formatierungssyntax unter [printf format string](https://en.wikipedia.org/wiki/Printf_format_string) (engl.).

-   **Beliebiger Text**: Falls aktiviert, wird die Bemaßung durch den Inhalt des **Formatspezifizierer**-Feldes ersetzt.

-   **Übertoleranz Formatspezifizierer**: Wie der Übertoleranzbemaßungswert formatiert werden soll. Standardspezifizierer ist*%.xf*, wobei *x* die Anzahl der Dezimalstellen angibt. Details zur Formatierungssyntax unter [printf format string](https://en.wikipedia.org/wiki/Printf_format_string) (engl.).

-   **Untertoleranz Formatspezifizierer**: Wie der Untertoleranzbemaßungswert formatiert werden soll. Standardspezifizierer ist*%.xf*, wobei *x* die Anzahl der Dezimalstellen angibt. Details zur Formatierungssyntax unter [printf format string](https://en.wikipedia.org/wiki/Printf_format_string) (engl.).

-   **Beliebiger Toleranztext**: Falls aktiviert, werden die Toleranzen durch den Inhalt der **Übertoleranz Formatspezifizierer**- und **Untertoleranz Formatspezifizierer**-Felder ersetzt.

### Anzeigeformat

-   **Maßpfeile umdrehen**: Dreht die Richtung um, in die die Bemaßungspfeile zeigen. Als Vorgabe sind sie innerhalb der/des Bemaßungslinie/-bogens und zeigen nach außen.

-   **Farbe**: Die Farbe für Linien und Texte.

-   **Schrifthöhe**: Die Größe des Bemaßungstextes.

-   **Drawing Style**: The standard (and its style) according to which the dimension is drawn. See the property [**Standard And Style**](#View.md) for details.

## Eigenschaften


<div class="mw-translate-fuzzy">

### Daten


{{Properties_Title/de|Basis}}

-    {{PropertyData/de|X}}: Horizontale Position des Bemaßungstexts relativ zur Ansicht.

-    {{PropertyData/de|Y}}: Vertikale Position des Bemaßungstexts relativ zur Ansicht.

-    {{PropertyData/de|Typ}}: Länge, Radius, Durchmesser usw. Wird normalerweise vom Endanwender nicht geändert.

-    {{PropertyData/de|MessungsTyp}}: »True« - bezogen auf die 3D Geometrie, oder *Projiziert*- bezogen auf die Zeichnung. Normalerweise nicht direkt durch den Endbenutzer verändert.

-    {{PropertyData/de|TheoretischExakt}}: Gibt eine theoretisch exakte (oder grundlegende) Abmessung an.

:   

    :   
        `False`
        
        \- standardmäßig ein gemeinsames Maß, eventuell mit Toleranzen.

    :   
        `True`
        
        \- ein theoretischer Wert. Als solcher darf er keine Toleranzen aufweisen. Der Wert ist durch einen Rahmen um den Wert gekennzeichnet.

-    {{PropertyData/de|ObereToleranz}}: Der Betrag, um den das Stück größer sein könnte als die angezeigte Bemaßung.

-    {{PropertyData/de|UntereToleranz}}: Der Betrag, um den das Stück kleiner sein könnte als die angezeigte Bemaßung.

-    {{PropertyData/de|Umgekehrt}}: Hebt hervor, ob die Dimension einen üblichen oder einen invertierten Wert darstellt.

:   

    :   
        `False`
        
        \- der gewöhnliche Wert wird verwendet. Für Länge ist es eine positive Zahl, für Winkel der schräggestellte Wert (0° - 180°).

    :   
        `True`
        
        \- der umgekehrte Wert wird verwendet. Für Länge eine negative Zahl, für Winkel der Reflexwert (180° - 360°).


</div>


<div class="mw-translate-fuzzy">


{{Properties_Title/de|Format}}

-    {{PropertyData/de|FormatAngabe}}: Ermöglicht das Hinzufügen von zusätzlichem Text zum Bemaßungstext.

:   

    :   Der Dimensionswert ersetzt den %.2f Teil des Textes (oder jeden anderen gültigen Formatangabe - siehe [printf](https://en.wikipedia.org/wiki/Printf_format_string)).

-    {{PropertyData/de|frei wählbar}}: Gibt an, ob **FormatAngabe** als Vorlage oder als aktueller Text behandelt werden soll.

:   

    :   
        `False`
        
        \- ersetze die Formatangabe durch den tatsächlichen Dimensionswert.

    :   
        `True`
        
        \- ignoriere den Bemaßungwert und zeige genau **FormatAngabe** an.


</div>


<div class="mw-translate-fuzzy">

### Ansicht


{{Properties_Title|Base}}

-    **Visibility**: Setzt, ob die Dimension sichtbar ist. `True`: - sichtbar, `False` - versteckt.


{{Properties_Title|Dim Format}}

-    {{PropertyView/de|Schriftart}}: Der Name der Schriftart, die für den Bemaßungstext verwendet werden soll.

-    {{PropertyView/de|Schriftgröße}}: Größe des Bemaßungstextes in mm.

-    {{PropertyView/de|Linienbreite}}: Bemaßungslinienstärke.

-    {{PropertyView/de|Farbe}}: Farbe für Linien und Text.

-    {{PropertyView/de|StandardUndStil}}: Gibt den Standard (und dessen Stil) an, nach dem die Bemaßung gezeichnet wird:

:   

    :   ISO Orientiert - gezeichnet nach ISO 129.1 (Internationale Norm), Text wird so gedreht, dass er parallel zur Tangente der Bemaßungslinie liegt.
    :   ISO Referenzierung - gezeichnet nach ISO-129.1, der Text ist immer horizontal, über der kürzest möglichen Referenzlinie.
    :   ASME Innenliegend - gezeichnet nach ASME Y14.5M (US Norm), der Text ist horizontal, in einem Bruch innerhalb der Maßlinie oder des Bogens eingefügt.
    :   ASME Referenzierung - gezeichnet nach ASME Y14.5M, der Text ist horizontal, eine kurze Referenzlinie ist an der vertikalen Mitte einer Seite angebracht.

-    {{PropertyView/de|RenderingExtent}}: Eher universelle Eigenschaft, die angibt, wie viel Platz die Maßzeichnung einnehmen darf:

:   

    :   None - es werden keine Linien oder Pfeile gezeichnet, sondern nur der nackte Bemaßungswert angezeigt.
    :   Minimal - für Längen und Winkel wird eine einzelne Kopflinie gezeichnet, die den Bemaßungswert mit der *virtuellen Verlängerungslinie* des Endpunktes verbindet. Die Verlängerungslinie selbst wird nicht hinzugefügt.
    :   Durchmesser werden nach Begrenzt Umfang, Radien nach Reduziert Umfang gerendert.
    :   Eingegrenzt - für Längen und Winkel wird eine doppelte Linie (oder ein Bogen) gezeichnet, die die *virtuellen Verlängerungslinien* des Start- und Endpunktes verbindet, wobei die Verlängerungslinien selbst nicht hinzugefügt werden.
    :   Durchmesser werden mit einer minimalen einteiligen Linie vom Bemaßungswert zum nächsten Punkt auf dem Kreis gezeichnet, Radien wie bei ReduziertUmfang.
    :   Normal - der Standardwert. Für Längen und Winkel wird eine doppelseitige Linie (oder ein Bogen) gezeichnet, die die *Verlängerungslinien* des Start- und Endpunktes verbindet, die Verlängerungslinien selbst ebenfalls.
    :   Durchmesser werden als doppelseitige Linien gezeichnet, die den Mittelpunkt treffen und den nächsten und den entferntesten Punkt auf dem Kreis verbinden.
    :   Radien werden als einseitige Linie vom Mittelpunkt zum nächsten Kreisbogenpunkt gezeichnet.
    :    Erweitert\>/code\> - Nur Durchmesser unterstützen diesen Wert, so dass sie horizontal oder vertikal längenähnlich dargestellt werden. Andere Bemaßungstypen werden wie bei Normal Ausdehnung dargestellt.

-    {{PropertyView/de|Pfeilspitzen kippen}}: Standardmäßig bedeutet der Wert *innerhalb* der Dimensionslinie/des Bogens die Pfeile, die *nach außen* zeigen. Wird der Wert *außerhalb* der Bemaßungslinie/des Bogens platziert, zeigen die Pfeile der Bemaßungslinie/des Bogens *nach innen*.

:   

    :   
        `False`
        
        \- Lasse die Richtung der Pfeile automatisch nach der obigen Regel wählen.

    :   {`True`} - Außer Kraft setzen der automatisch gewählten Richtung und erzwingen der entgegengesetzte Richtung.


</div>

## Begrenzungen

Bemaßungsobjekte sind anfällig für das \"[topologisches Benennungsproblem](topological_naming_problem/de.md)\". Das bedeutet, dass bei einer Änderung der 3D Geometrie die Flächen und Kanten des Modells intern umbenannt werden können; wenn eine Bemaßung an eine Kante angehängt wird, die dann geändert wird, kann die Bemaßung brechen. Im Allgemeinen ist es nicht möglich, die projizierten 2D Bemaßungen mit den tatsächlichen 3D Objekten synchronisiert zu halten.

Es wird daher empfohlen, Bemaßungen hinzuzufügen, wenn das 3D Modell nicht mehr verändert wird.

### Zwischenlösung

Wenn du eine TechDraw Ansicht mit Bemaßungen behalten möchtest, die nicht brechen, musst du ein Objekt bemaßen, das sich nicht ändert.

-   Wähle das zu projizierende Objekt aus, wechsle dann zur <img alt="" src=images/Workbench_Part.svg  style="width:24px;"> [Part Arbeitsbereich](Part_Workbench/de.md) und verwende {{MenuCommand/de|Part → <img src="images/Part_SimpleCopy.svg" width=16px> [Einfache Kopie erstellen](Part_SimpleCopy.md)}}. Dadurch wird ein einzelnes Objekt erzeugt, das nicht parametrisch ist, d.h. nicht mehr bearbeitet werden kann.
-   Wähle diese Kopie aus, verwende dann [TechDraw Ansicht](TechDraw_View/de.md) und füge die gewünschten Bemaßungen hinzu.
-   Wenn das ursprüngliche 3D Modell geändert wird, wirken sich die Änderungen weder auf die einfache Kopie noch auf die Bemaßungen in der TechDraw Ansicht aus.

Siehe [Leitbemaßungen](TechDraw_Dimension_Landmark/de.md) für einen weiteren Ansatz zur Umgehung des topologischen Benennungsproblems.

## Skripten


**Siehe auch:**

[TechDraw API](TechDraw_API/de.md) und [FreeCAD Scripting Basics](FreeCAD_Scripting_Basics/de.md).

Das Werkzeug Längenbemaßung kann in [Makros](Macros/de.md) und aus der [Python](Python/de.md) Konsole mit den folgenden Funktionen verwendet werden:


```python
dim1 = FreeCAD.ActiveDocument.addObject('TechDraw::DrawViewDimension','Dimension')
dim1.Type = "Distance"
dim1.References2D=[(view1, 'Edge1')]
rc = page.addView(dim1)
```

## Anmerkungen

-   **Kantenauswahl**. Die Auswahl von Kanten kann schwierig sein. Du kannst den Auswahlbereich für Kanten mit dem Parameter \"/Mod/TechDraw/General/EdgeFuzz\" anpassen (siehe [Std\_DlgParameter](Std_DlgParameter.md)). Dies ist eine dimensionslose Zahl. Die Voreinstellung ist 10.0. Werte im Bereich von 20-30 erleichtern die Auswahl von Kanten spürbar. Große Zahlen führen zu Überlappungen mit anderen Zeichnungselementen.
-   **Nachkommastellen**. Bei Bemaßungen wird standardmäßig die globale Einstellung der Dezimalstellen verwendet. Diese kann über [Einstellungen](TechDraw_Preferences#Dimensions/de.md) oder durch Ändern der FormatSpec Eigenschaft geändert werden.
-   **Mehrfache Objekte**\'. Ansichten können mehrere 3D Objekte als Quelle enthalten. Bemaßungen können auf die Geometrie von jedem Objekt in der Ansicht angewendet werden (z.B. von Objekt1.Vertex0 bis Objekt2.Vertex3).





{{TechDraw Tools navi

}}  