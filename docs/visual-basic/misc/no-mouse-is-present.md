---
title: Żadna mysz nie jest obecna
ms.date: 07/20/2015
f1_keywords:
- vbrMouse_NoMouseIsPresent
ms.assetid: 4472fd57-4217-4463-9d3c-dc4a8fe88f1b
ms.openlocfilehash: ceb850d98d29c232da304fbdfaddf5611714ef1a
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91078856"
---
# <a name="no-mouse-is-present"></a>Żadna mysz nie jest obecna

Jedna z właściwości `My.Computer.Mouse` obiektu została wywołana, ale na komputerze nie jest zainstalowany mysz ani port myszy.  
  
## <a name="to-correct-this-error"></a>Aby poprawić ten błąd  
  
- Dodaj `Try...Catch` blok wokół wywołania właściwości `My.Computer.Mouse` obiektu.  
  
     oraz  
  
- Zainstaluj myszą na komputerze.  
  
## <a name="see-also"></a>Zobacz także

- [My. Computer. Mouse](xref:Microsoft.VisualBasic.Devices.Mouse)
- [Obsługa i zgłaszanie wyjątków w programie .NET](../../standard/exceptions/index.md)
- [Try...Catch...Finally, instrukcja](../language-reference/statements/try-catch-finally-statement.md)
