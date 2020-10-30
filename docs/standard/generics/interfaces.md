---
title: Interfejsy ogólne
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- generic interfaces [.NET]
- equality comparisons [.NET]
- generics [.NET], interfaces
- ordering comparisons [.NET]
ms.assetid: 88bf5b04-d371-4edb-ba38-01ec7cabaacf
ms.openlocfilehash: 6e107250cef38d532310cd193c9324d1d39c096a
ms.sourcegitcommit: b1442669f1982d3a1cb18ea35b5acfb0fc7d93e4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/30/2020
ms.locfileid: "93064057"
---
# <a name="generic-interfaces"></a>Interfejsy ogólne

Ten artykuł zawiera omówienie ogólnych interfejsów, które udostępniają typowe funkcje w różnych rodzinach typów ogólnych.  
  
Interfejsy generyczne zapewniają bezpieczne dla typu interfejsy nieogólne do sortowania i porównywania równości oraz funkcji, które są współużytkowane przez typy kolekcji generycznej.  
  
> [!NOTE]
> Parametry typu kilku ogólnych interfejsów są oznaczone jako współvariant lub kontrawariantne, co zapewnia większą elastyczność podczas przypisywania i używania typów, które implementują te interfejsy. Zobacz [Kowariancja i kontrawariancja](covariance-and-contravariance.md).  
  
## <a name="equality-and-ordering-comparisons"></a>Porównania równości i określania kolejności  
 W <xref:System> obszarze nazw, <xref:System.IComparable%601?displayProperty=nameWithType> i <xref:System.IEquatable%601?displayProperty=nameWithType> interfejsy ogólne, takie jak ich niegeneryczne odpowiedniki, definiują metody określania kolejności porównań i porównywania równości. Typy implementują te interfejsy, aby zapewnić możliwość wykonywania takich porównań.  
  
 W <xref:System.Collections.Generic> przestrzeni nazw <xref:System.Collections.Generic.IComparer%601> i <xref:System.Collections.Generic.IEqualityComparer%601> interfejsy ogólne umożliwiają zdefiniowanie porównania porządkunia lub równości dla typów, które nie implementują <xref:System.IComparable%601?displayProperty=nameWithType> <xref:System.IEquatable%601?displayProperty=nameWithType> interfejsu lub ogólnych, a także umożliwiają zdefiniowanie tych relacji dla typów, które wykonują. Te interfejsy są używane przez metody i konstruktory wielu klas kolekcji ogólnej. Na przykład można przekazać obiekt generyczny <xref:System.Collections.Generic.IComparer%601> do konstruktora <xref:System.Collections.Generic.SortedDictionary%602> klasy, aby określić kolejność sortowania dla typu, który nie implementuje generycznej <xref:System.IComparable%601?displayProperty=nameWithType> . Istnieją przeciążenia <xref:System.Array.Sort%2A?displayProperty=nameWithType> ogólnej metody statycznej i <xref:System.Collections.Generic.List%601.Sort%2A?displayProperty=nameWithType> metody instancji do sortowania tablic i list przy użyciu <xref:System.Collections.Generic.IComparer%601> implementacji ogólnych.  
  
 <xref:System.Collections.Generic.Comparer%601>Klasy i <xref:System.Collections.Generic.EqualityComparer%601> generyczne zapewniają klasy bazowe dla implementacji <xref:System.Collections.Generic.IComparer%601> <xref:System.Collections.Generic.IEqualityComparer%601> interfejsów i ogólnych, a także zapewniają domyślne sortowanie i Porównywanie równości przy użyciu ich odpowiednich <xref:System.Collections.Generic.Comparer%601.Default%2A?displayProperty=nameWithType> i <xref:System.Collections.Generic.EqualityComparer%601.Default%2A?displayProperty=nameWithType> właściwości.  
  
## <a name="collection-functionality"></a>Funkcje kolekcji  
 <xref:System.Collections.Generic.ICollection%601>Ogólny interfejs to podstawowy interfejs dla typów kolekcji rodzajowych. Zapewnia podstawowe funkcje dodawania, usuwania, kopiowania i wyliczania elementów. <xref:System.Collections.Generic.ICollection%601> dziedziczy z zarówno rodzajowe <xref:System.Collections.Generic.IEnumerable%601> , jak i nieogólne <xref:System.Collections.IEnumerable> .  
  
 <xref:System.Collections.Generic.IList%601>Ogólny interfejs rozszerza <xref:System.Collections.Generic.ICollection%601> interfejs ogólny o metody do pobierania indeksowanego.  
  
 <xref:System.Collections.Generic.IDictionary%602>Interfejs generyczny rozszerza <xref:System.Collections.Generic.ICollection%601> interfejs ogólny o metody do pobierania, który został utworzony. Typy słowników rodzajowych w bibliotece klas podstawowych .NET implementują również interfejs nieogólny <xref:System.Collections.IDictionary> .  
  
 <xref:System.Collections.Generic.IEnumerable%601>Ogólny interfejs zawiera ogólną strukturę modułu wyliczającego. <xref:System.Collections.Generic.IEnumerator%601>Ogólny interfejs implementowany przez moduł wyliczający generyczne dziedziczy interfejs nieogólny <xref:System.Collections.IEnumerator> ; <xref:System.Collections.IEnumerator.MoveNext%2A> i <xref:System.Collections.IEnumerator.Reset%2A> składowe, które nie są zależne od parametru typu `T` , są wyświetlane tylko w nieogólnym interfejsie. Oznacza to, że każdy użytkownik niegenerycznego interfejsu może również korzystać z interfejsu ogólnego.  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.Collections.Generic?displayProperty=nameWithType>
- <xref:System.Collections.ObjectModel?displayProperty=nameWithType>
- [Typy ogólne](index.md)
- [Kolekcje ogólne w programie .NET](collections.md)
- [Delegaty ogólne do manipulowania tablicami i listami](delegates-for-manipulating-arrays-and-lists.md)
- [Kowariancja i kontrawariancja](covariance-and-contravariance.md)
