---
title: Distinct, klauzula
ms.date: 07/20/2015
f1_keywords:
- vb.QueryDistinct
helpviewer_keywords:
- Distinct clause [Visual Basic]
- Distinct statement [Visual Basic]
- queries [Visual Basic], Distinct
ms.assetid: 86f42614-0d8f-4ffc-b888-ce8a37a8d36a
ms.openlocfilehash: 49eaab2e6a8c48d61518ea51ef2f644b6eb48314
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90875277"
---
# <a name="distinct-clause-visual-basic"></a><span data-ttu-id="4540a-102">Distinct — Klauzula (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4540a-102">Distinct Clause (Visual Basic)</span></span>

<span data-ttu-id="4540a-103">Ogranicza wartości bieżącej zmiennej zakresu w celu wyeliminowania zduplikowanych wartości w kolejnych klauzulach zapytania.</span><span class="sxs-lookup"><span data-stu-id="4540a-103">Restricts the values of the current range variable to eliminate duplicate values in subsequent query clauses.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4540a-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="4540a-104">Syntax</span></span>  
  
```vb  
Distinct  
```  
  
## <a name="remarks"></a><span data-ttu-id="4540a-105">Uwagi</span><span class="sxs-lookup"><span data-stu-id="4540a-105">Remarks</span></span>  

 <span data-ttu-id="4540a-106">Możesz użyć klauzuli, `Distinct` Aby zwrócić listę unikatowych elementów.</span><span class="sxs-lookup"><span data-stu-id="4540a-106">You can use the `Distinct` clause to return a list of unique items.</span></span> <span data-ttu-id="4540a-107">`Distinct`Klauzula powoduje, że zapytanie ignoruje zduplikowane wyniki zapytania.</span><span class="sxs-lookup"><span data-stu-id="4540a-107">The `Distinct` clause causes the query to ignore duplicate query results.</span></span> <span data-ttu-id="4540a-108">`Distinct`Klauzula ma zastosowanie do zduplikowanych wartości dla wszystkich zwracanych pól określonych przez `Select` klauzulę.</span><span class="sxs-lookup"><span data-stu-id="4540a-108">The `Distinct` clause applies to duplicate values for all return fields specified by the `Select` clause.</span></span> <span data-ttu-id="4540a-109">Jeśli `Select` klauzula nie jest określona, `Distinct` klauzula jest stosowana do zmiennej zakresu dla zapytania określonego w `From` klauzuli.</span><span class="sxs-lookup"><span data-stu-id="4540a-109">If no `Select` clause is specified, the `Distinct` clause is applied to the range variable for the query identified in the `From` clause.</span></span> <span data-ttu-id="4540a-110">Jeśli zmienna zakresu nie jest niezmiennym typem, zapytanie zignoruje tylko wynik zapytania, jeśli wszystkie elementy członkowskie tego typu pasują do istniejącego wyniku zapytania.</span><span class="sxs-lookup"><span data-stu-id="4540a-110">If the range variable is not an immutable type, the query will only ignore a query result if all members of the type match an existing query result.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4540a-111">Przykład</span><span class="sxs-lookup"><span data-stu-id="4540a-111">Example</span></span>  

 <span data-ttu-id="4540a-112">Poniższe wyrażenie zapytania dołącza listę klientów i listę zamówień klientów.</span><span class="sxs-lookup"><span data-stu-id="4540a-112">The following query expression joins a list of customers and a list of customer orders.</span></span> <span data-ttu-id="4540a-113">`Distinct`Klauzula jest uwzględniona w celu zwrócenia listy unikatowych nazw klientów i dat kolejności.</span><span class="sxs-lookup"><span data-stu-id="4540a-113">The `Distinct` clause is included to return a list of unique customer names and order dates.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#20)]  
  
## <a name="see-also"></a><span data-ttu-id="4540a-114">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="4540a-114">See also</span></span>

- [<span data-ttu-id="4540a-115">Wprowadzenie do LINQ w Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4540a-115">Introduction to LINQ in Visual Basic</span></span>](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="4540a-116">Zapytania</span><span class="sxs-lookup"><span data-stu-id="4540a-116">Queries</span></span>](index.md)
- [<span data-ttu-id="4540a-117">Klauzula from</span><span class="sxs-lookup"><span data-stu-id="4540a-117">From Clause</span></span>](from-clause.md)
- [<span data-ttu-id="4540a-118">SELECT — klauzula</span><span class="sxs-lookup"><span data-stu-id="4540a-118">Select Clause</span></span>](select-clause.md)
- [<span data-ttu-id="4540a-119">Klauzula WHERE</span><span class="sxs-lookup"><span data-stu-id="4540a-119">Where Clause</span></span>](where-clause.md)
