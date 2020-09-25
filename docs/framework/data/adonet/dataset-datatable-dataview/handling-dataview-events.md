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
# <a name="handling-dataview-events"></a><span data-ttu-id="579f3-102">Obsługa zdarzeń elementu DataView</span><span class="sxs-lookup"><span data-stu-id="579f3-102">Handling DataView Events</span></span>

<span data-ttu-id="579f3-103"><xref:System.Data.DataView.ListChanged>Aby określić, czy widok został zaktualizowany, można użyć zdarzenia <xref:System.Data.DataView> .</span><span class="sxs-lookup"><span data-stu-id="579f3-103">You can use the <xref:System.Data.DataView.ListChanged> event of the <xref:System.Data.DataView> to determine if a view has been updated.</span></span> <span data-ttu-id="579f3-104">Aktualizacje, które powodują wygenerowanie zdarzenia, obejmują dodawanie, usuwanie lub modyfikowanie wiersza w tabeli źródłowej; Dodawanie lub usuwanie kolumny do schematu tabeli bazowej; i zmiana relacji nadrzędnej lub podrzędnej.</span><span class="sxs-lookup"><span data-stu-id="579f3-104">Updates that raise the event include adding, deleting, or modifying a row in the underlying table; adding or deleting a column to the schema of the underlying table; and a change in a parent or child relationship.</span></span> <span data-ttu-id="579f3-105">Zdarzenie **ListChanged** powiadamia również o tym, czy lista wyświetlanych wierszy została znacząco zmieniona z powodu zastosowania nowej kolejności sortowania lub filtru.</span><span class="sxs-lookup"><span data-stu-id="579f3-105">The **ListChanged** event also notifies you if the list of rows you are viewing has changed significantly due to the application of a new sort order or a filter.</span></span>  
  
 <span data-ttu-id="579f3-106">Zdarzenie **ListChanged** implementuje delegata **ListChangedEventHandler** <xref:System.ComponentModel> przestrzeni nazw i przyjmuje jako obiekt wejściowy <xref:System.ComponentModel.ListChangedEventArgs> .</span><span class="sxs-lookup"><span data-stu-id="579f3-106">The **ListChanged** event implements the **ListChangedEventHandler** delegate of the <xref:System.ComponentModel> namespace and takes as input a <xref:System.ComponentModel.ListChangedEventArgs> object.</span></span> <span data-ttu-id="579f3-107">Można określić, jakiego typu zmiany wystąpiły przy użyciu <xref:System.ComponentModel.ListChangedType> wartości wyliczenia we właściwości **ListChangedType** obiektu **ListChangedEventArgs** .</span><span class="sxs-lookup"><span data-stu-id="579f3-107">You can determine what type of change has occurred using the <xref:System.ComponentModel.ListChangedType> enumeration value in the **ListChangedType** property of the **ListChangedEventArgs** object.</span></span> <span data-ttu-id="579f3-108">W przypadku zmian, które obejmują dodawanie, usuwanie lub przenoszenie wierszy, nowy indeks dodanego lub przeniesionego wiersza i poprzedni indeks usuniętego wiersza są dostępne za pomocą właściwości **NewIndex** obiektu **ListChangedEventArgs** .</span><span class="sxs-lookup"><span data-stu-id="579f3-108">For changes that involve adding, deleting, or moving rows, the new index of the added or moved row and the previous index of the deleted row can be accessed using the **NewIndex** property of the **ListChangedEventArgs** object.</span></span> <span data-ttu-id="579f3-109">W przypadku przenoszonego wiersza poprzedni indeks przenoszonego wiersza można uzyskać za pomocą właściwości **OldIndex** obiektu **ListChangedEventArgs** .</span><span class="sxs-lookup"><span data-stu-id="579f3-109">In the case of a moved row, the previous index of the moved row can be accessed using the **OldIndex** property of the **ListChangedEventArgs** object.</span></span>  
  
 <span data-ttu-id="579f3-110">Element **DataViewManager** udostępnia również zdarzenie **ListChanged** w celu powiadomienia użytkownika o dodaniu lub usunięciu tabeli lub wprowadzeniu zmiany do kolekcji **relacji** bazowego **zestawu danych**.</span><span class="sxs-lookup"><span data-stu-id="579f3-110">The **DataViewManager** also exposes a **ListChanged** event to notify you if a table has been added or removed, or if a change has been made to the **Relations** collection of the underlying **DataSet**.</span></span>  
  
 <span data-ttu-id="579f3-111">Poniższy przykład kodu pokazuje, jak dodać program obsługi zdarzeń **ListChanged** .</span><span class="sxs-lookup"><span data-stu-id="579f3-111">The following code example shows how to add a **ListChanged** event handler.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="579f3-112">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="579f3-112">See also</span></span>

- <xref:System.Data.DataView>
- <xref:System.ComponentModel.ListChangedEventHandler>
- [<span data-ttu-id="579f3-113">Elementy DataView</span><span class="sxs-lookup"><span data-stu-id="579f3-113">DataViews</span></span>](dataviews.md)
- [<span data-ttu-id="579f3-114">Omówienie ADO.NET</span><span class="sxs-lookup"><span data-stu-id="579f3-114">ADO.NET Overview</span></span>](../ado-net-overview.md)
