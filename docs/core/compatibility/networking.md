---
title: Zmiany w sieci
description: Wyświetla listę istotnych zmian w sieci w programie .NET Core.
ms.date: 05/05/2020
ms.openlocfilehash: fdbd3f3bdcae5048b4f01e4d827f8a0e876c5c15
ms.sourcegitcommit: 39b1d5f2978be15409c189a66ab30781d9082cd8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/14/2020
ms.locfileid: "92050528"
---
# <a name="networking-breaking-changes"></a><span data-ttu-id="eb954-103">Zmiany w sieci</span><span class="sxs-lookup"><span data-stu-id="eb954-103">Networking breaking changes</span></span>

<span data-ttu-id="eb954-104">Następujące istotne zmiany zostały udokumentowane na tej stronie:</span><span class="sxs-lookup"><span data-stu-id="eb954-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="eb954-105">Zmiana podziału</span><span class="sxs-lookup"><span data-stu-id="eb954-105">Breaking change</span></span> | <span data-ttu-id="eb954-106">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="eb954-106">Introduced version</span></span> |
| - | - |
| [<span data-ttu-id="eb954-107">NegotiateStream i SslStream Zezwalaj na kolejne operacje BEGIN</span><span class="sxs-lookup"><span data-stu-id="eb954-107">NegotiateStream and SslStream allow successive Begin operations</span></span>](#negotiatestream-and-sslstream-allow-successive-begin-operations) | <span data-ttu-id="eb954-108">5,0</span><span class="sxs-lookup"><span data-stu-id="eb954-108">5.0</span></span> |
| [<span data-ttu-id="eb954-109">Gniazdo. LocalEndPoint zostało zaktualizowane po wywołaniu SendToAsync</span><span class="sxs-lookup"><span data-stu-id="eb954-109">Socket.LocalEndPoint is updated after calling SendToAsync</span></span>](#socketlocalendpoint-is-updated-after-calling-sendtoasync) | <span data-ttu-id="eb954-110">5,0</span><span class="sxs-lookup"><span data-stu-id="eb954-110">5.0</span></span> |
| [<span data-ttu-id="eb954-111">WinHttpHandler usunięte z środowiska uruchomieniowego platformy .NET</span><span class="sxs-lookup"><span data-stu-id="eb954-111">WinHttpHandler removed from .NET runtime</span></span>](#winhttphandler-removed-from-net-runtime) | <span data-ttu-id="eb954-112">5,0</span><span class="sxs-lookup"><span data-stu-id="eb954-112">5.0</span></span> |
| [<span data-ttu-id="eb954-113">MulticastOption. Group nie akceptuje wartości null</span><span class="sxs-lookup"><span data-stu-id="eb954-113">MulticastOption.Group doesn't accept a null value</span></span>](#multicastoptiongroup-doesnt-accept-a-null-value) | <span data-ttu-id="eb954-114">5,0</span><span class="sxs-lookup"><span data-stu-id="eb954-114">5.0</span></span> |
| [<span data-ttu-id="eb954-115">Obsługa ścieżki plików cookie jest teraz zgodna ze specyfikacją RFC 6265</span><span class="sxs-lookup"><span data-stu-id="eb954-115">Cookie Path handling now conforms to RFC 6265</span></span>](#cookie-path-handling-now-conforms-to-rfc-6265) | <span data-ttu-id="eb954-116">5,0</span><span class="sxs-lookup"><span data-stu-id="eb954-116">5.0</span></span> |
| [<span data-ttu-id="eb954-117">Wartość domyślna HttpRequestMessage. Version została zmieniona na 1,1</span><span class="sxs-lookup"><span data-stu-id="eb954-117">Default value of HttpRequestMessage.Version changed to 1.1</span></span>](#default-value-of-httprequestmessageversion-changed-to-11) | <span data-ttu-id="eb954-118">3,0</span><span class="sxs-lookup"><span data-stu-id="eb954-118">3.0</span></span> |
| [<span data-ttu-id="eb954-119">Klient WebClient. CancelAsync nie zawsze anuluje natychmiast</span><span class="sxs-lookup"><span data-stu-id="eb954-119">WebClient.CancelAsync doesn't always cancel immediately</span></span>](#webclientcancelasync-doesnt-always-cancel-immediately) | <span data-ttu-id="eb954-120">2,0</span><span class="sxs-lookup"><span data-stu-id="eb954-120">2.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="eb954-121">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="eb954-121">.NET 5.0</span></span>

[!INCLUDE [negotiatestream-sslstream-dont-fail-on-successive-begin-calls](../../../includes/core-changes/networking/5.0/negotiatestream-sslstream-dont-fail-on-successive-begin-calls.md)]

***

[!INCLUDE [localendpoint-updated-on-sendtoasync](../../../includes/core-changes/networking/5.0/localendpoint-updated-on-sendtoasync.md)]

***

[!INCLUDE [winhttphandler-removed-from-runtime](../../../includes/core-changes/networking/5.0/winhttphandler-removed-from-runtime.md)]

***

[!INCLUDE [multicastoption-group-doesnt-accept-null](../../../includes/core-changes/networking/5.0/multicastoption-group-doesnt-accept-null.md)]

***

[!INCLUDE [cookie-path-conforms-to-rfc6265](../../../includes/core-changes/networking/5.0/cookie-path-conforms-to-rfc6265.md)]

***

## <a name="net-core-30"></a><span data-ttu-id="eb954-122">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="eb954-122">.NET Core 3.0</span></span>

[!INCLUDE[Default value of HttpRequestMessage.Version changed to 1.1](~/includes/core-changes/networking/3.0/httprequestmessage-version-change.md)]

***

## <a name="net-core-20"></a><span data-ttu-id="eb954-123">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="eb954-123">.NET Core 2.0</span></span>

[!INCLUDE [behavior-change-webclient-cancelasync](../../../includes/core-changes/networking/2.0/behavior-change-webclient-cancelasync.md)]

***
