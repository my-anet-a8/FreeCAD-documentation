---
- GuiCommand:/ru
   Name:Part Cone
   Name/ru:Конус
   MenuLocation:Деталь → Примитивы → Конус
   Workbenches:[Part](Part_Workbench/ru.md)
   SeeAlso:[Создать примитивы](Part_Primitives/ru.md)
---

# Part Cone/ru

## Описание

Параметрический усечённый конус доступен из панели инструментов верстака Part, через меню (подменю примитивы), диалогового окна Создать примитивы.

<img alt="" src=images/Otherwisedefault270degree_Part_Cone.png  style="width:300px;"> 
*Конус с параметром "Угол", установленным на 270 градусов (все остальные параметры имеют значения по умолчанию).*

## Применение

1.  Переключитесь на <img alt="" src=images/Workbench_Part.svg  style="width:16px;"> [верстак Part](Part_Workbench/ru.md)
2.  Существует два способа вызова данной команды:
    -   Нажатием на иконку **<img src="images/Part_Cone.svg" width=16px> Конуса** на панели инструментов.
    -   Или через пункт меню **Деталь → Примитивы → <img src="images/Part_Cone.svg" width=16px> Конус**.


<div class="mw-translate-fuzzy">

**Результат:** Значения по умолчанию создают усеченный параметрический конус, определяемый параметрами `Радиус 1(Radius 1)`, `Радиус 2(Radius 2)`, `Высота(Height)` и `Угол(Angle)`. По умолчанию, при создании, конус будет расположен в начале координат (точка 0,0,0). Параметр угол(angle) позволяет создать часть(сектор) конуса (по умолчанию он установлен на 360°), а радиусы 1 и 2 соответствуют радиусу основания и верхнему радиусу усеченного конуса.


</div>

The cone properties can later be edited, either in the [Property editor](Property_editor.md) or by double-clicking the cone in the [Tree view](Tree_view.md).

## Свойства


<div class="mw-translate-fuzzy">

-   **Радиус 1 (Radius 1):** радиус дуги или окружности, определяющей нижнюю грань
-   **Радиус 2 (Radius 2):** радиус дуги или окружности, определяющей верхнюю грань
-   **Высота (Height):** высота Конуса
-   **Угол (Angle):** размер дуги в градусах или полные окружности, определяющих верхнюю и нижнюю грани усеченного конуса. По умолчанию значение 360 создает полностью круговые грани, меньшее значение создаст часть(сектор) конуса, определяемую верхней и нижней гранями, каждая из которых имеет рёбра, определяемые длиной дуги в градусах и двумя радиусами.


</div>

## Scripting

A Part Cone can be created using the following function:


```python
cone = FreeCAD.ActiveDocument.addObject("Part::Cone", "myCone")
```

-   Where {{Incode|"myCone"}} is the name for the object.
-   The function returns the newly created object.



---
![](images/Right_arrow.png) [documentation index](../README.md) > [Part](Part_Workbench.md) > Part Cone/ru
