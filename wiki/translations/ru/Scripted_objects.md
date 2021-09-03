


{{TOCright}}

## Введение


<div class="mw-translate-fuzzy">

Кроме стандартных типов объектов, таких как аннотации, полигональные сетки и детали, FreeCAD так же предлагает удивительные возможности для создания параметрических объектов полностью, через Python-скрипты, называемые Python Функционалом (Python Features). Эти объекты будут вести себя точно так же как и любой другой объект FreeCAD, могут быть сохранены в документе и открыты на любом другом компьютере с установленным FreeCAD, так как код python, определяющий этот объект, также сохраняется в документе.


</div>


<div class="mw-translate-fuzzy">

Должна быть понята одна особенность, эти объекты сохраняются в файлах FreeCAD FcStd вместе с модулем pythonа [json](https://docs.python.org/3/library/json.html). Этот модуль превращает объект pythonа в строку, позволяя его добавление в сохраняемый файл. При загрузке, модуль json использует эту строку для пересоздания оригинального объекта, обеспечивает его доступ к исходному коду, создавшему объект. Это значит, что если Вы сохранили этот пользовательский объект и открыли его на машине, где код python, который сгенерировал объект, отсутствует, объект не может быть восстановлен. Если Вы распространяете эти объекты среди других друзей, Вам нужно передавать вместе с ними скрипт pythonа, который его создал.


</div>

**Note**: It is possible to pack python code inside a FreeCAD file using json serializing with an App::PropertyPythonObject, but that code can never directly be run, and therefore has little use for our purpose here.


<div class="mw-translate-fuzzy">

Python Функционалы следуют тому же правилу что и все FreeCAD Функционалы: они разделены на App и GUI части. App часть, Документированный Объект(Document Object), определяет геометрию нашего объекта, тогда как его GUI часть, Визуальное Представление Объекта(View Provider Object), определяет как объект будет отрисован на экране. Визуальное Представление Объекта, как и любой другой FreeCAD функционал, доступно только когда если вы запустили FreeCAD с его собственным GUI. Есть несколько свойств и методов доступных для создания вашего объекта. Свойства должны быть любыми Свойства должны быть любыми предопределенные типами свойств которые предлагает FreeCAD, и они появятся в окне отображающим свойства, так что они могут быть отредактированы пользователем. Таким образом, Python Функционалы являются истинно и полностью параметрическими. вы можете отдельно задать свойства Документированного и Визуального Объектов.


</div>

## Простой пример 

Следующий пример можно найти в файле [src/Mod/TemplatePyMod/FeaturePython.py](https://github.com/FreeCAD/FreeCAD/blob/master/src/Mod/TemplatePyMod/FeaturePython.py) вместе с другими примерами: 
```python
'''Examples for a feature class and its view provider.'''

import FreeCAD, FreeCADGui
from pivy import coin

class Box:
    def __init__(self, obj):
        '''Add some custom properties to our box feature'''
        obj.addProperty("App::PropertyLength","Length","Box","Length of the box").Length=1.0
        obj.addProperty("App::PropertyLength","Width","Box","Width of the box").Width=1.0
        obj.addProperty("App::PropertyLength","Height","Box", "Height of the box").Height=1.0
        obj.Proxy = self
   
    def onChanged(self, fp, prop):
        '''Do something when a property has changed'''
        FreeCAD.Console.PrintMessage("Change property: " + str(prop) + "\n")
 
    def execute(self, fp):
        '''Do something when doing a recomputation, this method is mandatory'''
        FreeCAD.Console.PrintMessage("Recompute Python Box feature\n")

class ViewProviderBox:
    def __init__(self, obj):
        '''Set this object to the proxy object of the actual view provider'''
        obj.addProperty("App::PropertyColor","Color","Box","Color of the box").Color=(1.0,0.0,0.0)
        obj.Proxy = self
 
    def attach(self, obj):
        '''Setup the scene sub-graph of the view provider, this method is mandatory'''
        self.shaded = coin.SoGroup()
        self.wireframe = coin.SoGroup()
        self.scale = coin.SoScale()
        self.color = coin.SoBaseColor()
       
        data=coin.SoCube()
        self.shaded.addChild(self.scale)
        self.shaded.addChild(self.color)
        self.shaded.addChild(data)
        obj.addDisplayMode(self.shaded,"Shaded");
        style=coin.SoDrawStyle()
        style.style = coin.SoDrawStyle.LINES
        self.wireframe.addChild(style)
        self.wireframe.addChild(self.scale)
        self.wireframe.addChild(self.color)
        self.wireframe.addChild(data)
        obj.addDisplayMode(self.wireframe,"Wireframe");
        self.onChanged(obj,"Color")
 
    def updateData(self, fp, prop):
        '''If a property of the handled feature has changed we have the chance to handle this here'''
        # fp is the handled feature, prop is the name of the property that has changed
        l = fp.getPropertyByName("Length")
        w = fp.getPropertyByName("Width")
        h = fp.getPropertyByName("Height")
        self.scale.scaleFactor.setValue(float(l),float(w),float(h))
        pass
 
    def getDisplayModes(self,obj):
        '''Return a list of display modes.'''
        modes=[]
        modes.append("Shaded")
        modes.append("Wireframe")
        return modes
 
    def getDefaultDisplayMode(self):
        '''Return the name of the default display mode. It must be defined in getDisplayModes.'''
        return "Shaded"
 
    def setDisplayMode(self,mode):
        '''Map the display mode defined in attach with those defined in getDisplayModes.\
                Since they have the same names nothing needs to be done. This method is optional'''
        return mode
 
    def onChanged(self, vp, prop):
        '''Here we can do something when a single property got changed'''
        FreeCAD.Console.PrintMessage("Change property: " + str(prop) + "\n")
        if prop == "Color":
            c = vp.getPropertyByName("Color")
            self.color.rgb.setValue(c[0],c[1],c[2])
 
    def getIcon(self):
        '''Return the icon in XPM format which will appear in the tree view. This method is\
                optional and if not defined a default icon is shown.'''
        return """
            /* XPM */
            static const char * ViewProviderBox_xpm[] = {
            "16 16 6 1",
            "   c None",
            ".  c #141010",
            "+  c #615BD2",
            "@  c #C39D55",
            "#  c #000000",
            "$  c #57C355",
            "        ........",
            "   ......++..+..",
            "   .@@@@.++..++.",
            "   .@@@@.++..++.",
            "   .@@  .++++++.",
            "  ..@@  .++..++.",
            "###@@@@ .++..++.",
            "##$.@@$#.++++++.",
            "#$#$.$$$........",
            "#$$#######      ",
            "#$$#$$$$$#      ",
            "#$$#$$$$$#      ",
            "#$$#$$$$$#      ",
            " #$#$$$$$#      ",
            "  ##$$$$$#      ",
            "   #######      "};
            """
 
    def __getstate__(self):
        '''When saving the document this object gets stored using Python's json module.\
                Since we have some un-serializable parts here -- the Coin stuff -- we must define this method\
                to return a tuple of all serializable objects or None.'''
        return None
 
    def __setstate__(self,state):
        '''When restoring the serialized object from document we have the chance to set some internals here.\
                Since no data were serialized nothing needs to be done here.'''
        return None


def makeBox():
    FreeCAD.newDocument()
    a=FreeCAD.ActiveDocument.addObject("App::FeaturePython","Box")
    Box(a)
    ViewProviderBox(a.ViewObject)

makeBox()

```

### Что нужно знать 

Если Ваш объект полагается на то, что будет пересчитан во время создания, Вы должны сделать это вручную в функции `__init__`, поскольку пересчёт не вызывается автоматически. Этот пример не требует этого поскольку метод `onChanged` класса `Box` имеет тот же эффект, что и функция `execute`, но пример ниже полагается на то, что будет пересчитан перед тем как будет показан в окне трёхмерного просмотра. В этих примерах это делается вручную с помощью `ActiveDocument.recompute()`, но в более сложных сценариях Вы должны решить, где пересчитать либо весь документ, или объект FeaturePython.

Этот пример создаёт несколько исключений трасс стека в окне отчётов. Это поскольку метод `onChanged` класса `Box` вызывается каждый раз как свойство добавляется в `__init__`. Когда первое было добавлено, параметры Width и Height и потому попытки доступа к ним безуспешны.

Описание `__getstate__` и `__setstate__` находится в теме форума [obj.Proxy.Type is a dict, not a string](https://forum.freecadweb.org/viewtopic.php?f=18&t=44009&start=10#p377892).

## Доступные методы 

Смотрите полное описание в [методах FeaturePython](FeaturePython_methods.md).

## Доступные свойства 

Свойства это действительные строительные камни(не вспомнил замену) Python Функционалов. Через них пользователь может взаимодествовать с объектом и изменять его. После создания нового Python Функционала в вашем документе ( a=FreeCAD.ActiveDocument.addObject(\"App::FeaturePython\",\"Box\") ),вы можете получить список доступных свойств, использовав:


```python
obj.supportedProperties()
```


<div class="mw-translate-fuzzy">

Вы получите список доступных свойств:


</div>

-   [App::PropertyAcceleration](FeaturePython_Custom_Properties#App::PropertyAcceleration.md)
-   [App::PropertyAngle](FeaturePython_Custom_Properties#App::PropertyAngle.md)
-   [App::PropertyArea](FeaturePython_Custom_Properties#App::PropertyArea.md)
-   [App::PropertyBool](FeaturePython_Custom_Properties#App::PropertyBool.md)
-   [App::PropertyBoolList](FeaturePython_Custom_Properties#App::PropertyBoolList.md)
-   [App::PropertyColor](FeaturePython_Custom_Properties#App::PropertyColor.md)
-   [App::PropertyColorList](FeaturePython_Custom_Properties#App::PropertyColorList.md)
-   [App::PropertyDirection](FeaturePython_Custom_Properties#App::PropertyDirection.md)
-   [App::PropertyDistance](FeaturePython_Custom_Properties#App::PropertyDistance.md)
-   [App::PropertyEnumeration](FeaturePython_Custom_Properties#App::PropertyEnumeration.md)
-   [App::PropertyExpressionEngine](FeaturePython_Custom_Properties#App::PropertyExpressionEngine.md)
-   [App::PropertyFile](FeaturePython_Custom_Properties#App::PropertyFile.md)
-   [App::PropertyFileIncluded](FeaturePython_Custom_Properties#App::PropertyFileIncluded.md)
-   [App::PropertyFloat](FeaturePython_Custom_Properties#App::PropertyFloat.md)
-   [App::PropertyFloatConstraint](FeaturePython_Custom_Properties#App::PropertyFloatConstraint.md)
-   [App::PropertyFloatList](FeaturePython_Custom_Properties#App::PropertyFloatList.md)
-   [App::PropertyFont](FeaturePython_Custom_Properties#App::PropertyFont.md)
-   [App::PropertyForce](FeaturePython_Custom_Properties#App::PropertyForce.md)
-   [App::PropertyFrequency](FeaturePython_Custom_Properties#App::PropertyFrequency.md)
-   [App::PropertyInteger](FeaturePython_Custom_Properties#App::PropertyInteger.md)
-   [App::PropertyIntegerConstraint](FeaturePython_Custom_Properties#App::PropertyIntegerConstraint.md)
-   [App::PropertyIntegerList](FeaturePython_Custom_Properties#App::PropertyIntegerList.md)
-   [App::PropertyIntegerSet](FeaturePython_Custom_Properties#App::PropertyIntegerSet.md)
-   [App::PropertyLength](FeaturePython_Custom_Properties#App::PropertyLength.md)
-   [App::PropertyLink](FeaturePython_Custom_Properties#App::PropertyLink.md)
-   [App::PropertyLinkChild](FeaturePython_Custom_Properties#App::PropertyLinkChild.md)
-   [App::PropertyLinkGlobal](FeaturePython_Custom_Properties#App::PropertyLinkGlobal.md)
-   [App::PropertyLinkHidden](FeaturePython_Custom_Properties#App::PropertyLinkHidden.md)
-   [App::PropertyLinkList](FeaturePython_Custom_Properties#App::PropertyLinkList.md)
-   [App::PropertyLinkListChild](FeaturePython_Custom_Properties#App::PropertyLinkListChild.md)
-   [App::PropertyLinkListGlobal](FeaturePython_Custom_Properties#App::PropertyLinkListGlobal.md)
-   [App::PropertyLinkListHidden](FeaturePython_Custom_Properties#App::PropertyLinkListHidden.md)
-   [App::PropertyLinkSub](FeaturePython_Custom_Properties#App::PropertyLinkSub.md)
-   [App::PropertyLinkSubChild](FeaturePython_Custom_Properties#App::PropertyLinkSubChild.md)
-   [App::PropertyLinkSubGlobal](FeaturePython_Custom_Properties#App::PropertyLinkSubGlobal.md)
-   [App::PropertyLinkSubHidden](FeaturePython_Custom_Properties#App::PropertyLinkSubHidden.md)
-   [App::PropertyLinkSubList](FeaturePython_Custom_Properties#App::PropertyLinkSubList.md)
-   [App::PropertyLinkSubListChild](FeaturePython_Custom_Properties#App::PropertyLinkSubListChild.md)
-   [App::PropertyLinkSubListGlobal](FeaturePython_Custom_Properties#App::PropertyLinkSubListGlobal.md)
-   [App::PropertyLinkSubListHidden](FeaturePython_Custom_Properties#App::PropertyLinkSubListHidden.md)
-   [App::PropertyMap](FeaturePython_Custom_Properties#App::PropertyMap.md)
-   [App::PropertyMaterial](FeaturePython_Custom_Properties#App::PropertyMaterial.md)
-   [App::PropertyMaterialList](FeaturePython_Custom_Properties#App::PropertyMaterialList.md)
-   [App::PropertyMatrix](FeaturePython_Custom_Properties#App::PropertyMatrix.md)
-   [App::PropertyPath](FeaturePython_Custom_Properties#App::PropertyPath.md)
-   [App::PropertyPercent](FeaturePython_Custom_Properties#App::PropertyPercent.md)
-   [App::PropertyPersistentObject](FeaturePython_Custom_Properties#App::PropertyPersistentObject.md)
-   [App::PropertyPlacement](FeaturePython_Custom_Properties#App::PropertyPlacement.md)
-   [App::PropertyPlacementLink](FeaturePython_Custom_Properties#App::PropertyPlacementLink.md)
-   [App::PropertyPlacementList](FeaturePython_Custom_Properties#App::PropertyPlacementList.md)
-   [App::PropertyPosition](FeaturePython_Custom_Properties#App::PropertyPosition.md)
-   [App::PropertyPrecision](FeaturePython_Custom_Properties#App::PropertyPrecision.md)
-   [App::PropertyPressure](FeaturePython_Custom_Properties#App::PropertyPressure.md)
-   [App::PropertyPythonObject](FeaturePython_Custom_Properties#App::PropertyPythonObject.md)
-   [App::PropertyQuantity](FeaturePython_Custom_Properties#App::PropertyQuantity.md)
-   [App::PropertyQuantityConstraint](FeaturePython_Custom_Properties#App::PropertyQuantityConstraint.md)
-   [App::PropertySpeed](FeaturePython_Custom_Properties#App::PropertySpeed.md)
-   [App::PropertyString](FeaturePython_Custom_Properties#App::PropertyString.md)
-   [App::PropertyStringList](FeaturePython_Custom_Properties#App::PropertyStringList.md)
-   [App::PropertyUUID](FeaturePython_Custom_Properties#App::PropertyUUID.md)
-   [App::PropertyVacuumPermittivity](FeaturePython_Custom_Properties#App::PropertyVacuumPermittivity.md)
-   [App::PropertyVector](FeaturePython_Custom_Properties#App::PropertyVector.md)
-   [App::PropertyVectorDistance](FeaturePython_Custom_Properties#App::PropertyVectorDistance.md)
-   [App::PropertyVectorList](FeaturePython_Custom_Properties#App::PropertyVectorList.md)
-   [App::PropertyVolume](FeaturePython_Custom_Properties#App::PropertyVolume.md)
-   [App::PropertyXLink](FeaturePython_Custom_Properties#App::PropertyXLink.md)
-   [App::PropertyXLinkList](FeaturePython_Custom_Properties#App::PropertyXLinkList.md)
-   [App::PropertyXLinkSub](FeaturePython_Custom_Properties#App::PropertyXLinkSub.md)
-   [App::PropertyXLinkSubList](FeaturePython_Custom_Properties#App::PropertyXLinkSubList.md)
-   [Mesh::PropertyCurvatureList](FeaturePython_Custom_Properties#Mesh::PropertyCurvatureList.md)
-   [Mesh::PropertyMeshKernel](FeaturePython_Custom_Properties#Mesh::PropertyMeshKernel.md)
-   [Mesh::PropertyNormalList](FeaturePython_Custom_Properties#Mesh::PropertyNormalList.md)
-   [Part::PropertyFilletEdges](FeaturePython_Custom_Properties#Part::PropertyFilletEdges.md)
-   [Part::PropertyGeometryList](FeaturePython_Custom_Properties#Part::PropertyGeometryList.md)
-   [Part::PropertyPartShape](FeaturePython_Custom_Properties#Part::PropertyPartShape.md)
-   [Part::PropertyShapeHistory](FeaturePython_Custom_Properties#Part::PropertyShapeHistory.md)
-   [Path::PropertyPath](FeaturePython_Custom_Properties#Path::PropertyPath.md)
-   [Path::PropertyTool](FeaturePython_Custom_Properties#Path::PropertyTool.md)
-   [Path::PropertyTooltable](FeaturePython_Custom_Properties#Path::PropertyTooltable.md)
-   [Sketcher::PropertyConstraintList](FeaturePython_Custom_Properties#Sketcher::PropertyConstraintList.md)
-   [Spreadsheet::PropertyColumnWidths](FeaturePython_Custom_Properties#Spreadsheet::PropertyColumnWidths.md)
-   [Spreadsheet::PropertyRowHeights](FeaturePython_Custom_Properties#Spreadsheet::PropertyRowHeights.md)
-   [Spreadsheet::PropertySheet](FeaturePython_Custom_Properties#Spreadsheet::PropertySheet.md)
-   [Spreadsheet::PropertySpreadsheetQuantity](FeaturePython_Custom_Properties#Spreadsheet::PropertySpreadsheetQuantity.md)
-   [TechDraw::PropertyCenterLineList](FeaturePython_Custom_Properties#TechDraw::PropertyCenterLineList.md)
-   [TechDraw::PropertyCosmeticEdgeList](FeaturePython_Custom_Properties#TechDraw::PropertyCosmeticEdgeList.md)
-   [TechDraw::PropertyCosmeticVertexList](FeaturePython_Custom_Properties#TechDraw::PropertyCosmeticVertexList.md)
-   [TechDraw::PropertyGeomFormatList](FeaturePython_Custom_Properties#TechDraw::PropertyGeomFormatList.md)

При добавлении новых свойств к пользовательским объектам, позаботьтесь об этом:

-   Не используйте символы \"\<\" или \"\>\" в описании свойств (это вызовет поломку xml части .fcstd файла)
-   Свойства хранятся в .fcstd файле в алфавитном порядке. Если у вас есть форма(shape) в ваших свойствах, любое свойство имя которого идет, в алфавитном порядке, после \"Shape\" , будет загружено ПОСЛЕ формы, что может привести к странному поведению.

Полный список атрибутов свойств можно посмотреть в [заголовочном файле C++ PropertyStandard](https://github.com/FreeCAD/FreeCAD/blob/master/src/App/PropertyStandard.h). Например, если Вы хотите позволить пользователю вводить ограниченный диапазон значений (например, используя using PropertyIntegerConstraint), в Python Вы назначаете кортеж, содержащий не только значение свойства, но и верхний, нижний предел и шаг изменения, как сделано ниже:


```python
prop = (value, lower, upper, stepsize)
```

## Property Type 

По умолчанию свойства могут быть обновлены. Можно сделать их только для чтения, например, в случае если хочется показать результат метода. Так же можно скрыть свойство. Тип свойства может быть установлен используя


```python
obj.setEditorMode("MyPropertyName", mode)
```

где режим это short int, которое может быть установлено в:

 0 -- по умолчанию, чтение и запись
 1 -- только чтение
 2 -- скрыто

The EditorModes are not set at FreeCAD file reload. This could to be done by the \_\_setstate\_\_ function. See <http://forum.freecadweb.org/viewtopic.php?f=18&t=13460&start=10#p108072>. By using the setEditorMode the properties are only read only in PropertyEditor. They could still be changed from python. To really make them read only the setting has to be passed directly inside the addProperty function. See <http://forum.freecadweb.org/viewtopic.php?f=18&t=13460&start=20#p109709> for an example.

Using the direct setting in the addProperty function, you also have more possibilities. In particular, an interesting one is mark a property as an output property. This way FreeCAD won\'t mark the feature as touched when changing it (so no need to recompute).

Example of output property (see also <https://forum.freecadweb.org/viewtopic.php?t=24928>):


```python
obj.addProperty("App::PropertyString","MyCustomProperty","","",8)
```

The property types that can be set at last parameter of the addProperty function are:

 0 -- Prop_None, No special property type
 1 -- Prop_ReadOnly, Property is read-only in the editor
 2 -- Prop_Transient, Property won't be saved to file
 4 -- Prop_Hidden, Property won't appear in the editor
 8 -- Prop_Output, Modified property doesn't touch its parent container
 16 -- Prop_NoRecompute, Modified property doesn't touch its container for recompute

Вы можете найти эти различные типы свойств, определённые в [заголовочном файле PropertyContainer исходного кода C++](https://github.com/FreeCAD/FreeCAD/blob/master/src/App/PropertyContainer.h)

## Другие примеры, посложней 

Этот пример использует [Модуль Деталей](Part_Workbench/ru.md) для создания октаэдра, затем создает собственное представление coin с помощью pivy.

Сначала сам Документированный Объект:


```python
import FreeCAD, FreeCADGui, Part
import pivy
from pivy import coin

class Octahedron:
  def __init__(self, obj):
     "Add some custom properties to our box feature"
     obj.addProperty("App::PropertyLength","Length","Octahedron","Length of the octahedron").Length=1.0
     obj.addProperty("App::PropertyLength","Width","Octahedron","Width of the octahedron").Width=1.0
     obj.addProperty("App::PropertyLength","Height","Octahedron", "Height of the octahedron").Height=1.0
     obj.addProperty("Part::PropertyPartShape","Shape","Octahedron", "Shape of the octahedron")
     obj.Proxy = self

  def execute(self, fp):
     # Define six vetices for the shape
     v1 = FreeCAD.Vector(0,0,0)
     v2 = FreeCAD.Vector(fp.Length,0,0)
     v3 = FreeCAD.Vector(0,fp.Width,0)
     v4 = FreeCAD.Vector(fp.Length,fp.Width,0)
     v5 = FreeCAD.Vector(fp.Length/2,fp.Width/2,fp.Height/2)
     v6 = FreeCAD.Vector(fp.Length/2,fp.Width/2,-fp.Height/2)
     
     # Make the wires/faces
     f1 = self.make_face(v1,v2,v5)
     f2 = self.make_face(v2,v4,v5)
     f3 = self.make_face(v4,v3,v5)
     f4 = self.make_face(v3,v1,v5)
     f5 = self.make_face(v2,v1,v6)
     f6 = self.make_face(v4,v2,v6)
     f7 = self.make_face(v3,v4,v6)
     f8 = self.make_face(v1,v3,v6)
     shell=Part.makeShell([f1,f2,f3,f4,f5,f6,f7,f8])
     solid=Part.makeSolid(shell)
     fp.Shape = solid

  # helper mehod to create the faces
  def make_face(self,v1,v2,v3):
     wire = Part.makePolygon([v1,v2,v3,v1])
     face = Part.Face(wire)
     return face
```

Теперь , мы обладаем визуальным представлением объекта, ответственного за отображение объекта в 3D сцене:


```python
class ViewProviderOctahedron:
  def __init__(self, obj):
     "Set this object to the proxy object of the actual view provider"
     obj.addProperty("App::PropertyColor","Color","Octahedron","Color of the octahedron").Color=(1.0,0.0,0.0)
     obj.Proxy = self

  def attach(self, obj):
     "Setup the scene sub-graph of the view provider, this method is mandatory"
     self.shaded = coin.SoGroup()
     self.wireframe = coin.SoGroup()
     self.scale = coin.SoScale()
     self.color = coin.SoBaseColor()

     self.data=coin.SoCoordinate3()
     self.face=coin.SoIndexedLineSet()

     self.shaded.addChild(self.scale)
     self.shaded.addChild(self.color)
     self.shaded.addChild(self.data)
     self.shaded.addChild(self.face)
     obj.addDisplayMode(self.shaded,"Shaded");
     style=coin.SoDrawStyle()
     style.style = coin.SoDrawStyle.LINES
     self.wireframe.addChild(style)
     self.wireframe.addChild(self.scale)
     self.wireframe.addChild(self.color)
     self.wireframe.addChild(self.data)
     self.wireframe.addChild(self.face)
     obj.addDisplayMode(self.wireframe,"Wireframe");
     self.onChanged(obj,"Color")

  def updateData(self, fp, prop):
     "If a property of the handled feature has changed we have the chance to handle this here"
     # fp is the handled feature, prop is the name of the property that has changed
     if prop == "Shape":
        s = fp.getPropertyByName("Shape")
        self.data.point.setNum(6)
        cnt=0
        for i in s.Vertexes:
           self.data.point.set1Value(cnt,i.X,i.Y,i.Z)
           cnt=cnt+1
        
        self.face.coordIndex.set1Value(0,0)
        self.face.coordIndex.set1Value(1,1)
        self.face.coordIndex.set1Value(2,2)
        self.face.coordIndex.set1Value(3,-1)

        self.face.coordIndex.set1Value(4,1)
        self.face.coordIndex.set1Value(5,3)
        self.face.coordIndex.set1Value(6,2)
        self.face.coordIndex.set1Value(7,-1)

        self.face.coordIndex.set1Value(8,3)
        self.face.coordIndex.set1Value(9,4)
        self.face.coordIndex.set1Value(10,2)
        self.face.coordIndex.set1Value(11,-1)

        self.face.coordIndex.set1Value(12,4)
        self.face.coordIndex.set1Value(13,0)
        self.face.coordIndex.set1Value(14,2)
        self.face.coordIndex.set1Value(15,-1)

        self.face.coordIndex.set1Value(16,1)
        self.face.coordIndex.set1Value(17,0)
        self.face.coordIndex.set1Value(18,5)
        self.face.coordIndex.set1Value(19,-1)

        self.face.coordIndex.set1Value(20,3)
        self.face.coordIndex.set1Value(21,1)
        self.face.coordIndex.set1Value(22,5)
        self.face.coordIndex.set1Value(23,-1)

        self.face.coordIndex.set1Value(24,4)
        self.face.coordIndex.set1Value(25,3)
        self.face.coordIndex.set1Value(26,5)
        self.face.coordIndex.set1Value(27,-1)

        self.face.coordIndex.set1Value(28,0)
        self.face.coordIndex.set1Value(29,4)
        self.face.coordIndex.set1Value(30,5)
        self.face.coordIndex.set1Value(31,-1)

  def getDisplayModes(self,obj):
     "Return a list of display modes."
     modes=[]
     modes.append("Shaded")
     modes.append("Wireframe")
     return modes

  def getDefaultDisplayMode(self):
     "Return the name of the default display mode. It must be defined in getDisplayModes."
     return "Shaded"

  def setDisplayMode(self,mode):
     return mode

  def onChanged(self, vp, prop):
     "Here we can do something when a single property got changed"
     FreeCAD.Console.PrintMessage("Change property: " + str(prop) + "\n")
     if prop == "Color":
        c = vp.getPropertyByName("Color")
        self.color.rgb.setValue(c[0],c[1],c[2])

  def getIcon(self):
     return """
        /* XPM */
        static const char * ViewProviderBox_xpm[] = {
        "16 16 6 1",
        "    c None",
        ".   c #141010",
        "+   c #615BD2",
        "@   c #C39D55",
        "#   c #000000",
        "$   c #57C355",
        "        ........",
        "   ......++..+..",
        "   .@@@@.++..++.",
        "   .@@@@.++..++.",
        "   .@@  .++++++.",
        "  ..@@  .++..++.",
        "###@@@@ .++..++.",
        "##$.@@$#.++++++.",
        "#$#$.$$$........",
        "#$$#######      ",
        "#$$#$$$$$#      ",
        "#$$#$$$$$#      ",
        "#$$#$$$$$#      ",
        " #$#$$$$$#      ",
        "  ##$$$$$#      ",
        "   #######      "};
        """

  def __getstate__(self):
     return None

  def __setstate__(self,state):
     return None
```

Наконец, когда определен наш объект и его визуальный объект, нам просто нужно вызвать их:


```python
FreeCAD.newDocument()
a=FreeCAD.ActiveDocument.addObject("App::FeaturePython","Octahedron")
Octahedron(a)
ViewProviderOctahedron(a.ViewObject)
```

## Создание выделяемых объектов 

Если вы хотите чтобы ваш объект можно было выбрать, или по крайней мере его часть, щелкнув по нему в окне, вы должны включить его coin геометрию внутрь узла SoFCSelection. Если ваш объект обладает сложным представлением, с виджетами, аннотациями, и т.д, вам может потребоваться только часть его в SoFCSelection. Все что находится в SoFCSelection постоянно сканируется FreeCAD для обнаружения выделения/предварительного отбора, так что имеет смысл попробовать не перегружать его ненужным сканированием.

Как только части графа сцены, которые должны быть выбраны, оказываются внутри узлов SoFCSelection, вам необходимо предоставить два метода для обработки пути выбора. Путь выбора может принимать форму строки, содержащей имена каждого элемента в пути, или массива объектов графа сцены. Вы предоставляете два метода: `getDetailPath`, который преобразует путь строки в массив объектов scenegraph (графа сцены), и `getElementPicked`, который принимает элемент, по которому щелкнули в графе сцены, и возвращает его строковое имя (примечание, а не его строковый путь).

Вот вышеприведённый пример с молекулой, адаптированный для выбора элементов молекулы: 
```python
class Molecule:
    def __init__(self, obj):
        ''' Add two point properties '''
        obj.addProperty("App::PropertyVector","p1","Line","Start point")
        obj.addProperty("App::PropertyVector","p2","Line","End point").p2=FreeCAD.Vector(5,0,0)

        obj.Proxy = self

    def onChanged(self, fp, prop):
        if prop == "p1" or prop == "p2":
            ''' Print the name of the property that has changed '''
            fp.Shape = Part.makeLine(fp.p1,fp.p2)

    def execute(self, fp):
        ''' Print a short message when doing a recomputation, this method is mandatory '''
        fp.Shape = Part.makeLine(fp.p1,fp.p2)

class ViewProviderMolecule:
    def __init__(self, obj):
        ''' Set this object to the proxy object of the actual view provider '''
        obj.Proxy = self
        self.ViewObject = obj
        sep1=coin.SoSeparator()
        sel1 = coin.SoType.fromName('SoFCSelection').createInstance()
        # sel1.policy.setValue(coin.SoSelection.SHIFT)
        sel1.ref()
        sep1.addChild(sel1)
        self.trl1=coin.SoTranslation()
        sel1.addChild(self.trl1)
        sel1.addChild(coin.SoSphere())
        sep2=coin.SoSeparator()
        sel2 = coin.SoType.fromName('SoFCSelection').createInstance()
        sel2.ref()
        sep2.addChild(sel2)
        self.trl2=coin.SoTranslation()
        sel2.addChild(self.trl2)
        sel2.addChild(coin.SoSphere())
        obj.RootNode.addChild(sep1)
        obj.RootNode.addChild(sep2)
        self.updateData(obj.Object, 'p2')
        self.sel1 = sel1
        self.sel2 = sel2

    def getDetailPath(self, subname, path, append):
        vobj = self.ViewObject
        if append:
            path.append(vobj.RootNode)
            path.append(vobj.SwitchNode)

            mode = vobj.SwitchNode.whichChild.getValue()
            if mode >= 0:
                mode = vobj.SwitchNode.getChild(mode)
                path.append(mode)
                sub = Part.splitSubname(subname)[-1]
                if sub == 'Atom1':
                    path.append(self.sel1)
                elif sub == 'Atom2':
                    path.append(self.sel2)
                else:
                    path.append(mode.getChild(0))
        return True

    def getElementPicked(self, pp):
        path = pp.getPath()
        if path.findNode(self.sel1) >= 0:
            return 'Atom1'
        if path.findNode(self.sel2) >= 0:
            return 'Atom2'
        raise NotImplementedError


    def updateData(self, fp, prop):
        "If a property of the handled feature has changed we have the chance to handle this here"
        # fp is the handled feature, prop is the name of the property that has changed
        if prop == "p1":
            p = fp.getPropertyByName("p1")
            self.trl1.translation=(p.x,p.y,p.z)
        elif prop == "p2":
            p = fp.getPropertyByName("p2")
            self.trl2.translation=(p.x,p.y,p.z)

    def __getstate__(self):
        return None

    def __setstate__(self,state):
        return None

def makeMolecule():
    FreeCAD.newDocument()
    a=FreeCAD.ActiveDocument.addObject("Part::FeaturePython","Molecule")
    Molecule(a)
    ViewProviderMolecule(a.ViewObject)
    FreeCAD.ActiveDocument.recompute()
```

## Работа с простыми формами 

Если ваш параметрический объект просто выводит форму, вам не нужно импользовать объект визуального представления. форма будет отображена используя стандартное FreeCAD-ое представление форм :


```python
import FreeCAD as App
import FreeCADGui
import FreeCAD
import Part
class Line:
    def __init__(self, obj):
        '''"App two point properties" '''
        obj.addProperty("App::PropertyVector","p1","Line","Start point")
        obj.addProperty("App::PropertyVector","p2","Line","End point").p2=FreeCAD.Vector(1,0,0)
        obj.Proxy = self

    def execute(self, fp):
        '''"Print a short message when doing a recomputation, this method is mandatory" '''
        fp.Shape = Part.makeLine(fp.p1,fp.p2)

a=FreeCAD.ActiveDocument.addObject("Part::FeaturePython","Line")
Line(a)
a.ViewObject.Proxy=0 # just set it to something different from None (this assignment is needed to run an internal notification)
FreeCAD.ActiveDocument.recompute()
```

Тот же код с использованием **ViewProviderLine**


```python
import FreeCAD as App
import FreeCADGui
import FreeCAD
import Part

class Line:
    def __init__(self, obj):
         '''"App two point properties" '''
         obj.addProperty("App::PropertyVector","p1","Line","Start point")
         obj.addProperty("App::PropertyVector","p2","Line","End point").p2=FreeCAD.Vector(100,0,0)
         obj.Proxy = self
   
    def execute(self, fp):
        '''"Print a short message when doing a recomputation, this method is mandatory" '''
        fp.Shape = Part.makeLine(fp.p1,fp.p2)

class ViewProviderLine:
   def __init__(self, obj):
      ''' Set this object to the proxy object of the actual view provider '''
      obj.Proxy = self

   def getDefaultDisplayMode(self):
      ''' Return the name of the default display mode. It must be defined in getDisplayModes. '''
      return "Flat Lines"

a=FreeCAD.ActiveDocument.addObject("Part::FeaturePython","Line")
Line(a)
ViewProviderLine(a.ViewObject)
App.ActiveDocument.recompute()
```

## Scenegraph Structure 

You may have noticed that the examples above construct their scenegraphs in slightly different ways. Some use `obj.addDisplayMode(node, "modename")` while others use `obj.SwitchNode.getChild(x).addChild(y)`.

Each feature in a FreeCAD document is based the following scenegraph structure:


```python
RootNode
 \- SwitchNode
     \- Shaded
      - Wireframe
      - etc
```

The `SwitchNode` displays only one of its children, depending on which display mode is selection in FreeCAD.

The examples which use `addDisplayMode` are constructing their scenegraphs solely out of coin3d scenegraph elements. Under the covers, `addDisplayMode` adds a new child to the `SwitchNode`; the name of that node will match the display mode it was passed.

The examples which use `SwitchNode.getChild(x).addChild` also construct part of their geometry using functions from the Part workbench, such as `1=fp.Shape = Part.makeLine(fp.p1,fp.p2)`. This constructs the different display mode scenegraphs under the `SwitchNode`; when we later come to add coin3d elements to the scenegraph, we need to add them to the existing display mode scenegraphs using `addChild` rather than creating a new child of the `SwitchNode`.

When using `addDisplayMode()` to add geometry to the scenegraph, each display mode should have its own node which is passed to `addDisplayMode()`; don\'t reuse the same node for this. Doing so will confuse the selection mechanism. It\'s okay if each display mode\'s node has the same geometry nodes added below it, just the root of each display mode needs to be distinct.

Here is the above molecule example, adapted to be drawn only with Coin3D scenegraph objects instead of using objects from the Part workbench:


```python
import Part
from pivy import coin

class Molecule:
    def __init__(self, obj):
        ''' Add two point properties '''
        obj.addProperty("App::PropertyVector","p1","Line","Start point")
        obj.addProperty("App::PropertyVector","p2","Line","End point").p2=FreeCAD.Vector(5,0,0)

        obj.Proxy = self

    def onChanged(self, fp, prop):
        pass

    def execute(self, fp):
        ''' Print a short message when doing a recomputation, this method is mandatory '''
        pass

class ViewProviderMolecule:
    def __init__(self, obj):
        ''' Set this object to the proxy object of the actual view provider '''
        self.constructed = False
        obj.Proxy = self
        self.ViewObject = obj

    def attach(self, obj):
        material = coin.SoMaterial()
        material.diffuseColor = (1.0, 0.0, 0.0)
        material.emissiveColor = (1.0, 0.0, 0.0)
        drawStyle = coin.SoDrawStyle()
        drawStyle.pointSize.setValue(10)
        drawStyle.style = coin.SoDrawStyle.LINES
        wireframe = coin.SoGroup()
        shaded = coin.SoGroup()
        self.wireframe = wireframe
        self.shaded = shaded

        self.coords = coin.SoCoordinate3()
        self.coords.point.setValues(0, 2, [FreeCAD.Vector(0, 0, 0), FreeCAD.Vector(1, 0, 0)])
        wireframe += self.coords
        wireframe += drawStyle
        wireframe += material
        shaded += self.coords
        shaded += drawStyle
        shaded += material

        g = coin.SoGroup()
        sel1 = coin.SoType.fromName('SoFCSelection').createInstance()
        sel1.style = 'EMISSIVE_DIFFUSE'
        p1 = coin.SoType.fromName('SoIndexedPointSet').createInstance()
        p1.coordIndex.set1Value(0, 0)
        sel1 += p1
        g += sel1
        wireframe += g
        shaded += g

        g = coin.SoGroup()
        sel2 = coin.SoType.fromName('SoFCSelection').createInstance()
        sel2.style = 'EMISSIVE_DIFFUSE'
        p2 = coin.SoType.fromName('SoIndexedPointSet').createInstance()
        p2.coordIndex.set1Value(0, 1)
        sel2 += p2
        g += sel2
        wireframe += g
        shaded += g

        g = coin.SoGroup()
        sel3 = coin.SoType.fromName('SoFCSelection').createInstance()
        sel3.style = 'EMISSIVE_DIFFUSE'
        p3 = coin.SoType.fromName('SoIndexedLineSet').createInstance()
        p3.coordIndex.setValues(0, 2, [0, 1])
        sel3 += p3
        g += sel3
        wireframe += g
        shaded += g

        obj.addDisplayMode(wireframe, 'Wireframe')
        obj.addDisplayMode(shaded, 'Shaded')

        self.sel1 = sel1
        self.sel2 = sel2
        self.sel3 = sel3
        self.constructed = True
        self.updateData(obj.Object, 'p2')

    def getDetailPath(self, subname, path, append):
        vobj = self.ViewObject
        if append:
            path.append(vobj.RootNode)
            path.append(vobj.SwitchNode)

            mode = vobj.SwitchNode.whichChild.getValue()
            FreeCAD.Console.PrintWarning("getDetailPath: mode {} is active\n".format(mode))
            if mode >= 0:
                mode = vobj.SwitchNode.getChild(mode)
                path.append(mode)
                sub = Part.splitSubname(subname)[-1]
                print(sub)
                if sub == 'Atom1':
                    path.append(self.sel1)
                elif sub == 'Atom2':
                    path.append(self.sel2)
                elif sub == 'Line':
                    path.append(self.sel3)
                else:
                    path.append(mode.getChild(0))
        return True

    def getElementPicked(self, pp):
        path = pp.getPath()
        if path.findNode(self.sel1) >= 0:
            return 'Atom1'
        if path.findNode(self.sel2) >= 0:
            return 'Atom2'
        if path.findNode(self.sel3) >= 0:
            return 'Line'
        raise NotImplementedError


    def updateData(self, fp, prop):
        "If a property of the handled feature has changed we have the chance to handle this here"
        # fp is the handled feature, prop is the name of the property that has changed
        if not self.constructed:
            return
        if prop == "p1":
            p = fp.getPropertyByName("p1")
            self.coords.point.set1Value(0, p)
        elif prop == "p2":
            p = fp.getPropertyByName("p2")
            self.coords.point.set1Value(1, p)

    def getDisplayModes(self, obj):
        return ['Wireframe', 'Shaded']

    def getDefaultDisplayMode(self):
        return 'Shaded'

    def setDisplayMode(self, mode):
        return mode

    def __getstate__(self):
        return None

    def __setstate__(self,state):
        return None

def makeMolecule():
    FreeCAD.newDocument()
    a=FreeCAD.ActiveDocument.addObject("App::FeaturePython","Molecule")
    Molecule(a)
    b=ViewProviderMolecule(a.ViewObject)
    a.touch()
    FreeCAD.ActiveDocument.recompute()
    return a,b

a,b = makeMolecule()
```

## Дальнейшая информация 

Дополнительные страницы Вики FreeCADа:

-   [Scripted objects saving attributes](Scripted_objects_saving_attributes/ru.md)
-   [Scripted objects migration](Scripted_objects_migration/ru.md)
-   [Scripted objects with attachment](Scripted_objects_with_attachment/ru.md)
-   [Viewproviders](Viewprovider/ru.md)

Интересные темы форума про создание объектов с помощью скриптов:

-   [Python object attributes lost at load](http://forum.freecadweb.org/viewtopic.php?f=22&t=13740)
-   [New FeaturePython is grey](http://forum.freecadweb.org/viewtopic.php?t=12139)
-   [Explanation on \_\_getstate\_\_ and \_\_setstate\_\_](https://forum.freecadweb.org/viewtopic.php?f=18&t=44009), [official documentation](https://docs.python.org/3/library/pickle.html#object.__getstate__)
-   [Eigenmode frequency always 0?](https://forum.freecadweb.org/viewtopic.php?f=18&t=13460&start=20#p109709)
-   [how to implement python feature\'s setEdit properly?](https://forum.freecadweb.org/viewtopic.php?f=22&t=21330)

В дополнение к представленным примерам, посмотрите FreeCAD [src/Mod/TemplatePyMod/FeaturePython.py](https://github.com/FreeCAD/FreeCAD/blob/master/src/Mod/TemplatePyMod/FeaturePython.py), находящийся в папке с исходными кодами FreeCAD.


{{Powerdocnavi

}} 

[Category:Developer Documentation{{\#translation:}}](Category:Developer_Documentation.md) [Category:Python Code{{\#translation:}}](Category:Python_Code.md)