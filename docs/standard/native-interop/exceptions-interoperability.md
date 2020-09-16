---
title: Współdziałanie wyjątków
ms.date: 01/16/2020
ms.technology: dotnet-standard
helpviewer_keywords:
- unmanaged code, exceptions
- exceptions, unmanaged code
- interop, exceptions
- exceptions, interop
ms.openlocfilehash: 90774b5d1b64feb34e01f48708d94f8f841a7c9d
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90550875"
---
# <a name="working-with-interop-exceptions-in-unmanaged-code"></a>Praca z wyjątkami międzyoperacyjnymi w kodzie niezarządzanym

Międzyoperacyjność wyjątku kodu niezarządzanego jest obsługiwana tylko na platformach systemu Windows. Problemy z przenośnością powstają na platformach innych niż Windows. Ponieważ ABI systemu UNIX nie ma definicji obsługi wyjątków, kod zarządzany nie może wiedzieć, jak mechanizmy wyjątków działają w ramach okładek. W związku z tym wyjątki mogą kończyć się wynikiem nieprzewidywalnych zachowań i awarii.

## <a name="setjmplongjmp-behaviors"></a>Zachowania setjmp/longjmp

Funkcje Interop with `setjmp` i języka `longjmp` C nie są obsługiwane. Nie można użyć, `longjmp` Aby pominąć ramki zarządzane.

Aby uzyskać więcej informacji, zobacz [dokumentację longjmp](/cpp/c-runtime-library/reference/longjmp).

## <a name="see-also"></a>Zobacz także

- [Wyjątki](index.md)
- [Współdziałanie z natywnymi bibliotekami](https://www.mono-project.com/docs/advanced/pinvoke/#runtime-exception-propagation)
