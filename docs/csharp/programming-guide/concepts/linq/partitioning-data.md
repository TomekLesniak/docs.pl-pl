---
title: Partycjonowanie danych (C#)
description: Dowiedz się, jak podzielić dane na partycje w LINQ. Wyświetl ilustrację przedstawiającą wyniki operacji partycjonowania.
ms.date: 07/20/2015
ms.assetid: 2a5c507b-fe22-443c-a768-dec7f9ec568d
ms.openlocfilehash: 3c85eaec2dc01b683234a27714750354982be440
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302610"
---
# <a name="partitioning-data-c"></a><span data-ttu-id="43420-104">Partycjonowanie danych (C#)</span><span class="sxs-lookup"><span data-stu-id="43420-104">Partitioning Data (C#)</span></span>
<span data-ttu-id="43420-105">Partycjonowanie w LINQ odwołuje się do operacji dzielenia sekwencji wejściowej na dwie sekcje, bez konieczności ponownej rozmieszczania elementów, a następnie zwrócenia jednej z sekcji.</span><span class="sxs-lookup"><span data-stu-id="43420-105">Partitioning in LINQ refers to the operation of dividing an input sequence into two sections, without rearranging the elements, and then returning one of the sections.</span></span>  
  
 <span data-ttu-id="43420-106">Na poniższej ilustracji przedstawiono wyniki trzech różnych operacji partycjonowania na sekwencji znaków.</span><span class="sxs-lookup"><span data-stu-id="43420-106">The following illustration shows the results of three different partitioning operations on a sequence of characters.</span></span> <span data-ttu-id="43420-107">Pierwsza operacja zwraca trzy pierwsze elementy w sekwencji.</span><span class="sxs-lookup"><span data-stu-id="43420-107">The first operation returns the first three elements in the sequence.</span></span> <span data-ttu-id="43420-108">Druga operacja pomija pierwsze trzy elementy i zwraca pozostałe elementy.</span><span class="sxs-lookup"><span data-stu-id="43420-108">The second operation skips the first three elements and returns the remaining elements.</span></span> <span data-ttu-id="43420-109">Trzecia operacja pomija pierwsze dwa elementy w sekwencji i zwraca następne trzy elementy.</span><span class="sxs-lookup"><span data-stu-id="43420-109">The third operation skips the first two elements in the sequence and returns the next three elements.</span></span>  
  
 ![Ilustracja przedstawiająca trzy operacje partycjonowania LINQ.](./media/partitioning-data/linq-partitioning-operations.png)  
  
 <span data-ttu-id="43420-111">Standardowe metody operatorów zapytań, które są sekwencje partycji, są wymienione w poniższej sekcji.</span><span class="sxs-lookup"><span data-stu-id="43420-111">The standard query operator methods that partition sequences are listed in the following section.</span></span>  
  
## <a name="operators"></a><span data-ttu-id="43420-112">Operatory</span><span class="sxs-lookup"><span data-stu-id="43420-112">Operators</span></span>  
  
|<span data-ttu-id="43420-113">Nazwa operatora</span><span class="sxs-lookup"><span data-stu-id="43420-113">Operator Name</span></span>|<span data-ttu-id="43420-114">Opis</span><span class="sxs-lookup"><span data-stu-id="43420-114">Description</span></span>|<span data-ttu-id="43420-115">Składnia wyrażenia zapytania C#</span><span class="sxs-lookup"><span data-stu-id="43420-115">C# Query Expression Syntax</span></span>|<span data-ttu-id="43420-116">Więcej informacji</span><span class="sxs-lookup"><span data-stu-id="43420-116">More Information</span></span>|  
|-------------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="43420-117">Pomiń</span><span class="sxs-lookup"><span data-stu-id="43420-117">Skip</span></span>|<span data-ttu-id="43420-118">Pomija elementy do określonej pozycji w sekwencji.</span><span class="sxs-lookup"><span data-stu-id="43420-118">Skips elements up to a specified position in a sequence.</span></span>|<span data-ttu-id="43420-119">Nie dotyczy.</span><span class="sxs-lookup"><span data-stu-id="43420-119">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Skip%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Skip%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="43420-120">SkipWhile —</span><span class="sxs-lookup"><span data-stu-id="43420-120">SkipWhile</span></span>|<span data-ttu-id="43420-121">Pomija elementy na podstawie funkcji predykatu, dopóki element nie spełnia warunku.</span><span class="sxs-lookup"><span data-stu-id="43420-121">Skips elements based on a predicate function until an element does not satisfy the condition.</span></span>|<span data-ttu-id="43420-122">Nie dotyczy.</span><span class="sxs-lookup"><span data-stu-id="43420-122">Not applicable.</span></span>|<xref:System.Linq.Enumerable.SkipWhile%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.SkipWhile%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="43420-123">Take</span><span class="sxs-lookup"><span data-stu-id="43420-123">Take</span></span>|<span data-ttu-id="43420-124">Pobiera elementy do określonej pozycji w sekwencji.</span><span class="sxs-lookup"><span data-stu-id="43420-124">Takes elements up to a specified position in a sequence.</span></span>|<span data-ttu-id="43420-125">Nie dotyczy.</span><span class="sxs-lookup"><span data-stu-id="43420-125">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Take%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Take%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="43420-126">TakeWhile —</span><span class="sxs-lookup"><span data-stu-id="43420-126">TakeWhile</span></span>|<span data-ttu-id="43420-127">Pobiera elementy na podstawie funkcji predykatu, dopóki element nie spełnia warunku.</span><span class="sxs-lookup"><span data-stu-id="43420-127">Takes elements based on a predicate function until an element does not satisfy the condition.</span></span>|<span data-ttu-id="43420-128">Nie dotyczy.</span><span class="sxs-lookup"><span data-stu-id="43420-128">Not applicable.</span></span>|<xref:System.Linq.Enumerable.TakeWhile%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.TakeWhile%2A?displayProperty=nameWithType>|  
  
## <a name="see-also"></a><span data-ttu-id="43420-129">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="43420-129">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="43420-130">Standardowe operatory zapytań — Omówienie (C#)</span><span class="sxs-lookup"><span data-stu-id="43420-130">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
