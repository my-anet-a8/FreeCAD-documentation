


<div class="mw-translate-fuzzy">


{{VeryImportantMessage|LuxRender n'est plus en développement car le projet a été redémarré sous le nom de [LuxCoreRender](LuxCoreRender/fr.md) avec une réécriture majeure du code et de nombreux changements de compatibilité. L'information ici est fournie parce que FreeCAD est toujours livré par défaut (à partir de la version 0.19-24276) avec l'[atelier Raytracing](Raytracing_Workbench/fr.md), qui ne supporte officiellement que LuxRender. Cependant, il semble également fonctionner avec [LuxCoreRender](LuxCoreRender/fr.md) donc pensez à l'essayer avant d'utiliser LuxRender.}}


</div>

# Description


<div class="mw-translate-fuzzy">

# Description 

[LuxRender](https://luxcorerender.org/history/) est l\'un des deux moteurs de rendu supportés par l\'[atelier Raytracing](Raytracing_Workbench/fr.md) avec [POV-Ray](POV-Ray/fr.md). En 2013, le projet a été redémarré pour devenir [LuxCoreRender](LuxCoreRender/fr.md), avec une réécriture majeure du code et des changements de compatibilité, le projet LuxRender a donc été abandonné. Officiellement, [LuxCoreRender](LuxCoreRender/fr.md) n\'est pas supporté par l\'[atelier Raytracing](Raytracing_Workbench/fr.md), bien qu\'il puisse être intéressant d\'essayer.


</div>

# Installation

## Raytracing Workbench 


<div class="mw-translate-fuzzy">

# Installation 

## Atelier Raytracing 


{{VeryImportantMessage|L'[atelier Raytracing](Raytracing_Workbench/fr.md) a été remplacé par le nouvel [https://github.com/FreeCAD/FreeCAD-render atelier Render], qui est destiné à le remplacer. Il ne doit pas être confondu avec [Le module de rendus](Render_project.md), arrêté et dépassé. Le Render Workbench peut être installé via le [Gestionnaire d'Addon](Std_AddonMgr/fr.md). L'information ici est fournie parce que par défaut FreeCAD est toujours livré (à partir de 0.19-24276) avec l'atelier Raytracing et parce que le nouveau module devrait fondamentalement fonctionner de la même manière}}

.


</div>

### Stable Version 


<div class="mw-translate-fuzzy">

### Version stable 

La dernière version stable est [LuxRender 1.6 (2017-12-28)](https://github.com/LuxCoreRender/LuxCore/releases/tag/luxrender_v1.6).


</div>

#### Linux


<div class="mw-translate-fuzzy">

#### Linux 

***Binaires compilés***


</div>

Comme LuxRender n\'est plus développé, presque aucune distribution ne le possède encore dans ses dépôts, vous devrez donc installer manuellement les binaires officiels. Déterminez d\'abord si votre carte graphique supporte [OpenCL](https://en.wikipedia.org/wiki/OpenCL) et si vous avez installé toutes les dépendances nécessaires. Si c\'est le cas, téléchargez [LuxRender 1.6 with OpenCL support](https://github.com/LuxCoreRender/LuxCore/releases/download/luxrender_v1.6/lux-v1.6-x86_64-sse2-OpenCL.tar.bz2). Sinon, téléchargez [LuxRender 1.6 sans OpenCL](https://github.com/LuxCoreRender/LuxCore/releases/download/luxrender_v1.6/lux-v1.6-x86_64-sse2-NoOpenCL.tar.bz2), mais pensez à vous procurer une carte graphique plus récente ou à installer les logiciels nécessaires pour l\'activer sur votre ordinateur.

La solution la plus rapide (bien que ce ne soit pas la meilleure pratique) est d\'extraire le contenu de l\'archive dans un emplacement approprié, comme *\~\\LuxRender*. Si nécessaire, modifiez les autorisations de fichiers afin que votre utilisateur puisse exécuter les fichiers que vous venez d\'extraire.

***Compilation à partir de la source***

Si votre distribution n\'a pas LuxRender dans ses dépôts et que les binaires officiels ne fonctionnent pas sur votre distribution, ou si vous le souhaitez, il est possible de compiler LuxRender à partir des sources. [Télécharger le code source de LuxRender 1.6 depuis GitHub](https://github.com/LuxCoreRender/LuxCore/archive/refs/tags/luxrender_v1.6.tar.gz)

***Configuration de FreeCAD***

Après avoir installé LuxCoreRender, lancez FreeCAD, ouvrez [Réglage des préférences](Preferences_Editor/fr.md), [charger l\'atelier Raytracing](Preferences_Editor/fr#Ateliers_non_charg.C3.A9s.md) et allez dans les [Raytracing Préférences](Raytracing_Preferences/fr.md).

Définissez le chemin de l\'exécutable Luxrender pour qu\'il pointe vers votre installation de LuxRender, en particulier vers l\'exécutable *luxrender*, et appliquez. Dans l\'exemple ci-dessus, le chemin serait *\~\\LuxRender\\luxrender*.

#### macOS


<div class="mw-translate-fuzzy">

#### macOS 

Utilisez l\'[installateur pour OSX officiel LuxRender 1.6](https://github.com/LuxCoreRender/LuxCore/releases/download/luxrender_v1.6/LuxRender_1.6_OSXIntel_64bit.dmg).


</div>

#### Windows


<div class="mw-translate-fuzzy">

#### Windows 

Déterminez d\'abord si votre carte graphique supporte [OpenCL](https://fr.wikipedia.org/wiki/OpenCL) et si vous avez installé les pilotes graphiques nécessaires. Si c\'est le cas, téléchargez [Configuration de LuxRender 1.6 avec support OpenCL](https://github.com/LuxCoreRender/LuxCore/releases/download/luxrender_v1.6/LuxRender.1.6.x64.OpenCL.Setup.exe). Sinon, téléchargez [Configuration de LuxRender 1.6 sans support OpenCL](https://github.com/LuxCoreRender/LuxCore/releases/download/luxrender_v1.6/LuxRender.1.6.x64.NoOpenCL.Setup.exe), mais pensez à vous procurer une carte graphique plus récente ou à installer les logiciels nécessaires pour l\'activer sur votre ordinateur. Exécutez ensuite le programme d\'installation téléchargé et suivez les étapes proposées.


</div>

Par défaut, le dossier de destination est *C:\\Program Files\\LuxRender*, avec des exemples de scènes dans *C:\\Users\\Public\\Documents\\LuxRender\\Example Scene*.


<div class="mw-translate-fuzzy">

Après avoir installé LuxCoreRender, lancez FreeCAD, ouvrez [Réglage des préférences](Preferences_Editor/fr.md), [charger l\'atelier Raytracing](Preferences_Editor/fr#Ateliers_non_charg.C3.A9s.md) et allez dans les [Raytracing Préférences](Raytracing_Preferences/fr.md).


</div>

Définissez le chemin de l\'exécutable de Luxrender pour qu\'il pointe vers votre installation de LuxRender, généralement c\'est *C:/Program Files/LuxRender/luxrender.exe* et appliquez.

### Development Version 


<div class="mw-translate-fuzzy">

### Version de développement 

Il n\'existe pas de version de développement de LuxRender, le développement ayant été arrêté au profit du reboot [LuxCoreRender](LuxCoreRender/fr.md).


</div>

## Render Workbench 


<div class="mw-translate-fuzzy">

## Atelier Render 

L\'[Atelier Render](https://github.com/FreeCAD/FreeCAD-render) a abandonné la prise en charge de LuxRender, car il est dépassé. Il supporte à la place le redémarrage moderne [LuxCoreRender](LuxCoreRender/fr.md).


</div>
