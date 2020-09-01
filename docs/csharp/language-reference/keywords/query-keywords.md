---
description: Słowa kluczowe zapytania — odwołanie w C#
title: Słowa kluczowe zapytania — odwołanie w C#
ms.date: 07/20/2015
helpviewer_keywords:
- query keywords [C#]
- LINQ [C#], query keywords
ms.assetid: 6c9bec16-dbd7-4a7c-a060-fe4600b2021f
ms.openlocfilehash: 0beea8634d13222aa18f14d79fdbd95a35cc832e
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89137139"
---
# <a name="query-keywords-c-reference"></a><span data-ttu-id="6788c-103">Słowa kluczowe zapytania (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="6788c-103">Query keywords (C# Reference)</span></span>

<span data-ttu-id="6788c-104">Ta sekcja zawiera kontekstowe słowa kluczowe używane w wyrażeniach zapytań.</span><span class="sxs-lookup"><span data-stu-id="6788c-104">This section contains the contextual keywords used in query expressions.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="6788c-105">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="6788c-105">In this section</span></span>

|<span data-ttu-id="6788c-106">Klauzula</span><span class="sxs-lookup"><span data-stu-id="6788c-106">Clause</span></span>|<span data-ttu-id="6788c-107">Opis</span><span class="sxs-lookup"><span data-stu-id="6788c-107">Description</span></span>|
|------------|-----------------|
|[<span data-ttu-id="6788c-108">wniosek</span><span class="sxs-lookup"><span data-stu-id="6788c-108">from</span></span>](from-clause.md)|<span data-ttu-id="6788c-109">Określa źródło danych i zmienną zakresu (podobnie jak Zmienna iteracji).</span><span class="sxs-lookup"><span data-stu-id="6788c-109">Specifies a data source and a range variable (similar to an iteration variable).</span></span>|
|[<span data-ttu-id="6788c-110">miejscu</span><span class="sxs-lookup"><span data-stu-id="6788c-110">where</span></span>](where-clause.md)|<span data-ttu-id="6788c-111">Filtruje elementy źródłowe na podstawie jednego lub kilku wyrażeń logicznych oddzielonych operatorami logicznymi i i lub ( `&&` lub <code>&#124;&#124;</code> ).</span><span class="sxs-lookup"><span data-stu-id="6788c-111">Filters source elements based on one or more Boolean expressions separated by logical AND and OR operators ( `&&` or <code>&#124;&#124;</code> ).</span></span>|
|[<span data-ttu-id="6788c-112">zaznaczenia</span><span class="sxs-lookup"><span data-stu-id="6788c-112">select</span></span>](select-clause.md)|<span data-ttu-id="6788c-113">Określa typ i kształt, które elementy w zwracanej sekwencji będą miały miejsce, gdy zapytanie zostanie wykonane.</span><span class="sxs-lookup"><span data-stu-id="6788c-113">Specifies the type and shape that the elements in the returned sequence will have when the query is executed.</span></span>|
|[<span data-ttu-id="6788c-114">Group</span><span class="sxs-lookup"><span data-stu-id="6788c-114">group</span></span>](group-clause.md)|<span data-ttu-id="6788c-115">Grupuje wyniki zapytania zgodnie z określoną wartością klucza.</span><span class="sxs-lookup"><span data-stu-id="6788c-115">Groups query results according to a specified key value.</span></span>|
|[<span data-ttu-id="6788c-116">przekształca</span><span class="sxs-lookup"><span data-stu-id="6788c-116">into</span></span>](into.md)|<span data-ttu-id="6788c-117">Dostarcza identyfikator, który może być używany jako odwołanie do wyników klauzuli join, Group lub SELECT.</span><span class="sxs-lookup"><span data-stu-id="6788c-117">Provides an identifier that can serve as a reference to the results of a join, group or select clause.</span></span>|
|[<span data-ttu-id="6788c-118">OrderBy</span><span class="sxs-lookup"><span data-stu-id="6788c-118">orderby</span></span>](orderby-clause.md)|<span data-ttu-id="6788c-119">Sortuje wyniki zapytania w porządku rosnącym lub malejącym w oparciu o domyślną funkcję porównującą dla typu elementu.</span><span class="sxs-lookup"><span data-stu-id="6788c-119">Sorts query results in ascending or descending order based on the default comparer for the element type.</span></span>|
|[<span data-ttu-id="6788c-120">Złącza</span><span class="sxs-lookup"><span data-stu-id="6788c-120">join</span></span>](join-clause.md)|<span data-ttu-id="6788c-121">Łączy dwa źródła danych na podstawie porównania równości między dwoma określonymi kryteriami dopasowywania.</span><span class="sxs-lookup"><span data-stu-id="6788c-121">Joins two data sources based on an equality comparison between two specified matching criteria.</span></span>|
|[<span data-ttu-id="6788c-122">wpuść</span><span class="sxs-lookup"><span data-stu-id="6788c-122">let</span></span>](let-clause.md)|<span data-ttu-id="6788c-123">Wprowadza zmienną zakresu do przechowywania wyników podwyrażenia w wyrażeniu zapytania.</span><span class="sxs-lookup"><span data-stu-id="6788c-123">Introduces a range variable to store sub-expression results in a query expression.</span></span>|
|[<span data-ttu-id="6788c-124">podczas</span><span class="sxs-lookup"><span data-stu-id="6788c-124">in</span></span>](in.md)|<span data-ttu-id="6788c-125">Kontekstowe słowo kluczowe w klauzuli [Join](join-clause.md) .</span><span class="sxs-lookup"><span data-stu-id="6788c-125">Contextual keyword in a [join](join-clause.md) clause.</span></span>|
|[<span data-ttu-id="6788c-126">z</span><span class="sxs-lookup"><span data-stu-id="6788c-126">on</span></span>](on.md)|<span data-ttu-id="6788c-127">Kontekstowe słowo kluczowe w klauzuli [Join](join-clause.md) .</span><span class="sxs-lookup"><span data-stu-id="6788c-127">Contextual keyword in a [join](join-clause.md) clause.</span></span>|
|[<span data-ttu-id="6788c-128">equals</span><span class="sxs-lookup"><span data-stu-id="6788c-128">equals</span></span>](equals.md)|<span data-ttu-id="6788c-129">Kontekstowe słowo kluczowe w klauzuli [Join](join-clause.md) .</span><span class="sxs-lookup"><span data-stu-id="6788c-129">Contextual keyword in a [join](join-clause.md) clause.</span></span>|
|[<span data-ttu-id="6788c-130">by</span><span class="sxs-lookup"><span data-stu-id="6788c-130">by</span></span>](by.md)|<span data-ttu-id="6788c-131">Kontekstowe słowo kluczowe w klauzuli [Group](group-clause.md) .</span><span class="sxs-lookup"><span data-stu-id="6788c-131">Contextual keyword in a [group](group-clause.md) clause.</span></span>|
|[<span data-ttu-id="6788c-132">ascending</span><span class="sxs-lookup"><span data-stu-id="6788c-132">ascending</span></span>](ascending.md)|<span data-ttu-id="6788c-133">Kontekstowe słowo kluczowe w klauzuli [OrderBy](orderby-clause.md) .</span><span class="sxs-lookup"><span data-stu-id="6788c-133">Contextual keyword in an [orderby](orderby-clause.md) clause.</span></span>|
|[<span data-ttu-id="6788c-134">descending</span><span class="sxs-lookup"><span data-stu-id="6788c-134">descending</span></span>](descending.md)|<span data-ttu-id="6788c-135">Kontekstowe słowo kluczowe w klauzuli [OrderBy](orderby-clause.md) .</span><span class="sxs-lookup"><span data-stu-id="6788c-135">Contextual keyword in an [orderby](orderby-clause.md) clause.</span></span>|

## <a name="see-also"></a><span data-ttu-id="6788c-136">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="6788c-136">See also</span></span>

- [<span data-ttu-id="6788c-137">Słowa kluczowe języka C#</span><span class="sxs-lookup"><span data-stu-id="6788c-137">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="6788c-138">LINQ (zapytanie zintegrowane z językiem)</span><span class="sxs-lookup"><span data-stu-id="6788c-138">LINQ (Language-Integrated Query)</span></span>](../../programming-guide/concepts/linq/index.md)
- [<span data-ttu-id="6788c-139">LINQ w C#</span><span class="sxs-lookup"><span data-stu-id="6788c-139">LINQ in C#</span></span>](../../linq/index.md)
