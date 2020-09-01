---
description: Zaznaczone i niesprawdzone — odwołanie w C#
title: Zaznaczone i niesprawdzone — odwołanie w C#
ms.date: 05/15/2018
helpviewer_keywords:
- operators [C#], checked and unchecked
- exceptions [C#], overflow checking
- checked statement [C#]
- overflow checking [C#]
- unchecked statement [C#]
- statements [C#], checked and unchecked
ms.assetid: a84bc877-2c7f-4396-8735-1ce97c42f35e
ms.openlocfilehash: a8d6a26e28062da682689bf64a9e38ea5fd158b2
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89138270"
---
# <a name="checked-and-unchecked-c-reference"></a>checked i unchecked (odwołanie w C#)
Instrukcje języka C# można wykonać w kontekście zaznaczonym lub niezaznaczonym. W kontekście, przepełnienie arytmetyczne wywołuje wyjątek. W kontekście niesprawdzonym przepełnienie arytmetyczne jest ignorowane, a wynik zostanie obcięty przez odrzucenie wszystkich bitów o dużej kolejności, które nie mieszczą się w typie docelowym.  
  
- [zaznaczone](checked.md) Określ sprawdzony kontekst.  
  
- [niezaznaczone](unchecked.md) Określ kontekst niesprawdzony.  
  
 Sprawdzanie przepełnienia ma wpływ na następujące operacje:  
  
- Wyrażenia wykorzystujące następujące wstępnie zdefiniowane operatory w typach całkowitych:  
  
     `++`,,,,,, `--` `-` `+` `-` `*` , `/`  
  
- Jawne konwersje liczbowe między typami całkowitymi lub z `float` lub `double` do typu całkowitego.  
  
 Jeśli ani `checked` nie `unchecked` zostanie określony, domyślny kontekst dla wyrażeń niestałych (wyrażenia, które są oceniane w czasie wykonywania) jest zdefiniowany przez wartość opcji kompilatora [-Checked](../compiler-options/checked-compiler-option.md) . Domyślnie wartość tej opcji to unoptional, a operacje arytmetyczne są wykonywane w niesprawdzonym kontekście.

 W przypadku wyrażeń stałych (wyrażenia, które mogą być w pełni oceniane w czasie kompilacji), domyślnym kontekstem jest zawsze zaznaczone. Jeśli wyrażenie stałe nie jest jawnie umieszczane w niesprawdzonym kontekście, przepełnienie następuje podczas obliczania czasu kompilacji wyrażenia powodującego błędy czasu kompilacji.
  
## <a name="see-also"></a>Zobacz też

- [Odwołanie w C#](../index.md)
- [Przewodnik programowania w języku C#](../../programming-guide/index.md)
- [Słowa kluczowe języka C#](index.md)
- [Słowa kluczowe instrukcji](statement-keywords.md)
