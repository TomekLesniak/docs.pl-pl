---
title: Wykonywanie niezależnych od kultury operacji na ciągach w tablicach
ms.date: 03/30/2017
helpviewer_keywords:
- culture-insensitive string operations, in arrays
- arrays [.NET], culture-insensitive string operations
- comparer parameter
ms.assetid: f12922e1-6234-4165-8896-63f0653ab478
ms.openlocfilehash: ac8074c5d13209b6828b7afbc720921015e11bfd
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2020
ms.locfileid: "94829807"
---
# <a name="performing-culture-insensitive-string-operations-in-arrays"></a>Wykonywanie niezależnych od kultury operacji na ciągach w tablicach

Przeciążenia <xref:System.Array.Sort%2A?displayProperty=nameWithType> metod i są <xref:System.Array.BinarySearch%2A?displayProperty=nameWithType> Domyślnie wykonywane w celu sortowania z uwzględnieniem kultury, przy użyciu <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> właściwości. Wyniki wrażliwe na kulturę zwracane przez te metody mogą się różnić w zależności od różnic w kolejności sortowania. Aby wyeliminować zachowanie wrażliwe na kulturę, użyj jednego z przeciążeń tej metody, która akceptuje `comparer` parametr. `comparer`Parametr określa <xref:System.Collections.IComparer> implementację do użycia podczas porównywania elementów w tablicy. Dla parametru należy określić niestandardową klasę niezmiennej porównującej, która używa <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType> . Przykład niestandardowej klasy niezmiennej porównującej znajduje się w podrozdziale "Używanie klasy SortedList" [operacji wykonywania ciągu Culture-Insensitive w temacie kolekcje](performing-culture-insensitive-string-operations-in-collections.md) .

> [!NOTE]
> Przekazywanie **CultureInfo. InvariantCulture** do metody porównania wykonuje porównanie nieuwzględniające kulturę. Nie powoduje to jednak porównania w języku innym niż język, na przykład w przypadku ścieżek plików, kluczy rejestru i zmiennych środowiskowych. Żadna z tych funkcji nie wspiera podejmowania decyzji dotyczących zabezpieczeń w oparciu o wynik porównania. W przypadku niezgodności z językiem lub pomocy technicznej dla decyzji o zabezpieczeniach opartych na wynikach aplikacja powinna używać metody porównania, która akceptuje <xref:System.StringComparison> wartość. Aplikacja powinna następnie przejść <xref:System.StringComparison.Ordinal> .

## <a name="see-also"></a>Zobacz także

- <xref:System.Array.Sort%2A?displayProperty=nameWithType>
- <xref:System.Array.BinarySearch%2A?displayProperty=nameWithType>
- <xref:System.Collections.IComparer>
- [Wykonywanie niezależnych od kultury operacji na ciągach](performing-culture-insensitive-string-operations.md)
