---
title: Element "ReDim" nie może zmienić liczby wymiarów
ms.date: 07/20/2015
f1_keywords:
- vbrArray_RankMismatch
ms.assetid: 52505298-9985-4682-8f6e-ff7d56077f34
ms.openlocfilehash: 8d80af7682f27b403e0f463fdbebbcac71f18b01
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91077374"
---
# <a name="redim-cannot-change-the-number-of-dimensions"></a>Element "ReDim" nie może zmienić liczby wymiarów

Operacja próbuje użyć instrukcji, `ReDim` Aby zmienić rangę (liczbę wymiarów) tablicy. `ReDim` można zmienić rozmiar co najmniej jednego wymiaru tablicy, która została już formalnie zadeklarowana, ale nie może zmienić rangi tablicy.  
  
## <a name="to-correct-this-error"></a>Aby poprawić ten błąd  
  
- Upewnij się, że zamierzasz zmienić rangę tablicy, a nie rozmiary jej wymiarów, a jeśli to możliwe, użyj, `Dim` Aby zadeklarować nową tablicę z odpowiednią rangą.  
  
## <a name="see-also"></a>Zobacz także

- [Tablice w Visual Basic](../programming-guide/language-features/arrays/index.md)
- [Wymiary tablicy w Visual Basic](../programming-guide/language-features/arrays/array-dimensions.md)
- [ReDim, instrukcja](../language-reference/statements/redim-statement.md)
- [Dim, instrukcja](../language-reference/statements/dim-statement.md)
