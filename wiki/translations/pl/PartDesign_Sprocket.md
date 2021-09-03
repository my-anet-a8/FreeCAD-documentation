---
- GuiCommand:/pl
   Name:PartDesign Sprocket
   Name/pl:Projekt Części: Koło łańcuchowe
   MenuLocation:Projekt Części → Koło łańcuchowe ...
   Workbenches:[Projekt Części](PartDesign_Workbench/pl.md)
   Version:0.19
---

## Opis

To narzędzie pozwala na stworzenie profilu 2D koła łańcuchowego. Może on być wypełniony za pomocą funkcji [wyciągnięcia](PartDesign_Pad/pl.md).

## Użycie

1.  Przejdź do menu **Projekt Części → <img src=images/PartDesign_Sprocket.svg style="width:24px"> Sprocket...**.
2.  Ustaw **Liczbę zębów** i **Oznaczenie koła łańcuchowego**.
3.  Kliknij w przycisk **OK**
4.  Jeśli zębatka została utworzona poza aktywną zawartością, przeciągnij ją do niej i upuść, aby zastosować dalsze funkcje, takie jak wyciągnięcie.

## Właściwości

-    {{PropertyData/pl|Liczba zębów}}: Ilość zębów.

-    {{PropertyData/pl|Oznaczenie koła łańcuchowego}}: Typ koła łańcuchowego. Lista definicji zębatek. {{Version/pl|0.20}} Lista zawiera definicje ANSI i ISO, jak również niektóre definicje zębatek rowerowych i motocyklowych.

-    **Odstęp**: Odległość pomiędzy zębami.

-    **Średnica rolki**: Średnica rolek łańcucha, dla których przeznaczone jest koło łańcuchowe.

-    **Grubość**: Główna grubość koła łańcuchowego. **Uwaga:** Koło łańcuchowe nie może być po prostu wyciągnięte tą grubością, ponieważ zęby mają fazki boczne. Dlatego należy spojrzeć na definicję koła łańcuchowego, aby wymodelować prawidłowe koło łańcuchowe 3D. {{Version/pl|0.20}}





{{PartDesign Tools navi

}} 