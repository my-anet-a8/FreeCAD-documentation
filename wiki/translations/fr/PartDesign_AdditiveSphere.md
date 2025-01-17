---
- GuiCommand:/fr
   Name:PartDesign AdditiveSphere
   Name/fr:PartDesign Sphère additive
   MenuLocation:Conception de pièces → Créer une primitive additive → Sphère additive
   Workbenches:[PartDesign](PartDesign_Workbench/fr.md)
   Version:0.17
   SeeAlso:[PartDesign Primitives additives](PartDesign_CompPrimitiveAdditive/fr.md)
---

# PartDesign AdditiveSphere/fr

## Description

Insére une sphère primitive dans un corps actif (body) comme fonction de base, ou la fusionne avec les fonctions existantes.

<img alt="" src=images/PartDesign_AdditiveSphere_example.png  style="width:200px;">

## Utilisation

1.  Presser le bouton **<img src="images/PartDesign_AdditiveSphere.svg" width=24px> '''Sphère additive'''**. **Remarque**: la sphère additive fait partie du menu d\'icônes appelé *Créer une primitive additive*. Après le lancement de FreeCAD, le cube additif est affiché par défaut dans la barre d\'outils. Pour obtenir la sphère additive, cliquer sur la flèche vers le bas et choisissez <img alt="" src=images/PartDesign_AdditiveSphere.png  style="width:24px;"> Sphère additive dans le menu.
2.  Définir les paramètres primitifs et de l\'[ancrage](Part_EditAttachment/fr.md).
3.  Cliquer sur **OK**.
4.  Une sphère apparaît dans le corps actif.

## Options

La Sphère peut être éditée après sa création de deux façons:

-   Double-cliquez la dans l\'arborescence ou faire un clic droit dessus et sélectionnez **Éditer la primitive** dans le menu contextuel. Cela fait apparaître les paramètres des Primitives.
-   Via l\'[Éditeur de propriétés](Property_editor/fr.md).

## Propriétés

-    {{PropertyData/fr|Attachment}}: définit les modes d\'ancrage ainsi que le décalage d\'ancrage. Voir [Part Ancrage](Part_EditAttachment/fr.md).

-    {{PropertyData/fr|Label}}: donne le nom de la Sphère. Changez si nécessaire.

-    {{PropertyData/fr|Radius}}: rayon de la sphère.

-    {{PropertyData/fr|Angle1}}: (nommé *V parameter* dans Paramètres de la primitive) coupe la sphère dans sa partie inférieure par un cercle parallèle à la section (-90 pour une sphère entière)

-    {{PropertyData/fr|Angle2}}: (sans nom dans Paramètres de la primitive) coupe la sphère dans la partie supérieure en ellipsoïde (90 pour une sphère entière).

-    {{PropertyData/fr|Angle3}}: (nommé *U parameter* dans Paramètres de la primitive) angle de rotation de la section (comme une part de melon)(360° pour une sphère entière).





{{PartDesign Tools navi

}}



---
![](images/Right_arrow.png) [documentation index](../README.md) > [PartDesign](PartDesign_Workbench.md) > PartDesign AdditiveSphere/fr
