---
title: Obsługa zdarzeń elementu DataView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e5675663-fc91-4e0d-87a9-481b25b64c0f
ms.openlocfilehash: 2a67cb040c5d438d17ad91d41e97f24f3166262b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204544"
---
# <a name="handling-dataview-events"></a>Obsługa zdarzeń elementu DataView

<xref:System.Data.DataView.ListChanged>Aby określić, czy widok został zaktualizowany, można użyć zdarzenia <xref:System.Data.DataView> . Aktualizacje, które powodują wygenerowanie zdarzenia, obejmują dodawanie, usuwanie lub modyfikowanie wiersza w tabeli źródłowej; Dodawanie lub usuwanie kolumny do schematu tabeli bazowej; i zmiana relacji nadrzędnej lub podrzędnej. Zdarzenie **ListChanged** powiadamia również o tym, czy lista wyświetlanych wierszy została znacząco zmieniona z powodu zastosowania nowej kolejności sortowania lub filtru.  
  
 Zdarzenie **ListChanged** implementuje delegata **ListChangedEventHandler** <xref:System.ComponentModel> przestrzeni nazw i przyjmuje jako obiekt wejściowy <xref:System.ComponentModel.ListChangedEventArgs> . Można określić, jakiego typu zmiany wystąpiły przy użyciu <xref:System.ComponentModel.ListChangedType> wartości wyliczenia we właściwości **ListChangedType** obiektu **ListChangedEventArgs** . W przypadku zmian, które obejmują dodawanie, usuwanie lub przenoszenie wierszy, nowy indeks dodanego lub przeniesionego wiersza i poprzedni indeks usuniętego wiersza są dostępne za pomocą właściwości **NewIndex** obiektu **ListChangedEventArgs** . W przypadku przenoszonego wiersza poprzedni indeks przenoszonego wiersza można uzyskać za pomocą właściwości **OldIndex** obiektu **ListChangedEventArgs** .  
  
 Element **DataViewManager** udostępnia również zdarzenie **ListChanged** w celu powiadomienia użytkownika o dodaniu lub usunięciu tabeli lub wprowadzeniu zmiany do kolekcji **relacji** bazowego **zestawu danych**.  
  
 Poniższy przykład kodu pokazuje, jak dodać program obsługi zdarzeń **ListChanged** .  
  
```vb  
AddHandler custView.ListChanged, _  
  New System.ComponentModel.ListChangedEventHandler( _  
  AddressOf OnListChanged)  
  
Private Shared Sub OnListChanged( _  
  sender As Object, args As System.ComponentModel.ListChangedEventArgs)  
  Console.WriteLine("ListChanged:")  
  Console.WriteLine(vbTab & "    Type = " & _  
    System.Enum.GetName(args.ListChangedType.GetType(), _  
    args.ListChangedType))  
  Console.WriteLine(vbTab & "OldIndex = " & args.OldIndex)  
  Console.WriteLine(vbTab & "NewIndex = " & args.NewIndex)  
End Sub  
```  
  
```csharp  
custView.ListChanged  += new
  System.ComponentModel.ListChangedEventHandler(OnListChanged);  
  
protected static void OnListChanged(object sender,
  System.ComponentModel.ListChangedEventArgs args)  
{  
  Console.WriteLine("ListChanged:");  
  Console.WriteLine("\t    Type = " + args.ListChangedType);  
  Console.WriteLine("\tOldIndex = " + args.OldIndex);  
  Console.WriteLine("\tNewIndex = " + args.NewIndex);  
}  
```  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.Data.DataView>
- <xref:System.ComponentModel.ListChangedEventHandler>
- [Elementy DataView](dataviews.md)
- [Omówienie ADO.NET](../ado-net-overview.md)
