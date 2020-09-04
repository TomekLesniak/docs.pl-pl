---
title: Interfejsy ogólne — Przewodnik programowania w języku C#
description: Dowiedz się więcej o używaniu interfejsów ogólnych w języku C#. Zobacz przykłady kodu i Wyświetl dodatkowe dostępne zasoby.
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, generic interfaces
- generics [C#], interfaces
ms.assetid: a8fa49a1-6e78-4a09-87e5-84a0b9f5ffbe
ms.openlocfilehash: b7225e295268a3e46e4e9bd446372ae87bbbbb10
ms.sourcegitcommit: e7acba36517134238065e4d50bb4a1cfe47ebd06
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/04/2020
ms.locfileid: "89466147"
---
# <a name="generic-interfaces-c-programming-guide"></a>Interfejsy ogólne (Przewodnik programowania w języku C#)
Często warto zdefiniować interfejsy dla klas kolekcji generycznej lub dla klas ogólnych, które reprezentują elementy w kolekcji. Preferencją dla klas ogólnych jest użycie interfejsów ogólnych, takich jak <xref:System.IComparable%601> zamiast <xref:System.IComparable> , aby uniknąć pakowania i rozpakowywania operacji na typach wartości. Biblioteka klas .NET definiuje kilka ogólnych interfejsów do użycia z klasami kolekcji w <xref:System.Collections.Generic> przestrzeni nazw.  
  
 Gdy interfejs jest określony jako ograniczenie dla parametru typu, można użyć tylko typów, które implementują interfejs. Poniższy przykład kodu pokazuje `SortedList<T>` klasę, która dziedziczy z `GenericList<T>` klasy. Aby uzyskać więcej informacji, zobacz [wprowadzenie do typów ogólnych](./index.md). `SortedList<T>` dodaje ograniczenie `where T : IComparable<T>` . Dzięki temu `BubbleSort` Metoda w programie `SortedList<T>` może używać metody ogólnej <xref:System.IComparable%601.CompareTo%2A> dla elementów listy. W tym przykładzie elementy list są prostą klasą, `Person` która implementuje `IComparable<Person>` .  
  
 [!code-csharp[csProgGuideGenerics#29](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics2.cs#29)]  
  
 Można określić wiele interfejsów jako ograniczenia dotyczące pojedynczego typu w następujący sposób:  
  
 [!code-csharp[csProgGuideGenerics#30](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#30)]  
  
 Interfejs może definiować więcej niż jeden parametr typu w następujący sposób:  
  
 [!code-csharp[csProgGuideGenerics#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#31)]  
  
 Reguły dziedziczenia stosowane do klas dotyczą również interfejsów:  
  
 [!code-csharp[csProgGuideGenerics#32](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#32)]  
  
 Interfejsy generyczne mogą dziedziczyć z interfejsów innych niż ogólne, jeśli interfejs generyczny jest kontrawariantne, co oznacza, że używa jego parametru typu jako wartości zwracanej. W bibliotece klas .NET <xref:System.Collections.Generic.IEnumerable%601> dziedziczy z, <xref:System.Collections.IEnumerable> ponieważ <xref:System.Collections.Generic.IEnumerable%601> używa tylko `T` w wartości zwracanej i w metodzie <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> <xref:System.Collections.Generic.IEnumerator%601.Current%2A> pobierającej właściwości.  
  
 Konkretne klasy mogą zaimplementować zamknięte interfejsy skonstruowane w następujący sposób:  
  
 [!code-csharp[csProgGuideGenerics#33](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#33)]  
  
 Klasy generyczne mogą implementować interfejsy ogólne lub zamknięte skonstruowane interfejsy, o ile lista parametrów klasy dostarcza wszystkie argumenty wymagane przez interfejs, w następujący sposób:  
  
 [!code-csharp[csProgGuideGenerics#34](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#34)]  
  
 Reguły przeciążania metody kontrolującej są takie same dla metod w klasach ogólnych, strukturach ogólnych lub w interfejsach ogólnych. Aby uzyskać więcej informacji, zobacz [metody ogólne](./generic-methods.md).  
  
## <a name="see-also"></a>Zobacz także

- [Przewodnik programowania w języku C#](../index.md)
- [Wprowadzenie do typów ogólnych](./index.md)
- [interfejsu](../../language-reference/keywords/interface.md)
- [Typy ogólne](../../../standard/generics/index.md)
