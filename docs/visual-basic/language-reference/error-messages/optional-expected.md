---
title: Oczekiwano instrukcji „Optional”
ms.date: 07/20/2015
f1_keywords:
- bc30202
- vbc30202
helpviewer_keywords:
- BC30202
ms.assetid: 6f75060c-2db4-4a79-b5d1-5780c09a74cd
ms.openlocfilehash: 9c717cef2052722563e04595ef7a808ea103a75d
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92159823"
---
# <a name="bc30202-optional-expected"></a>BC30202: Oczekiwano instrukcji "optional"

Po argumencie opcjonalnym w deklaracji procedury występuje wymagany argument. Każdy argument po opcjonalnym argumencie musi być również opcjonalny.

 **Identyfikator błędu:** BC30202

## <a name="to-correct-this-error"></a>Aby poprawić ten błąd

- Jeśli argument jest wymagany, przenieś go, aby poprzedzał pierwszy opcjonalny argument na liście argumentów.

- Jeśli argument jest zamierzony jako opcjonalny, użyj `Optional` słowa kluczowego.

## <a name="see-also"></a>Zobacz też

- [Parametry opcjonalne](../../programming-guide/language-features/procedures/optional-parameters.md)
