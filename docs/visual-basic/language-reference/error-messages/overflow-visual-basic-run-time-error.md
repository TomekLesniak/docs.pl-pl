---
title: Przepełnienie (błąd czasu wykonywania w Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vbrERRID_Overflow
ms.assetid: c6a23279-3086-412a-bcff-ff8ed2cb8c6f
ms.openlocfilehash: e287d6c24eca75d8bf20181a201056f467d6fc4e
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90871224"
---
# <a name="overflow-visual-basic-run-time-error"></a>Przepełnienie (błąd czasu wykonywania w Visual Basic)

Przepełnienie wyników podczas próby przypisania, które przekracza limity docelowego przypisania.  
  
## <a name="to-correct-this-error"></a>Aby poprawić ten błąd  
  
1. Upewnij się, że wyniki przypisań, obliczeń i konwersji typów danych nie są zbyt duże, aby były reprezentowane w zakresie zmiennych dozwolonych dla tego typu wartości, i przypisz wartość do zmiennej typu, która może zawierać większy zakres wartości, w razie potrzeby.  
  
2. Upewnij się, że przypisania do właściwości mieszczą się w zakresie właściwości, w której zostały wprowadzone.  
  
3. Upewnij się, że liczby używane w obliczeniach, które są przekształcane w liczby całkowite, nie mają wyników większych niż liczby całkowite.  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.Int32.MaxValue?displayProperty=nameWithType>
- <xref:System.Double.MaxValue?displayProperty=nameWithType>
- [Typy danych](../data-types/index.md)
- [Typy błędów](../../programming-guide/language-features/error-types.md)
