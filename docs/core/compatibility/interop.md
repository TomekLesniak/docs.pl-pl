---
title: Zmiany dotyczące łamania międzyoperacyjnych
description: Wyświetla listę istotnych zmian w współdziałaniu w oprogramowaniu .NET Core i .NET 5,0 i nowszych.
ms.date: 06/23/2020
ms.openlocfilehash: a38fb1837e565be33f8ae1119480c8f1ae848ab0
ms.sourcegitcommit: b4a46f6d7ebf44c0035627d00924164bcae2db30
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/29/2020
ms.locfileid: "91438037"
---
# <a name="interop-breaking-changes"></a>Zmiany dotyczące łamania międzyoperacyjnych

Następujące istotne zmiany zostały udokumentowane na tej stronie:

| Zmiana podziału | Wprowadzona wersja |
| - | :-: |
| [Rzutowanie OTOKi z `InterfaceIsIInspectable` interfejsem zgłasza PlatformNotSupportedException](#casting-rcw-to-an-interfaceisiinspectable-interface-throws-platformnotsupportedexception) | 5,0 |
| [Brak podwyższenia poziomu sufiksu na platformach innych niż Windows](#no-aw-suffix-probing-on-non-windows-platforms) | 5,0 |
| [Wbudowana obsługa środowiska WinRT jest usuwana z platformy .NET](#built-in-support-for-winrt-is-removed-from-net) | 5,0 |

## <a name="net-50"></a>.NET 5,0

[!INCLUDE [casting-rcw-to-inspectable-interface-throws-exception](../../../includes/core-changes/interop/5.0/casting-rcw-to-inspectable-interface-throws-exception.md)]

***

[!INCLUDE [function-suffix-pinvoke](../../../includes/core-changes/interop/5.0/function-suffix-pinvoke.md)]

***

[!INCLUDE [built-in-support-for-winrt-removed](~/includes/core-changes/interop/5.0/built-in-support-for-winrt-removed.md)]

***
