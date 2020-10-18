---
title: Plik jest już otwarty
ms.date: 07/20/2015
f1_keywords:
- vbrID55
ms.assetid: d674a0fb-ef16-4cc2-9da7-709a8a07dbea
ms.openlocfilehash: ce8f8bf96d7355e45b2df82e8a131472c2ed2367
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162755"
---
# <a name="file-already-open"></a>Plik jest już otwarty

Czasami plik musi być zamknięty, aby `FileOpen` można było wykonać inną lub inną operację. Wśród możliwych przyczyn tego błędu są:

- Operacja trybu sekwencyjnego wyjścia `FileOpen` została wykonana dla pliku, który jest już otwarty

- Instrukcja odwołuje się do otwartego pliku.

## <a name="to-correct-this-error"></a>Aby poprawić ten błąd

- Zamknij plik przed wykonaniem instrukcji.

## <a name="see-also"></a>Zobacz też

- <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>
