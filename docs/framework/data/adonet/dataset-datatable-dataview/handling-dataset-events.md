---
title: Obsługa zdarzeń elementu DataSet
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 54edefe0-bc38-419b-b486-3d8a0c356f13
ms.openlocfilehash: 0f79b97b486bbc3e1150cd6aff8162d37134f62e
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557999"
---
# <a name="handling-dataset-events"></a><span data-ttu-id="34c39-102">Obsługa zdarzeń elementu DataSet</span><span class="sxs-lookup"><span data-stu-id="34c39-102">Handling DataSet Events</span></span>
<span data-ttu-id="34c39-103"><xref:System.Data.DataSet>Obiekt zawiera trzy zdarzenia: <xref:System.ComponentModel.MarshalByValueComponent.Disposed> , <xref:System.Data.DataSet.Initialized> , i <xref:System.Data.DataSet.MergeFailed> .</span><span class="sxs-lookup"><span data-stu-id="34c39-103">The <xref:System.Data.DataSet> object provides three events: <xref:System.ComponentModel.MarshalByValueComponent.Disposed>, <xref:System.Data.DataSet.Initialized>, and <xref:System.Data.DataSet.MergeFailed>.</span></span>  
  
## <a name="the-mergefailed-event"></a><span data-ttu-id="34c39-104">Zdarzenie MergeFailed</span><span class="sxs-lookup"><span data-stu-id="34c39-104">The MergeFailed Event</span></span>  
 <span data-ttu-id="34c39-105">Najczęściej używane zdarzenie `DataSet` obiektu to `MergeFailed` , który jest wywoływany, gdy schemat `DataSet` scalonych obiektów jest w konflikcie.</span><span class="sxs-lookup"><span data-stu-id="34c39-105">The most commonly used event of the `DataSet` object is `MergeFailed`, which is raised when the schema of the `DataSet` objects being merged are in conflict.</span></span> <span data-ttu-id="34c39-106">Dzieje się tak, gdy element docelowy i źródło <xref:System.Data.DataRow> mają tę samą wartość klucza podstawowego i <xref:System.Data.DataSet.EnforceConstraints%2A> Właściwość jest ustawiona na `true` .</span><span class="sxs-lookup"><span data-stu-id="34c39-106">This occurs when a target and source <xref:System.Data.DataRow> have the same primary key value, and the <xref:System.Data.DataSet.EnforceConstraints%2A> property is set to `true`.</span></span> <span data-ttu-id="34c39-107">Na przykład, jeśli kolumny klucza podstawowego Scalonej tabeli są takie same między tabelami w dwóch `DataSet` obiektach, zgłaszany jest wyjątek, a `MergeFailed` zdarzenie jest zgłaszane.</span><span class="sxs-lookup"><span data-stu-id="34c39-107">For example, if the primary key columns of a table being merged are the same between the tables in the two `DataSet` objects, an exception is thrown and the `MergeFailed` event is raised.</span></span> <span data-ttu-id="34c39-108"><xref:System.Data.MergeFailedEventArgs>Obiekt przesłany do `MergeFailed` zdarzenia ma <xref:System.Data.MergeFailedEventArgs.Conflict%2A> Właściwość, która identyfikuje konflikt w schemacie między tymi dwoma `DataSet` obiektami, i <xref:System.Data.MergeFailedEventArgs.Table%2A> Właściwość, która określa nazwę tabeli w konflikcie.</span><span class="sxs-lookup"><span data-stu-id="34c39-108">The <xref:System.Data.MergeFailedEventArgs> object passed to the `MergeFailed` event have a <xref:System.Data.MergeFailedEventArgs.Conflict%2A> property that identifies the conflict in schema between the two `DataSet` objects, and a <xref:System.Data.MergeFailedEventArgs.Table%2A> property that identifies the name of the table in conflict.</span></span>  
  
 <span data-ttu-id="34c39-109">Poniższy fragment kodu pokazuje, jak dodać program obsługi zdarzeń dla `MergeFailed` zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="34c39-109">The following code fragment demonstrates how to add an event handler for the `MergeFailed` event.</span></span>  
  
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
  
## <a name="the-initialized-event"></a><span data-ttu-id="34c39-110">Zainicjowane zdarzenie</span><span class="sxs-lookup"><span data-stu-id="34c39-110">The Initialized Event</span></span>  
 <span data-ttu-id="34c39-111"><xref:System.Data.DataSet.Initialized>Zdarzenie występuje, gdy `DataSet` Konstruktor inicjuje nowe wystąpienie obiektu `DataSet` .</span><span class="sxs-lookup"><span data-stu-id="34c39-111">The <xref:System.Data.DataSet.Initialized> event occurs after the `DataSet` constructor initializes a new instance of the `DataSet`.</span></span>  
  
 <span data-ttu-id="34c39-112"><xref:System.Data.DataSet.IsInitialized%2A>Właściwość zwraca, `true` Jeśli `DataSet` zakończył inicjalizację; w przeciwnym razie zwraca `false` .</span><span class="sxs-lookup"><span data-stu-id="34c39-112">The <xref:System.Data.DataSet.IsInitialized%2A> property returns `true` if the `DataSet` has completed initialization; otherwise it returns `false`.</span></span> <span data-ttu-id="34c39-113"><xref:System.Data.DataSet.BeginInit%2A>Metoda, która rozpoczyna inicjalizację `DataSet` , ustawia <xref:System.Data.DataSet.IsInitialized%2A> na `false` .</span><span class="sxs-lookup"><span data-stu-id="34c39-113">The <xref:System.Data.DataSet.BeginInit%2A> method, which begins the initialization of a `DataSet`, sets <xref:System.Data.DataSet.IsInitialized%2A> to `false`.</span></span> <span data-ttu-id="34c39-114"><xref:System.Data.DataSet.EndInit%2A>Metoda, która przerywa inicjalizację `DataSet` , ustawia ją na `true` .</span><span class="sxs-lookup"><span data-stu-id="34c39-114">The <xref:System.Data.DataSet.EndInit%2A> method, which ends the initialization of the `DataSet`, sets it to `true`.</span></span> <span data-ttu-id="34c39-115">Te metody są używane przez środowisko projektowe programu Visual Studio do inicjowania `DataSet` , który jest używany przez inny składnik.</span><span class="sxs-lookup"><span data-stu-id="34c39-115">These methods are used by the Visual Studio design environment to initialize a `DataSet` that is being used by another component.</span></span> <span data-ttu-id="34c39-116">Nie są one często używane w kodzie.</span><span class="sxs-lookup"><span data-stu-id="34c39-116">You will not commonly use them in your code.</span></span>  
  
