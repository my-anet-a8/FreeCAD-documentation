---
- GuiCommand:/fr
   Name:FEM MaterialSolid
   Name/fr:FEM Matériau pour solide
   MenuLocation:Model → Materials → Matériau pour le solide
   Workbenches:[FEM](FEM_Workbench/fr.md)
   Shortcut:**M** **S**
   SeeAlso:[Tutoriel FEM](FEM_tutorial/fr.md)
---

# FEM MaterialSolid/fr

## Description

Ajoute des propriétés matériau à une pièce.

![](images/FEMMaterialSolidProperties.png ) 
*Le panneau des tâches des matériaux MEF*

## Utilisation

1.  Pour créer un nouvel objet MaterialSolid, effectuez l\'une des opérations suivantes:
    -   Appuyez sur le bouton **<img src="images/FEM_MaterialSolid.svg" width=16px> [Creates a FEM material for solid (M,S)](FEM_MaterialSolid/fr.md)**.
    -   Sélectionnez l\'option **Model → Materials → <img src="images/FEM_MaterialSolid.svg" width=16px> Matériau pour solide** dans le menu.
2.  Pour éditer un objet MaterialSolid existant:
    -   Double-cliquez dessus dans la [Vue en arborescence](Tree_view/fr.md).
3.  Le panneau des tâches de matériau MEF s\'ouvre.
4.  Sélectionnez un matériau. Pour l\'analyse mécanique d\'ingénierie, **CalculiX-Steel** est une option typique.
5.  Si vous appliquez du matériau à l\'ensemble de l\'objet, ne sélectionnez aucune entité géométrique (laissez la liste de références vide). Le matériau sera appliqué à l\'ensemble du modèle. Sinon, attribuez manuellement du matériau à des pièces de modèle particulières en sélectionnant certains d\'entre eux pour chaque matériau inséré, mais ne laissez aucune partie du modèle sans matériau affecté.
6.  Vous pouvez ajuster les propriétés des matériaux telles que la densité, le module de Young, le rapport de poisson, etc., mais la plupart des matériaux courants sont déjà disponibles dans les préréglages et ils n\'ont pas besoin d\'être modifiés.
7.  Si vous apportez des modifications, vous pouvez enregistrer votre matériel personnalisé.
8.  Appuyez sur le bouton **Close** pour fermer le panneau des tâches.

## Notes

1.  Les propriétés mécaniques du matériau utilisent \*MATERIAL card in CalculiX. Les détails des propriétés mécaniques sont expliqués sur <http://web.mit.edu/calculix_v2.7/CalculiX/ccx_2.7/doc/ccx/node216.html>





{{FEM Tools navi

}}



---
![](images/Right_arrow.png) [documentation index](../README.md) > [FEM](Category_FEM.md) > FEM MaterialSolid/fr
