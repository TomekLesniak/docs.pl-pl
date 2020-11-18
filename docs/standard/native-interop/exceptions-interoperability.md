---
title: Współdziałanie wyjątków
ms.date: 01/16/2020
helpviewer_keywords:
- unmanaged code, exceptions
- exceptions, unmanaged code
- interop, exceptions
- exceptions, interop
ms.openlocfilehash: db7c9943c298607aa91a4bd08ddc12bbafc872be
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2020
ms.locfileid: "94830626"
---
# <a name="working-with-interop-exceptions-in-unmanaged-code"></a>Praca z wyjątkami międzyoperacyjnymi w kodzie niezarządzanym

Międzyoperacyjność wyjątku kodu niezarządzanego jest obsługiwana tylko na platformach systemu Windows. Problemy z przenośnością powstają na platformach innych niż Windows. Ponieważ ABI systemu UNIX nie ma definicji obsługi wyjątków, kod zarządzany nie może wiedzieć, jak mechanizmy wyjątków działają w ramach okładek. W związku z tym wyjątki mogą kończyć się wynikiem nieprzewidywalnych zachowań i awarii.

## <a name="setjmplongjmp-behaviors"></a>Zachowania setjmp/longjmp

Funkcje Interop with `setjmp` i języka `longjmp` C nie są obsługiwane. Nie można użyć, `longjmp` Aby pominąć ramki zarządzane.

Aby uzyskać więcej informacji, zobacz [dokumentację longjmp](/cpp/c-runtime-library/reference/longjmp).

## <a name="see-also"></a>Zobacz także

- [Wyjątki](index.md)
- [Współdziałanie z natywnymi bibliotekami](https://www.mono-project.com/docs/advanced/pinvoke/#runtime-exception-propagation)
