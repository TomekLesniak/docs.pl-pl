---
title: Użyj elementu "FilePutObject" zamiast elementu "FilePut" w przypadku używania argumentu typu "Object"
ms.date: 07/20/2015
f1_keywords:
- vbrUseFilePutObject
ms.assetid: d207b9b7-5898-4c13-8b03-9feefac5f726
ms.openlocfilehash: c6ae755ad3eca4b1c50b83049885b6cf66f13c07
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91100337"
---
# <a name="use-fileputobject-instead-of-fileput-when-using-argument-of-type-object"></a>Użyj elementu "FilePutObject" zamiast elementu "FilePut" w przypadku używania argumentu typu "Object"

`FilePut`Metoda zawiera argument typu `Object` . `FilePutObject` należy zamiast tego użyć, `FilePut` Aby uniknąć niejasności.  
  
## <a name="to-correct-this-error"></a>Aby poprawić ten błąd  
  
- Zastąp element `FilePut` pytaniem `FilePutObject`.  
  
- Rzutowanie `Object` argumentu na bardziej konkretny typ.  
  
- Użyj funkcji dostępnych w `My.Computer.FileSystem` obiekcie.  
  
## <a name="see-also"></a>Zobacz także

- [My. Computer. FileSystem](xref:Microsoft.VisualBasic.FileIO.FileSystem)
- [My. Computer. FileSystem. WriteAllBytes](xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.WriteAllBytes%2A)
