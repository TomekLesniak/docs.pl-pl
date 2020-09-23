---
title: Partycjonowanie danych
ms.date: 07/20/2015
ms.assetid: 69c59379-b66e-422c-b324-5b5c07760ef7
ms.openlocfilehash: 07e33c4ce0d062a0f083d8970c0ad01f98923a52
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91075320"
---
# <a name="partitioning-data-visual-basic"></a><span data-ttu-id="1fc99-102">Partycjonowanie danych (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1fc99-102">Partitioning Data (Visual Basic)</span></span>

<span data-ttu-id="1fc99-103">Partycjonowanie w LINQ odwołuje się do operacji dzielenia sekwencji wejściowej na dwie sekcje, bez konieczności ponownej rozmieszczania elementów, a następnie zwrócenia jednej z sekcji.</span><span class="sxs-lookup"><span data-stu-id="1fc99-103">Partitioning in LINQ refers to the operation of dividing an input sequence into two sections, without rearranging the elements, and then returning one of the sections.</span></span>  
  
 <span data-ttu-id="1fc99-104">Na poniższej ilustracji przedstawiono wyniki trzech różnych operacji partycjonowania na sekwencji znaków.</span><span class="sxs-lookup"><span data-stu-id="1fc99-104">The following illustration shows the results of three different partitioning operations on a sequence of characters.</span></span> <span data-ttu-id="1fc99-105">Pierwsza operacja zwraca trzy pierwsze elementy w sekwencji.</span><span class="sxs-lookup"><span data-stu-id="1fc99-105">The first operation returns the first three elements in the sequence.</span></span> <span data-ttu-id="1fc99-106">Druga operacja pomija pierwsze trzy elementy i zwraca pozostałe elementy.</span><span class="sxs-lookup"><span data-stu-id="1fc99-106">The second operation skips the first three elements and returns the remaining elements.</span></span> <span data-ttu-id="1fc99-107">Trzecia operacja pomija pierwsze dwa elementy w sekwencji i zwraca następne trzy elementy.</span><span class="sxs-lookup"><span data-stu-id="1fc99-107">The third operation skips the first two elements in the sequence and returns the next three elements.</span></span>  
  
 ![Ilustracja przedstawiająca trzy operacje partycjonowania LINQ.](./media/partitioning-data/linq-partitioning-operations.png)  
  
 <span data-ttu-id="1fc99-109">Standardowe metody operatorów zapytań, które są sekwencje partycji, są wymienione w poniższej sekcji.</span><span class="sxs-lookup"><span data-stu-id="1fc99-109">The standard query operator methods that partition sequences are listed in the following section.</span></span>  
  
## <a name="operators"></a><span data-ttu-id="1fc99-110">Operatory</span><span class="sxs-lookup"><span data-stu-id="1fc99-110">Operators</span></span>  
  
|<span data-ttu-id="1fc99-111">Nazwa operatora</span><span class="sxs-lookup"><span data-stu-id="1fc99-111">Operator Name</span></span>|<span data-ttu-id="1fc99-112">Opis</span><span class="sxs-lookup"><span data-stu-id="1fc99-112">Description</span></span>|<span data-ttu-id="1fc99-113">Składnia wyrażenia zapytania Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1fc99-113">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="1fc99-114">Więcej informacji</span><span class="sxs-lookup"><span data-stu-id="1fc99-114">More Information</span></span>|  
|-------------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="1fc99-115">Pomiń</span><span class="sxs-lookup"><span data-stu-id="1fc99-115">Skip</span></span>|<span data-ttu-id="1fc99-116">Pomija elementy do określonej pozycji w sekwencji.</span><span class="sxs-lookup"><span data-stu-id="1fc99-116">Skips elements up to a specified position in a sequence.</span></span>|`Skip`|<xref:System.Linq.Enumerable.Skip%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Skip%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="1fc99-117">SkipWhile —</span><span class="sxs-lookup"><span data-stu-id="1fc99-117">SkipWhile</span></span>|<span data-ttu-id="1fc99-118">Pomija elementy na podstawie funkcji predykatu, dopóki element nie spełnia warunku.</span><span class="sxs-lookup"><span data-stu-id="1fc99-118">Skips elements based on a predicate function until an element does not satisfy the condition.</span></span>|`Skip While`|<xref:System.Linq.Enumerable.SkipWhile%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.SkipWhile%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="1fc99-119">Take</span><span class="sxs-lookup"><span data-stu-id="1fc99-119">Take</span></span>|<span data-ttu-id="1fc99-120">Pobiera elementy do określonej pozycji w sekwencji.</span><span class="sxs-lookup"><span data-stu-id="1fc99-120">Takes elements up to a specified position in a sequence.</span></span>|`Take`|<xref:System.Linq.Enumerable.Take%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Take%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="1fc99-121">TakeWhile —</span><span class="sxs-lookup"><span data-stu-id="1fc99-121">TakeWhile</span></span>|<span data-ttu-id="1fc99-122">Pobiera elementy na podstawie funkcji predykatu, dopóki element nie spełnia warunku.</span><span class="sxs-lookup"><span data-stu-id="1fc99-122">Takes elements based on a predicate function until an element does not satisfy the condition.</span></span>|`Take While`|<xref:System.Linq.Enumerable.TakeWhile%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.TakeWhile%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="1fc99-123">Przykłady składni wyrażeń zapytania</span><span class="sxs-lookup"><span data-stu-id="1fc99-123">Query Expression Syntax Examples</span></span>  
  
