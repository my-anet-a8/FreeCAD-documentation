---
- GuiCommand:/it
   Name:Std_Group   Name/it:Crea Gruppo
   MenuLocation:Vista ad albero → Cliccare col destro sul nome del documento → Crea gruppo
   |Workbenches:Tutti
   Shortcut:
   Version:
   SeeAlso:[Parte](Std_Part/it.md), [Seleziona gruppo](Draft_SelectGroup/it.md), [Aggiungi al gruppo](Draft_AddToGroup/it.md)
---

## Descrizione

Un [Gruppo](Std_Group/it.md) (chiamato internamente [App DocumentObjectGroup](App_DocumentObjectGroup/it.md)) è un contenitore per scopi generici che consente di raggruppare diversi tipi di oggetti nella [vista ad albero](tree_view/it.md), indipendentemente dal tipo di dati. È usato come una semplice cartella per classificare e organizzare gli oggetti nel modello, al fine di mantenere una struttura logica. I gruppi possono essere nidificati all\'interno di altri gruppi.

Lo strumento Gruppo non è definito da un particolare ambiente di lavoro, ma dal sistema base; di conseguenza lo si ritrova nella **barra degli strumenti struttura**, che è disponibile in tutti gli [ambienti di lavoro](Workbenches/it.md).

Per raggruppare gli oggetti 3D come una singola unità, con l\'intenzione di creare degli assiemi, utilizzare [Parte](Std_Part/it.md).

![](images/Std_Group_example.png )


*Vari elementi all'interno di Gruppo nella vista ad albero.*

## Utilizzo

1.  Fare clic sul nome del documento nella [vista ad albero](tree_view/it.md), aprire il menu di scelta rapida (clic con il tasto destro) e scegliere **Crea gruppo**.
2.  In alternativa premere il pulsante **<img src="images/Std_Group.svg" width=16px> [Gruppo](Std_Group/it.md)** nella barra degli strumenti della struttura. Viene creato un gruppo vuoto.
3.  Per aggiungere degli oggetti a un gruppo, selezionarli nella [vista ad albero](tree_view/it.md), quindi trascinarli e rilasciarli sul gruppo.
4.  Per rimuovere degli oggetti da un gruppo, trascinarli fuori dal gruppo, sull\'etichetta del documento nella parte superiore della [ vista ad albero](tree_view/it.md).

### Note

-   L\'oggetto Gruppo non influisce sulle posizioni nella [Vista 3D](3D_view/it.md) degli elementi che contiene; è essenzialmente solo una cartella che viene utilizzata per mantenere organizzata la [vista ad albero](tree_view/it.md).
-   Il Gruppo può anche essere creato nella [Python console](Python_console.md) e sotto-classificato per creare speciali \"gruppi\" come indicato nella sezione [Script](Std_Group/it#Script.md).

## Proprietà

Un [Gruppo](Std_Group/it.md) è internamente chiamato [App DocumentObjectGroup](App_DocumentObjectGroup/it.md) (`App::DocumentObjectGroup` class), è derivato dall\'oggetto base [App DocumentObject](App_DocumentObject/it.md) (`App::DocumentObject` class), pertanto condivide tutte le proprietà di quest\'ultimo.

Oltre alle proprietà descritte in [App FeaturePython](App_FeaturePython/it.md), che è l\'istanza più elementare di un [App DocumentObject](App_DocumentObject/it.md), l\'App DocumentObjectGroup ha la proprietà **Group**.

Queste sono le proprietà disponibili nel [editore delle proprietà](property_editor/it.md). Le proprietà nascoste possono essere mostrate usando il comando **Mostra tutto** nel menu contestuale dell\'[editore delle proprietà](property_editor/it.md).

### Dati


{{TitleProperty|Base}}

-    **Label|String**: il nome modificabile dall\'utente di questo oggetto, è una stringa UTF8 arbitraria.

-    **Group|LinkList**: un elenco di oggetti referenziati. Di default, è vuoto {{value|[]}}.

#### Proprietà dati nascoste 

-    **Proxy|PythonObject**: una classe personalizzata associata a questo oggetto. Questa esiste solo per la versione [Python](Python/it.md). Vedere [Script](Std_Group/it#Script.md).

### Vista


{{TitleProperty|Base}}

Vedere [App FeaturePython](App_FeaturePython/it.md) per le proprietà di base della vista.

#### Proprietà vista nascoste 

-    **Proxy|PythonObject**: una classe del provider di visualizzazione personalizzata associata a questo oggetto. Questo esiste solo per la versione [Python](Python/it.md). Vedere [Script](Std_Group/it#Script.md).

## Eredità

Un [Gruppo](Std_Group/it.md) è formalmente un\'istanza della classe `App::DocumentObjectGroup`, il cui parente è [App DocumentObject](App_DocumentObject/it.md) (`App::DocumentObject` class), e viene incrementato con un\'estensione del Gruppo.

<img alt="" src=images/FreeCAD_core_objects.svg  style="width:800px;">


*Schema semplificato delle relazioni tra gli oggetti principali del programma. La classe `App::DocumentObjectGroup* è un semplice contenitore che utilizza l'estensione Gruppo per poter contenere qualsiasi tipo di oggetto.`

## Script


**Vedere anche:**

[Script di base per FreeCAD](FreeCAD_Scripting_Basics/it.md), e [script di oggetti](scripted_objects/it.md).

Vedi [Funzione Part](Part_Feature/it.md) per le informazioni generali su come aggiungere oggetti al documento.

Un Gruppo ([App DocumentObjectGroup](App_DocumentObjectGroup.md)) è creato con il metodo del documento `addObject()`. Una volta che un Gruppo esiste, altri oggetti possono essere aggiunti ad esso con i metodi `addObject()` o `addObjects()`. 
```python
import FreeCAD as App

doc = App.newDocument()
obj = App.ActiveDocument.addObject("App::DocumentObjectGroup", "Group")

bod1 = App.ActiveDocument.addObject("PartDesign::Body", "Body")
bod2 = App.ActiveDocument.addObject("Part::Box", "Box")

obj.addObjects([bod1, bod2])
App.ActiveDocument.recompute()
```

Questo `App::DocumentObjectGroup` di base non ha un oggetto Proxy, quindi non può essere pienamente utilizzato per la sotto-classe.

Pertanto, per la sottoclasse [Python](Python/it.md), è necessario creare l\'oggetto `App::DocumentObjectGroupPython`.


```python
import FreeCAD as App

doc = App.newDocument()
obj = App.ActiveDocument.addObject("App::DocumentObjectGroupPython", "Name")
obj.Label = "Custom label"
```

Per esempio, un [Analisi FEM](FEM_Analysis/it.md) è un oggetto `App::DocumentObjectGroupPython` con un\'icona personalizzata e proprietà aggiuntive.

## Link

-   [Esempio di utilizzo in Arch Tutorial](Arch_tutorial/it#Organizzare_il_modello.md)
-   [Struttura del documento](Document_structure/it.md)
-   [Esempio di organizzazione del modello](http://www.freecadweb.org/wiki/index.php?title=Arch_tutorial#Organizing_your_model)





{{Std Base navi

}}  