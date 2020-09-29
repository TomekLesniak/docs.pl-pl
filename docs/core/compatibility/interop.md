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
# <a name="interop-breaking-changes"></a><span data-ttu-id="84326-103">Zmiany dotyczące łamania międzyoperacyjnych</span><span class="sxs-lookup"><span data-stu-id="84326-103">Interop breaking changes</span></span>

<span data-ttu-id="84326-104">Następujące istotne zmiany zostały udokumentowane na tej stronie:</span><span class="sxs-lookup"><span data-stu-id="84326-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="84326-105">Zmiana podziału</span><span class="sxs-lookup"><span data-stu-id="84326-105">Breaking change</span></span> | <span data-ttu-id="84326-106">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="84326-106">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="84326-107">Rzutowanie OTOKi z `InterfaceIsIInspectable` interfejsem zgłasza PlatformNotSupportedException</span><span class="sxs-lookup"><span data-stu-id="84326-107">Casting RCW to an `InterfaceIsIInspectable` interface throws PlatformNotSupportedException</span></span>](#casting-rcw-to-an-interfaceisiinspectable-interface-throws-platformnotsupportedexception) | <span data-ttu-id="84326-108">5,0</span><span class="sxs-lookup"><span data-stu-id="84326-108">5.0</span></span> |
| [<span data-ttu-id="84326-109">Brak podwyższenia poziomu sufiksu na platformach innych niż Windows</span><span class="sxs-lookup"><span data-stu-id="84326-109">No A/W suffix probing on non-Windows platforms</span></span>](#no-aw-suffix-probing-on-non-windows-platforms) | <span data-ttu-id="84326-110">5,0</span><span class="sxs-lookup"><span data-stu-id="84326-110">5.0</span></span> |
| [<span data-ttu-id="84326-111">Wbudowana obsługa środowiska WinRT jest usuwana z platformy .NET</span><span class="sxs-lookup"><span data-stu-id="84326-111">Built-in support for WinRT is removed from .NET</span></span>](#built-in-support-for-winrt-is-removed-from-net) | <span data-ttu-id="84326-112">5,0</span><span class="sxs-lookup"><span data-stu-id="84326-112">5.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="84326-113">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="84326-113">.NET 5.0</span></span>

[!INCLUDE [casting-rcw-to-inspectable-interface-throws-exception](../../../includes/core-changes/interop/5.0/casting-rcw-to-inspectable-interface-throws-exception.md)]

***

[!INCLUDE [function-suffix-pinvoke](../../../includes/core-changes/interop/5.0/function-suffix-pinvoke.md)]

***

[!INCLUDE [built-in-support-for-winrt-removed](~/includes/core-changes/interop/5.0/built-in-support-for-winrt-removed.md)]

***
