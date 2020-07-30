---
title: Różnice między szablonami C++ i typami ogólnymi C# — Przewodnik programowania w języku C#
description: Dowiedz się więcej o różnicach między szablonami C++ i typami ogólnymi języka C#. Obie są funkcjami językowymi, które zapewniają obsługę typów sparametryzowanych.
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], vs. C++ templates
ms.assetid: 1da6beeb-d4a4-4da0-87b7-0cfbe04920b7
ms.openlocfilehash: f405e2d4bef730317703b3b8470edef5b89f0bed
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/28/2020
ms.locfileid: "87301934"
---
# <a name="differences-between-c-templates-and-c-generics-c-programming-guide"></a>Różnice między szablonami C++ i typami ogólnymi C# (Przewodnik programowania w języku C#)
Typy ogólne języka C# i szablony języka C++ są funkcjami językowymi, które zapewniają obsługę typów sparametryzowanych. Istnieje jednak wiele różnic między nimi. Na poziomie składni, typy ogólne języka C# to prostsze podejście do typów sparametryzowanych bez złożoności szablonów języka C++. Ponadto w języku C# nie jest podejmowana próba udostępnienia wszystkich funkcji udostępnianych przez szablony języka C++. Na poziomie implementacji podstawowa różnica polega na tym, że podstawienia typów ogólnych C# są wykonywane w czasie wykonywania, a ogólne informacje o typie są zachowywane w przypadku obiektów wystąpień. Aby uzyskać więcej informacji, zobacz [typy ogólne w czasie wykonywania](./generics-in-the-run-time.md).  
  
 Poniżej przedstawiono kluczowe różnice między typami ogólnymi C# i szablonami języka C++:  
  
- Typy ogólne języka C# nie zapewniają takiej samej elastyczności jak szablony języka C++. Na przykład nie jest możliwe wywołanie operatorów arytmetycznych w klasie generycznej języka C#, chociaż istnieje możliwość wywołania operatorów zdefiniowanych przez użytkownika.  
  
- Język C# nie zezwala na parametry szablonu bez typu, takie jak `template C<int i> {}` .  
  
- Język C# nie obsługuje jawnej specjalizacji; oznacza to, że niestandardowa implementacja szablonu dla określonego typu.  
  
- Język C# nie obsługuje specjalizacji częściowej: niestandardowej implementacji dla podzbioru argumentów typu.  
  
- Język C# nie zezwala na użycie parametru typu jako klasy bazowej dla typu ogólnego.  
  
- Język C# nie zezwala na używanie parametrów typu w typach domyślnych.  
  
- W języku C# parametr typu generycznego nie może być typem ogólnym, chociaż skonstruowane typy mogą służyć jako generyczne. Język C++ zezwala na parametry szablonu.  
  
- Język C++ umożliwia kod, który może być nieprawidłowy dla wszystkich parametrów typu w szablonie, który jest sprawdzany pod kątem określonego typu, który jest używany jako parametr typu. Język C# wymaga, aby kod w klasie był pisany w taki sposób, że będzie działać z dowolnym typem, który spełnia ograniczenia. Na przykład w języku C++ można napisać funkcję, która używa operatorów arytmetycznych `+` i `-` obiektów parametru typu, co spowoduje błąd w czasie tworzenia wystąpienia szablonu z typem, który nie obsługuje tych operatorów. Język C# nie zezwala na to; Jedyne konstrukcje języka dozwolone są te, które można wywnioskować na podstawie ograniczeń.  
  
## <a name="see-also"></a>Zobacz też

- [Przewodnik programowania w języku C#](../index.md)
- [Wprowadzenie do typów ogólnych](./index.md)
- [Szablony](/cpp/cpp/templates-cpp)
