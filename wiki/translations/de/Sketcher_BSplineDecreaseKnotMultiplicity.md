---
- GuiCommand:/de
   Name:Sketcher BSplineDecreaseKnotMultiplicity
   Name/de:Skizzierer BSplineKnotenVielfaltVerringern
   Workbenches:[Skizzierer](Sketcher_Workbench/de.md)
   MenuLocation:Skizze → Skizzierer B-spline Werkzeuge → Knotenvielfalt verringern
   Version:0.17
   SeeAlso:[Erstelle B-spline](Sketcher_CompCreateBSpline/de.md)
---

# Sketcher BSplineDecreaseKnotMultiplicity/de


</div>

## Beschreibung


<div class="mw-translate-fuzzy">

Verringert die Knotenvielfalt eines B-Spline Kurvenknotens (siehe [B-Spline](https://en.wikipedia.org/wiki/B-spline)).


</div>

B-splines are basically a combination of [Bézier curves](B-Splines#B.C3.A9zier_curves.md) (nicely explained in [this](https://www.youtube.com/watch?v=bE1MrrqBAl8) and [this](https://www.youtube.com/watch?v=xXJylM2S72s) video). The points where two Bézier curves are connected to form the spline are called knots. A knot on a degree *d* spline with the multiplicity *m* means that the curve left and right to the knot has at least an equal *n* order derivative (called *C*^*n*^ continuity) whereas $n=d-m$.
Here is a cubic spline ($d=3$) whose knots have the multiplicity 1. The multiplicity is indicated by the number in parentheses. The indication can be changed using the toolbar button **[<img src=images/Sketcher_BSplineKnotMultiplicity.svg style="width:24px"> [Show/hide B-spline knot multiplicity](Sketcher_BSplineKnotMultiplicity.md)**):

<img alt="" src=images/Sketcher_KnotMultiplicity_multiplicity1.png  style="width:400px;">


<div class="mw-translate-fuzzy">



*B-spline Kurve zeigt abnehmende Knotenvielfalt.*


</div>

A multiplicity of 3 will change this spline so that even the first order derivatives are not equal (*C*^0^ continuity). Here is the same spline where the left\'s knot multiplicity was increased to 3:

<img alt="" src=images/Sketcher_KnotMultiplicity_multiplicity3.png  style="width:400px;"> 
*B-spline from above with knot multiplicity 3. A control point was moved to show that the knot has ''C''<sup>0</sup> continuity.*

A consequence of a higher multiplicity is that for the price of loosing continuity you gain local control. This means the change of one control point only affects the spline locally to this changed point. This can be seen in this example, where the spline from the first image above was taken and its second control point from the right side was moved up:

<img alt="" src=images/Sketcher_KnotMultiplicity_locality.png  style="width:400px;"> 
*Effect of locality due to different multiplicity.*

One can see that the spline with knot multiplicity 1 is completely changed while the one with multiplicity 2 kept its form at its left side.

**Note:** If you decrease the multiplicity, the knot vanishes, because mathematically it appears then zero times in the knot vector, meaning there is no longer a basis function. Understanding this, requires some math, but it will also be clear when you look at the multiplicity: For example degree = 3 then multiplicity = 0 means that at the position of the knot two Bézier pieces are connected with *C*^3^ continuity. So the third derivative should be equal on both sides of the knot. However for a cubic Bézier curve (that is a polynom with degree 3) , this means both sides must be part of the same curve. So there is then actually no longer a knot connecting 2 different Bézier curves, the former knot is then simply a point onto one Bézier curve.

## Anwendung


<div class="mw-translate-fuzzy">

1.  Wähle einen B-Spline Knoten
2.  Rufe das Werkzeug mit mehreren Methoden auf:
    -   Drücke die **[<img src=images/Sketcher_BSplineDecreaseKnotMultiplicity.svg style="width:16px">  [B-spline Knotenvervielfalt Verringern](Sketcher_BSplineDecreaseKnotMultiplicity/de.md)** Schaltfläche.
    -   Verwende den **Skizze → Skizzierer B-Spline Werkzeuge → [<img src=images/Sketcher_BSplineDecreaseKnotMultiplicity.svg style="width:16px"> Knotenvervielfalt Verringern** Eintrag im oberen Menü.


</div>

**Note:** Decreasing the multiplicity from 1 to 0 will remove the knot since the result would be a curve with an \"edge\" at the knot position (*C*^0^ continuity) and this is not supported. (To create curves with an \"edges\", you can create two splines and connect them.)


<div class="mw-translate-fuzzy">





</div>


{{Sketcher Tools navi

}}



---
![](images/Right_arrow.png) [documentation index](../README.md) > [Sketcher](Sketcher_Workbench.md) > Sketcher BSplineDecreaseKnotMultiplicity/de
