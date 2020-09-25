---
title: Dodawanie elementów DataRelation
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a4a564fb-c1c4-4135-b6c2-b030e51195e4
ms.openlocfilehash: 5fe2bd45e0abada1f9ec7071e3863da853479b51
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202386"
---
# <a name="adding-datarelations"></a><span data-ttu-id="5e02b-102">Dodawanie elementów DataRelation</span><span class="sxs-lookup"><span data-stu-id="5e02b-102">Adding DataRelations</span></span>

<span data-ttu-id="5e02b-103">W przypadku <xref:System.Data.DataSet> z wieloma <xref:System.Data.DataTable> obiektami można użyć obiektów, <xref:System.Data.DataRelation> Aby powiązać jedną tabelę z inną, aby nawigować przez tabele i zwracać elementy podrzędne lub nadrzędne z powiązanej tabeli.</span><span class="sxs-lookup"><span data-stu-id="5e02b-103">In a <xref:System.Data.DataSet> with multiple <xref:System.Data.DataTable> objects, you can use <xref:System.Data.DataRelation> objects to relate one table to another, to navigate through the tables, and to return child or parent rows from a related table.</span></span>  
  
 <span data-ttu-id="5e02b-104">Argumenty wymagane do utworzenia **relacji** datarelationship są nazwami **tworzonego elementu** datarelationship i tablicą zawierającą co najmniej jedno <xref:System.Data.DataColumn> odwołanie do kolumn, które pełnią rolę kolumn nadrzędnych i podrzędnych w relacji.</span><span class="sxs-lookup"><span data-stu-id="5e02b-104">The arguments required to create a **DataRelation** are a name for the **DataRelation** being created, and an array of one or more <xref:System.Data.DataColumn> references to the columns that serve as the parent and child columns in the relationship.</span></span> <span data-ttu-id="5e02b-105">Po utworzeniu **relacji**można jej używać do nawigowania między tabelami i pobierania wartości.</span><span class="sxs-lookup"><span data-stu-id="5e02b-105">After you have created a **DataRelation**, you can use it to navigate between tables and to retrieve values.</span></span>  
  
 <span data-ttu-id="5e02b-106">Dodawanie **relacji** do dodawania <xref:System.Data.DataSet> , domyślnie, <xref:System.Data.UniqueConstraint> do tabeli nadrzędnej i <xref:System.Data.ForeignKeyConstraint> do tabeli podrzędnej.</span><span class="sxs-lookup"><span data-stu-id="5e02b-106">Adding a **DataRelation** to a <xref:System.Data.DataSet> adds, by default, a <xref:System.Data.UniqueConstraint> to the parent table and a <xref:System.Data.ForeignKeyConstraint> to the child table.</span></span> <span data-ttu-id="5e02b-107">Aby uzyskać więcej informacji o tych domyślnych ograniczeniach, zobacz temat [ograniczenia DataTable](datatable-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="5e02b-107">For more information about these default constraints, see [DataTable Constraints](datatable-constraints.md).</span></span>  
  
 <span data-ttu-id="5e02b-108">Poniższy przykład kodu tworzy **relację** danych przy użyciu dwóch <xref:System.Data.DataTable> obiektów w <xref:System.Data.DataSet> .</span><span class="sxs-lookup"><span data-stu-id="5e02b-108">The following code example creates a **DataRelation** using two <xref:System.Data.DataTable> objects in a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="5e02b-109">Każda <xref:System.Data.DataTable> z nich zawiera kolumnę o nazwie **CustId**, która służy jako link między dwoma <xref:System.Data.DataTable> obiektami.</span><span class="sxs-lookup"><span data-stu-id="5e02b-109">Each <xref:System.Data.DataTable> contains a column named **CustID**, which serves as a link between the two <xref:System.Data.DataTable> objects.</span></span> <span data-ttu-id="5e02b-110">Przykład dodaje pojedyncze **powiązanie** do kolekcji **relacji** <xref:System.Data.DataSet> .</span><span class="sxs-lookup"><span data-stu-id="5e02b-110">The example adds a single **DataRelation** to the **Relations** collection of the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="5e02b-111">Pierwszy argument w przykładzie określa nazwę tworzonego **powiązania** .</span><span class="sxs-lookup"><span data-stu-id="5e02b-111">The first argument in the example specifies the name of the **DataRelation** being created.</span></span> <span data-ttu-id="5e02b-112">Drugi argument ustawia nadrzędną **kolumnę** danych, a trzeci argument ustawia podrzędną **kolumnę**danych.</span><span class="sxs-lookup"><span data-stu-id="5e02b-112">The second argument sets the parent **DataColumn** and the third argument sets the child **DataColumn**.</span></span>  
  
```vb  
customerOrders.Relations.Add("CustOrders", _  
  customerOrders.Tables("Customers").Columns("CustID"), _  
  customerOrders.Tables("Orders").Columns("CustID"))  
```  
  
```csharp  
customerOrders.Relations.Add("CustOrders",  
  customerOrders.Tables["Customers"].Columns["CustID"],  
  customerOrders.Tables["Orders"].Columns["CustID"]);  
```  
  
 <span data-ttu-id="5e02b-113">**Relacja** danych ma również **zagnieżdżoną** właściwość, która po ustawieniu na **wartość true**powoduje, że wiersze z tabeli podrzędnej będą zagnieżdżone w skojarzonym wierszu z tabeli nadrzędnej, gdy są zapisywane jako elementy XML przy użyciu <xref:System.Data.DataSet.WriteXml%2A> .</span><span class="sxs-lookup"><span data-stu-id="5e02b-113">A **DataRelation** also has a **Nested** property which, when set to **true**, causes the rows from the child table to be nested within the associated row from the parent table when written as XML elements using <xref:System.Data.DataSet.WriteXml%2A> .</span></span> <span data-ttu-id="5e02b-114">Aby uzyskać więcej informacji, zobacz [Używanie języka XML w zestawie danych](using-xml-in-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="5e02b-114">For more information, see [Using XML in a DataSet](using-xml-in-a-dataset.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e02b-115">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="5e02b-115">See also</span></span>

- [<span data-ttu-id="5e02b-116">Elementy DataSet, DataTable i DataView</span><span class="sxs-lookup"><span data-stu-id="5e02b-116">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="5e02b-117">Omówienie ADO.NET</span><span class="sxs-lookup"><span data-stu-id="5e02b-117">ADO.NET Overview</span></span>](../ado-net-overview.md)
