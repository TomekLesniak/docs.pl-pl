---
title: Instrukcje „Line” nie są już obsługiwane (Błąd kompilatora Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- bc30830
- vbc30830
helpviewer_keywords:
- BC30830
ms.assetid: 4734bc1d-882e-4555-b498-1f1ec0399d16
ms.openlocfilehash: 4ca1538dbde0d585b7b421d60cde4531c00e9145
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873841"
---
# <a name="line-statements-are-no-longer-supported-visual-basic-compiler-error"></a>Instrukcje „Line” nie są już obsługiwane (Błąd kompilatora Visual Basic)

Instrukcje liniowe nie są już obsługiwane. Funkcja we/wy plików jest dostępna, ponieważ `Microsoft.VisualBasic.FileSystem.LineInput` Funkcja graficzna jest dostępna jako `System.Drawing.Graphics.DrawLine` .  
  
 **Identyfikator błędu:** BC30830  
  
## <a name="to-correct-this-error"></a>Aby poprawić ten błąd  
  
1. W przypadku uzyskiwania dostępu do plików użyj `Microsoft.VisualBasic.FileSystem.LineInput` .  
  
2. Jeśli wykonujesz grafikę, użyj `System.Drawing.Graphics.Drawline` .  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.IO>
- <xref:System.Drawing>
- [Dostęp do plików za pomocą Visual Basic](../../developing-apps/programming/drives-directories-files/file-access.md)