## <a name="the-disposed-event"></a><span data-ttu-id="34c39-117">Usunięte zdarzenie</span><span class="sxs-lookup"><span data-stu-id="34c39-117">The Disposed Event</span></span>  
 <span data-ttu-id="34c39-118">`DataSet` pochodzi od <xref:System.ComponentModel.MarshalByValueComponent> klasy, która uwidacznia zarówno <xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A> metodę, jak i <xref:System.ComponentModel.MarshalByValueComponent.Disposed> zdarzenie.</span><span class="sxs-lookup"><span data-stu-id="34c39-118">`DataSet` is derived from the <xref:System.ComponentModel.MarshalByValueComponent> class, which exposes both the <xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A> method and the <xref:System.ComponentModel.MarshalByValueComponent.Disposed> event.</span></span> <span data-ttu-id="34c39-119"><xref:System.ComponentModel.MarshalByValueComponent.Disposed>Zdarzenie dodaje procedurę obsługi zdarzeń, która umożliwia nasłuchiwanie usuniętego zdarzenia w składniku.</span><span class="sxs-lookup"><span data-stu-id="34c39-119">The <xref:System.ComponentModel.MarshalByValueComponent.Disposed> event adds an event handler to listen to the disposed event on the component.</span></span> <span data-ttu-id="34c39-120">Możesz użyć zdarzenia, <xref:System.ComponentModel.MarshalByValueComponent.Disposed> `DataSet` Jeśli chcesz wykonać kod, gdy <xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A> wywoływana jest metoda.</span><span class="sxs-lookup"><span data-stu-id="34c39-120">You can use the <xref:System.ComponentModel.MarshalByValueComponent.Disposed> event of a `DataSet` if you want to execute code when the <xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A> method is called.</span></span> <span data-ttu-id="34c39-121"><xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A> Zwalnia zasoby używane przez program <xref:System.ComponentModel.MarshalByValueComponent> .</span><span class="sxs-lookup"><span data-stu-id="34c39-121"><xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A> releases the resources used by the <xref:System.ComponentModel.MarshalByValueComponent>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="34c39-122">`DataSet`Obiekty i `DataTable` dziedziczą z <xref:System.ComponentModel.MarshalByValueComponent> i obsługują <xref:System.Runtime.Serialization.ISerializable> interfejs na potrzeby komunikacji zdalnej.</span><span class="sxs-lookup"><span data-stu-id="34c39-122">The `DataSet` and `DataTable` objects inherit from <xref:System.ComponentModel.MarshalByValueComponent> and support the <xref:System.Runtime.Serialization.ISerializable> interface for remoting.</span></span> <span data-ttu-id="34c39-123">Są to jedyne ADO.NET obiekty, które można zdalnie.</span><span class="sxs-lookup"><span data-stu-id="34c39-123">These are the only ADO.NET objects that can be remoted.</span></span> <span data-ttu-id="34c39-124">Aby uzyskać więcej informacji, zobacz [komunikacja zdalna platformy .NET](/previous-versions/dotnet/netframework-4.0/72x4h507(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="34c39-124">For more information, see [.NET Remoting](/previous-versions/dotnet/netframework-4.0/72x4h507(v=vs.100)).</span></span>  
  
 <span data-ttu-id="34c39-125">Aby uzyskać informacje o innych zdarzeniach dostępnych podczas pracy z usługą `DataSet` , zobacz [obsługiwanie zdarzeń DataTable](handling-datatable-events.md) i [Obsługa zdarzeń DataAdapter](../handling-dataadapter-events.md).</span><span class="sxs-lookup"><span data-stu-id="34c39-125">For information about other events available when working with a `DataSet`, see [Handling DataTable Events](handling-datatable-events.md) and [Handling DataAdapter Events](../handling-dataadapter-events.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34c39-126">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="34c39-126">See also</span></span>

- [<span data-ttu-id="34c39-127">Elementy DataSet, DataTable i DataView</span><span class="sxs-lookup"><span data-stu-id="34c39-127">DataSets, DataTables, and DataViews</span></span>](index.md)
- <span data-ttu-id="34c39-128">[Sprawdzanie poprawności danych](/previous-versions/visualstudio/visual-studio-2013/t3b36awf(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="34c39-128">[Validating Data](/previous-versions/visualstudio/visual-studio-2013/t3b36awf(v=vs.120))</span></span>
- [<span data-ttu-id="34c39-129">Pobieranie i modyfikowanie danych ADO.NET</span><span class="sxs-lookup"><span data-stu-id="34c39-129">Retrieving and Modifying Data in ADO.NET</span></span>](../retrieving-and-modifying-data.md)
- [<span data-ttu-id="34c39-130">Omówienie ADO.NET</span><span class="sxs-lookup"><span data-stu-id="34c39-130">ADO.NET Overview</span></span>](../ado-net-overview.md)