### <a name="skip"></a><span data-ttu-id="1fc99-124">Pomiń</span><span class="sxs-lookup"><span data-stu-id="1fc99-124">Skip</span></span>  

 <span data-ttu-id="1fc99-125">Poniższy przykład kodu używa `Skip` klauzuli w Visual Basic, aby pominąć pierwsze cztery ciągi w tablicy ciągów przed zwróceniem pozostałych ciągów w tablicy.</span><span class="sxs-lookup"><span data-stu-id="1fc99-125">The following code example uses the `Skip` clause in Visual Basic to skip over the first four strings in an array of strings before returning the remaining strings in the array.</span></span>  
  
 [!code-vb[CsLINQPartitioning#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQPartitioning/VB/Partitioning.vb#1)]  
  
### <a name="skipwhile"></a><span data-ttu-id="1fc99-126">SkipWhile —</span><span class="sxs-lookup"><span data-stu-id="1fc99-126">SkipWhile</span></span>  

 <span data-ttu-id="1fc99-127">Poniższy przykład kodu używa `Skip While` klauzuli w Visual Basic, aby pominąć ciągi w tablicy, podczas gdy pierwsza litera ciągu ma wartość "a".</span><span class="sxs-lookup"><span data-stu-id="1fc99-127">The following code example uses the `Skip While` clause in Visual Basic to skip over the strings in an array while the first letter of the string is "a".</span></span> <span data-ttu-id="1fc99-128">Zwracane są pozostałe ciągi w tablicy.</span><span class="sxs-lookup"><span data-stu-id="1fc99-128">The remaining strings in the array are returned.</span></span>  
  
 [!code-vb[CsLINQPartitioning#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQPartitioning/VB/Partitioning.vb#2)]  
  
### <a name="take"></a><span data-ttu-id="1fc99-129">Take</span><span class="sxs-lookup"><span data-stu-id="1fc99-129">Take</span></span>  

 <span data-ttu-id="1fc99-130">Poniższy przykład kodu używa `Take` klauzuli w Visual Basic, aby zwrócić pierwsze dwa ciągi w tablicy ciągów.</span><span class="sxs-lookup"><span data-stu-id="1fc99-130">The following code example uses the `Take` clause in Visual Basic to return the first two strings in an array of strings.</span></span>  
  
 [!code-vb[CsLINQPartitioning#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQPartitioning/VB/Partitioning.vb#3)]  
  
### <a name="takewhile"></a><span data-ttu-id="1fc99-131">TakeWhile —</span><span class="sxs-lookup"><span data-stu-id="1fc99-131">TakeWhile</span></span>  

 <span data-ttu-id="1fc99-132">Poniższy przykład kodu używa `Take While` klauzuli w Visual Basic, aby zwrócić ciągi z tablicy, gdy długość ciągu jest pięć lub mniej.</span><span class="sxs-lookup"><span data-stu-id="1fc99-132">The following code example uses the `Take While` clause in Visual Basic to return strings from an array while the length of the string is five or less.</span></span>  
  
 [!code-vb[CsLINQPartitioning#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQPartitioning/VB/Partitioning.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="1fc99-133">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="1fc99-133">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="1fc99-134">Standardowe operatory zapytań — Omówienie (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1fc99-134">Standard Query Operators Overview (Visual Basic)</span></span>](standard-query-operators-overview.md)
- [<span data-ttu-id="1fc99-135">Skip, klauzula</span><span class="sxs-lookup"><span data-stu-id="1fc99-135">Skip Clause</span></span>](../../../language-reference/queries/skip-clause.md)
- [<span data-ttu-id="1fc99-136">Skip While, klauzula</span><span class="sxs-lookup"><span data-stu-id="1fc99-136">Skip While Clause</span></span>](../../../language-reference/queries/skip-while-clause.md)
- [<span data-ttu-id="1fc99-137">Take, klauzula</span><span class="sxs-lookup"><span data-stu-id="1fc99-137">Take Clause</span></span>](../../../language-reference/queries/take-clause.md)
- [<span data-ttu-id="1fc99-138">Take While, klauzula</span><span class="sxs-lookup"><span data-stu-id="1fc99-138">Take While Clause</span></span>](../../../language-reference/queries/take-while-clause.md)
