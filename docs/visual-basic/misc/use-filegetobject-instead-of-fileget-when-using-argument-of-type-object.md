---
title: Użyj elementu "FileGetObject" zamiast elementu "FileGet" w przypadku używania argumentu typu "Object"
ms.date: 07/20/2015
ms.assetid: 090b8088-895a-482a-9362-606596bac304
ms.openlocfilehash: 318a0772a99aa86d9a4633e6021f77616a43fc7e
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91059408"
---
# <a name="use-filegetobject-instead-of-fileget-when-using-argument-of-type-object"></a>Użyj elementu "FileGetObject" zamiast elementu "FileGet" w przypadku używania argumentu typu "Object"

`FileGet`Metoda zawiera argument typu `Object` . `FileGetObject` należy zamiast tego użyć, `FileGet` Aby uniknąć niejasności.  
  
 Zwróć uwagę, że funkcje oferowane przez program `My.Computer.Filesystem` oferują większą łatwość użytkowania i wydajności niż `FileGet` lub `FileGetObject` .  
  
## <a name="to-correct-this-error"></a>Aby poprawić ten błąd  
  
1. Zastąp element `FileGet` pytaniem `FileGetObject`.  
  
2. Rzutowanie `Object` argumentu na bardziej konkretny typ.  
  
## <a name="see-also"></a>Zobacz także

- [My. Computer. FileSystem](xref:Microsoft.VisualBasic.FileIO.FileSystem)
