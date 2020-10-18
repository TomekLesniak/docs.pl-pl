---
title: Nie można załadować informacji dla klasy „<classname>”
ms.date: 07/20/2015
f1_keywords:
- vbc30712
- bc30712
helpviewer_keywords:
- BC30712
ms.assetid: c7ffbd6d-05c6-4261-b44b-1bcd521bb350
ms.openlocfilehash: 05c3303db90a396479bc396c5c2395c3afbb59ae
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92161611"
---
# <a name="bc30712-unable-to-load-information-for-class-classname"></a>BC30712: nie można załadować informacji dla klasy " \<classname> "

Wykonano odwołanie do klasy, która jest niedostępna.

 **Identyfikator błędu:** BC30712

## <a name="to-correct-this-error"></a>Aby poprawić ten błąd

1. Sprawdź, czy Klasa jest zdefiniowana i czy nazwa została wpisana poprawnie.

2. Spróbuj uzyskać dostęp do jednego z elementów członkowskich zadeklarowanych w module. W niektórych przypadkach środowisko debugowania nie może zlokalizować elementów członkowskich, ponieważ moduły, w których są zadeklarowane, nie zostały jeszcze załadowane.

## <a name="see-also"></a>Zobacz też

- [Debugowanie w Visual Studio](/visualstudio/debugger/debugger-feature-tour)
