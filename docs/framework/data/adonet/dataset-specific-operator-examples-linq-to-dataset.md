---
title: Przykłady operatorów specyficznych dla zestawu danych (LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8fdd64af-6ad0-46cd-91c8-dbe26620eeb1
ms.openlocfilehash: 4cd99a103fabee3c87036a9933077a3a967f5a13
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173695"
---
# <a name="dataset-specific-operator-examples-linq-to-dataset"></a><span data-ttu-id="97967-102">Przykłady operatorów specyficznych dla zestawu danych (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="97967-102">DataSet-Specific Operator Examples (LINQ to DataSet)</span></span>

<span data-ttu-id="97967-103">W przykładach w tym temacie pokazano, jak używać <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> metody i <xref:System.Data.DataRowComparer> klasy.</span><span class="sxs-lookup"><span data-stu-id="97967-103">The examples in this topic demonstrate how to use the <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> method and the <xref:System.Data.DataRowComparer> class.</span></span>  
  
 <span data-ttu-id="97967-104">`FillDataSet`Metoda użyta w tych przykładach jest określona w temacie [ładowanie danych do zestawu danych](loading-data-into-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="97967-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="97967-105">W przykładach w tym temacie użyto tabel Contact, Address, Product, SalesOrderHeader i SalesOrderDetail w przykładowej bazie danych AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="97967-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="97967-106">Przykłady w tym temacie wykorzystują następujące `using` / `Imports` instrukcje:</span><span class="sxs-lookup"><span data-stu-id="97967-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="97967-107">Aby uzyskać więcej informacji, zobacz [How to: Create a LINQ to DataSet Project in Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md).</span><span class="sxs-lookup"><span data-stu-id="97967-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="copytodatatable"></a><span data-ttu-id="97967-108">CopyToDataTable</span><span class="sxs-lookup"><span data-stu-id="97967-108">CopyToDataTable</span></span>  
  
### <a name="example"></a><span data-ttu-id="97967-109">Przykład</span><span class="sxs-lookup"><span data-stu-id="97967-109">Example</span></span>  

 <span data-ttu-id="97967-110">Ten przykład ładuje <xref:System.Data.DataTable> wyniki zapytania przy użyciu <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> metody.</span><span class="sxs-lookup"><span data-stu-id="97967-110">This example loads a <xref:System.Data.DataTable> with query results by using the <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> method.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#LoadDataTableWithQueryResults](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#loaddatatablewithqueryresults)]
 [!code-vb[DP LINQ to DataSet Examples#LoadDataTableWithQueryResults](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#loaddatatablewithqueryresults)]  
  
## <a name="datarowcomparer"></a><span data-ttu-id="97967-111">DataRowComparer</span><span class="sxs-lookup"><span data-stu-id="97967-111">DataRowComparer</span></span>  
  
### <a name="example"></a><span data-ttu-id="97967-112">Przykład</span><span class="sxs-lookup"><span data-stu-id="97967-112">Example</span></span>  

 <span data-ttu-id="97967-113">Ten przykład porównuje dwa różne wiersze danych przy użyciu <xref:System.Data.DataRowComparer> .</span><span class="sxs-lookup"><span data-stu-id="97967-113">This example compares two different data rows by using <xref:System.Data.DataRowComparer>.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#CompareDifferentDataRows](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#comparedifferentdatarows)]  
  
## <a name="see-also"></a><span data-ttu-id="97967-114">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="97967-114">See also</span></span>

- [<span data-ttu-id="97967-115">Ładowanie danych do zestawu danych</span><span class="sxs-lookup"><span data-stu-id="97967-115">Loading Data Into a DataSet</span></span>](loading-data-into-a-dataset.md)
- [<span data-ttu-id="97967-116">Przykłady LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="97967-116">LINQ to DataSet Examples</span></span>](linq-to-dataset-examples.md)
