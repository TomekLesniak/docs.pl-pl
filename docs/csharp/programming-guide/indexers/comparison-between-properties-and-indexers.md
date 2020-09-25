---
title: Porównanie właściwości i indeksatorów — Przewodnik programowania w języku C#
description: Porównaj, w jaki sposób indeksatory języka C# są podobne do właściwości. Z wyjątkiem różnic, reguły, które są zdefiniowane dla metod dostępu do właściwości, mają zastosowanie do metod dostępu indeksatora.
ms.date: 07/20/2015
helpviewer_keywords:
- properties [C#], vs. indexers
- indexers [C#], vs. properties
ms.assetid: 3358a89f-44a0-4a4d-bf8c-07237a90af39
ms.openlocfilehash: fff20ca965e7614d26f7da32321a829d13292389
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91192532"
---
# <a name="comparison-between-properties-and-indexers-c-programming-guide"></a><span data-ttu-id="ee2f1-104">Porównanie właściwości i indeksatorów (Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="ee2f1-104">Comparison Between Properties and Indexers (C# Programming Guide)</span></span>

<span data-ttu-id="ee2f1-105">Indeksatory są podobne do właściwości.</span><span class="sxs-lookup"><span data-stu-id="ee2f1-105">Indexers are like properties.</span></span> <span data-ttu-id="ee2f1-106">Z wyjątkiem różnic przedstawionych w poniższej tabeli, wszystkie reguły, które są zdefiniowane dla metod dostępu do właściwości stosuje się również do metod dostępu indeksatora.</span><span class="sxs-lookup"><span data-stu-id="ee2f1-106">Except for the differences shown in the following table, all the rules that are defined for property accessors apply to indexer accessors also.</span></span>  
  
|<span data-ttu-id="ee2f1-107">Właściwość</span><span class="sxs-lookup"><span data-stu-id="ee2f1-107">Property</span></span>|<span data-ttu-id="ee2f1-108">Indeksator</span><span class="sxs-lookup"><span data-stu-id="ee2f1-108">Indexer</span></span>|  
|--------------|-------------|  
|<span data-ttu-id="ee2f1-109">Umożliwia wywoływanie metod w taki sposób, jakby były publicznymi elementami członkowskimi danych.</span><span class="sxs-lookup"><span data-stu-id="ee2f1-109">Allows methods to be called as if they were public data members.</span></span>|<span data-ttu-id="ee2f1-110">Zezwala na dostęp do elementów w wewnętrznej kolekcji obiektów przy użyciu notacji tablicy dla samego obiektu.</span><span class="sxs-lookup"><span data-stu-id="ee2f1-110">Allows elements of an internal collection of an object to be accessed by using array notation on the object itself.</span></span>|  
|<span data-ttu-id="ee2f1-111">Dostępne za pomocą prostej nazwy.</span><span class="sxs-lookup"><span data-stu-id="ee2f1-111">Accessed through a simple name.</span></span>|<span data-ttu-id="ee2f1-112">Dostępne za za poorednictwem indeksu.</span><span class="sxs-lookup"><span data-stu-id="ee2f1-112">Accessed through an index.</span></span>|  
|<span data-ttu-id="ee2f1-113">Może być elementem członkowskim typu static lub instance.</span><span class="sxs-lookup"><span data-stu-id="ee2f1-113">Can be a static or an instance member.</span></span>|<span data-ttu-id="ee2f1-114">Musi być elementem członkowskim wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="ee2f1-114">Must be an instance member.</span></span>|  
|<span data-ttu-id="ee2f1-115">Metoda dostępu [Get](../../language-reference/keywords/get.md) właściwości nie ma parametrów.</span><span class="sxs-lookup"><span data-stu-id="ee2f1-115">A [get](../../language-reference/keywords/get.md) accessor of a property has no parameters.</span></span>|<span data-ttu-id="ee2f1-116">`get`Metoda dostępu indeksatora ma taką samą formalną listę parametrów jak indeksator.</span><span class="sxs-lookup"><span data-stu-id="ee2f1-116">A `get` accessor of an indexer has the same formal parameter list as the indexer.</span></span>|  
|<span data-ttu-id="ee2f1-117">Metoda dostępu [Set](../../language-reference/keywords/set.md) właściwości zawiera parametr niejawny `value` .</span><span class="sxs-lookup"><span data-stu-id="ee2f1-117">A [set](../../language-reference/keywords/set.md) accessor of a property contains the implicit `value` parameter.</span></span>|<span data-ttu-id="ee2f1-118">`set`Metoda dostępu indeksatora ma taką samą formalną listę parametrów jak indeksator, a także parametr [Value](../../language-reference/keywords/value.md) .</span><span class="sxs-lookup"><span data-stu-id="ee2f1-118">A `set` accessor of an indexer has the same formal parameter list as the indexer, and also to the [value](../../language-reference/keywords/value.md) parameter.</span></span>|  
|<span data-ttu-id="ee2f1-119">Obsługuje skróconą składnię z [zaimplementowanymi właściwościami](../classes-and-structs/auto-implemented-properties.md).</span><span class="sxs-lookup"><span data-stu-id="ee2f1-119">Supports shortened syntax with [Auto-Implemented Properties](../classes-and-structs/auto-implemented-properties.md).</span></span>|<span data-ttu-id="ee2f1-120">Obsługuje składowe wyrażeń składowanych tylko dla indeksatorów tylko do pobrania.</span><span class="sxs-lookup"><span data-stu-id="ee2f1-120">Supports expression bodied members for get only indexers.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ee2f1-121">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="ee2f1-121">See also</span></span>

- [<span data-ttu-id="ee2f1-122">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="ee2f1-122">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="ee2f1-123">Indexers (Indeksatory)</span><span class="sxs-lookup"><span data-stu-id="ee2f1-123">Indexers</span></span>](./index.md)
- [<span data-ttu-id="ee2f1-124">Właściwości</span><span class="sxs-lookup"><span data-stu-id="ee2f1-124">Properties</span></span>](../classes-and-structs/properties.md)
