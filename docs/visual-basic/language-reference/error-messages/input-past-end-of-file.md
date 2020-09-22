---
title: Próba zapisu poza końcem pliku
ms.date: 07/20/2015
f1_keywords:
- vbrID62
ms.assetid: 65292704-6e7d-4622-9f50-eb655a59b016
ms.openlocfilehash: c0cb0373fb0652e9600ac8651661708414561aca
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873966"
---
# <a name="input-past-end-of-file"></a>Próba zapisu poza końcem pliku

`Input`Instrukcja odczytuje z pliku, który jest pusty lub jeden, w którym są używane wszystkie dane, albo użyto `EOF` funkcji z plikiem otwartym do dostępu do danych binarnych.  
  
## <a name="to-correct-this-error"></a>Aby poprawić ten błąd  
  
1. Użyj `EOF` funkcji bezpośrednio przed `Input` instrukcją w celu wykrycia końca pliku.  
  
2. Jeśli plik jest otwarty do dostępu do danych binarnych, użyj `Seek` i `Loc` .  
  
## <a name="see-also"></a>Zobacz też

- <xref:Microsoft.VisualBasic.FileSystem.Input%2A>
- <xref:Microsoft.VisualBasic.FileSystem.EOF%2A>
- <xref:Microsoft.VisualBasic.FileSystem.Seek%2A>
- <xref:Microsoft.VisualBasic.FileSystem.Loc%2A>
