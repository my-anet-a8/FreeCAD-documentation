# Preferences Editor/zh-cn
{{TOCright}}

## Introduction


<div class="mw-translate-fuzzy">

FreeCAD的首选项系统位于**Edit menu → Preferences**。


</div>


<div class="mw-translate-fuzzy">

FreeCAD中的功能被分为不同的模块，每个模块负责实现一种特定[workbench的具体工作](Workbenches.md)。 FreeCAD采用的是延迟加载方式，意即只有当需要使用特定组件时才会进行加载。您在FreeCAD的工具栏中选择工作台时可能会注意到这一点，因为在加载工作台及其所有组件时需要花费一点儿时间。在进行首选项设置时也是如此。


</div>


<div class="mw-translate-fuzzy">

在没有加载任何模块时，您可以访问两个配置部分，分别用于应用通用设置（general）与显示设置（display）。当您使用特定的工作台时，便会在新选项卡中显示对应工作台的首选项设置，并在**Import-Export**新加部分显示该工作台所支持的文件格式。


</div>


<div class="mw-translate-fuzzy">

点击首选项左下角的**Reset**按钮，即可将FreeCAD中的**所有**首选项设置还原为其默认值。


</div>

Some advanced preferences can only be changed in the [Parameter editor](Std_DlgParameter.md). The [Fine-tuning](Fine-tuning.md) page lists some of them.


<div class="mw-translate-fuzzy">

## 通用设置


</div>


<div class="mw-translate-fuzzy">

本首选项部分包含6个选项卡：


</div>

### 常规

在*General*选项卡中，您可以指定下列内容：


<div class="mw-translate-fuzzy">

