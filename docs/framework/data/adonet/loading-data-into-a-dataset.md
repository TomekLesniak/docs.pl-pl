---
title: Ładowanie danych do zestawu danych
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a53e5dc1-9669-49d4-828d-efa633237066
ms.openlocfilehash: c870cabc875aa0152910ce916819fb1ff1c018f7
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166719"
---
# <a name="loading-data-into-a-dataset"></a><span data-ttu-id="0e303-102">Ładowanie danych do zestawu danych</span><span class="sxs-lookup"><span data-stu-id="0e303-102">Loading Data Into a DataSet</span></span>

<span data-ttu-id="0e303-103"><xref:System.Data.DataSet>Aby można było wykonać zapytanie dotyczące obiektu przy użyciu LINQ to DataSet, należy najpierw wypełnić obiekt.</span><span class="sxs-lookup"><span data-stu-id="0e303-103">A <xref:System.Data.DataSet> object must first be populated before you can query over it with LINQ to DataSet.</span></span> <span data-ttu-id="0e303-104">Istnieje kilka różnych sposobów wypełnienia <xref:System.Data.DataSet> .</span><span class="sxs-lookup"><span data-stu-id="0e303-104">There are several different ways to populate the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="0e303-105">Na przykład można użyć [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] programu do wysyłania zapytań do bazy danych i załadowania wyników do <xref:System.Data.DataSet> .</span><span class="sxs-lookup"><span data-stu-id="0e303-105">For example, you can use [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] to query the database and load the results into the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="0e303-106">Aby uzyskać więcej informacji, zobacz [LINQ to SQL](./sql/linq/index.md).</span><span class="sxs-lookup"><span data-stu-id="0e303-106">For more information, see [LINQ to SQL](./sql/linq/index.md).</span></span>  
  
 <span data-ttu-id="0e303-107">Innym typowym sposobem ładowania danych do programu <xref:System.Data.DataSet> jest użycie <xref:System.Data.Common.DataAdapter> klasy do pobierania danych z bazy danych.</span><span class="sxs-lookup"><span data-stu-id="0e303-107">Another common way to load data into a <xref:System.Data.DataSet> is to use the <xref:System.Data.Common.DataAdapter> class to retrieve data from the database.</span></span> <span data-ttu-id="0e303-108">Jest to zilustrowane w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="0e303-108">This is illustrated in the following example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0e303-109">Przykład</span><span class="sxs-lookup"><span data-stu-id="0e303-109">Example</span></span>  

 <span data-ttu-id="0e303-110">W tym przykładzie używa <xref:System.Data.Common.DataAdapter> się do wysyłania zapytań do bazy danych AdventureWorks o informacje o sprzedaży z roku 2002 i ładowania wyników do programu <xref:System.Data.DataSet> .</span><span class="sxs-lookup"><span data-stu-id="0e303-110">This example uses a <xref:System.Data.Common.DataAdapter> to query the AdventureWorks database for sales information from the year 2002, and loads the results into a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="0e303-111">Po wypełnieniu <xref:System.Data.DataSet> można napisać zapytania do niego przy użyciu LINQ to DataSet.</span><span class="sxs-lookup"><span data-stu-id="0e303-111">After the <xref:System.Data.DataSet> has been populated, you can write queries against it by using LINQ to DataSet.</span></span> <span data-ttu-id="0e303-112">`FillDataSet`Metoda w tym przykładzie jest używana w przykładowych kwerendach [LINQ to DataSet przykładów](linq-to-dataset-examples.md).</span><span class="sxs-lookup"><span data-stu-id="0e303-112">The `FillDataSet` method in this example is used in the example queries in [LINQ to DataSet Examples](linq-to-dataset-examples.md).</span></span> <span data-ttu-id="0e303-113">Aby uzyskać więcej informacji, zobacz [wykonywanie zapytania dotyczącego zestawów danych](querying-datasets-linq-to-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="0e303-113">For more information, see [Querying DataSets](querying-datasets-linq-to-dataset.md).</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#FillDataSet](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#filldataset)]
 [!code-vb[DP LINQ to DataSet Examples#FillDataSet](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#filldataset)]  
  
## <a name="see-also"></a><span data-ttu-id="0e303-114">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="0e303-114">See also</span></span>

- [<span data-ttu-id="0e303-115">Omówienie LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="0e303-115">LINQ to DataSet Overview</span></span>](linq-to-dataset-overview.md)
- [<span data-ttu-id="0e303-116">Wykonywanie zapytania do zestawów danych</span><span class="sxs-lookup"><span data-stu-id="0e303-116">Querying DataSets</span></span>](querying-datasets-linq-to-dataset.md)
- [<span data-ttu-id="0e303-117">Przykłady LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="0e303-117">LINQ to DataSet Examples</span></span>](linq-to-dataset-examples.md)
