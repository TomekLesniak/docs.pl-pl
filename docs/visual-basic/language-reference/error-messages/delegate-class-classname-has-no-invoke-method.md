---
title: Klasa obiektu delegowanego „<classname>” nie ma metody Invoke, dlatego wyrażenie tego typu nie może być elementem docelowym wywołania metody
ms.date: 07/20/2015
f1_keywords:
- vbc30220
- bc30220
helpviewer_keywords:
- BC30220
ms.assetid: 6be0d61c-f2f9-4f9b-ab90-8871a0d7206d
ms.openlocfilehash: e6ad06262806088347c94b3040b743618a3b3695
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874492"
---
# <a name="delegate-class-classname-has-no-invoke-method-so-an-expression-of-this-type-cannot-be-the-target-of-a-method-call"></a>Klasa obiektu delegowanego „\<classname>” nie ma metody Invoke, dlatego wyrażenie tego typu nie może być elementem docelowym wywołania metody

Wywołanie `Invoke` za pomocą delegata nie powiodło się `Invoke` , ponieważ nie jest zaimplementowany w klasie delegata.  
  
 **Identyfikator błędu:** BC30220  
  
## <a name="to-correct-this-error"></a>Aby poprawić ten błąd  
  
1. Upewnij się, że wystąpienie klasy Delegate zostało utworzone z `Dim` instrukcją i że procedura została przypisana do wystąpienia delegata z `AddressOf` operatorem.  
  
2. Znajdź kod implementujący klasę delegata i upewnij się, że implementuje `Invoke` procedurę.  
  
## <a name="see-also"></a>Zobacz też

- [Delegaci](../../programming-guide/language-features/delegates/index.md)
- [Delegate — Instrukcja](../statements/delegate-statement.md)
- [AddressOf, operator](../operators/addressof-operator.md)
- [Dim, instrukcja](../statements/dim-statement.md)
