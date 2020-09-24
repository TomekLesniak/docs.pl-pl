---
title: Przewodnik programowania (LINQ to DataSet)
ms.date: 03/30/2017
ms.assetid: 977aedd7-0084-46a0-b56f-345787a55da1
ms.openlocfilehash: 720d9a90583a0dcf3453689a362f6043157a326c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91161562"
---
# <a name="programming-guide-linq-to-dataset"></a><span data-ttu-id="cf41c-102">Przewodnik programowania (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="cf41c-102">Programming Guide (LINQ to DataSet)</span></span>

<span data-ttu-id="cf41c-103">Ta sekcja zawiera informacje o pojęciach i przykłady dotyczące programowania w programie LINQ to DataSet.</span><span class="sxs-lookup"><span data-stu-id="cf41c-103">This section provides conceptual information and examples for programming with LINQ to DataSet.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cf41c-104">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="cf41c-104">In This Section</span></span>  

 [<span data-ttu-id="cf41c-105">Zapytania w LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="cf41c-105">Queries in LINQ to DataSet</span></span>](queries-in-linq-to-dataset.md)  
 <span data-ttu-id="cf41c-106">Zawiera informacje o sposobach pisania zapytań LINQ to DataSet.</span><span class="sxs-lookup"><span data-stu-id="cf41c-106">Provides information about how to write LINQ to DataSet queries.</span></span>  
  
 [<span data-ttu-id="cf41c-107">Wykonywanie zapytania do zestawów danych</span><span class="sxs-lookup"><span data-stu-id="cf41c-107">Querying DataSets</span></span>](querying-datasets-linq-to-dataset.md)  
 <span data-ttu-id="cf41c-108">Opisuje sposób wykonywania zapytań względem <xref:System.Data.DataSet> obiektów.</span><span class="sxs-lookup"><span data-stu-id="cf41c-108">Describes how to query <xref:System.Data.DataSet> objects.</span></span>  
  
 [<span data-ttu-id="cf41c-109">Porównywanie wierszy danych</span><span class="sxs-lookup"><span data-stu-id="cf41c-109">Comparing DataRows</span></span>](comparing-datarows-linq-to-dataset.md)  
 <span data-ttu-id="cf41c-110">Opisuje, jak używać <xref:System.Data.DataRowComparer> obiektu do porównywania wierszy danych.</span><span class="sxs-lookup"><span data-stu-id="cf41c-110">Describes how to use the <xref:System.Data.DataRowComparer> object to compare data rows.</span></span>  
  
 [<span data-ttu-id="cf41c-111">Tworzenie elementu DataTable na podstawie zapytania</span><span class="sxs-lookup"><span data-stu-id="cf41c-111">Creating a DataTable From a Query</span></span>](creating-a-datatable-from-a-query-linq-to-dataset.md)  
 <span data-ttu-id="cf41c-112">Zawiera informacje dotyczące tworzenia <xref:System.Data.DataTable> z kwerendy LINQ to DataSet przy użyciu <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> metody.</span><span class="sxs-lookup"><span data-stu-id="cf41c-112">Provides information about creating a <xref:System.Data.DataTable> from a LINQ to DataSet query by using the <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> method.</span></span>  
  
 [<span data-ttu-id="cf41c-113">Instrukcje: implementowanie CopyToDataTable \<T> , gdzie typ ogólny T nie jest typem DataRow</span><span class="sxs-lookup"><span data-stu-id="cf41c-113">How to: Implement CopyToDataTable\<T> Where the Generic Type T Is Not a DataRow</span></span>](implement-copytodatatable-where-type-not-a-datarow.md)  
 <span data-ttu-id="cf41c-114">Opisuje, jak zaimplementować metodę niestandardową `CopyToDataTable<T>` , w której parametr generyczny T nie jest typu <xref:System.Data.DataRow> .</span><span class="sxs-lookup"><span data-stu-id="cf41c-114">Describes how to implement a custom `CopyToDataTable<T>` method where the generic parameter T is not of type <xref:System.Data.DataRow>.</span></span>  
  
 [<span data-ttu-id="cf41c-115">Field i SetField, metody ogólne</span><span class="sxs-lookup"><span data-stu-id="cf41c-115">Generic Field and SetField Methods</span></span>](generic-field-and-setfield-methods-linq-to-dataset.md)  
 <span data-ttu-id="cf41c-116">Zawiera informacje o <xref:System.Data.DataRowExtensions.Field%2A> <xref:System.Data.DataRowExtensions.SetField%2A> metodach ogólnych i.</span><span class="sxs-lookup"><span data-stu-id="cf41c-116">Provides information about the generic <xref:System.Data.DataRowExtensions.Field%2A> and <xref:System.Data.DataRowExtensions.SetField%2A> methods.</span></span>  
  
 [<span data-ttu-id="cf41c-117">Powiązanie danych i LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="cf41c-117">Data Binding and LINQ to DataSet</span></span>](data-binding-and-linq-to-dataset.md)  
 <span data-ttu-id="cf41c-118">Opisuje powiązanie danych przy użyciu <xref:System.Data.DataView> obiektu.</span><span class="sxs-lookup"><span data-stu-id="cf41c-118">Describes databinding using the <xref:System.Data.DataView> object.</span></span>  
  
 [<span data-ttu-id="cf41c-119">Debugowanie zapytań LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="cf41c-119">Debugging LINQ to DataSet Queries</span></span>](debugging-linq-to-dataset-queries.md)  
 <span data-ttu-id="cf41c-120">Zawiera informacje dotyczące debugowania i rozwiązywania problemów LINQ to DataSet zapytań.</span><span class="sxs-lookup"><span data-stu-id="cf41c-120">Provides information about debugging and troubleshooting LINQ to DataSet queries.</span></span>  
  
 [<span data-ttu-id="cf41c-121">Zabezpieczenia</span><span class="sxs-lookup"><span data-stu-id="cf41c-121">Security</span></span>](security-linq-to-dataset.md)  
 <span data-ttu-id="cf41c-122">Opisuje problemy z zabezpieczeniami w LINQ to DataSet.</span><span class="sxs-lookup"><span data-stu-id="cf41c-122">Describes security issues in LINQ to DataSet.</span></span>  
  
 [<span data-ttu-id="cf41c-123">Przykłady LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="cf41c-123">LINQ to DataSet Examples</span></span>](linq-to-dataset-examples.md)  
 <span data-ttu-id="cf41c-124">Zawiera przykłady zapytań, które używają operatorów LINQ.</span><span class="sxs-lookup"><span data-stu-id="cf41c-124">Provides query examples that use the LINQ operators.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="cf41c-125">Tematy pomocy</span><span class="sxs-lookup"><span data-stu-id="cf41c-125">Reference</span></span>  

 <xref:System.Data.DataRowComparer>  
  
 <xref:System.Data.DataRowExtensions>  
  
 <xref:System.Data.DataTableExtensions>  
  
 <xref:System.Data.DataView>  
  
## <a name="see-also"></a><span data-ttu-id="cf41c-126">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="cf41c-126">See also</span></span>

- [<span data-ttu-id="cf41c-127">LINQ i ADO.NET</span><span class="sxs-lookup"><span data-stu-id="cf41c-127">LINQ and ADO.NET</span></span>](linq-and-ado-net.md)
- [<span data-ttu-id="cf41c-128">Language Integrated Query (LINQ)</span><span class="sxs-lookup"><span data-stu-id="cf41c-128">Language Integrated Query (LINQ)</span></span>](../../../csharp/programming-guide/concepts/linq/index.md)
