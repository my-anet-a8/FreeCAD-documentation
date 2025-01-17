---
- GuiCommand:/ru
   Name:Part Torus
   Name/ru:Тор
   MenuLocation:Деталь → Примитивы → Тор
   Workbenches:[Part(Деталь)](Part_Workbench/ru.md)
   SeeAlso:[Создать примитивы](Part_Primitives/ru.md)
---

# Part Torus/ru

## Описание

Создаёт простой параметрический тор с следующими параметрами: положение (position), угол1 (angle1), угол2 (angle2), угол3 (angle3), радиус1 (radius1) и радиус2 (radius2).

<img alt="" src=images/SimpleTorus.jpg  style="width:400px;">

## Применение


<div class="mw-translate-fuzzy">

1.  Переключитесь на <img alt="" src=images/Workbench_Part.svg  style="width:16px;"> [верстак Part](Part_Workbench/ru.md)
2.  Существует несколько способов вызова команды:
    -   Нажмите на иконку **<img src="images/Part_Torus.svg" width=16px> тора** на панели инструментов.
    -   Выберите из меню **Деталь → Примитивы → <img src="images/Part_Torus.svg" width=16px> Тор**.


</div>

**Результат:** Будет создан Тор расположенный в начале системы координат (точка 0,0,0).
Параметры угла (угол1, угол2, угол3) и параметры радиуса (радиус 1 , радиус 2) позволяют параметризовать (изменять) тор, о чём будет рассказано в следующем разделе.

## Опции

![](images/TorusExampleOverviewParameters.jpg )

**Параметр**

Тор можно сравнить с небольшим диском, который вращается по круговой орбите вокруг воображаемой оси. Таким образом, наш тор имеет следующие параметры:

-    {{Parameter|Радиус1(Radius1):}}Радиус окружности, вокруг которой вращается наш диск

-    {{Parameter|Радиус2 (Radius2):}}Радиус диска, определяющий форму тора

-    {{Parameter|Угол1 (Angle1):}}1-й угол для обрезки / построения диска тора

-    {{Parameter|Угол2 (Angle2):}}2-й угол для обрезки / построения диска тора

-    {{Parameter|Угол3 (Angle3):}}3-й угол для определения длины окружности тора.

а также стандартный набор параметров размещения.На рисунках ниже представлен визуальный обзор вышеупомянутых параметров:

![](images/TorusExampleRadius1.jpg ) Параметр Радиус1 (Radius1) со значением 20мм.

![](images/TorusExampleRadius2.jpg ) Параметр Радиус2 (Radius2) имеет значение 2мм.

![](images/TorusExampleAngle1.jpg ) Здесь параметр Угол1 (Angle1) имеет значение -90°. Обратите внимание, что инструмент \"измерение угла\" не может отобразить отрицательный угол. Так что считаем, что отображаемое значение на картинке равно \"-90°\".

![](images/TorusExampleAngle2.jpg ) Параметр Угол2 (Angle2) равен 90°.

![](images/TorusExampleAngle3.jpg ) Параметр Угол3 (Angle3) имеет значение 90°. 

## Scripting

A Part Torus can be created using the following function:


```python
torus = FreeCAD.ActiveDocument.addObject("Part::Torus", "myTorus")
```

-   Where {{Incode|"myTorus"}} is the name for the object.
-   The function returns the newly created object.



---
![](images/Right_arrow.png) [documentation index](../README.md) > [Part](Part_Workbench.md) > Part Torus/ru
