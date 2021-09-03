---
- GuiCommand:/ro
   Name:Constraint Horizontal
   Name/ro:Constraint Horizontal
   Workbenches:[Sketcher](Sketcher_Workbench/ro.md)
   Shortcut:H
   MenuLocation:Sketch → Sketcher constraints → Constrain horizontally
   SeeAlso:[Constraint Vertical](Sketcher_ConstrainVertical/ro.md)
---


</div>

## Descriere

**Constrângerea orizontală** forțează o linie din schiță să fie paralelă cu axa orizontală a schiței.


<div class="mw-translate-fuzzy">

## Cum se folosește 


</div>


<div class="mw-translate-fuzzy">

<img alt="" src=images/HorizontalConstraint1.png  style="width:256px;"> Selectați linia făcând click pe ea.
<img alt="" src=images/HorizontalConstraint2.png  style="width:256px;"> Linia își schimbă culaorea în verde închis.
<img alt="" src=images/HorizontalConstraint3.png  style="width:256px;"> Apply the Horizontal Constraint by clicking on the Horizontal Constraint icon <img alt="" src=images/Constraint_Horizontal.png  style="width:16px;"> în bara de instrumente Sketcher Constructors sau selectând elementul de meniu Sketcher Constructors din Atelierul Sketcher (sau elementul de design al piesei de proiectare a bancului de lucru Part Design). Linia selectată este constrânsă să fie paralelă cu axa orizontală a schiței.
<img alt="" src=images/HorizontalConstraint4.png  style="width:256px;"> Multiple linii pot fi selectate,
<img alt="" src=images/HorizontalConstraint5.png  style="width:256px;"> și apoi aplicarea constrângerii așa cum este descrisă mai sus, ele sunt constrânse să fie paralele cu axa orizontală.


</div>

<img alt="" src=images/HorizontalConstraint2.png  style="width:500px;"> 
*The line turns dark green.*

<img alt="" src=images/HorizontalConstraint3.png  style="width:500px;"> 
*Apply the Horizontal Constraint by clicking on the **<img src=images/Sketcher_ConstrainHorizontal.svg style="width:16px"> [Constraint horizontal](Sketcher_ConstrainHorizontal.md)* in the Sketcher Constraints toolbar or by selecting the Constrain horizontally menu item in the Sketcher constraints sub menu of the Sketcher menu item in the Sketcher work bench (or the Part Design menu item of the Part Design work bench). The selected line is constrained to be parallel to the horizontal axis of the sketch.**

<img alt="" src=images/HorizontalConstraint4.png  style="width:500px;"> 
*Multiple lines may be selected*

<img alt="" src=images/HorizontalConstraint5.png  style="width:500px;"> 
*and then applying the constraint as described above, they are constrained to be parallel to the sketch horizontal axis.*

## Scripting


```pythonSketch.addConstraint(Sketcher.Constraint('Horizontal', Line))```

The [Sketcher scripting](Sketcher_scripting.md) page explains the values which can be used for `Line` and contains further examples on how to create constraints from Python scripts.


<div class="mw-translate-fuzzy">


</div>


{{Sketcher Tools navi

}}  

[Category:Sketcher/ro](Category:Sketcher/ro.md)