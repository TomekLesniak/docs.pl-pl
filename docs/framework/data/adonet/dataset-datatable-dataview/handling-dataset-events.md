---
title: Obsługa zdarzeń elementu DataSet
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 54edefe0-bc38-419b-b486-3d8a0c356f13
ms.openlocfilehash: cc425f3217409a154fd319acb8b1555895cbda54
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91183367"
---
# <a name="handling-dataset-events"></a>Obsługa zdarzeń elementu DataSet

<xref:System.Data.DataSet>Obiekt zawiera trzy zdarzenia: <xref:System.ComponentModel.MarshalByValueComponent.Disposed> , <xref:System.Data.DataSet.Initialized> , i <xref:System.Data.DataSet.MergeFailed> .  
  
## <a name="the-mergefailed-event"></a>Zdarzenie MergeFailed  

 Najczęściej używane zdarzenie `DataSet` obiektu to `MergeFailed` , który jest wywoływany, gdy schemat `DataSet` scalonych obiektów jest w konflikcie. Dzieje się tak, gdy element docelowy i źródło <xref:System.Data.DataRow> mają tę samą wartość klucza podstawowego i <xref:System.Data.DataSet.EnforceConstraints%2A> Właściwość jest ustawiona na `true` . Na przykład, jeśli kolumny klucza podstawowego Scalonej tabeli są takie same między tabelami w dwóch `DataSet` obiektach, zgłaszany jest wyjątek, a `MergeFailed` zdarzenie jest zgłaszane. <xref:System.Data.MergeFailedEventArgs>Obiekt przesłany do `MergeFailed` zdarzenia ma <xref:System.Data.MergeFailedEventArgs.Conflict%2A> Właściwość, która identyfikuje konflikt w schemacie między tymi dwoma `DataSet` obiektami, i <xref:System.Data.MergeFailedEventArgs.Table%2A> Właściwość, która określa nazwę tabeli w konflikcie.  
  
 Poniższy fragment kodu pokazuje, jak dodać program obsługi zdarzeń dla `MergeFailed` zdarzenia.  
  
```vb  
AddHandler workDS.MergeFailed, New MergeFailedEventHandler( _  
  AddressOf DataSetMergeFailed)  
  
Private Shared Sub DataSetMergeFailed(  _  
  sender As Object,args As MergeFailedEventArgs)  
  Console.WriteLine("Merge failed for table " & args.Table.TableName)  
  Console.WriteLine("Conflict = " & args.Conflict)  
End Sub  
```  
  
```csharp  
workDS.MergeFailed += new MergeFailedEventHandler(DataSetMergeFailed);  
  
private static void DataSetMergeFailed(  
  object sender, MergeFailedEventArgs args)  
{  
  Console.WriteLine("Merge failed for table " + args.Table.TableName);  
  Console.WriteLine("Conflict = " + args.Conflict);  
}  
```  
  
## <a name="the-initialized-event"></a>Zainicjowane zdarzenie  

 <xref:System.Data.DataSet.Initialized>Zdarzenie występuje, gdy `DataSet` Konstruktor inicjuje nowe wystąpienie obiektu `DataSet` .  
  
 <xref:System.Data.DataSet.IsInitialized%2A>Właściwość zwraca, `true` Jeśli `DataSet` zakończył inicjalizację; w przeciwnym razie zwraca `false` . <xref:System.Data.DataSet.BeginInit%2A>Metoda, która rozpoczyna inicjalizację `DataSet` , ustawia <xref:System.Data.DataSet.IsInitialized%2A> na `false` . <xref:System.Data.DataSet.EndInit%2A>Metoda, która przerywa inicjalizację `DataSet` , ustawia ją na `true` . Te metody są używane przez środowisko projektowe programu Visual Studio do inicjowania `DataSet` , który jest używany przez inny składnik. Nie są one często używane w kodzie.  
  
## <a name="the-disposed-event"></a>Usunięte zdarzenie  

 `DataSet` pochodzi od <xref:System.ComponentModel.MarshalByValueComponent> klasy, która uwidacznia zarówno <xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A> metodę, jak i <xref:System.ComponentModel.MarshalByValueComponent.Disposed> zdarzenie. <xref:System.ComponentModel.MarshalByValueComponent.Disposed>Zdarzenie dodaje procedurę obsługi zdarzeń, która umożliwia nasłuchiwanie usuniętego zdarzenia w składniku. Możesz użyć zdarzenia, <xref:System.ComponentModel.MarshalByValueComponent.Disposed> `DataSet` Jeśli chcesz wykonać kod, gdy <xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A> wywoływana jest metoda. <xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A> Zwalnia zasoby używane przez program <xref:System.ComponentModel.MarshalByValueComponent> .  
  
> [!NOTE]
> `DataSet`Obiekty i `DataTable` dziedziczą z <xref:System.ComponentModel.MarshalByValueComponent> i obsługują <xref:System.Runtime.Serialization.ISerializable> interfejs na potrzeby komunikacji zdalnej. Są to jedyne ADO.NET obiekty, które można zdalnie. Aby uzyskać więcej informacji, zobacz [komunikacja zdalna platformy .NET](/previous-versions/dotnet/netframework-4.0/72x4h507(v=vs.100)).  
  
 Aby uzyskać informacje o innych zdarzeniach dostępnych podczas pracy z usługą `DataSet` , zobacz [obsługiwanie zdarzeń DataTable](handling-datatable-events.md) i [Obsługa zdarzeń DataAdapter](../handling-dataadapter-events.md).  
  
## <a name="see-also"></a>Zobacz też

- [Elementy DataSet, DataTable i DataView](index.md)
- [Sprawdzanie poprawności danych](/previous-versions/visualstudio/visual-studio-2013/t3b36awf(v=vs.120))
- [Pobieranie i modyfikowanie danych ADO.NET](../retrieving-and-modifying-data.md)
- [Omówienie ADO.NET](../ado-net-overview.md)
