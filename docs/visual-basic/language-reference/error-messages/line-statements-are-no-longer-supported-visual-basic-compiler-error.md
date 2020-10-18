---
title: Instrukcje „Line” nie są już obsługiwane (Błąd kompilatora Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- bc30830
- vbc30830
helpviewer_keywords:
- BC30830
ms.assetid: 4734bc1d-882e-4555-b498-1f1ec0399d16
ms.openlocfilehash: f34095becf321c6cb4b316b6378a2da0107577ba
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162482"
---
# <a name="bc30830-line-statements-are-no-longer-supported"></a>BC30830: instrukcje "line" nie są już obsługiwane

Instrukcje liniowe nie są już obsługiwane. Funkcja we/wy plików jest dostępna, ponieważ `Microsoft.VisualBasic.FileSystem.LineInput` Funkcja graficzna jest dostępna jako `System.Drawing.Graphics.DrawLine` .

 **Identyfikator błędu:** BC30830

## <a name="to-correct-this-error"></a>Aby poprawić ten błąd

- W przypadku uzyskiwania dostępu do plików użyj `Microsoft.VisualBasic.FileSystem.LineInput` .

- Jeśli wykonujesz grafikę, użyj `System.Drawing.Graphics.Drawline` .

## <a name="see-also"></a>Zobacz też

- <xref:System.IO>
- <xref:System.Drawing>
- [Dostęp do plików za pomocą Visual Basic](../../developing-apps/programming/drives-directories-files/file-access.md)
