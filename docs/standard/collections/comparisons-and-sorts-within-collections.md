---
title: Porównywanie i sortowanie w kolekcjach
description: Porównuje & sortuje przy użyciu klas System. Collections w programie .NET, które ułatwiają znalezienie elementu do usunięcia lub zwrócenia wartości pary klucz-wartość.
ms.date: 04/30/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sorting data, collections
- IComparable.CompareTo method
- Collections classes
- Equals method
- collections [.NET], comparisons
ms.assetid: 5e4d3b45-97f0-423c-a65f-c492ed40e73b
ms.openlocfilehash: e4d40568710498df811954c86bb36382d93057a3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733545"
---
# <a name="comparisons-and-sorts-within-collections"></a><span data-ttu-id="9f703-103">Porównywanie i sortowanie w kolekcjach</span><span class="sxs-lookup"><span data-stu-id="9f703-103">Comparisons and sorts within collections</span></span>

<span data-ttu-id="9f703-104"><xref:System.Collections>Klasy wykonują porównania niemal wszystkich procesów związanych z zarządzaniem kolekcjami, niezależnie od tego, czy są szukane elementy do usunięcia, czy zwracająca wartość pary klucz-wartość.</span><span class="sxs-lookup"><span data-stu-id="9f703-104">The <xref:System.Collections> classes perform comparisons in almost all the processes involved in managing collections, whether searching for the element to remove or returning the value of a key-and-value pair.</span></span>

<span data-ttu-id="9f703-105">Kolekcje zwykle wykorzystują funkcję porównującą równość i/lub funkcję porównującą porządkowania.</span><span class="sxs-lookup"><span data-stu-id="9f703-105">Collections typically utilize an equality comparer and/or an ordering comparer.</span></span> <span data-ttu-id="9f703-106">Dwa konstrukcje są używane do porównywania.</span><span class="sxs-lookup"><span data-stu-id="9f703-106">Two constructs are used for comparisons.</span></span>

<a name="BKMK_Checkingforequality"></a>

## <a name="check-for-equality"></a><span data-ttu-id="9f703-107">Sprawdź pod kątem równości</span><span class="sxs-lookup"><span data-stu-id="9f703-107">Check for equality</span></span>

<span data-ttu-id="9f703-108">Metody takie jak `Contains` , <xref:System.Collections.IList.IndexOf%2A> , <xref:System.Collections.Generic.List%601.LastIndexOf%2A> i `Remove` wykorzystują funkcję porównującą równość dla elementów kolekcji.</span><span class="sxs-lookup"><span data-stu-id="9f703-108">Methods such as `Contains`, <xref:System.Collections.IList.IndexOf%2A>, <xref:System.Collections.Generic.List%601.LastIndexOf%2A>, and `Remove` use an equality comparer for the collection elements.</span></span> <span data-ttu-id="9f703-109">Jeśli kolekcja jest ogólna, elementy są porównywane pod kątem równości zgodnie z poniższymi wskazówkami:</span><span class="sxs-lookup"><span data-stu-id="9f703-109">If the collection is generic, then items are compared for equality according to the following guidelines:</span></span>

- <span data-ttu-id="9f703-110">Jeśli typ T implementuje <xref:System.IEquatable%601> interfejs ogólny, to metoda porównania równości jest <xref:System.IEquatable%601.Equals%2A> metodą tego interfejsu.</span><span class="sxs-lookup"><span data-stu-id="9f703-110">If type T implements the <xref:System.IEquatable%601> generic interface, then the equality comparer is the <xref:System.IEquatable%601.Equals%2A> method of that interface.</span></span>

- <span data-ttu-id="9f703-111">Jeśli typ T nie implementuje <xref:System.IEquatable%601> , <xref:System.Object.Equals%2A?displayProperty=nameWithType> jest używany.</span><span class="sxs-lookup"><span data-stu-id="9f703-111">If type T does not implement <xref:System.IEquatable%601>, <xref:System.Object.Equals%2A?displayProperty=nameWithType> is used.</span></span>

<span data-ttu-id="9f703-112">Ponadto niektóre przeciążenia konstruktorów dla kolekcji słowników akceptują <xref:System.Collections.Generic.IEqualityComparer%601> implementację, która jest używana do porównywania kluczy pod kątem równości.</span><span class="sxs-lookup"><span data-stu-id="9f703-112">In addition, some constructor overloads for dictionary collections accept an <xref:System.Collections.Generic.IEqualityComparer%601> implementation, which is used to compare keys for equality.</span></span> <span data-ttu-id="9f703-113">Aby zapoznać się z przykładem, zobacz <xref:System.Collections.Generic.Dictionary%602.%23ctor%2A> Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="9f703-113">For an example, see the <xref:System.Collections.Generic.Dictionary%602.%23ctor%2A> constructor.</span></span>

