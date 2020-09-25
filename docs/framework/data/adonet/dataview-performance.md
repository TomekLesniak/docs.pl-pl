---
title: Wydajność widoku danych
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 90820e49-9d46-41f6-9a3d-6c0741bbd8eb
ms.openlocfilehash: b2483becce31ab75d8b55b7a642c4ada83da59f6
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91183354"
---
# <a name="dataview-performance"></a><span data-ttu-id="8249f-102">Wydajność widoku danych</span><span class="sxs-lookup"><span data-stu-id="8249f-102">DataView Performance</span></span>

<span data-ttu-id="8249f-103">W tym temacie omówiono zalety korzystania z <xref:System.Data.DataView.Find%2A> <xref:System.Data.DataView.FindRows%2A> metod i klasy oraz <xref:System.Data.DataView> buforowanie a <xref:System.Data.DataView> w aplikacji sieci Web.</span><span class="sxs-lookup"><span data-stu-id="8249f-103">This topic discusses the performance benefits of using the <xref:System.Data.DataView.Find%2A> and <xref:System.Data.DataView.FindRows%2A> methods of the <xref:System.Data.DataView> class, and of caching a <xref:System.Data.DataView> in a Web application.</span></span>  
  
## <a name="find-and-findrows"></a><span data-ttu-id="8249f-104">Znajdź i FindRows</span><span class="sxs-lookup"><span data-stu-id="8249f-104">Find and FindRows</span></span>  

 <span data-ttu-id="8249f-105"><xref:System.Data.DataView> tworzy indeks.</span><span class="sxs-lookup"><span data-stu-id="8249f-105"><xref:System.Data.DataView> constructs an index.</span></span> <span data-ttu-id="8249f-106">Indeks zawiera klucze skompilowane z co najmniej jednej kolumny w tabeli lub widoku.</span><span class="sxs-lookup"><span data-stu-id="8249f-106">An index contains keys built from one or more columns in the table or view.</span></span> <span data-ttu-id="8249f-107">Klucze te są przechowywane w strukturze, która umożliwia <xref:System.Data.DataView> szybkie i wydajne Znajdowanie wierszy lub wierszy skojarzonych z wartościami klucza.</span><span class="sxs-lookup"><span data-stu-id="8249f-107">These keys are stored in a structure that enables the <xref:System.Data.DataView> to find the row or rows associated with the key values quickly and efficiently.</span></span> <span data-ttu-id="8249f-108">Operacje, które używają indeksu, takie jak filtrowanie i sortowanie, zobacz znaczące zwiększenie wydajności.</span><span class="sxs-lookup"><span data-stu-id="8249f-108">Operations that use the index, such as filtering and sorting, see significant performance increases.</span></span> <span data-ttu-id="8249f-109">Indeks dla obiektu <xref:System.Data.DataView> jest kompilowany zarówno podczas tworzenia, <xref:System.Data.DataView> jak i gdy dowolna z informacji o sortowaniu lub filtrowaniu jest modyfikowana.</span><span class="sxs-lookup"><span data-stu-id="8249f-109">The index for a <xref:System.Data.DataView> is built both when the <xref:System.Data.DataView> is created and when any of the sorting or filtering information is modified.</span></span> <span data-ttu-id="8249f-110">Utworzenie <xref:System.Data.DataView> a, a następnie ustawienie informacji o sortowaniu lub filtrowaniu później spowoduje, że indeks zostanie skompilowany co najmniej dwa razy: raz podczas <xref:System.Data.DataView> tworzenia i ponownie, gdy właściwości sortowania lub filtrowania są modyfikowane.</span><span class="sxs-lookup"><span data-stu-id="8249f-110">Creating a <xref:System.Data.DataView> and then setting the sorting or filtering information later causes the index to be built at least twice: once when the <xref:System.Data.DataView> is created, and again when any of the sort or filter properties are modified.</span></span> <span data-ttu-id="8249f-111">Aby uzyskać więcej informacji o filtrowaniu i sortowaniu w programie <xref:System.Data.DataView> , zobacz [filtrowanie z widokiem](filtering-with-dataview-linq-to-dataset.md) danych i [sortowanie za pomocą widoku](sorting-with-dataview-linq-to-dataset.md)danych.</span><span class="sxs-lookup"><span data-stu-id="8249f-111">For more information about filtering and sorting with <xref:System.Data.DataView>, see [Filtering with DataView](filtering-with-dataview-linq-to-dataset.md) and [Sorting with DataView](sorting-with-dataview-linq-to-dataset.md).</span></span>  
  
 <span data-ttu-id="8249f-112">Jeśli chcesz zwrócić wyniki konkretnego zapytania dotyczącego danych, w przeciwieństwie do udostępnienia dynamicznego widoku podzbioru danych, możesz użyć <xref:System.Data.DataView.Find%2A> metod lub zamiast <xref:System.Data.DataView.FindRows%2A> <xref:System.Data.DataView> ustawić <xref:System.Data.DataView.RowFilter%2A> Właściwość.</span><span class="sxs-lookup"><span data-stu-id="8249f-112">If you want to return the results of a particular query on the data, as opposed to providing a dynamic view of a subset of the data, you can use the <xref:System.Data.DataView.Find%2A> or <xref:System.Data.DataView.FindRows%2A> methods of the <xref:System.Data.DataView>, rather than setting the <xref:System.Data.DataView.RowFilter%2A> property.</span></span> <span data-ttu-id="8249f-113"><xref:System.Data.DataView.RowFilter%2A>Właściwość najlepiej jest używana w aplikacji powiązanej z danymi, gdzie kontrolka powiązania Wyświetla przefiltrowane wyniki.</span><span class="sxs-lookup"><span data-stu-id="8249f-113">The <xref:System.Data.DataView.RowFilter%2A> property is best used in a data-bound application where a bound control displays filtered results.</span></span> <span data-ttu-id="8249f-114">Ustawienie <xref:System.Data.DataView.RowFilter%2A> właściwości powoduje odbudowanie indeksu dla danych, dodanie obciążenia do aplikacji i zmniejszenie wydajności.</span><span class="sxs-lookup"><span data-stu-id="8249f-114">Setting the <xref:System.Data.DataView.RowFilter%2A> property rebuilds the index for the data, adding overhead to your application and decreasing performance.</span></span> <span data-ttu-id="8249f-115"><xref:System.Data.DataView.Find%2A>Metody i <xref:System.Data.DataView.FindRows%2A> używają bieżącego indeksu bez konieczności ponownego kompilowania indeksu.</span><span class="sxs-lookup"><span data-stu-id="8249f-115">The <xref:System.Data.DataView.Find%2A> and <xref:System.Data.DataView.FindRows%2A> methods use the current index without requiring the index to be rebuilt.</span></span> <span data-ttu-id="8249f-116">Jeśli zamierzasz wywołać <xref:System.Data.DataView.Find%2A> lub <xref:System.Data.DataView.FindRows%2A> tylko raz, należy użyć istniejącej <xref:System.Data.DataView> .</span><span class="sxs-lookup"><span data-stu-id="8249f-116">If you are going to call <xref:System.Data.DataView.Find%2A> or <xref:System.Data.DataView.FindRows%2A> only once, then you should use the existing <xref:System.Data.DataView>.</span></span> <span data-ttu-id="8249f-117">Jeśli chcesz wywoływać <xref:System.Data.DataView.Find%2A> lub <xref:System.Data.DataView.FindRows%2A> wiele razy, należy utworzyć nową, <xref:System.Data.DataView> Aby ponownie skompilować indeks w kolumnie, w której ma zostać wyszukane, a następnie wywołać <xref:System.Data.DataView.Find%2A> <xref:System.Data.DataView.FindRows%2A> metody lub.</span><span class="sxs-lookup"><span data-stu-id="8249f-117">If you are going to call <xref:System.Data.DataView.Find%2A> or <xref:System.Data.DataView.FindRows%2A> multiple times, you should create a new <xref:System.Data.DataView> to rebuild the index on the column you want to search on, and then call the <xref:System.Data.DataView.Find%2A> or <xref:System.Data.DataView.FindRows%2A> methods.</span></span> <span data-ttu-id="8249f-118">Aby uzyskać więcej informacji o <xref:System.Data.DataView.Find%2A> <xref:System.Data.DataView.FindRows%2A> metodach i, zobacz [Znajdowanie wierszy](./dataset-datatable-dataview/finding-rows.md).</span><span class="sxs-lookup"><span data-stu-id="8249f-118">For more information about the <xref:System.Data.DataView.Find%2A> and <xref:System.Data.DataView.FindRows%2A> methods, see [Finding Rows](./dataset-datatable-dataview/finding-rows.md).</span></span>  
  
 <span data-ttu-id="8249f-119">Poniższy przykład używa metody, <xref:System.Data.DataView.Find%2A> Aby znaleźć kontakt z nazwiskiem "Zhu".</span><span class="sxs-lookup"><span data-stu-id="8249f-119">The following example uses the <xref:System.Data.DataView.Find%2A> method to find a contact with the last name "Zhu".</span></span>  
  
 [!code-csharp[DP DataView Samples#LDVFromQueryOrderByFind](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvfromqueryorderbyfind)]
 [!code-vb[DP DataView Samples#LDVFromQueryOrderByFind](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvfromqueryorderbyfind)]  
  
 <span data-ttu-id="8249f-120">W poniższym przykładzie zastosowano <xref:System.Data.DataView.FindRows%2A> metodę, aby znaleźć wszystkie czerwone kolorowe produkty.</span><span class="sxs-lookup"><span data-stu-id="8249f-120">The following example uses the <xref:System.Data.DataView.FindRows%2A> method to find all the red colored products.</span></span>  
  
 [!code-csharp[DP DataView Samples#LDVFromQueryFindRows](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvfromqueryfindrows)]
 [!code-vb[DP DataView Samples#LDVFromQueryFindRows](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvfromqueryfindrows)]  
  
## <a name="aspnet"></a><span data-ttu-id="8249f-121">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="8249f-121">ASP.NET</span></span>  

 <span data-ttu-id="8249f-122">ASP.NET ma mechanizm buforowania, który umożliwia przechowywanie obiektów wymagających rozległych zasobów serwera do tworzenia w pamięci.</span><span class="sxs-lookup"><span data-stu-id="8249f-122">ASP.NET has a caching mechanism that allows you to store objects that require extensive server resources to create in memory.</span></span> <span data-ttu-id="8249f-123">Buforowanie tych typów zasobów może znacząco poprawić wydajność aplikacji.</span><span class="sxs-lookup"><span data-stu-id="8249f-123">Caching these types of resources can significantly improve the performance of your application.</span></span> <span data-ttu-id="8249f-124">Buforowanie jest implementowane przez <xref:System.Web.Caching.Cache> klasę, z wystąpieniami pamięci podręcznej, które są prywatne dla każdej aplikacji.</span><span class="sxs-lookup"><span data-stu-id="8249f-124">Caching is implemented by the <xref:System.Web.Caching.Cache> class, with cache instances that are private to each application.</span></span> <span data-ttu-id="8249f-125">Ponieważ tworzenie nowego <xref:System.Data.DataView> obiektu może być czasochłonne, warto użyć tej funkcji buforowania w aplikacjach sieci Web, aby <xref:System.Data.DataView> nie trzeba było jej odbudować za każdym razem, gdy strona sieci Web zostanie odświeżona.</span><span class="sxs-lookup"><span data-stu-id="8249f-125">Because creating a new <xref:System.Data.DataView> object can be resource intensive, you might want to use this caching functionality in Web applications so that the <xref:System.Data.DataView> does not have to be rebuilt every time the Web page is refreshed.</span></span>  
  
 <span data-ttu-id="8249f-126">W poniższym przykładzie <xref:System.Data.DataView> znajduje się w pamięci podręcznej, dzięki czemu dane nie muszą być ponownie sortowane po odświeżeniu strony.</span><span class="sxs-lookup"><span data-stu-id="8249f-126">In the following example, the <xref:System.Data.DataView> is cached so that the data does not have to be re-sorted when the page is refreshed.</span></span>  
  
```vb  
If (Cache("ordersView") = Nothing) Then  
  
Dim dataSet As New DataSet()  
  
   FillDataSet(dataSet)  
  
   Dim orders As DataTable = dataSet.Tables("SalesOrderHeader")  
  
   Dim query = _  
                    From order In orders.AsEnumerable() _  
                    Where order.Field(Of Boolean)("OnlineOrderFlag") = True _  
                    Order By order.Field(Of Decimal)("TotalDue") _  
                    Select order  
  
   Dim view As DataView = query.AsDataView()  
  
   Cache.Insert("ordersView", view)  
  
End If  
  
Dim ordersView = CType(Cache("ordersView"), DataView)  
  
GridView1.DataSource = ordersView  
GridView1.DataBind()  
```  
  
```csharp  
if (Cache["ordersView"] == null)  
{  
   // Fill the DataSet.
   DataSet dataSet = FillDataSet();  
  
   DataTable orders = dataSet.Tables["SalesOrderHeader"];  
  
   EnumerableRowCollection<DataRow> query =  
                        from order in orders.AsEnumerable()  
                        where order.Field<bool>("OnlineOrderFlag") == true  
                        orderby order.Field<decimal>("TotalDue")  
                        select order;  
  
   DataView view = query.AsDataView();  
   Cache.Insert("ordersView", view);  
}  
  
DataView ordersView = (DataView)Cache["ordersView"];  
  
GridView1.DataSource = ordersView;  
GridView1.DataBind();  
```  
  
## <a name="see-also"></a><span data-ttu-id="8249f-127">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="8249f-127">See also</span></span>

- [<span data-ttu-id="8249f-128">Powiązanie danych i LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="8249f-128">Data Binding and LINQ to DataSet</span></span>](data-binding-and-linq-to-dataset.md)
