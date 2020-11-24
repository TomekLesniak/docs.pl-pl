---
title: Zmiany w sieci
description: Wyświetla listę istotnych zmian w sieci w programie .NET Core 2,0 i 3,0.
ms.date: 05/05/2020
ms.openlocfilehash: 761c6481888bcb8e91f7b4212355aca067632495
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95689215"
---
# <a name="networking-breaking-changes-in-net-core-20-and-30"></a><span data-ttu-id="593f3-103">Wprowadzanie zmian w sieci w programie .NET Core 2,0 i 3,0</span><span class="sxs-lookup"><span data-stu-id="593f3-103">Networking breaking changes in .NET Core 2.0 and 3.0</span></span>

<span data-ttu-id="593f3-104">Następujące istotne zmiany zostały udokumentowane na tej stronie:</span><span class="sxs-lookup"><span data-stu-id="593f3-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="593f3-105">Zmiana podziału</span><span class="sxs-lookup"><span data-stu-id="593f3-105">Breaking change</span></span> | <span data-ttu-id="593f3-106">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="593f3-106">Introduced version</span></span> |
| - | - |
| [<span data-ttu-id="593f3-107">Wartość domyślna HttpRequestMessage. Version została zmieniona na 1,1</span><span class="sxs-lookup"><span data-stu-id="593f3-107">Default value of HttpRequestMessage.Version changed to 1.1</span></span>](#default-value-of-httprequestmessageversion-changed-to-11) | <span data-ttu-id="593f3-108">3.0</span><span class="sxs-lookup"><span data-stu-id="593f3-108">3.0</span></span> |
| [<span data-ttu-id="593f3-109">Klient WebClient. CancelAsync nie zawsze anuluje natychmiast</span><span class="sxs-lookup"><span data-stu-id="593f3-109">WebClient.CancelAsync doesn't always cancel immediately</span></span>](#webclientcancelasync-doesnt-always-cancel-immediately) | <span data-ttu-id="593f3-110">2,0</span><span class="sxs-lookup"><span data-stu-id="593f3-110">2.0</span></span> |

## <a name="net-core-30"></a><span data-ttu-id="593f3-111">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="593f3-111">.NET Core 3.0</span></span>

[!INCLUDE[Default value of HttpRequestMessage.Version changed to 1.1](~/includes/core-changes/networking/3.0/httprequestmessage-version-change.md)]

***

## <a name="net-core-20"></a><span data-ttu-id="593f3-112">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="593f3-112">.NET Core 2.0</span></span>

[!INCLUDE [behavior-change-webclient-cancelasync](../../../includes/core-changes/networking/2.0/behavior-change-webclient-cancelasync.md)]

***
