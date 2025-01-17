# Manual:A gentle introduction/ru
<div class="mw-translate-fuzzy">





</div>


{{Manual:TOC/ru}}

[Python](https://ru.wikipedia.org/wiki/Python) - популярный язык программирования с открытыми исходниками, часто встраиваемый в приложения как скриптовый язык, как в случае FreeCAD. У него так же много возможностей, интересных для пользователей FreeCAD: он лёгок в изучении, особенно для людей, ранее не программировавших, и встроен во множество других приложений. Это делает его очень ценным для изучения, поскольку Вы сможете использовать его во множестве других приложений, таких как [Blender](http://www.blender.org), [Inkscape](http://www.inkscape.org) или [GRASS](http://grass.osgeo.org/).

FreeCAD широко использует Python. С его помощью Вы можете иметь доступ и управлять практически любой возможностью FreeCAD. Например, Вы можете создавать новые объекты, модифицировать его геометрию, анализировать содержимое, или даже создавать новые элементы управления, инструменты и панели. Некоторые верстаки FreeCAD и большинство дополнительных верстаков запрограммированы полностью на Python. У FreeCAD есть совершенная консоль Python, доступная из меню **Вид-\>Панели-\>Консоль Python**. Она часто полезна для выполнения операций, для которых пока нет кнопок инструментальных панелей, или проверки фигур на ошибки, или выполнения повторяющихся задач:

![](images/Exercise_python_01.jpg )

Но консоль Python можно использовать и по-другому: каждый раз как Вы нажмёте на кнопку в панели инструментов или выполните в FreeCAD другую операцию, в консоли появляется и выполняется код Python. Оставляя консоль Python открытой, Вы можете точно видеть как разворачивается код Python в процессе работы, и довольно быстро, почти не замечая, Вы сможете выучить что-то из языка Python.

У FreeCAD так же есть [система макросов](Macros/ru.md), позволяющая записывать действия для последующего воспроизведения. Эта система так же использует консоль Python, просто записывая всё, что им сделано.

В этой главе мы покажем общие основы языка Python. Если Вы хотите изучать дальше, wiki-документация FreeCAD содержит обширный раздел насчёт [программирования на Python](Power_users_hub.md).

### Написание кода на Python 

Есть два простых способа написания кода Python в FreeCAD: из консоли Python (меню **Вид -\> Панели -\> Консоль Python**), или из редактора макросов (меню **Tools -\> Macros -\> New**). В консоли Вы пишете команды Python одну за одной, и они выполняются после нажатия кнопки Return, в то время как макросы могут содержать сложный скрипт из нескольких линий, исполняемый лишь когда макрос запущен из того же окна макросов.

В этой главе Вы сможете использовать оба метода, но рекомендуется использовать консоль Python, поскольку она немедленно проинформирует Вас о любой ошибке ввода.

Если Вы впервые используете Python, перед продолжением сначала подумайте о знакомстве с [введением в программирование на Python](Introduction_to_Python/ru.md), которое сделает Ваши основные понятия о Python яснее.

### Манипуляция объектами FreeCAD 

Начнём с создания нового пустого документа:

doc = FreeCAD.newDocument()

Если Вы вводили это в консоли Python FreeCADа, то заметили, что как только Вы ввели \"FreeCAD.\" (слово FreeCAD с последующей точкой), появилось окно, позволяющее быстро автозаполнить продолжение строки. Даже лучше, каждый ввод в списке автодополнения содержит подсказку. Это облегчает раскрытие имеющейся функциональности. Перед выбором \"newDocument\", взгляните на другие доступные опции.

![](images/Exercise_python_02.jpg )

Как только Вы нажмёте **Enter**, будет создан новый документ. Это то же, что нажать на панели инструментов кнопку \"Создать\". В Python кнопка используется, чтобы показать нечто, что содержится в чём-то другом (функция newDocument содержится внутри модуля FreeCAD). Окно с вариантами, которое появляется, соответственно показывает всё, что содержится в \"FreeCAD\". Если Вы вместо скобок добавите точку после newDocument, Вам будет показано всё содержимое функции newDocument. Скобки обязательны, когда Вы вызываете функцию Python, такую как эта. Мы покажем это яснее внизу.

Теперь вернёмся назад в документ. Посмотрим, что мы можем с ним сделать. Введите следующее и изучите доступные варианты:

doc.

Обычно имена, начинающиеся с заглавной буквы, это атрибуты, они содержат значения. Имена с маленькой буквы являются функциями (называемые так же методами), они \"что-то делают\". Имена, начинающиеся с подчёркиваний, обычно используются для внутренних нужд модуля, и Вам лучше игнорировать их. Используем один из методов для добавления в документ нового объекта:

box = doc.addObject("Part::Box","myBox")

Наш куб уже добавлен в древо проекта, но ничего не возникло в окне трёхмерного вида, поскольку при работе из Python документ не пересчитывается автоматически. Нам надо сделать это вручную, когда нужно:

doc.recompute()

Теперь наш куб появился в окне трёхмерного вида. Большинство кнопок панелей инструментов фактически делают две вещи: добавляют объект и выполняют рекомпиляцию. Если Вы включите в настройках опцию \"Показывать команды скриптов в консоли Python\" и попробуете добавить сферу с соответствующей кнопкой в верстаке Part, Вы увидите две линии кода Python, выполняемые одна за другой.

Вы можете получить список всех возможных объектов, подобных Part::Box:

doc.supportedTypes()

Теперь рассмотрим содержимое нашего куба:

box.

Вы немедленно увидите несколько очень интересных вещей вроде этого:

box.Height 

Это покажет текущую высоту нашего куба. Теперь попробуем её изменить:

box.Height = 5 

Если Вы выделите Ваш куб мышью, Вы увидите что в панели параметров, под вкладкой **Данные**, наш параметр **Height** будет показан с новым значением. Все параметры объектов FreeCAD, показываемые во вкладках **Data** и **View**, так же доступны через Python через их имена, как мы делали через параметр Height. Параметры доступны через сам объект, например:

box.Length 

Параметры вида хранятся внутри **ViewObject**. Каждый объект FreeCAD содержит ViewObject, где хранятся визуальные параметры объекта. При запуске FreeCAD без графического интерфейса (например, при запуске из терминала с опцией -c, или из другого скрипта Python), ViewObject недоступен, поскольку отображения нет.

Попробуйте следующий пример для доступа к цвету линии нашего куба:

box.ViewObject.LineColor 

### Векторы и места размещения 

Вектора это фундаментальная концепция в любом приложении трёхмерного моделирования. Это список из 3 чисел (x, y и z), указывающих точку или позицию в трёхмерном пространстве. С векторами могут быть выполнены множество вещей, сложение, вычитание, проекции и многое другое. В FreeCAD векторы работают так:

myvec = FreeCAD.Vector(2,0,0)
print(myvec)
print(myvec.x)
print(myvec.y)
othervec = FreeCAD.Vector(0,3,0)
sumvec = myvec.add(othervec)

Другое общее свойство объектов FreeCAD это их размещение **Placement**. Как мы видели в предыдущих главах, у каждого объекта есть параметр Placement, содержащий его позицию (Base) и ориентацию (Rotation). Ими легко манипулировать через Python, например, для перемещения нашего объекта:

print(box.Placement)
print(box.Placement.Base)
box.Placement.Base = sumvec
otherpla = FreeCAD.Placement()
otherpla.Base = FreeCAD.Vector(5,5,0)
box.Placement = otherpla

**Читать далее**


<div class="mw-translate-fuzzy">

-   [Python](https://www.python.org)
-   [Работа с макросами](Macros/ru.md)
-   [Введение в создание скриптов Python](Introduction_to_Python/ru.md)
-   [Использование Python в FreeCAD](Python_scripting_tutorial/ru.md)
-   [Хаб wiki работы со скриптами Python](Power_users_hub/ru.md)


</div>


<div class="mw-translate-fuzzy">





</div>



---
![](images/Right_arrow.png) [documentation index](../README.md) > [Developer Documentation](Category_Developer Documentation.md) > [Python Code](Category_Python Code.md) > Manual:A gentle introduction/ru
