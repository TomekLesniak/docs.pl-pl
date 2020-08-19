---
title: Zmiany w sieci
description: Wyświetla listę istotnych zmian w sieci w programie .NET Core.
ms.date: 05/05/2020
ms.openlocfilehash: 5d27f9663a2c1b79610ab002a03beeafa8b2818e
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/18/2020
ms.locfileid: "88557970"
---
# <a name="networking-breaking-changes"></a><span data-ttu-id="e710f-103">Zmiany w sieci</span><span class="sxs-lookup"><span data-stu-id="e710f-103">Networking breaking changes</span></span>

<span data-ttu-id="e710f-104">Następujące istotne zmiany zostały udokumentowane na tej stronie:</span><span class="sxs-lookup"><span data-stu-id="e710f-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="e710f-105">Zmiana podziału</span><span class="sxs-lookup"><span data-stu-id="e710f-105">Breaking change</span></span> | <span data-ttu-id="e710f-106">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="e710f-106">Introduced version</span></span> |
| - | - |
| [<span data-ttu-id="e710f-107">MulticastOption. Group nie akceptuje wartości null</span><span class="sxs-lookup"><span data-stu-id="e710f-107">MulticastOption.Group doesn't accept a null value</span></span>](#multicastoptiongroup-doesnt-accept-a-null-value) | <span data-ttu-id="e710f-108">5.0</span><span class="sxs-lookup"><span data-stu-id="e710f-108">5.0</span></span> |
| [<span data-ttu-id="e710f-109">Wartość domyślna HttpRequestMessage. Version została zmieniona na 1,1</span><span class="sxs-lookup"><span data-stu-id="e710f-109">Default value of HttpRequestMessage.Version changed to 1.1</span></span>](#default-value-of-httprequestmessageversion-changed-to-11) | <span data-ttu-id="e710f-110">3.0</span><span class="sxs-lookup"><span data-stu-id="e710f-110">3.0</span></span> |
| [<span data-ttu-id="e710f-111">Klient WebClient. CancelAsync nie zawsze anuluje natychmiast</span><span class="sxs-lookup"><span data-stu-id="e710f-111">WebClient.CancelAsync doesn't always cancel immediately</span></span>](#webclientcancelasync-doesnt-always-cancel-immediately) | <span data-ttu-id="e710f-112">2,0</span><span class="sxs-lookup"><span data-stu-id="e710f-112">2.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="e710f-113">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="e710f-113">.NET 5.0</span></span>

[!INCLUDE [multicastoption-group-doesnt-accept-null](../../../includes/core-changes/networking/5.0/multicastoption-group-doesnt-accept-null.md)]

***

## <a name="net-core-30"></a><span data-ttu-id="e710f-114">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="e710f-114">.NET Core 3.0</span></span>

[!INCLUDE[Default value of HttpRequestMessage.Version changed to 1.1](~/includes/core-changes/networking/3.0/httprequestmessage-version-change.md)]

***

## <a name="net-core-20"></a><span data-ttu-id="e710f-115">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="e710f-115">.NET Core 2.0</span></span>

[!INCLUDE [behavior-change-webclient-cancelasync](../../../includes/core-changes/networking/2.0/behavior-change-webclient-cancelasync.md)]

***
