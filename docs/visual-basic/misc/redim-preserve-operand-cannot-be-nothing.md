---
title: Argument operacji zachowywania "ReDim" nie może mieć wartości Nothing
ms.date: 07/20/2015
ms.assetid: b857f313-3fc2-4262-a577-88df1718b811
ms.openlocfilehash: 274b616387d214f32dd9cf05eaa17eb97898ffa4
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91077348"
---
# <a name="redim-preserve-operand-cannot-be-nothing"></a>Argument operacji zachowywania "ReDim" nie może mieć wartości Nothing

`ReDim`Instrukcja próbuje użyć `Preserve` słowa kluczowego, aby zmienić wymiar tablicy, która nie jest ostatnim wymiarem, ale nie dostarcza prawidłowej wartości dla tego operandu.  
  
## <a name="to-correct-this-error"></a>Aby poprawić ten błąd  
  
- Zmień `Preserve` operand na prawidłową wartość.  
  
## <a name="see-also"></a>Zobacz także

- [Tablice w Visual Basic](../programming-guide/language-features/arrays/index.md)
- [Wymiary tablicy w Visual Basic](../programming-guide/language-features/arrays/array-dimensions.md)
- [ReDim, instrukcja](../language-reference/statements/redim-statement.md)
- [Dim, instrukcja](../language-reference/statements/dim-statement.md)
