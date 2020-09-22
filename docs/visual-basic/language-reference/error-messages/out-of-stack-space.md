---
title: Za mało miejsca na stosie
ms.date: 07/20/2015
f1_keywords:
- vbrID28
ms.assetid: bfcd792b-ac29-4158-81fc-ea0c13f4ffa2
ms.openlocfilehash: afb6a42372bdbd2e49ac15fbbf2b9e254f8db431
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90871309"
---
# <a name="out-of-stack-space-visual-basic"></a>Za mało miejsca na stosie (Visual Basic)

Stos jest obszarem roboczym pamięci, który powiększa się i zmniejsza dynamicznie z wymaganiami wykonywanymi przez program. Przekroczono limity.  
  
## <a name="to-correct-this-error"></a>Aby poprawić ten błąd  
  
1. Sprawdź, czy procedury nie są zbyt głęboko zagnieżdżone.  
  
2. Upewnij się, że procedury cykliczne kończą się prawidłowo.  
  
3. Jeśli zmienne lokalne wymagają więcej przestrzeni zmiennych lokalnych niż jest dostępna, spróbuj Zadeklaruj pewne zmienne na poziomie modułu. Można również zadeklarować wszystkie zmienne w procedurze statycznej przez poprzedzający `Property` `Sub` słowo kluczowe,, lub `Function` za pomocą `Static` . Można też użyć instrukcji, `Static` Aby zadeklarować poszczególne zmienne statyczne w ramach procedur.  
  
4. Przedefiniuj niektóre ciągi o stałej długości jako ciągi o zmiennej długości, ponieważ ciągi o stałej długości używają większej ilości miejsca na stosie niż ciągi o zmiennej długości. Możesz również zdefiniować ciąg na poziomie modułu, gdzie nie wymaga miejsca na stosie.  
  
5. Sprawdź liczbę zagnieżdżonych `DoEvents` wywołań funkcji przy użyciu `Calls` okna dialogowego, aby zobaczyć, które procedury są aktywne na stosie.  
  
6. Upewnij się, że "zdarzenie kaskadowe" nie zostało wywołane przez wyzwolenie zdarzenia, które wywołuje procedurę zdarzenia już na stosie. Zdarzenie kaskadowe jest podobne do niekończącego wywołania procedury cyklicznej, ale jest mniej oczywiste, ponieważ wywołanie jest wykonywane przez Visual Basic, a nie jawne wywołanie w kodzie. Za pomocą okna `Calls` dialogowego można zobaczyć, które procedury są aktywne na stosie.  
  
## <a name="see-also"></a>Zobacz też

- [Okno pamięci](/visualstudio/debugger/memory-windows)
