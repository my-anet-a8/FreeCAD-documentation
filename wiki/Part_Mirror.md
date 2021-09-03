---
- GuiCommand:
   Name:Part Mirror
   MenuLocation:Part → Mirror
   Workbenches:[Part](Part_Workbench.md)
---

## Description

\'Mirror Object\' - This tool creates a new object (image) which is a reflection of the original object (source). The image object is created behind a mirror plane. The mirror plane may be standard plane (**XY**, **YZ**, or **XZ**), or any plane parallel to a standard plane.

An example:

![Before](images/PARTMirrorBeforev11.png )

![After (mirrored through **YZ** plane)](images/PARTMirrorAfterv11.png )  

## Usage

![](images/PARTMirrorDialogv11.png )

1.  Select the source object from the Mirroring Panel list.
2.  Select a standard **Mirror plane** from the dropdown menu.
3.  Press **OK** to create the image object.

 

## Options

The **Base point** boxes can be used to move the mirror plane parallel to the selected standard mirror plane. Only one of the **X**, **Y**, or **Z** boxes is effective for a given standard plane.

  Standard Plane   Base Point Box   Effect
  ---------------- ---------------- -------------------------------------
  **XY**           **Z**            Move mirror plane along **Z** axis.
  **XY**           **X**, **Y**     No effect.
  **XZ**           **Y**            Move mirror plane along **Y** axis.
  **XZ**           **X**, **Z**     No effect.
  **YZ**           **X**            Move mirror plane along **X** axis.
  **YZ**           **Y**, **Z**     No effect.

## Limitations

-   Arbitrary mirror planes (ie not parallel to a standard plane) are not supported.




   