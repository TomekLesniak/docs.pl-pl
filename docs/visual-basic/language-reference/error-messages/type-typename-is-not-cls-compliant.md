---
title: Typ „<typename>” jest niezgodny ze specyfikacją CLS
ms.date: 07/20/2015
f1_keywords:
- bc40041
- vbc40041
helpviewer_keywords:
- BC40041
ms.assetid: 634132c2-5646-44aa-98c6-f773e2e63882
ms.openlocfilehash: 369516fb12b24981eaecfe467bf421dec279aa01
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90875092"
---
# <a name="type-typename-is-not-cls-compliant"></a>Typ „\<typename>” jest niezgodny ze specyfikacją CLS

Zmienna, właściwość lub return funkcji jest zadeklarowana z typem danych, który jest niezgodny ze specyfikacją CLS.  
  
 Aby aplikacja była zgodna z [niezależnością od języka i składnikami niezależnymi od języka](../../../standard/language-independence-and-language-independent-components.md) (CLS), musi używać tylko typów zgodnych ze specyfikacją CLS.  
  
 Następujące Visual Basic typy danych nie są zgodne ze specyfikacją CLS:  
  
- [SByte, typ danych](../data-types/sbyte-data-type.md)  
  
- [UInteger, typ danych](../data-types/uinteger-data-type.md)  
  
- [ULong, typ danych](../data-types/ulong-data-type.md)  
  
- [UShort, typ danych](../data-types/ushort-data-type.md)  
  
 **Identyfikator błędu:** BC40041  
  
## <a name="to-correct-this-error"></a>Aby poprawić ten błąd  
  
- Jeśli aplikacja musi być zgodna ze specyfikacją CLS, Zmień typ danych tego elementu na najbliższy typ zgodny ze specyfikacją CLS. Na przykład, zamiast `UInteger` można użyć, `Integer` Jeśli nie potrzebujesz zakresu wartości powyżej 2 147 483 647. Jeśli potrzebujesz rozszerzonego zakresu, możesz zamienić `UInteger` na `Long` .  
  
- Jeśli aplikacja nie musi być zgodna ze specyfikacją CLS, nie trzeba nic zmieniać. Należy jednak pamiętać o jego niezgodności.
