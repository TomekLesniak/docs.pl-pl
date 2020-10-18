---
title: Klasa obiektu delegowanego „<classname>” nie ma metody Invoke, dlatego wyrażenie tego typu nie może być elementem docelowym wywołania metody
ms.date: 07/20/2015
f1_keywords:
- vbc30220
- bc30220
helpviewer_keywords:
- BC30220
ms.assetid: 6be0d61c-f2f9-4f9b-ab90-8871a0d7206d
ms.openlocfilehash: 4e0fc61c7356008755134f670fa1fab0165cfd48
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162794"
---
# <a name="bc30220-delegate-class-classname-has-no-invoke-method-so-an-expression-of-this-type-cannot-be-the-target-of-a-method-call"></a>BC30220: Klasa delegata " \<classname> " nie ma metody Invoke, dlatego wyrażenie tego typu nie może być elementem docelowym wywołania metody

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
