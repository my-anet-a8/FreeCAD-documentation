

<img alt="Icône de l\'atelier externe Fasteners" src=images/Fasteners_workbench_icon.svg  style="width:128px;">


{{TOCright}}

## Introduction

L\'<img alt="" src=images/Fasteners_workbench_icon.svg  style="width:24px;"> [atelier Fasteners](Fasteners_Workbench/fr.md) est un [atelier externe](External_workbenches/fr.md) qui permet d\'ajouter/fixer diverses fixations aux pièces.

## Utilisation

L\'utilisation est assez simple :

1.  Installez l\'atelier Fasteners via le [gestionnaire d'addon](Addon_Manager/fr.md)
2.  Démarrer un nouveau document dans FreeCAD. Sélectionnez l\'atelier Fasteners dans la liste déroulante.
3.  Sélectionnez l\'<img alt="" src=images/Fasteners_workbench_icon.svg  style="width:24px;"> [atelier Fasteners](Fasteners_Workbench/fr.md) dans le [menu déroulant des ateliers](Std_Workbench/fr#Dans_le_menu_d.C3.A9roulant.md).
4.  La [barre d\'outils](#Barre_d.27outils.md) appartenant à l\'atelier sera affichée.

Utilisation simple : En cliquant sur l\'un des boutons de fixation, la fixation en question sera créée à l\'origine avec des propriétés par défaut. Pour modifier les propriétés d\'une fixation, sélectionnez-la et allez dans l\'onglet **Data** de l\'[Éditeur de propriétés](Property_editor/fr.md).

## Problèmes connus 

-   D\'autres problèmes/demandes de fonctionnalités sont disponibles dans la [file d\'attente GitHub des problèmes de l\'atelier Fasteners](https://github.com/shaise/FreeCAD_FastenersWB/issues?utf8=✓&q=is%3Aissue).

## Références

-   Auteur : [shaise](http://theseger.com/projects/author/shaise/)
    -   Concepteur d\'objets : Ulrich Brammer
    -   Architecture de l\'atelier : Shai Seger
-   Page d\'accueil : <http://theseger.com/projects/2015/06/fasteners-workbench-for-freecad/>
-   Code source sur github : <https://github.com/shaise/FreeCAD_FastenersWB>

## Installation

Cet atelier peut être installé à partir du <img alt="" src=images/Std_AddonMgr.svg  style="width:24px;"> [Gestionnaire d\'Addon](Std_AddonMgr/fr.md). Pour une installation manuelle, voir [Installer des ateliers supplémentaires](Installing_more_workbenches/fr.md).

## Barre d\'outils 

L\'atelier Fasteners comporte deux barres d\'outils. La barre d\'outils **FS Screws** contient de nombreux outils. Si nécessaire, elle peut être étendue en appuyant sur le bouton **&gt;&gt;**.

![](images/Fasteners_toolbars.png ) *Les barres d'outils de l'atelier Fasteners*

## Outils

Pour une description détaillée, voir [ici](http://theseger.com/projects/2015/06/fasteners-workbench-for-freecad/).

### Commandes


<div class="mw-translate-fuzzy">

-   <img alt="" src=images/Fasteners_Flip.svg  style="width:32px;"> [Flip](Fasteners_Flip.md): inverser l\'orientation
-   <img alt="" src=images/Fasteners_Move.svg  style="width:32px;"> [Move](Fasteners_Move.md): déplacer vers un nouvel emplacement
-   <img alt="" src=images/Fasteners_Shape.svg  style="width:32px;"> [Shape](Fasteners_Shape.md): changez l\'objet en une forme simple non paramétrique
-   <img alt="" src=images/Fasteners_MatchTypeInner.svg  style="width:32px;"> [Match Type Inner](Fasteners_MatchTypeInner.md):
-   <img alt="" src=images/Fasteners_MatchTypeOuter.svg  style="width:32px;"> [Match Type Outer](Fasteners_MatchTypeOuter.md): faire correspondre la vis au diamètre du filetage extérieur (trou de passage)
-   <img alt="" src=images/Fasteners_BOM.svg  style="width:32px;"> [BOM](Fasteners_BOM.md): générer une nomenclature
-   <img alt="" src=images/Fasteners_ScrewCalculator.svg  style="width:32px;"> [Screw Calculator](Fasteners_ScrewCalculator.md): afficher une calculatrice de trou de vis
-   <img alt="" src=images/Fasteners_ChamferHole.svg  style="width:32px;"> [Chamfer Hole](Fasteners_ChamferHole.md): chanfreinage trou pour vis à tête fraisée
-   <img alt="" src=images/Fasteners_ChangeParameters.svg  style="width:32px;"> [Change Parameters](Fasteners_ChangeParameters.md): Changer les paramètres des fixations sélectionnées


</div>

-   <img alt="" src=images/Fasteners_Move.svg  style="width:32px;"> [Move fastener](Fasteners_Move.md): move fastener to a new location.

-   <img alt="" src=images/Fasteners_Shape.svg  style="width:32px;"> [Simplify shape](Fasteners_Shape.md): change object to simple non-parametric shape.

-   <img alt="" src=images/Fasteners_MatchTypeInner.svg  style="width:32px;"> [Match screws by inner thread diameter (Tap hole)](Fasteners_MatchTypeInner.md): match screws by inner thread diameter (Tap hole).

-   <img alt="" src=images/Fasteners_MatchTypeOuter.svg  style="width:32px;"> [Match screws by outer thread diameter (Pass hole)](Fasteners_MatchTypeOuter.md): match screws by outer thread diameter (Pass hole).

-   <img alt="" src=images/Fasteners_BOM.svg  style="width:32px;"> [Generate BOM](Fasteners_BOM.md): generate fasteners bill of materials.

-   <img alt="" src=images/Fasteners_ScrewCalculator.svg  style="width:32px;"> [Screw calculator](Fasteners_ScrewCalculator.md): show a screw hole calculator.

-   <img alt="" src=images/Fasteners_ChamferHole.svg  style="width:32px;"> [Make countersunk](Fasteners_ChamferHole.md): chamfer holes for countersunk screws.

-   <img alt="" src=images/Fasteners_ChangeParameters.svg  style="width:32px;"> [Change fastener parameters](Fasteners_ChangeParameters.md): change parameters of selected fasteners.

### Fasteners PEM and PCB 

-   <img alt="" src=images/Fasteners_PEMPressNut.svg  style="width:32px;"> **PEM** Self clinching metric nut.

-   <img alt="" src=images/Fasteners_PEMTHStandoff.svg  style="width:32px;"> **PEM** Self clinching metric standoff.

-   <img alt="" src=images/Fasteners_PEMStud.svg  style="width:32px;"> **PEM** Self clinching metric stud.

-   <img alt="" src=images/Fasteners_PCBStandoff.svg  style="width:32px;"> **PCB** Metric standoff.

-   <img alt="" src=images/Fasteners_PCBSpacer.svg  style="width:32px;"> **PCB** Metric spacer.

### Fasteners DIN, EN and ISO 

-   <img alt="" src=images/Fasteners_ISO4017.svg  style="width:32px;"> 
**ISO 4017** Hexagon head screw. *Product grades A and B.*

-   <img alt="" src=images/Fasteners_ISO4014.svg  style="width:32px;"> 
**ISO 4014** Hexagon head bolt. *Product grades A and B.*

-   <img alt="" src=images/Fasteners_EN1662.svg  style="width:32px;"> **EN 1662** Hexagon head bolt with flange, small series.

-   <img alt="" src=images/Fasteners_EN1665.svg  style="width:32px;"> **EN 1665** Hexagon bolt with flange, heavy series.

-   <img alt="" src=images/Fasteners_ISO4762.svg  style="width:32px;"> **ISO 4762** Hexagon socket head cap screw.

-   <img alt="" src=images/Fasteners_DIN7984.svg  style="width:32px;"> **DIN 7984** Hexagon socket head cap screw with low head.

-   <img alt="" src=images/Fasteners_DIN6912.svg  style="width:32px;"> **DIN 6912** Hexagon socket head cap screw with low head with center.

-   <img alt="" src=images/Fasteners_ISO7380-1.svg  style="width:32px;"> **ISO 7380-1** Hexagon socket button head screw.

-   <img alt="" src=images/Fasteners_ISO7380-2.svg  style="width:32px;"> **ISO 7380-2** Hexagon socket button head screw with collar.

-   <img alt="" src=images/Fasteners_ISO10642.svg  style="width:32px;"> **ISO 10642** Hexagon socket countersunk head screw.

-   <img alt="" src=images/Fasteners_ISO2009.svg  style="width:32px;"> 
**ISO 2009** Slotted countersunk flat head screw. *Product grade A.*

-   <img alt="" src=images/Fasteners_ISO2010.svg  style="width:32px;"> 
**ISO 2010** Slotted raised countersunk head screw. *Product grade A.*

-   <img alt="" src=images/Fasteners_ISO1580.svg  style="width:32px;"> 
**ISO 1580** Slotted pan head screw. *Product grade A.*

-   <img alt="" src=images/Fasteners_ISO1207.svg  style="width:32px;"> 
**ISO 1207** Slotted cheese head screw. *Product grade A.*

-   <img alt="" src=images/Fasteners_DIN967.svg  style="width:32px;"> **DIN 967** Cross recessed pan head screw with collar.

-   <img alt="" src=images/Fasteners_ISO7045.svg  style="width:32px;"> 
**ISO 7045** Pan head screw type H cross recess. *Product grade A.*

-   <img alt="" src=images/Fasteners_ISO7046.svg  style="width:32px;"> 
**ISO 7046** Countersunk flat head screw H cross recess. *Product grade A.*

-   <img alt="" src=images/Fasteners_ISO7047.svg  style="width:32px;"> 
**ISO 7047** Raised countersunk head screw H cross recess. *Product grade A.*

-   <img alt="" src=images/Fasteners_ISO7048.svg  style="width:32px;"> **ISO 7048** Cheese head screw with type H cross recess.

-   <img alt="" src=images/Fasteners_ISO14579.svg  style="width:32px;"> **ISO 14579** Hexalobular socket head cap screw.

-   <img alt="" src=images/Fasteners_ISO14580.svg  style="width:32px;"> **ISO 14580** Hexalobular socket cheese head screw.

-   <img alt="" src=images/Fasteners_ISO14582.svg  style="width:32px;"> **ISO 14582** Hexalobular socket countersunk head screw, high head.

-   <img alt="" src=images/Fasteners_ISO14583.svg  style="width:32px;"> **ISO 14583** Hexalobular socket pan head screw.

-   <img alt="" src=images/Fasteners_ISO14584.svg  style="width:32px;"> **ISO 14584** Hexalobular socket raised countersunk head screw.

-   <img alt="" src=images/Fasteners_ISO7379.svg  style="width:32px;"> **ISO 7379** Hexagon socket head shoulder screw.

-   <img alt="" src=images/Fasteners_ISO7089.svg  style="width:32px;"> 
**ISO 7089** Plain washer, normal series. *Product grade A.*

-   <img alt="" src=images/Fasteners_ISO7090.svg  style="width:32px;"> 
**ISO 7090** Plain washer chamfered, normal series. *Product grade A.*

-   <img alt="" src=images/Fasteners_ISO7092.svg  style="width:32px;"> **ISO 7092** Plain washer, small series.

-   <img alt="" src=images/Fasteners_ISO7093-1.svg  style="width:32px;"> 
**ISO 7093-1** Plain washer, large series. *Product grade A.*

-   <img alt="" src=images/Fasteners_ISO7094.svg  style="width:32px;"> **ISO 7094** Plain washer, extra large series.

-   <img alt="" src=images/Fasteners_ISO4026.svg  style="width:32px;"> **ISO 4026** Hexagon socket set screw with flat point.

-   <img alt="" src=images/Fasteners_ISO4027.svg  style="width:32px;"> **ISO 4027** Hexagon socket set screw with cone point.

-   <img alt="" src=images/Fasteners_ISO4028.svg  style="width:32px;"> **ISO 4028** Hexagon socket set screw with dog point.

-   <img alt="" src=images/Fasteners_ISO4029.svg  style="width:32px;"> **ISO 4029** Hexagon socket set screw with cup point.

-   <img alt="" src=images/Fasteners_ISO4032.svg  style="width:32px;"> 
**ISO 4032** Hexagon nut, style 1. *Product grades A and B.*

-   <img alt="" src=images/Fasteners_ISO4033.svg  style="width:32px;"> 
**ISO 4033** Hexagon nut, style 2. *Product grades A and B.*

-   <img alt="" src=images/Fasteners_ISO4035.svg  style="width:32px;"> 
**ISO 4035** Hexagon thin nut, chamfered. *Product grades A and B.*

-   <img alt="" src=images/Fasteners_EN1661.svg  style="width:32px;"> **EN 1661** Hexagon nut with flange.

-   <img alt="" src=images/Fasteners_DIN557.svg  style="width:32px;"> **DIN 557** Square nut.

-   <img alt="" src=images/Fasteners_DIN562.svg  style="width:32px;"> **DIN 562** Square nut.

-   <img alt="" src=images/Fasteners_DIN985.svg  style="width:32px;"> **DIN 985** Nyloc nut.

### Fasteners ASME 

-   <img alt="" src=images/Fasteners_ASMEB18.2.1.6.svg  style="width:32px;"> **ASME B18.2.1.6** UNC Hex head screw.

-   <img alt="" src=images/Fasteners_ASMEB18.2.1.8.svg  style="width:32px;"> **ASME B18.2.1.8** UNC Hex head screw with flange.

-   <img alt="" src=images/Fasteners_ASMEB18.2.2.1A.svg  style="width:32px;"> **ASME B18.2.2.1A** UNC Machine screw nut.

-   <img alt="" src=images/Fasteners_ASMEB18.2.2.4A.svg  style="width:32px;"> **ASME B18.2.2.4A** UNC Hexagon nut.

-   <img alt="" src=images/Fasteners_ASMEB18.2.2.4B.svg  style="width:32px;"> **ASME B18.2.2.4B** UNC Hexagon thin nut.

-   <img alt="" src=images/Fasteners_ASMEB18.3.1A.svg  style="width:32px;"> **ASME B18.3.1A** UNC Hex socket head cap screw.

-   <img alt="" src=images/Fasteners_ASMEB18.3.2.svg  style="width:32px;"> **ASME B18.3.2** UNC Hex socket countersunk head screw.

-   <img alt="" src=images/Fasteners_ASMEB18.3.3A.svg  style="width:32px;"> **ASME B18.3.3A** UNC Hex socket button head screw.

-   <img alt="" src=images/Fasteners_ASMEB18.3.3B.svg  style="width:32px;"> **ASME B18.3.3B** UNC Hex socket button head screw with flange.

-   <img alt="" src=images/Fasteners_ASMEB18.3.4.svg  style="width:32px;"> **ASME B18.3.4** UNC Hexagon socket head shoulder screw.

-   <img alt="" src=images/Fasteners_ASMEB18.3.5A.svg  style="width:32px;"> **ASME B18.3.5A** UNC Hexagon socket set screw with flat point.

-   <img alt="" src=images/Fasteners_ASMEB18.3.5B.svg  style="width:32px;"> **ASME B18.3.5B** UNC Hexagon socket set screw with cone point.

-   <img alt="" src=images/Fasteners_ASMEB18.3.5C.svg  style="width:32px;"> **ASME B18.3.5C** UNC Hexagon socket set screw with dog point.

-   <img alt="" src=images/Fasteners_ASMEB18.3.5D.svg  style="width:32px;"> **ASME B18.3.5D** UNC Hexagon socket set screw with cup point.

-   <img alt="" src=images/Fasteners_ASMEB18.6.3.1A.svg  style="width:32px;"> **ASME B18.6.3.1A** UNC slotted countersunk flat head screw.

-   <img alt="" src=images/Fasteners_ASMEB18.21.1.12A.svg  style="width:32px;"> **ASME B18.21.1.12A** UN washer, narrow series.

-   <img alt="" src=images/Fasteners_ASMEB18.21.1.12B.svg  style="width:32px;"> **ASME B18.21.1.12B** UN washer, regular series.

-   <img alt="" src=images/Fasteners_ASMEB18.21.1.12C.svg  style="width:32px;"> **ASME B18.21.1.12C** UN washer, wide series.

### Fasteners miscellaneous 

-   <img alt="" src=images/Fasteners_ScrewTap.svg  style="width:32px;"> Arbitrary length threaded rod for tapping holes (metric).

-   <img alt="" src=images/Fasteners_ScrewTapInch.svg  style="width:32px;"> Arbitrary length threaded rod for tapping holes (inch).

-   <img alt="" src=images/Fasteners_ScrewDie.svg  style="width:32px;"> Arbitrary length threaded tube for cutting external threads (metric).

-   <img alt="" src=images/Fasteners_ScrewDieInch.svg  style="width:32px;"> Arbitrary length threaded tube for cutting external threads (inch).

-   <img alt="" src=images/Fasteners_ThreadedRod.svg  style="width:32px;"> Arbitrary length **DIN 975** threaded rod (metric).

-   <img alt="" src=images/Fasteners_ThreadedRodInch.svg  style="width:32px;"> Arbitrary length **UNC** threaded rod (inch).

## Autres

-   <img alt="" src=images/preferences-fasteners.svg  style="width:32px;"> 
**Préférences Fasteners**
-   <img alt="" src=images/Fasteners_workbench_icon.svg  style="width:32px;"> 
**Icône Fasteners**

## Liens relatifs à l\'atelier 

-   Wiki de l\'atelier : <http://theseger.com/projects/2015/06/fasteners-workbench-for-freecad/>
-   Wiki FreeCAD : <https://www.freecadweb.org/wiki/Fasteners_Workbench>
-   Forum FreeCAD : <https://forum.freecadweb.org/viewtopic.php?t=11429>
-   Tutoriels - Comment utiliser : <http://theseger.com/projects/2015/06/fasteners-workbench-for-freecad/>
-   Vidéos :
-   Fichiers :
-   Rapporter les bugs : SVP rapporter les bugs sur <https://github.com/shaise/FreeCAD_FastenersWB/issues>
-   Installation : <http://theseger.com/projects/2015/06/fasteners-workbench-for-freecad/>

## Autres liens 

-   [Génération de trous pour vis à tête fraisée dans freecad (en)](http://theseger.com/projects/2015/07/generating-holes-for-countersunk-screws-in-freecad/)
-   [BOLTS](https://github.com/jreinhardt/BOLTS): une librairie ouverte pour les spécifications techniques
-   [Ateliers externes](External_workbenches/fr.md)
-   [Macros](Macros_recipes/fr.md)



[Category:Addons{{\#translation:}}](Category:Addons.md) [Category:External Command Reference{{\#translation:}}](Category:External_Command_Reference.md) [Category:External Workbenches{{\#translation:}}](Category:External_Workbenches.md) [Category:Fasteners{{\#translation:}}](Category:Fasteners.md)