+++
| 名称                                             | 描述                                                                                                                                                                                                                                                                         |
+==================================================+==============================================================================================================================================================================================================================================================================+
|                                   | 选择FreeCAD的用户界面语言                                                                                                                                                                                                                                                    |
| **更改语言**                         |                                                                                                                                                                                                                                                                              |
|                                               |                                                                                                                                                                                                                                                                              |
+++
|                                   | 指定有多少最近用过的文件显示在recent files列表中                                                                                                                                                                                                                             |
| **最近文件列表大小**                 |                                                                                                                                                                                                                                                                              |
|                                               |                                                                                                                                                                                                                                                                              |
+++
|                                   | 如果选中此复选框，则FreeCAD的主窗口背景将默认由以下图片填充：<img alt="" src=images/Background.png  style="width:64px;">                                                                                                                                                            |
| **启用平面背景**                     | 本选项只有在**样式表：**/*No style sheet*被选中时才会生效。                                                                                                                                                                                        |
|                                               | 将图片加入到下列路径中的{{FileName|Gui/Images}}文件夹下即可改变贴图内容                                                                                                                                                                                        |
|                                                  | \[<https://www.howtogeek.com/318177/what-is-the-appdata-folder-in-windows/> {{FileName|%APPDATA%]/FreeCAD}} (在Windows上),                                                                                                                                     |
|                                                  | {{FileName|$HOME/.FreeCAD}} (在Linux上) or                                                                                                                                                                                                                     |
|                                                  | {{FileName|$HOME/Library/Preferences/FreeCAD}} (在MacOS上)。                                                                                                                                                                                                   |
|                                                  | 将图片文件命名为{{FileName|background.png}}，再依次取消/选中本选项来查看效果。                                                                                                                                                                                 |
|                                                  |                                                                                                                                                                                                                                                                              |
|                                                  |                                                                                                                                                                                                                                                                    |
|                                                  | </div>                                                                                                                                                                                                                                                                       |
|                                                  |                                                                                                                                                                                                                                                                           |
|                                                  | This option only has an effect if no **Style sheet** is selected.                                                                                                                                                                                  |
|                                                  |                                                                                                                                                                                                                                                                              |
|                                                  | The image can be changed by adding the folders {{FileName|Gui/Images}} in the folder:                                                                                                                                                                          |
|                                                  |                                                                                                                                                                                                                                                                              |
|                                                  |                                                                                                                                                                                                                                                               |
|                                                  | {{FileName|[https://www.howtogeek.com/318177/what-is-the-appdata-folder-in-windows/ %APPDATA%]/FreeCAD}}                                                                                                                                                                     |
|                                                  |                                                                                                                                                                                                                                                                           |
|                                                  | (on Windows),                                                                                                                                                                                                                                                                |
|                                                  |                                                                                                                                                                                                                                                                              |
|                                                  |                                                                                                                                                                                                                                                               |
|                                                  | {{FileName|$HOME/.FreeCAD}}                                                                                                                                                                                                                                                  |
|                                                  |                                                                                                                                                                                                                                                                           |
|                                                  | (on Linux) or                                                                                                                                                                                                                                                                |
|                                                  |                                                                                                                                                                                                                                                                              |
|                                                  |                                                                                                                                                                                                                                                               |
|                                                  | {{FileName|$HOME/Library/Preferences/FreeCAD}}                                                                                                                                                                                                                               |
|                                                  |                                                                                                                                                                                                                                                                           |
|                                                  | (on MacOS).                                                                                                                                                                                                                                                                  |
|                                                  |                                                                                                                                                                                                                                                                              |
|                                                  | Place a file named {{FileName|background.png}} in the {{FileName|Images}} folder, and uncheck/check this option to see the changed file.                                                                                                         |
+++
|                                   | Selection of a style sheet. Style sheets define how the user interface of FreeCAD looks. For technical details about the style sheets, see [themes](Interface_Customization#Themes.md).                                                                              |
| **Style sheet**                      |                                                                                                                                                                                                                                                                              |
|                                               |                                                                                                                                                                                                                                                                              |
+++
|                                   | Selection of the size for the toolbar icons                                                                                                                                                                                                                                  |
| **Size of toolbar icons**            |                                                                                                                                                                                                                                                                              |
|                                               |                                                                                                                                                                                                                                                                              |
+++
|                                   | Customization how the tree view is shown in the panel (restart required). The options are:                                                                                                                                                                                   |
| **Tree view mode**                   |                                                                                                                                                                                                                                                                              |
|                                               | -   **Combo View**: combine tree view and property view into one panel.                                                                                                                                                                                                      |
|                                                  | -   **TreeView and PropertyView**: split tree view and property view into separate panel.                                                                                                                                                                                    |
|                                                  | -   **Both**: keep all three panels, and you can have two sets of tree view and property view.                                                                                                                                                                               |
+++
|                                   | Selection what workbench will be used directly after starting FreeCAD                                                                                                                                                                                                        |
| **Auto load module after start up**  |                                                                                                                                                                                                                                                                              |
|                                               |                                                                                                                                                                                                                                                                              |
+++
|                                   | If checked, a splash screen is shown when starting FreeCAD.                                                                                                                                                                                                                  |
| **Enable splash screen at start up** |                                                                                                                                                                                                                                                                              |
|                                                                                                                                                                                                                                                                    |
|                                                  | <div class="mw-translate-fuzzy">                                                                                                                                                                                                                                             |
|                                                  |                                                                                                                                                                                                                                                                           |
+++
|                                   | 选择样式表。样式表定义了FreeCAD用户界面的外观。                                                                                                                                                                                                                              |
| **样式表：**                         |                                                                                                                                                                                                                                                                              |
|                                               |                                                                                                                                                                                                                                                                              |
+++
|                                   | 选择工具栏图标的大小。                                                                                                                                                                                                                                                       |
| **工具栏图标大小**                   |                                                                                                                                                                                                                                                                              |
|                                               |                                                                                                                                                                                                                                                                              |
+++
|                                   | 选择FreeCAD开启后将直接打开的工作台。                                                                                                                                                                                                                                        |
| **启动后自动加载模块**               |                                                                                                                                                                                                                                                                              |
|                                               |                                                                                                                                                                                                                                                                              |
+++
|                                   | 如果选中此项, 则在FreeCAD开启时展示启动画面。                                                                                                                                                                                                                                |
| **打开软件启动界面**                 | 可通过向{{FileName|%APPDATA%/FreeCAD}}（ %APPDATA%是用户在操作系统中为FreeCAD指定的应用文件夹）添加{{FileName|Gui/Images}}文件夹来修改启动画面。将作为启动画面的图像命名为{{FileName|splash_image.png}}并重启FreeCAD即可看到效果。 |
|                                               |                                                                                                                                                                                                                                                                              |
+++
|                                   | 利用此选项可实现在Python控制台中令超出一行中的文本自动换行。利用**View → Panels → Python console**菜单来开启Python控制台。                                                                                                                         |
| **启用自动换行**                     |                                                                                                                                                                                                                                                                              |
|                                               |                                                                                                                                                                                                                                                                              |
+++


</div>

![](images/Preferences_General_Tab_General_zh-cn.png )

### 文档

在*Document*选项卡中，您可以指定以下内容：


<div class="mw-translate-fuzzy">

+++
| 名称                                               | 描述                                                                                                                                                                                                                                                                               |
+====================================================+====================================================================================================================================================================================================================================================================================+
|                                     | 如果选中此选项，FreeCAD将在启动时创建一个新文档。                                                                                                                                                                                                                                  |
| **启动时创建新文档**                   |                                                                                                                                                                                                                                                                                    |
|                                                 |                                                                                                                                                                                                                                                                                    |
+++
|                                     | 指定{{FileName|FCStd}}文件的压缩级别。{{FileName|FCStd}}文件为ZIP压缩文件。因此，您可以将其后缀{{FileName|.FCStd}}改为{{FileName|.zip}}，并用ZIP归档程序来打开它们。                                                       |
| **Document save compression level**    |                                                                                                                                                                                                                                                                                    |
|                                                 |                                                                                                                                                                                                                                                                                    |
+++
|                                     | 如果选中此选项，所有文档的更改情况将被保存下来，因此即可实现undone/redone。                                                                                                                                                                                                        |
| **在文档上使用撤消/重做**              |                                                                                                                                                                                                                                                                                    |
|                                                 |                                                                                                                                                                                                                                                                                    |
+++
|                                     | 指定可以记录多少次Undo/Redo操作。                                                                                                                                                                                                                                                  |
| **最大撤消/重做步数**                  |                                                                                                                                                                                                                                                                                    |
|                                                 |                                                                                                                                                                                                                                                                                    |
+++
|                                     | 如果存在恢复文件，则FreeCAD将在开启时自动运行此文件进行恢复。此法可对程序崩溃时的文件进行恢复。                                                                                                                                                                                    |
| **在启动时运行自动恢复**               |                                                                                                                                                                                                                                                                                    |
|                                                 |                                                                                                                                                                                                                                                                                    |
+++
|                                     | 指定多久写一次恢复文件。                                                                                                                                                                                                                                                           |
| **每次都保存自动恢复信息**             |                                                                                                                                                                                                                                                                                    |
|                                                 |                                                                                                                                                                                                                                                                                    |
+++
|                                     | 如果选中此选项，在保存文档时，也将存储一份项目的缩略图。此缩略图将显示在[启动工作台中的最近打开文件列表中](Start_Workbench.md)。                                                                                                                                           |
| **保存文件时同时保存缩略图到项目文件** |                                                                                                                                                                                                                                                                                    |
|                                                 |                                                                                                                                                                                                                                                                                    |
+++
|                                     | 如果选中此选项，则会将FreeCAD程序的logo ![24px添加至缩略图中](images/FreeCAD-logo.svg)。此选项仅在开启**保存文件时同时保存缩略图到项目文件**选项后才会生效。                                                                                    |
| **将程序徽标添加到生成的缩略图**       |                                                                                                                                                                                                                                                                                    |
|                                                 |                                                                                                                                                                                                                                                                                    |
+++
|                                     | 如果选中此选项，在保存文档时也会保留备份文件。您可以指定保留备份文件的数量。这些文件中保存的是此前（previously）的文档版本。第一个备份文件的后缀为 {{FileName|.FCStd1}}, 第二个后缀为{{FileName|.FCStd2}}，并以此类推。                                |
| **保存文档时要保留的最大备份文件数**   |                                                                                                                                                                                                                                                                                    |
|                                                 |                                                                                                                                                                                                                                                                                    |
+++
|                                     | 如果选中此选项，则不同的对象可以使用相同的标签/名称。例如，同一文档中的不同零件与features可用相同的名字。                                                                                                                                                                          |
| **在一个文档中允许重复的对象标签**     |                                                                                                                                                                                                                                                                                    |
|                                                 |                                                                                                                                                                                                                                                                                    |
+++
|                                     | 创建的所有文档均采用此指定的作者名。对于匿名作者而言，作者名字的区域为空白内容。若开启了**保存时的设置**选项，则在保存文件时将*Last modified by*的内容设置为此作者名。可通过**File → Project information**菜单来查看该文本域。 |
| **作者姓名**                           |                                                                                                                                                                                                                                                                                    |
|                                                 |                                                                                                                                                                                                                                                                                    |
+++
|                                     | 将创建的所有文档都指定为此公司名称。                                                                                                                                                                                                                                               |
| **公司**                               |                                                                                                                                                                                                                                                                                    |
|                                                 |                                                                                                                                                                                                                                                                                    |
+++
|                                     | 为新文档所指定的默认许可证。对于预定义的许可证而言，**许可证网址**将自动做出对应的设置。而针对自定义许可证或特殊许可证来讲，可选择\'Other（其他）\'项。                                                                                                  |
| **默认许可证**                         |                                                                                                                                                                                                                                                                                    |
|                                                 |                                                                                                                                                                                                                                                                                    |
+++
|                                     | 指定URL来描述**默认许可证**中所选的许可证。                                                                                                                                                                                                              |
| **许可证网址**                         |                                                                                                                                                                                                                                                                                    |
|                                                 |                                                                                                                                                                                                                                                                                    |
+++


</div>

![](images/Preferences_General_Tab_Document_zh-cn.png )

### 选择

On the *Selection* tab (<small>(v0.19)</small> ) you can specify the following:

+++
| Name                                                                                              | Description                                                                                                                                    |
+===================================================================================================+================================================================================================================================================+
|                                                                                    | Enables the [Tree view SyncView mode](Std_TreeSyncView.md)                                                                             |
| **Auto switch to the 3D view containing the selected item**                           |                                                                                                                                                |
|                                                                                                |                                                                                                                                                |
+++
|                                                                                    | Enables the [Tree view SyncSelection mode](Std_TreeSyncSelection.md)                                                                   |
| **Auto expand tree item when the corresponding object is selected in 3D view**        |                                                                                                                                                |
|                                                                                                |                                                                                                                                                |
+++
|                                                                                    | Enables the [Tree view PreSelection mode](Std_TreePreSelection.md)                                                                     |
| **Preselect the object in 3D view when mouse over the tree item**                     |                                                                                                                                                |
|                                                                                                |                                                                                                                                                |
+++
|                                                                                    | Enables the [Tree view RecordSelection mode](Std_TreeRecordSelection.md)                                                               |
| **Record selection in tree view in order to go back/forward using navigation button** |                                                                                                                                                |
|                                                                                                |                                                                                                                                                |
+++
|                                                                                    | Each [document tree](Tree_view.md) item will get a checkbox. This is for example useful for selecting multiple items on a touchscreen. |
| **Add checkboxes for selection in document tree**                                     |                                                                                                                                                |
|                                                                                                |                                                                                                                                                |
+++

![](images/Preferences_General_Tab_Selection_zh-cn.png )

### Cache

On the *Cache* tab (<small>(v0.20)</small> ) you can specify the following:

+++
| Name                                                | Description |
+=====================================================+=============+
|                                      | ??          |
| **Location**                            |             |
|                                                  |             |
+++
|                                      | ??          |
| **Check periodically at program start** |             |
|                                                  |             |
+++
|                                      | ??          |
| **Cache size limit**                    |             |
|                                                  |             |
+++
|                                      | ??          |
| **Current cache size**                  |             |
|                                                  |             |
+++

![](images/Preferences_General_Tab_Cache.png )

### 编辑器


<div class="mw-translate-fuzzy">

编辑器首选项设置影响的是宏编辑器的行为。此编辑器可通过**Macro → Macros...  → Edit/Create**菜单打开。
**请注意:** 这里的颜色和字体设置也会影响到[Python](https://en.wikipedia.org/wiki/Python_(programming_language))控制台。此控制台可通过**View → Panels → Python console**菜单打开。


</div>

The color and font settings also affect the [Python console](Python_console.md). This console is shown using the menu **View → Panels → Python console**.

在*Editor*选项卡中，您可以指定以下内容：


<div class="mw-translate-fuzzy">

+++
| 名称                          | 描述                                                                                                                                                                                                                                       |
+===============================+============================================================================================================================================================================================================================================+
|                | 选择代码类型。此处的颜色与字体设置将应用于所选的代码类型。可以从**Preview**框中预览效果。                                                                                                                                                  |
| **Display Items** |                                                                                                                                                                                                                                            |
|                            |                                                                                                                                                                                                                                            |
+++
|                | 指定应用于所选代码类型的字体系列（font family）。                                                                                                                                                                                          |
| **字体族**        |                                                                                                                                                                                                                                            |
|                            |                                                                                                                                                                                                                                            |
+++
|                | 指定应用于所选代码类型的字体大小。                                                                                                                                                                                                         |
| **大小**          |                                                                                                                                                                                                                                            |
|                            |                                                                                                                                                                                                                                            |
+++
|                | 若开启此项，将显示代码行号。                                                                                                                                                                                                               |
| **启用行号**      |                                                                                                                                                                                                                                            |
|                            |                                                                                                                                                                                                                                            |
+++
|                | 指定一个tab符占多少空格位置。若将此值设置为\'6\'，则多次按下**Tab**键后，将根据当前光标位置，依次跳至其后的第7个字符、第13个字符或第19个字符等处。只有在选中**保留制表符**后，本选项才可生效。 |
| **制表符长度**    |                                                                                                                                                                                                                                            |
|                            |                                                                                                                                                                                                                                            |
+++
|                | 指定在按下**Tab**键后将会插入多少个空格。只有在选中**插入空格**后，本选项才会生效。                                                                                                            |
| **缩进大小**      |                                                                                                                                                                                                                                            |
|                            |                                                                                                                                                                                                                                            |
+++
|                | 如果选择本项，则按下**Tab**键将插入占空为**制表符长度**的tab符。                                                                                                                               |
| **保留制表符**    |                                                                                                                                                                                                                                            |
|                            |                                                                                                                                                                                                                                            |
+++
|                | 如果选择本项，则按下**Tab**键将插入数量为**缩进大小**的空格符。                                                                                                                                |
| **插入空格**      |                                                                                                                                                                                                                                            |
|                            |                                                                                                                                                                                                                                            |
+++


</div>

![](images/Preferences_General_Tab_Editor_zh-cn.png )

### 输出窗口

The output preferences affect the behavior of the [Report view](Report_view.md). This panel is shown using the menu **View → Panels → Report view**.

On the *Output* tab you can specify the following:


<div class="mw-translate-fuzzy">

+++
| 名称                                               | 描述                                                                                                                                                                              |
+====================================================+===================================================================================================================================================================================+
|                                     | If checked, normal messages will be recorded. They will be displayed in the [Report view](Report_view.md) with the color set in **正常的消息**. |
| **Record normal messages**             |                                                                                                                                                                                   |
|                                                 |                                                                                                                                                                                   |
+++
|                                     | If checked, log messages will be recorded. They will be displayed in the [Report view](Report_view.md) with the color set in **日志信息**.      |
| **记录日志**                           |                                                                                                                                                                                   |
|                                                 |                                                                                                                                                                                   |
+++
|                                     | If checked, warnings will be recorded. They will be displayed in the [Report view](Report_view.md) with the color set in **警告**.              |
| **记录警告**                           |                                                                                                                                                                                   |
|                                                 |                                                                                                                                                                                   |
+++
|                                     | If checked, error messages will be recorded. They will be displayed in the [Report view](Report_view.md) with the color set in **错误**.        |
| **记录错误**                           |                                                                                                                                                                                   |
|                                                 |                                                                                                                                                                                   |
+++
|                                     | If checked, the [Report view](Report_view.md) will be shown automatically when an error is recorded                                                                       |
| **错误时显示报表视图**                 |                                                                                                                                                                                   |
|                                                 |                                                                                                                                                                                   |
+++
|                                     | If checked, the [Report view](Report_view.md) will be shown automatically when a warning is recorded                                                                      |
| **在警告时显示报告视图**               |                                                                                                                                                                                   |
|                                                 |                                                                                                                                                                                   |
+++
|                                     | If checked, the [Report view](Report_view.md) will be shown automatically when a normal message is recorded                                                               |
| **Show report view on normal message** |                                                                                                                                                                                   |
|                                                 |                                                                                                                                                                                   |
+++
|                                     | If checked, the [Report view](Report_view.md) will be shown automatically when a log message is recorded                                                                  |
| **在日志消息中显示报告视图**           |                                                                                                                                                                                   |
|                                                 |                                                                                                                                                                                   |
+++
|                                     | If checked, each message and warning will receive a timecode                                                                                                                      |
| **Include a timecode for each entry**  |                                                                                                                                                                                   |
|                                                 |                                                                                                                                                                                   |
+++
|                                     | Specification of the font color for normal messages                                                                                                                               |
| **正常的消息**                         |                                                                                                                                                                                   |
|                                                 |                                                                                                                                                                                   |
+++
|                                     | Specification of the font color for log messages                                                                                                                                  |
| **日志信息**                           |                                                                                                                                                                                   |
|                                                 |                                                                                                                                                                                   |
+++
|                                     | Specification of the font color for warning messages                                                                                                                              |
| **警告**                               |                                                                                                                                                                                   |
|                                                 |                                                                                                                                                                                   |
+++
|                                     | Specification of the font color for error messages                                                                                                                                |
| **错误**                               |                                                                                                                                                                                   |
|                                                                                                                                                                         |
|                                                    | </div>                                                                                                                                                                            |
|                                                    |                                                                                                                                                                                |
|                                                    |                                                                                                                                                                         |
|                                                    | <div class="mw-translate-fuzzy">                                                                                                                                                  |
|                                                    |                                                                                                                                                                                |
+++
|                                     | If checked, internal Python output will be redirected from the [Python console](Python_console.md) to the [Report view](Report_view.md)                           |
| **将 Python 内部输出重定向到报告视图** |                                                                                                                                                                                   |
|                                                 |                                                                                                                                                                                   |
+++
|                                     | If checked, internal Python error messages will be redirected from the [Python console](Python_console.md) to the [Report view](Report_view.md)                   |
| **将 Python 内部错误重定向到报告视图** |                                                                                                                                                                                   |
|                                                 |                                                                                                                                                                                   |
+++


</div>

![](images/Preferences_General_Tab_Output_window_zh-cn.png )

### 宏

On the *Macro* tab you can specify the following:


<div class="mw-translate-fuzzy">

+++
| 名称                                       | 描述                                                                                                                                                                                                                                                                |
+============================================+=====================================================================================================================================================================================================================================================================+
|                             | If checked, variables defined by macros are created as local variables, otherwise as global Python variables                                                                                                                                                        |
| **在本地环境中运行宏**         |                                                                                                                                                                                                                                                                     |
|                                         |                                                                                                                                                                                                                                                                     |
+++
|                             | Specification of the path for macro files                                                                                                                                                                                                                           |
| **宏路径**                     |                                                                                                                                                                                                                                                                     |
|                                         |                                                                                                                                                                                                                                                                     |
+++
|                             | If checked, [recorded macros](Std_DlgMacroRecord.md) will also contain user interface commands                                                                                                                                                              |
| **录制图形用户界面命令**       |                                                                                                                                                                                                                                                                     |
|                                         |                                                                                                                                                                                                                                                                     |
+++
|                             | If checked, [recorded macros](Std_DlgMacroRecord.md) will also contain user interface commands, but as comments. This is useful if you don\'t want to execute these commands when running the macro, but do want to see what has been done while recording. |
| **录制为注释**                 |                                                                                                                                                                                                                                                                     |
|                                         |                                                                                                                                                                                                                                                                     |
+++
|                             | If checked, the commands executed by macro scripts are shown in the Python console. This console is shown using the **View → Panels → Python console** menu option.                                                                       |
| **在Python控制台显示脚本**     |                                                                                                                                                                                                                                                                     |
|                                         |                                                                                                                                                                                                                                                                     |
+++
|                             | Controls the number of recent macros to display in the menu                                                                                                                                                                                                         |
| **Size of recent macros list** |                                                                                                                                                                                                                                                                     |
|                                         |                                                                                                                                                                                                                                                                     |
+++
|                             | Controls the number of recent macros that get dynamically assigned shortcuts                                                                                                                                                                                        |
| **快捷方式计数**               |                                                                                                                                                                                                                                                                     |
|                                         |                                                                                                                                                                                                                                                                     |
+++
|                             | Controls which keyboard modifiers are used for the shortcuts, example **Ctrl+Shift+** creates shortcuts in the form of **Ctrl+Shift+1**, **Ctrl+Shift+2**, etc.                                                                                                     |
| **键盘编辑器**                 |                                                                                                                                                                                                                                                                     |
|                                         |                                                                                                                                                                                                                                                                     |
+++


</div>

![](images/Preferences_General_Tab_Macro_zh-cn.png )

### 单位

On the *Units* tab you can specify the following:


<div class="mw-translate-fuzzy">

+++
| 名称                           | 描述                                                                                                                                  |
+================================+=======================================================================================================================================+
|                 | Selection of the unit system to be used for all parts of FreeCAD                                                                      |
| **Unit system**    |                                                                                                                                       |
|                             |                                                                                                                                       |
+++
|                 | The number of decimals that should be shown for numbers and dimensions                                                                |
| **小数位数︰**     |                                                                                                                                       |
|                             |                                                                                                                                       |
+++
|                 | 最小分数英寸： that should be displayed. This setting is only available if the unit system **Building US (ft-in/sqft/cuft)** is used. |
| **最小分数英寸：** |                                                                                                                                       |
|                             |                                                                                                                                       |
+++


</div>

![](images/Preferences_General_Tab_Units_zh-cn.png )

## Display settings 

This preferences section has three standard tabs: 3D View, Navigation and Colors. A fourth tab, Mesh view, is added if the [Mesh Workbench](Mesh_Workbench.md) has been loaded.

### 三维视图

On the *3D View* tab you can specify the following:

+++
| Name                                                  | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
+=======================================================+=================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================+
|                                        | If checked, the main coordinate system will always be shown at the lower right in opened files. The **Relative size** <small>(v0.20)</small>  defines the size of the representation as a percentage of the viewport size (the minimum of its height and width).                                                                                                                                                                                                                                                                               |
| **Show coordinate system in the corner**  |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
|                                                    |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
+++
|                                        | If checked, the axis cross will be shown by default at file opening or creation                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| **Show axis cross by default**            |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
|                                                    |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| <small>(v0.19)</small>                         |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
+++
|                                        | If checked, the time needed for the last operation and the resulting [frame rate](https://en.wikipedia.org/wiki/Frame_rate) will always be shown at the lower left in opened files                                                                                                                                                                                                                                                                                                                                                                                              |
| **Show counter of frames per second**     |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
|                                                    |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
+++
|                                        | If checked, the application will remember the active workbench for each tab in the [Main view area](Main_view_area.md) independently. When switching to a tab this workbench will be restored automatically.                                                                                                                                                                                                                                                                                                                                                            |
| **Remember active workbench by tab**      |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
|                                                    |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| <small>(v0.19)</small>                         |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
+++
|                                        | If checked, [OpenGL](https://en.wikipedia.org/wiki/OpenGL) will use the CPU instead of the GPU. This option is useful for troubleshooting graphics card and driver problems. Changing this option requires a restart of the application.                                                                                                                                                                                                                                                                                                                                        |
| **Use software OpenGL**                   |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
|                                                    |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| <small>(v0.19)</small>                         |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
+++
|                                        | If checked, [Vertex Buffer Objects](https://en.wikipedia.org/wiki/Vertex_Buffer_Object) (VBO) will be used. A VBO is an [OpenGL](https://en.wikipedia.org/wiki/OpenGL) feature that provides methods for uploading vertex data (position, normal vector, color, etc.) to the graphics card. VBOs offer substantial performance gains because the data resides in the graphics memory rather than the system memory and so it can be rendered directly by the GPU. For more background info see [this webpage](https://www.haroldserrano.com/blog/understanding-opengl-objects). |
| **Use OpenGL VBO (Vertex Buffer Object)** |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
|                                                    |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
+++
|                                        | \"Render Cache\" or \"Render Acceleration\" is explained in more detail in [FreeCAD\_assembly3 render-caching](https://github.com/realthunder/FreeCAD_assembly3/wiki/Link#render-caching). There are 3 options:                                                                                                                                                                                                                                                                                                                                                                 |
| **Render Cache**                          |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
|                                                    | -   **Auto** (default), let Coin3D decide where to cache.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| <small>(v0.19)</small>                         | -   **Distributed**, manually turn on cache for all view provider root nodes.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
|                                                       | -   **Centralized**, manually turn off cache in all nodes of all view providers, and only cache at the scene graph root node. This offers the fastest rendering speed, but slower response to any scene changes.                                                                                                                                                                                                                                                                                                                                                                |
+++
|                                        | Selection if and what kind of [multisample anti-aliasing](https://en.wikipedia.org/wiki/Multisample_anti-aliasing) is used                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| **Anti-Aliasing**                         |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
|                                                    |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
+++
|                                        | Render type of transparent objects. The types are:                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| **Transparent objects**                   |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
|                                                    | -   **One pass** (default), rendering is done in one pass. For non-solid objects like faces or meshes this can lead to artifacts. [This image](https://forum.freecadweb.org/download/file.php?id=109935) shows such an artifact (black triangle) and that the type **Backface pass** avoids this.                                                                                                                                                                                                                                                                               |
| <small>(v0.19)</small>                         | -   **Backface pass**, has only an effect for non-solid objects. They are then rendered in two passes: Back-facing polygons are rendered in the first pass and the front-facing in the second pass.                                                                                                                                                                                                                                                                                                                                                                             |
+++
|                                        | Selection of the size of [vertices](Glossary#Vertex.md) (points) in the [Sketcher workbench](Sketcher_Workbench.md). The clickable area of points can be additionally enlarged by increasing the **Pick radius**.                                                                                                                                                                                                                                                                                                                     |
| **Marker size**                           |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
|                                                    |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
+++
|                                        | Sets the area for picking elements in the [3D view](3D_view.md). Larger value makes it easier to pick things, but can make some small features impossible to select.                                                                                                                                                                                                                                                                                                                                                                                                    |
| **Pick radius (px)**                      |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
|                                                    |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
+++
|                                        | Specification of the eye-to-eye distance used for stereo projections. The specified value is a factor that will be multiplied with the [bounding box](Property_editor#View.md) size of the 3D object that is currently displayed.                                                                                                                                                                                                                                                                                                                                       |
| **Eye to eye distance for stereo modes**  |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
|                                                    |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
+++
|                                        | If checked, backlight is enabled with the defined color. Backlight is used for rendering back sides of faces. Usually, you don\'t see them in solids, unless you slice one with a clipping plane, or if the faces aren\'t oriented correctly. It is only active for objects whose Lighting property (on the View tab) is set to **One side**. If disabled, back sides of faces of objects in **One side** lighting mode will be black. The related **Intensity** setting specifies the intensity of the backlight.                                    |
| **Backlight color**                       |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
|                                                    |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
+++
|                                        | Selection of the camera projection type.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| **Camera type**                           |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
|                                                    | -   **Perspective rendering**, objects will appear in a [perspective projection](https://en.wikipedia.org/wiki/Perspective_projection).                                                                                                                                                                                                                                                                                                                                                                                                                                         |
|                                                       | -   **Orthographic rendering**, objects will be projected in [orthographic projection](https://en.wikipedia.org/wiki/Orthographic_projection).                                                                                                                                                                                                                                                                                                                                                                                                                                  |
+++

![](images/Preferences_Display_Tab_3D_View.png )

### 导航栏

On the *Navigation* tab you can specify the following:

+++
| Name                                             | Description                                                                                                                                                                                                                                                                                                                                                                                          |
+==================================================+======================================================================================================================================================================================================================================================================================================================================================================================================+
|                                   | If checked, the [Navigation cube](Navigation_Cube.md) will always be shown.                                                                                                                                                                                                                                                                                                                  |
| **Navigation cube**                  |                                                                                                                                                                                                                                                                                                                                                                                                      |
|                                               |                                                                                                                                                                                                                                                                                                                                                                                       |
|                                                  | **Steps by turn**                                                                                                                                                                                                                                                                                                                                                                        |
|                                                  |                                                                                                                                                                                                                                                                                                                                                                                                   |
|                                                  | defines the number of steps required for a full rotation when using the Navigation cube rotation arrows.                                                                                                                                                                                                                                                                                             |
|                                                  |                                                                                                                                                                                                                                                                                                                                                                                                      |
|                                                  |                                                                                                                                                                                                                                                                                                                                                                                       |
|                                                  | **Corner**                                                                                                                                                                                                                                                                                                                                                                               |
|                                                  |                                                                                                                                                                                                                                                                                                                                                                                                   |
|                                                  | defines where the Navigation cube is displayed on the screen when creating or opening a document.                                                                                                                                                                                                                                                                                                    |
|                                                  |                                                                                                                                                                                                                                                                                                                                                                                                      |
|                                                  | If **Rotate to nearest** is checked, the 3D view is rotated to the nearest most logical state when a cube face is clicked. When it is off, clicking to a cube face will and up always to the same position, no matter in what cube state you were when you clicked the face. <small>(v0.20)</small>                                                                 |
|                                                  |                                                                                                                                                                                                                                                                                                                                                                                                      |
|                                                  |                                                                                                                                                                                                                                                                                                                                                                                       |
|                                                  | **Cube size**                                                                                                                                                                                                                                                                                                                                                                            |
|                                                  |                                                                                                                                                                                                                                                                                                                                                                                                   |
|                                                  | defines the size of the cube. <small>(v0.20)</small>                                                                                                                                                                                                                                                                                                                                          |
+++
|                                   | Selection of a [navigation settings set](Mouse_navigation.md). To see what each set defines, select it and then press the **Mouse...** button.                                                                                                                                                                                                                          |
| **3D Navigation**                    |                                                                                                                                                                                                                                                                                                                                                                                                      |
|                                               |                                                                                                                                                                                                                                                                                                                                                                                                      |
+++
|                                   | Selection of the rotation orbit style. When viewing a part in the x-y plane and being in the rotation mode of the 3D navigation, the difference is: If **Trackball** is selected, moving the mouse horizontally will rotate the part around the y-axis, if **Turntable** is selected the part will be rotated around the z-axis.                                                                     |
| **Orbit style**                      |                                                                                                                                                                                                                                                                                                                                                                                                      |
|                                               |                                                                                                                                                                                                                                                                                                                                                                                                      |
+++
|                                   | Defines the rotation center. Select **Window center**, **Drag at cursor**, or **Object center**.                                                                                                                                                                                                                                                                                                     |
| **Rotation mode**                    |                                                                                                                                                                                                                                                                                                                                                                                                      |
|                                               |                                                                                                                                                                                                                                                                                                                                                                                                      |
+++
|                                   | Selection of the camera orientation for new documents. This setting is also used by the [Std ViewHome](Std_ViewHome.md) command.                                                                                                                                                                                                                                                             |
| **Default camera orientation**       |                                                                                                                                                                                                                                                                                                                                                                                                      |
|                                               |                                                                                                                                                                                                                                                                                                                                                                                                      |
+++
|                                   | Affects the initial camera zoom level for new documents. The value you set is the diameter of a sphere that fits in 3D view. Default is 100 mm. It also sets the initial size of origin features (base planes in new [PartDesign Bodies](PartDesign_Body.md)).                                                                                                                               |
| **New document scale**               |                                                                                                                                                                                                                                                                                                                                                                                                      |
|                                               |                                                                                                                                                                                                                                                                                                                                                                                                      |
+++
|                                   | If checked, rotations can be animated. If for example the **3D Navigation** set *CAD* is used and the mouse is moved while the scroll wheel and the right mouse button are pressed, parts are rotated. If one keeps the mouse moving while releasing e.g. the right mouse button, the rotation will continue as animation. To end the animation left-click with the mouse. |
| **Enable animation**                 |                                                                                                                                                                                                                                                                                                                                                                                                      |
|                                               |                                                                                                                                                                                                                                                                                                                                                                                                      |
+++
|                                   | If checked, zoom operations will be performed at the position of the mouse pointer. Otherwise zoom operations will be performed at the center of the current view. The **Zoom step** defines how much will be zoomed. A zoom step of **1** means a factor of 7.5 for every zoom step.                                                                                      |
| **Zoom at cursor**                   |                                                                                                                                                                                                                                                                                                                                                                                                      |
|                                               |                                                                                                                                                                                                                                                                                                                                                                                                      |
+++
|                                   | If checked, the direction of zoom operations will be inverted                                                                                                                                                                                                                                                                                                                                        |
| **Invert zoom**                      |                                                                                                                                                                                                                                                                                                                                                                                                      |
|                                               |                                                                                                                                                                                                                                                                                                                                                                                                      |
+++
|                                   | If checked, the tilting gesture will be disabled for pinch-zooming (two-finger zooming). This only affects the **3D Navigation** set *Gesture*.                                                                                                                                                                                                                            |
| **Disable touchscreen tilt gesture** |                                                                                                                                                                                                                                                                                                                                                                                                      |
|                                               |                                                                                                                                                                                                                                                                                                                                                                                                      |
+++

![](images/Preferences_Display_Tab_Navigation.png )

### 颜色

On the *Colors* tab you can specify the following:

+++
| Name                                             | Description                                                                                                                                                                                                                         |
+==================================================+=====================================================================================================================================================================================================================================+
|                                   | If checked, preselection is turned on and the specified color will be used for it. Preselection means that for example edges in parts will be highlighted while hovering over them with the mouse to indicate they can be selected. |
| **Enable preselection highlighting** |                                                                                                                                                                                                                                     |
|                                               |                                                                                                                                                                                                                                     |
+++
|                                   | If checked, selection highlighting is turned on and the specified color will be used for it                                                                                                                                         |
| **Enable selection highlighting**    |                                                                                                                                                                                                                                     |
|                                               |                                                                                                                                                                                                                                     |
+++
|                                   | If selected, the background of the [3D view](3D_view.md) will have the selected color                                                                                                                                       |
| **Simple color**                     |                                                                                                                                                                                                                                     |
|                                               |                                                                                                                                                                                                                                     |
+++
|                                   | If selected, the background of the [3D view](3D_view.md) will have a vertical color gradient. The first color is the color at the top of the 3D view, the second the color at the bottom.                                   |
| **Color gradient**                   |                                                                                                                                                                                                                                     |
|                                               |                                                                                                                                                                                                                                     |
+++
|                                   | Is only enabled if **Color gradient** is selected. If checked, the color gradient will get the selected color as the middle color.                                                                        |
| **Middle color**                     |                                                                                                                                                                                                                                     |
|                                               |                                                                                                                                                                                                                                     |
+++
|                                   | Selection of the background color for objects in the tree view that are currently edited                                                                                                                                            |
| **Object being edited**              |                                                                                                                                                                                                                                     |
|                                               |                                                                                                                                                                                                                                     |
+++
|                                   | Selection of the background color for active containers in the tree view. For example an [active PartDesign Body](PartDesign_Body#Active_Status.md) will get the selected background color.                                 |
| **Active container**                 |                                                                                                                                                                                                                                     |
|                                               |                                                                                                                                                                                                                                     |
+++

![](images/Preferences_Display_Tab_Colors.png )

### 网格视图

This tab is only available if the [Mesh Workbench](Mesh_Workbench.md) has been loaded.

On the *Mesh view* tab you can specify the following:

+++
| Name                                                                 | Description                                                                                                                                                                                                                                                                                                                                              |
+======================================================================+==========================================================================================================================================================================================================================================================================================================================================================+
|                                                       | Selection of the default shape color                                                                                                                                                                                                                                                                                                                     |
| **Default mesh color**                                   |                                                                                                                                                                                                                                                                                                                                                          |
|                                                                   |                                                                                                                                                                                                                                                                                                                                                          |
+++
|                                                       | Selection of the default line color                                                                                                                                                                                                                                                                                                                      |
| **Default line color**                                   |                                                                                                                                                                                                                                                                                                                                                          |
|                                                                   |                                                                                                                                                                                                                                                                                                                                                          |
+++
|                                                       | Specification of the default mesh transparency                                                                                                                                                                                                                                                                                                           |
| **Mesh transparency**                                    |                                                                                                                                                                                                                                                                                                                                                          |
|                                                                   |                                                                                                                                                                                                                                                                                                                                                          |
+++
|                                                       | Specification of the default line transparency                                                                                                                                                                                                                                                                                                           |
| **Line transparency**                                    |                                                                                                                                                                                                                                                                                                                                                          |
|                                                                   |                                                                                                                                                                                                                                                                                                                                                          |
+++
|                                                       | If checked, the color of the interior side of faces will be the same as the exterior side. If not checked either the [backlight color](#3D_View.md), if enabled, or black will be used instead.                                                                                                                                                  |
| **Two-side rendering**                                   |                                                                                                                                                                                                                                                                                                                                                          |
|                                                                   |                                                                                                                                                                                                                                                                                                                                                          |
+++
|                                                       | If checked, a yellow bounding box will be displayed for highlighted or selected meshes                                                                                                                                                                                                                                                                   |
| **Show bounding-box for highlighted or selected meshes** |                                                                                                                                                                                                                                                                                                                                                          |
|                                                                   |                                                                                                                                                                                                                                                                                                                                                          |
+++
|                                                       | If checked, [Phong shading](https://en.wikipedia.org/wiki/Phong_shading) is used, otherwise flat shading. Shading defines the appearance of surfaces. With flat shading the surface normals are not defined per vertex. This leads to an unrealistic appearance for curved surfaces. While Phong shading leads to a more realistic, smoother appearance. |
| **Define normal per vertex**                             |                                                                                                                                                                                                                                                                                                                                                          |
|                                                                   |                                                                                                                                                                                                                                                                                                                                                          |
+++
|                                                       | The crease angle is a threshold angle between two faces. It can only be set if the option **Define normal per vertex** is used.                                                                                                                                                                                                |
| **Crease angle**                                         |                                                                                                                                                                                                                                                                                                                                                          |
|                                                                   | :   If face angle ≥ crease angle, facet shading is used                                                                                                                                                                                                                                                                                                  |
|                                                                      | :   If face angle \< crease angle, smooth shading is used                                                                                                                                                                                                                                                                                                |
+++

![](images/Preferences_Display_Tab_Mesh_view.png )

## Workbenches

This preferences section has a single tab: Available Workbenches.

### Available Workbenches 

To preserve resources, FreeCAD does not automatically load all available workbenches. And only if a workbench has been loaded will its preferences, if any, appear in the Preferences editor.

In FreeCAD version 0.19 the tab has a different label: *Unloaded Workbenches*, and the tab displays a list of installed workbenches that have not yet been loaded. To load one or more workbenches select them in the list and then press the **Load Selected** button.

In FreeCAD version 0.20 the *Available Workbenches* tab displays a list of all installed workbenches. To load a workbench press its **Load now** button. If you check a workbench\'s **Autoload** checkbox it will autoload when FreeCAD starts up. Loading more workbenches will make the startup slower, but switching between workbenches that have already been loaded is faster.

If a newly loaded workbench has dedicated preference they will appear in a new section in the Preferences editor. Some workbenches add support for additional import and export formats. If there are any related preferences they will appear on one or more new tabs in the [Import-Export settings](#Import-Export_settings.md) section of the Preferences editor.

For a list of workbench preferences see [Workbench preferences](#Workbench_preferences.md)

![](images/Preferences_Workbenches_Tab_Available_Workbenches.png )

## Import-Export settings 

The Import-Export settings affect how files are imported and exported. They are described on the [Import Export Preferences](Import_Export_Preferences.md) page.


<div class="mw-translate-fuzzy">

## 工作台首选项

下列为常用工作台的首选项。部分工作台并没有对应的首选项。其他可选工作台可能也未列入其中。


</div>


**This section is incomplete and requires mentioning the preference pages of each core workbench**

Preferences for the more common workbenches are linked below. Some workbenches have no preferences. Other optional workbenches may not be listed. These links are also listed in [:Category:Preferences](:Category_Preferences.md)


<div class="mw-translate-fuzzy">

[Arch工作台首选项](Arch_Preferences.md)


</div>

### External workbenches 


**This section is incomplete and requires mentioning the preference pages of each [External workbench](External_workbenches.md)**


<div class="mw-translate-fuzzy">

[A2plus工作台首选项](A2plus_Workbench#Preferences.md)


</div>

## Scripting


**See also:**

[FreeCAD Scripting Basics](FreeCAD_Scripting_Basics.md).

For a scripting example see [Std DlgParameter](Std_DlgParameter.md).

## Related

-   [Parameter editor](Std_DlgParameter.md)
-   [Fine-tuning](Fine-tuning.md)



---
![](images/Right_arrow.png) [documentation index](../README.md) > [Preferences](Category_Preferences.md) > Preferences Editor/zh-cn
