---
title: Formułowanie połączeń i zapytań między produktami
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d8072ede-0521-4670-9bec-1778ceeb875b
ms.openlocfilehash: 1527ad26524dbef3ac73b92e136cd22e33046483
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91155890"
---
# <a name="formulate-joins-and-cross-product-queries"></a><span data-ttu-id="172d1-102">Formułowanie połączeń i zapytań między produktami</span><span class="sxs-lookup"><span data-stu-id="172d1-102">Formulate Joins and Cross-Product Queries</span></span>

<span data-ttu-id="172d1-103">W poniższych przykładach pokazano, jak połączyć wyniki z wielu tabel.</span><span class="sxs-lookup"><span data-stu-id="172d1-103">The following examples show how to combine results from multiple tables.</span></span>  
  
## <a name="example"></a><span data-ttu-id="172d1-104">Przykład</span><span class="sxs-lookup"><span data-stu-id="172d1-104">Example</span></span>  

 <span data-ttu-id="172d1-105">Poniższy przykład używa nawigacji klucza obcego w `From` klauzuli w Visual Basic ( `from` klauzula w języku C#), aby wybrać wszystkie zamówienia dla klientów w Londynie.</span><span class="sxs-lookup"><span data-stu-id="172d1-105">The following example uses foreign key navigation in the `From` clause in Visual Basic (`from` clause in C#) to select all orders for customers in London.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#47](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#47)]
 [!code-vb[DLinqQueryExamples#47](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#47)]  
  
## <a name="example"></a><span data-ttu-id="172d1-106">Przykład</span><span class="sxs-lookup"><span data-stu-id="172d1-106">Example</span></span>  

 <span data-ttu-id="172d1-107">W poniższym przykładzie jest używana Nawigacja klucza obcego w `Where` klauzuli w Visual Basic ( `where` klauzula w języku C#), aby odfiltrować elementy poza magazynem `Products` `Supplier` , których wartość znajduje się w Stany Zjednoczone.</span><span class="sxs-lookup"><span data-stu-id="172d1-107">The following example uses foreign key navigation in the `Where` clause in Visual Basic (`where` clause in C#) to filter for out-of-stock `Products` whose `Supplier` is in the United States.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#48](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#48)]
 [!code-vb[DLinqQueryExamples#48](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#48)]  
  
## <a name="example"></a><span data-ttu-id="172d1-108">Przykład</span><span class="sxs-lookup"><span data-stu-id="172d1-108">Example</span></span>  

 <span data-ttu-id="172d1-109">Poniższy przykład używa nawigacji klucza obcego w `From` klauzuli w Visual Basic ( `from` klauzula w języku C#) do filtrowania pracowników w Seattle i wyświetlania ich terytoriów.</span><span class="sxs-lookup"><span data-stu-id="172d1-109">The following example uses foreign key navigation in the `From` clause in Visual Basic (`from` clause in C#) to filter for employees in Seattle and to list their territories.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#49](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#49)]  
  
## <a name="example"></a><span data-ttu-id="172d1-110">Przykład</span><span class="sxs-lookup"><span data-stu-id="172d1-110">Example</span></span>  

 <span data-ttu-id="172d1-111">W poniższym przykładzie jest używana Nawigacja klucza obcego w `Select` klauzuli w Visual Basic ( `select` klauzula w języku C#), aby odfiltrować pary pracowników, w których jeden pracownik zgłosi się do drugiego i gdy obaj pracownicy są z tego samego `City` .</span><span class="sxs-lookup"><span data-stu-id="172d1-111">The following example uses foreign key navigation in the `Select` clause in Visual Basic (`select` clause in C#) to filter for pairs of employees where one employee reports to the other and where both employees are from the same `City`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#50](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#50)]
 [!code-vb[DLinqQueryExamples#50](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#50)]  
  
## <a name="example"></a><span data-ttu-id="172d1-112">Przykład</span><span class="sxs-lookup"><span data-stu-id="172d1-112">Example</span></span>  

 <span data-ttu-id="172d1-113">Poniższy Visual Basic przykład szuka wszystkich klientów i zamówień, upewnia się, że zamówienia są dopasowane do klientów i gwarantuje, że dla każdego klienta na tej liście zostanie podana nazwa kontaktu.</span><span class="sxs-lookup"><span data-stu-id="172d1-113">The following Visual Basic example looks for all customers and orders, makes sure that the orders are matched to customers, and guarantees that for every customer in that list, a contact name is provided.</span></span>  
  
 [!code-vb[DLinqQueryExamples#50v](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#50v)]  
  
## <a name="example"></a><span data-ttu-id="172d1-114">Przykład</span><span class="sxs-lookup"><span data-stu-id="172d1-114">Example</span></span>  

 <span data-ttu-id="172d1-115">Poniższy przykład jawnie łączy dwie tabele i projekty w obu tabelach.</span><span class="sxs-lookup"><span data-stu-id="172d1-115">The following example explicitly joins two tables and projects results from both tables.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#51](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#51)]
 [!code-vb[DLinqQueryExamples#51](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#51)]  
  
## <a name="example"></a><span data-ttu-id="172d1-116">Przykład</span><span class="sxs-lookup"><span data-stu-id="172d1-116">Example</span></span>  

 <span data-ttu-id="172d1-117">Poniższy przykład jawnie sprzęga trzy tabele i projekty z każdego z nich.</span><span class="sxs-lookup"><span data-stu-id="172d1-117">The following example explicitly joins three tables and projects results from each of them.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#52](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#52)]
 [!code-vb[DLinqQueryExamples#52](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#52)]  
  
## <a name="example"></a><span data-ttu-id="172d1-118">Przykład</span><span class="sxs-lookup"><span data-stu-id="172d1-118">Example</span></span>  

 <span data-ttu-id="172d1-119">Poniższy przykład pokazuje, jak osiągnąć za `LEFT OUTER JOIN` pomocą `DefaultIfEmpty()` .</span><span class="sxs-lookup"><span data-stu-id="172d1-119">The following example shows how to achieve a `LEFT OUTER JOIN` by using `DefaultIfEmpty()`.</span></span> <span data-ttu-id="172d1-120">`DefaultIfEmpty()`Metoda zwraca wartość null, jeśli nie ma `Order` dla elementu `Employee` .</span><span class="sxs-lookup"><span data-stu-id="172d1-120">The `DefaultIfEmpty()` method returns null when there is no `Order` for the `Employee`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#53](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#53)]
 [!code-vb[DLinqQueryExamples#53](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#53)]  
  
## <a name="example"></a><span data-ttu-id="172d1-121">Przykład</span><span class="sxs-lookup"><span data-stu-id="172d1-121">Example</span></span>  

 <span data-ttu-id="172d1-122">Poniższy przykład tworzy w projekcie `let` wyrażenie wynikłe z sprzężenia.</span><span class="sxs-lookup"><span data-stu-id="172d1-122">The following example projects a `let` expression resulting from a join.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#54](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#54)]
 [!code-vb[DLinqQueryExamples#54](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#54)]  
  
## <a name="example"></a><span data-ttu-id="172d1-123">Przykład</span><span class="sxs-lookup"><span data-stu-id="172d1-123">Example</span></span>  

 <span data-ttu-id="172d1-124">Poniższy przykład przedstawia `join` z kluczem złożonym.</span><span class="sxs-lookup"><span data-stu-id="172d1-124">The following example shows a `join` with a composite key.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#55](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#55)]
 [!code-vb[DLinqQueryExamples#55](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#55)]  
  
## <a name="example"></a><span data-ttu-id="172d1-125">Przykład</span><span class="sxs-lookup"><span data-stu-id="172d1-125">Example</span></span>  

 <span data-ttu-id="172d1-126">Poniższy przykład pokazuje, jak utworzyć miejsce, `join` gdzie jedna strona ma wartość null, a druga nie.</span><span class="sxs-lookup"><span data-stu-id="172d1-126">The following example shows how to construct a `join` where one side is nullable and the other is not.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#56](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#56)]
 [!code-vb[DLinqQueryExamples#56](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#56)]  
  
## <a name="see-also"></a><span data-ttu-id="172d1-127">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="172d1-127">See also</span></span>

- [<span data-ttu-id="172d1-128">Przykłady zapytań</span><span class="sxs-lookup"><span data-stu-id="172d1-128">Query Examples</span></span>](query-examples.md)