<a name="BKMK_Determiningsortorder"></a>

## <a name="determine-sort-order"></a><span data-ttu-id="9f703-114">Określ kolejność sortowania</span><span class="sxs-lookup"><span data-stu-id="9f703-114">Determine sort order</span></span>

<span data-ttu-id="9f703-115">Metody takie jak `BinarySearch` i `Sort` wykorzystują funkcję porównującą porządkowanie dla elementów kolekcji.</span><span class="sxs-lookup"><span data-stu-id="9f703-115">Methods such as `BinarySearch` and `Sort` use an ordering comparer for the collection elements.</span></span> <span data-ttu-id="9f703-116">Porównania mogą znajdować się między elementami kolekcji lub między elementem a określoną wartością.</span><span class="sxs-lookup"><span data-stu-id="9f703-116">The comparisons can be between elements of the collection, or between an element and a specified value.</span></span> <span data-ttu-id="9f703-117">Do porównywania obiektów istnieje koncepcja `default comparer` i `explicit comparer` .</span><span class="sxs-lookup"><span data-stu-id="9f703-117">For comparing objects, there is the concept of a `default comparer` and an `explicit comparer`.</span></span>

<span data-ttu-id="9f703-118">Domyślna funkcja porównująca polega na co najmniej jednym z obiektów, które są porównywane w celu zaimplementowania interfejsu **IComparable** .</span><span class="sxs-lookup"><span data-stu-id="9f703-118">The default comparer relies on at least one of the objects being compared to implement the **IComparable** interface.</span></span> <span data-ttu-id="9f703-119">Dobrym sposobem implementacji interfejsu **IComparable** dla wszystkich klas są używane jako wartości w kolekcji list lub klucze w kolekcji słowników.</span><span class="sxs-lookup"><span data-stu-id="9f703-119">It is a good practice to implement **IComparable** on all classes are used as values in a list collection or as keys in a dictionary collection.</span></span> <span data-ttu-id="9f703-120">W przypadku kolekcji ogólnej Porównywanie równości jest określane na podstawie następujących elementów:</span><span class="sxs-lookup"><span data-stu-id="9f703-120">For a generic collection, equality comparison is determined according to the following:</span></span>

- <span data-ttu-id="9f703-121">Jeśli typ T implementuje <xref:System.IComparable%601?displayProperty=nameWithType> interfejs generyczny, domyślną metodą porównującą jest <xref:System.IComparable%601.CompareTo%28%600%29?displayProperty=nameWithType> Metoda tego interfejsu</span><span class="sxs-lookup"><span data-stu-id="9f703-121">If type T implements the <xref:System.IComparable%601?displayProperty=nameWithType> generic interface, then the default comparer is the <xref:System.IComparable%601.CompareTo%28%600%29?displayProperty=nameWithType> method of that interface</span></span>

- <span data-ttu-id="9f703-122">Jeśli typ T implementuje interfejs nieogólny <xref:System.IComparable?displayProperty=nameWithType> , wówczas domyślną metodą porównującą jest <xref:System.IComparable.CompareTo%28System.Object%29?displayProperty=nameWithType> Metoda tego interfejsu.</span><span class="sxs-lookup"><span data-stu-id="9f703-122">If type T implements the non-generic <xref:System.IComparable?displayProperty=nameWithType> interface, then the default comparer is the <xref:System.IComparable.CompareTo%28System.Object%29?displayProperty=nameWithType> method of that interface.</span></span>

- <span data-ttu-id="9f703-123">Jeśli typ T nie implementuje interfejsu, wówczas nie ma domyślnego programu porównującego i należy jawnie podać delegata lub delegowanie porównania.</span><span class="sxs-lookup"><span data-stu-id="9f703-123">If type T doesn't implement either interface, then there is no default comparer, and a comparer or comparison delegate must be provided explicitly.</span></span>

