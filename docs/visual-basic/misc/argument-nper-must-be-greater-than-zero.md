---
title: Argument "lokr" musi być większy od zera
ms.date: 07/20/2015
f1_keywords:
- vbrRate_NPerMustBeGTZero
ms.assetid: d49242df-dbd1-4b26-bd8c-ed56d24fdfcd
ms.openlocfilehash: f0185e30cb711472105955f5febf8d7702b29c72
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91087144"
---
# <a name="argument-nper-must-be-greater-than-zero"></a>Argument "lokr" musi być większy od zera

`NPer`Funkcja, która zwraca `Double` określenie liczby okresów dla raty rocznej na podstawie okresowych stałych płatności i stałej stopy oprocentowania, wymaga argumentu większego od zera.  
  
## <a name="to-correct-this-error"></a>Aby poprawić ten błąd  
  
- Sprawdź pisownię argumentów w wyrażeniu. Błędnie wpisana nazwa zmiennej może niejawnie utworzyć zmienną numeryczną, która została zainicjowana do zera.  
  
- Sprawdź poprzednie operacje na zmiennych w wyrażeniu, szczególnie te przekazane do procedury jako argumenty z innych procedur.  
  
## <a name="see-also"></a>Zobacz także

- [Przekazywanie argumentów według wartości i według odwołania](../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
