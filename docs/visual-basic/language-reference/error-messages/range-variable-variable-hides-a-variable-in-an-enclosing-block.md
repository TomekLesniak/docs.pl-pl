---
title: Zmienna zakresu „<variable>” ukrywa zmienną w otaczającym bloku, w uprzednio zdefiniowanej zmiennej zakresu lub w niejawnie zadeklarowanej zmiennej w wyrażeniu zapytania
ms.date: 07/20/2015
f1_keywords:
- bc36633
- vbc36633
helpviewer_keywords:
- BC36633
ms.assetid: 5d5470e4-3de5-49c2-8831-1087625f4a77
ms.openlocfilehash: 90fed3dd27f18fe87c326cc36dfb774822fc4b21
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162352"
---
# <a name="bc36633-range-variable-variable-hides-a-variable-in-an-enclosing-block-a-previously-defined-range-variable-or-an-implicitly-declared-variable-in-a-query-expression"></a><span data-ttu-id="1ce8b-102">BC36633: zmienna zakresu \<variable> ukrywa zmienną w otaczającym bloku, w uprzednio zdefiniowanej zmiennej zakresu lub w niejawnie zadeklarowanej zmiennej w wyrażeniu zapytania</span><span class="sxs-lookup"><span data-stu-id="1ce8b-102">BC36633: Range variable \<variable> hides a variable in an enclosing block, a previously defined range variable, or an implicitly declared variable in a query expression</span></span>

<span data-ttu-id="1ce8b-103">Nazwa zmiennej zakresu określona w `Select` `From` klauzuli,, `Aggregate` , lub `Let` duplikuje nazwę zmiennej zakresu, która została już wcześniej określona w zapytaniu, lub nazwę zmiennej, która jest niejawnie zadeklarowana przez zapytanie, takie jak nazwa pola lub nazwa funkcji agregującej.</span><span class="sxs-lookup"><span data-stu-id="1ce8b-103">A range variable name specified in a `Select`, `From`, `Aggregate`, or `Let` clause duplicates the name of a range variable already specified previously in the query, or the name of a variable that is implicitly declared by the query, such as a field name or the name of an aggregate function.</span></span>

 <span data-ttu-id="1ce8b-104">**Identyfikator błędu:** BC36633</span><span class="sxs-lookup"><span data-stu-id="1ce8b-104">**Error ID:** BC36633</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="1ce8b-105">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="1ce8b-105">To correct this error</span></span>

- <span data-ttu-id="1ce8b-106">Upewnij się, że wszystkie zmienne zakresów w konkretnym zakresie zapytania mają unikatowe nazwy.</span><span class="sxs-lookup"><span data-stu-id="1ce8b-106">Ensure that all range variables in a particular query scope have unique names.</span></span> <span data-ttu-id="1ce8b-107">Zapytanie można ująć w nawiasy, aby upewnić się, że zagnieżdżone zapytania mają unikatowy zakres.</span><span class="sxs-lookup"><span data-stu-id="1ce8b-107">You can enclose a query in parentheses to ensure that nested queries have a unique scope.</span></span>

## <a name="see-also"></a><span data-ttu-id="1ce8b-108">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="1ce8b-108">See also</span></span>

- [<span data-ttu-id="1ce8b-109">Wprowadzenie do LINQ w Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1ce8b-109">Introduction to LINQ in Visual Basic</span></span>](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="1ce8b-110">Klauzula from</span><span class="sxs-lookup"><span data-stu-id="1ce8b-110">From Clause</span></span>](../queries/from-clause.md)
- [<span data-ttu-id="1ce8b-111">Klauzula Let</span><span class="sxs-lookup"><span data-stu-id="1ce8b-111">Let Clause</span></span>](../queries/let-clause.md)
- [<span data-ttu-id="1ce8b-112">Aggregate, klauzula</span><span class="sxs-lookup"><span data-stu-id="1ce8b-112">Aggregate Clause</span></span>](../queries/aggregate-clause.md)
- [<span data-ttu-id="1ce8b-113">SELECT — klauzula</span><span class="sxs-lookup"><span data-stu-id="1ce8b-113">Select Clause</span></span>](../queries/select-clause.md)