<span data-ttu-id="9f703-124">Aby zapewnić jawne porównania, niektóre metody akceptują implementację **IComparer** jako parametr.</span><span class="sxs-lookup"><span data-stu-id="9f703-124">To provide explicit comparisons, some methods accept an **IComparer** implementation as a parameter.</span></span> <span data-ttu-id="9f703-125">Na przykład <xref:System.Collections.Generic.List%601.Sort%2A?displayProperty=nameWithType> Metoda akceptuje <xref:System.Collections.Generic.IComparer%601?displayProperty=nameWithType> implementację.</span><span class="sxs-lookup"><span data-stu-id="9f703-125">For example, the <xref:System.Collections.Generic.List%601.Sort%2A?displayProperty=nameWithType> method accepts an <xref:System.Collections.Generic.IComparer%601?displayProperty=nameWithType> implementation.</span></span>

<span data-ttu-id="9f703-126">Bieżące ustawienie kultury systemu może wpływać na porównania i sortować je w obrębie kolekcji.</span><span class="sxs-lookup"><span data-stu-id="9f703-126">The current culture setting of the system can affect the comparisons and sorts within a collection.</span></span> <span data-ttu-id="9f703-127">Domyślnie porównania i sortowania w klasach **kolekcji** są zależne od kultury.</span><span class="sxs-lookup"><span data-stu-id="9f703-127">By default, the comparisons and sorts in the **Collections** classes are culture-sensitive.</span></span> <span data-ttu-id="9f703-128">Aby zignorować ustawienie kultury i w związku z tym uzyskać spójne wyniki porównania i sortowania, użyj <xref:System.Globalization.CultureInfo.InvariantCulture%2A> z przeciążeniami składowymi, które akceptują <xref:System.Globalization.CultureInfo> .</span><span class="sxs-lookup"><span data-stu-id="9f703-128">To ignore the culture setting and therefore obtain consistent comparison and sorting results, use the <xref:System.Globalization.CultureInfo.InvariantCulture%2A> with member overloads that accept a <xref:System.Globalization.CultureInfo>.</span></span> <span data-ttu-id="9f703-129">Aby uzyskać więcej informacji, zobacz [wykonywanie operacji Culture-Insensitive String w kolekcjach](../globalization-localization/performing-culture-insensitive-string-operations-in-collections.md) i [wykonywanie Culture-Insensitive operacji na ciągach w tablicach](../globalization-localization/performing-culture-insensitive-string-operations-in-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="9f703-129">For more information, see [Performing Culture-Insensitive String Operations in Collections](../globalization-localization/performing-culture-insensitive-string-operations-in-collections.md) and [Performing Culture-Insensitive String Operations in Arrays](../globalization-localization/performing-culture-insensitive-string-operations-in-arrays.md).</span></span>

<a name="BKMK_Equalityandsortexample"></a>

## <a name="equality-and-sort-example"></a><span data-ttu-id="9f703-130">Przykład równości i sortowania</span><span class="sxs-lookup"><span data-stu-id="9f703-130">Equality and sort example</span></span>

<span data-ttu-id="9f703-131">Poniższy kod ilustruje implementację <xref:System.IEquatable%601> i <xref:System.IComparable%601> w prostym obiekcie biznesowym.</span><span class="sxs-lookup"><span data-stu-id="9f703-131">The following code demonstrates an implementation of <xref:System.IEquatable%601> and <xref:System.IComparable%601> on a simple business object.</span></span> <span data-ttu-id="9f703-132">Ponadto, gdy obiekt jest przechowywany na liście i posortowane, zobaczysz, że wywołanie <xref:System.Collections.Generic.List%601.Sort> metody powoduje użycie domyślnej funkcji porównującej dla `Part` typu i <xref:System.Collections.Generic.List%601.Sort%28System.Comparison%7B%600%7D%29> metody zaimplementowane przy użyciu metody anonimowej.</span><span class="sxs-lookup"><span data-stu-id="9f703-132">In addition, when the object is stored in a list and sorted, you will see that calling the <xref:System.Collections.Generic.List%601.Sort> method results in the use of the default comparer for the `Part` type, and the <xref:System.Collections.Generic.List%601.Sort%28System.Comparison%7B%600%7D%29> method implemented by using an anonymous method.</span></span>

[!code-csharp[System.Collections.Generic.List.Sort#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.collections.generic.list.sort/cs/program.cs#1)]
[!code-vb[System.Collections.Generic.List.Sort#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.collections.generic.list.sort/vb/module1.vb#1)]

## <a name="see-also"></a><span data-ttu-id="9f703-133">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="9f703-133">See also</span></span>

- <xref:System.Collections.IComparer>
- <xref:System.IEquatable%601>
- <xref:System.Collections.Generic.IComparer%601>
- <xref:System.IComparable>
- <xref:System.IComparable%601>
