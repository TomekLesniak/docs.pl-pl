---
title: Delegaty ogólne — Przewodnik programowania w języku C#
description: Dowiedz się więcej o używaniu delegatów ogólnych w języku C#. Zobacz przykłady kodu i Wyświetl dodatkowe dostępne zasoby.
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], delegates
- delegates [C#], generic
ms.assetid: bdea509c-44c1-4309-aaa9-15c7aee009df
ms.openlocfilehash: df417701feb77dc47cff1cdd68eb4c7405d15beb
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91157411"
---
# <a name="generic-delegates-c-programming-guide"></a>Delegaty ogólne (Przewodnik programowania w języku C#)

[Delegat](../../language-reference/builtin-types/reference-types.md) może definiować własne parametry typu. Kod, który odwołuje się do delegata generycznego, może określić argument typu, aby utworzyć zamknięty typ skonstruowany, podobnie jak podczas tworzenia wystąpienia klasy generycznej lub wywołania metody ogólnej, jak pokazano w następującym przykładzie:  
  
 [!code-csharp[csProgGuideGenerics#36](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#36)]  
  
 Język C# w wersji 2,0 ma nową funkcję o nazwie konwersja grup metod, która ma zastosowanie do konkretnych typów delegatów, i umożliwia zapisanie poprzedniego wiersza z tą uproszczoną składnią:  
  
 [!code-csharp[csProgGuideGenerics#37](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#37)]  
  
 Delegaty zdefiniowane w klasie generycznej mogą używać parametrów typu klasy generycznej w taki sam sposób, jak metody klasy.  
  
 [!code-csharp[csProgGuideGenerics#38](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#38)]  
  
 Kod odwołujący się do delegata musi określać argument typu klasy zawierającej w następujący sposób:  
  
 [!code-csharp[csProgGuideGenerics#39](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#39)]  
  
 Delegaty ogólne są szczególnie przydatne w definiowaniu zdarzeń na podstawie typowego wzorca projektowego, ponieważ argument nadawcy może być silnie określony i nie musi być już rzutowany do i z <xref:System.Object> .  
  
 [!code-csharp[csProgGuideGenerics#40](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#40)]  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.Collections.Generic>
- [Przewodnik programowania w języku C#](../index.md)
- [Wprowadzenie do typów ogólnych](./index.md)
- [Metody ogólne](./generic-methods.md)
- [Klasy ogólne](./generic-classes.md)
- [Interfejsy ogólne](./generic-interfaces.md)
- [Delegaci](../delegates/index.md)
- [Typy ogólne](../../../standard/generics/index.md)
