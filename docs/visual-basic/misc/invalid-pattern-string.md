---
title: Nieprawidłowy ciąg wzorca
ms.date: 07/20/2015
ms.assetid: ec1aecdb-5339-4a93-be71-eec56b1d7438
ms.openlocfilehash: 5ef12ac27e96205f9ef1c964293847f56b11cb78
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91090693"
---
# <a name="invalid-pattern-string"></a>Nieprawidłowy ciąg wzorca

Ciąg wzorca określony w `Like` operacji wyszukiwania jest nieprawidłowy.  
  
## <a name="to-correct-this-error"></a>Aby poprawić ten błąd  
  
1. Przejrzyj prawidłowe znaki dla wyrażeń listy.  
  
2. W zakresie wzorców upewnij się, że znak zakresu początkowego jest mniejszy niż znak zakresu końcowego, jak w `[a-z]` .  
  
3. W zakresie wzorców upewnij się, że nie ma kilku łączników obok siebie, jak w `[a--z]` .  
  
4. Końcowe zakresy wzorców z nawiasem zamykającym.  
  
## <a name="see-also"></a>Zobacz także

- [Like — Operator](../language-reference/operators/like-operator.md)
