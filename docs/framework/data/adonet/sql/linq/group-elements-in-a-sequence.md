---
title: Grupowanie elementów w sekwencji
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1d50c8b4-f550-4775-bbb6-eab6e874cb43
ms.openlocfilehash: d11d6f6231c1871cd54f0b0e3f6f862dc10b328b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91194349"
---
# <a name="group-elements-in-a-sequence"></a><span data-ttu-id="378d9-102">Grupowanie elementów w sekwencji</span><span class="sxs-lookup"><span data-stu-id="378d9-102">Group Elements in a Sequence</span></span>

<span data-ttu-id="378d9-103"><xref:System.Linq.Enumerable.GroupBy%2A>Operator Grupuje elementy sekwencji.</span><span class="sxs-lookup"><span data-stu-id="378d9-103">The <xref:System.Linq.Enumerable.GroupBy%2A> operator groups the elements of a sequence.</span></span> <span data-ttu-id="378d9-104">W poniższych przykładach użyto bazy danych Northwind.</span><span class="sxs-lookup"><span data-stu-id="378d9-104">The following examples use the Northwind database.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="378d9-105">Wartości pustej kolumny w <xref:System.Linq.Enumerable.GroupBy%2A> zapytaniach mogą czasami zgłosić <xref:System.InvalidOperationException> .</span><span class="sxs-lookup"><span data-stu-id="378d9-105">Null column values in <xref:System.Linq.Enumerable.GroupBy%2A> queries can sometimes throw an <xref:System.InvalidOperationException>.</span></span> <span data-ttu-id="378d9-106">Aby uzyskać więcej informacji, zobacz sekcję "GroupBy InvalidOperationException" w temacie [Rozwiązywanie problemów](troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="378d9-106">For more information, see the "GroupBy InvalidOperationException" section of [Troubleshooting](troubleshooting.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="378d9-107">Przykład</span><span class="sxs-lookup"><span data-stu-id="378d9-107">Example</span></span>  

 <span data-ttu-id="378d9-108">Poniższy przykład partycjonowania `Products` przez `CategoryID` .</span><span class="sxs-lookup"><span data-stu-id="378d9-108">The following example partitions `Products` by `CategoryID`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#27](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#27)]
 [!code-vb[DLinqQueryExamples#27](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#27)]  
  
## <a name="example"></a><span data-ttu-id="378d9-109">Przykład</span><span class="sxs-lookup"><span data-stu-id="378d9-109">Example</span></span>  

 <span data-ttu-id="378d9-110">Poniższy przykład używa, <xref:System.Linq.Enumerable.Max%2A> Aby znaleźć maksymalną cenę jednostkową dla każdej z nich `CategoryID` .</span><span class="sxs-lookup"><span data-stu-id="378d9-110">The following example uses <xref:System.Linq.Enumerable.Max%2A> to find the maximum unit price for each `CategoryID`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#28](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#28)]
 [!code-vb[DLinqQueryExamples#28](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#28)]  
  
## <a name="example"></a><span data-ttu-id="378d9-111">Przykład</span><span class="sxs-lookup"><span data-stu-id="378d9-111">Example</span></span>  

 <span data-ttu-id="378d9-112">W poniższym przykładzie zastosowano średnią, aby znaleźć średnią `UnitPrice` dla każdej z nich `CategoryID` .</span><span class="sxs-lookup"><span data-stu-id="378d9-112">The following example uses Average to find the average `UnitPrice` for each `CategoryID`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#29](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#29)]
 [!code-vb[DLinqQueryExamples#29](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#29)]  
  
## <a name="example"></a><span data-ttu-id="378d9-113">Przykład</span><span class="sxs-lookup"><span data-stu-id="378d9-113">Example</span></span>  

 <span data-ttu-id="378d9-114">Poniższy przykład używa, <xref:System.Linq.Queryable.Sum%2A> Aby znaleźć sumę `UnitPrice` dla każdej z nich `CategoryID` .</span><span class="sxs-lookup"><span data-stu-id="378d9-114">The following example uses <xref:System.Linq.Queryable.Sum%2A> to find the total `UnitPrice` for each `CategoryID`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#30](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#30)]
 [!code-vb[DLinqQueryExamples#30](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#30)]  
  
## <a name="example"></a><span data-ttu-id="378d9-115">Przykład</span><span class="sxs-lookup"><span data-stu-id="378d9-115">Example</span></span>  

 <span data-ttu-id="378d9-116">Poniższy przykład używa, <xref:System.Linq.Queryable.Count%2A> Aby znaleźć liczbę wycofanych `Products` w każdym z nich `CategoryID` .</span><span class="sxs-lookup"><span data-stu-id="378d9-116">The following example uses <xref:System.Linq.Queryable.Count%2A> to find the number of discontinued `Products` in each `CategoryID`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#31](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#31)]
 [!code-vb[DLinqQueryExamples#31](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#31)]  
  
## <a name="example"></a><span data-ttu-id="378d9-117">Przykład</span><span class="sxs-lookup"><span data-stu-id="378d9-117">Example</span></span>  

 <span data-ttu-id="378d9-118">W poniższym przykładzie zastosowano następującą `where` klauzulę, aby znaleźć wszystkie kategorie, które mają co najmniej 10 produktów.</span><span class="sxs-lookup"><span data-stu-id="378d9-118">The following example uses a following `where` clause to find all categories that have at least 10 products.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#32](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#32)]
 [!code-vb[DLinqQueryExamples#32](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#32)]  
  
## <a name="example"></a><span data-ttu-id="378d9-119">Przykład</span><span class="sxs-lookup"><span data-stu-id="378d9-119">Example</span></span>  

 <span data-ttu-id="378d9-120">Poniższy przykład grupuje produkty według `CategoryID` i `SupplierID` .</span><span class="sxs-lookup"><span data-stu-id="378d9-120">The following example groups products by `CategoryID` and `SupplierID`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#33](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#33)]
 [!code-vb[DLinqQueryExamples#33](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#33)]  
  
## <a name="example"></a><span data-ttu-id="378d9-121">Przykład</span><span class="sxs-lookup"><span data-stu-id="378d9-121">Example</span></span>  

 <span data-ttu-id="378d9-122">Poniższy przykład zwraca dwie sekwencje produktów.</span><span class="sxs-lookup"><span data-stu-id="378d9-122">The following example returns two sequences of products.</span></span> <span data-ttu-id="378d9-123">Pierwsza sekwencja zawiera produkty z ceną jednostkową mniejszą lub równą 10.</span><span class="sxs-lookup"><span data-stu-id="378d9-123">The first sequence contains products with unit price less than or equal to 10.</span></span> <span data-ttu-id="378d9-124">Druga sekwencja zawiera produkty z ceną jednostkową większą niż 10.</span><span class="sxs-lookup"><span data-stu-id="378d9-124">The second sequence contains products with unit price greater than 10.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#34](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#34)]
 [!code-vb[DLinqQueryExamples#34](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#34)]  
  
## <a name="example"></a><span data-ttu-id="378d9-125">Przykład</span><span class="sxs-lookup"><span data-stu-id="378d9-125">Example</span></span>  

 <span data-ttu-id="378d9-126"><xref:System.Linq.Queryable.GroupBy%2A>Operator może przyjmować tylko jeden argument klucza.</span><span class="sxs-lookup"><span data-stu-id="378d9-126">The <xref:System.Linq.Queryable.GroupBy%2A> operator can take only a single key argument.</span></span> <span data-ttu-id="378d9-127">Jeśli zachodzi potrzeba pogrupowania przez więcej niż jeden klucz, należy utworzyć typ anonimowy, jak w poniższym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="378d9-127">If you need to group by more than one key, you must create an anonymous type, as in the following example:</span></span>  
  
 [!code-csharp[DLinqQueryExamples#35](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#35)]
 [!code-vb[DLinqQueryExamples#35](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#35)]  
  
## <a name="see-also"></a><span data-ttu-id="378d9-128">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="378d9-128">See also</span></span>

- [<span data-ttu-id="378d9-129">Przykłady zapytań</span><span class="sxs-lookup"><span data-stu-id="378d9-129">Query Examples</span></span>](query-examples.md)
- [<span data-ttu-id="378d9-130">Pobieranie przykładowych baz danych</span><span class="sxs-lookup"><span data-stu-id="378d9-130">Downloading Sample Databases</span></span>](downloading-sample-databases.md)
