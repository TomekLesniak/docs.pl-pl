---
title: Zła nazwa lub numer pliku
ms.date: 07/20/2015
f1_keywords:
- vbrID52
ms.assetid: d0e96aea-7621-48f6-a78b-5d37d18aaa4e
ms.openlocfilehash: d57a9e78e6ae179d3050e5a92399ca731fa16ba7
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874902"
---
# <a name="bad-file-name-or-number"></a>Zła nazwa lub numer pliku

Wystąpił błąd podczas próby uzyskania dostępu do określonego pliku. Wśród możliwych przyczyn tego błędu są:  
  
- Instrukcja odwołuje się do pliku z nazwą lub numerem pliku, który nie został określony w `FileOpen` instrukcji lub który został określony w instrukcji, `FileOpen` ale został zamknięty.  
  
- Instrukcja odwołuje się do pliku o liczbie poza zakresem numerów plików.  
  
- Instrukcja odwołuje się do nieprawidłowej nazwy lub liczby plików.  
  
## <a name="to-correct-this-error"></a>Aby poprawić ten błąd  
  
1. Upewnij się, że nazwa pliku jest określona w `FileOpen` instrukcji. Należy pamiętać, że jeśli wywołano `FileClose` instrukcję bez argumentów, być może przypadkowo zamknięto wszystkie otwarte pliki.  
  
2. Jeśli kod generuje numery plików algorithmically, upewnij się, że liczby są prawidłowe.  
  
3. Sprawdź nazwy plików, aby upewnić się, że są one zgodne z konwencjami systemu operacyjnego.  
  
## <a name="see-also"></a>Zobacz też

- <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>
- [Visual Basic — Konwencje nazewnictwa](../../programming-guide/program-structure/naming-conventions.md)
