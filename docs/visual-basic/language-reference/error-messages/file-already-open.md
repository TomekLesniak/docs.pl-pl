---
title: Plik jest już otwarty
ms.date: 07/20/2015
f1_keywords:
- vbrID55
ms.assetid: d674a0fb-ef16-4cc2-9da7-709a8a07dbea
ms.openlocfilehash: 97f9e13e6802e793f7c7baf1f03ec51205eb6d42
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874186"
---
# <a name="file-already-open"></a>Plik jest już otwarty

Czasami plik musi być zamknięty, aby `FileOpen` można było wykonać inną lub inną operację. Wśród możliwych przyczyn tego błędu są:  
  
- Operacja trybu sekwencyjnego wyjścia `FileOpen` została wykonana dla pliku, który jest już otwarty  
  
- Instrukcja odwołuje się do otwartego pliku.  
  
## <a name="to-correct-this-error"></a>Aby poprawić ten błąd  
  
1. Zamknij plik przed wykonaniem instrukcji.  
  
## <a name="see-also"></a>Zobacz też

- <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>
