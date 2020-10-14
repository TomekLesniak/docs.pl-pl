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
# <a name="networking-breaking-changes"></a>Zmiany w sieci

Następujące istotne zmiany zostały udokumentowane na tej stronie:

| Zmiana podziału | Wprowadzona wersja |
| - | - |
| [NegotiateStream i SslStream Zezwalaj na kolejne operacje BEGIN](#negotiatestream-and-sslstream-allow-successive-begin-operations) | 5,0 |
| [Gniazdo. LocalEndPoint zostało zaktualizowane po wywołaniu SendToAsync](#socketlocalendpoint-is-updated-after-calling-sendtoasync) | 5,0 |
| [WinHttpHandler usunięte z środowiska uruchomieniowego platformy .NET](#winhttphandler-removed-from-net-runtime) | 5,0 |
| [MulticastOption. Group nie akceptuje wartości null](#multicastoptiongroup-doesnt-accept-a-null-value) | 5,0 |
| [Obsługa ścieżki plików cookie jest teraz zgodna ze specyfikacją RFC 6265](#cookie-path-handling-now-conforms-to-rfc-6265) | 5,0 |
| [Wartość domyślna HttpRequestMessage. Version została zmieniona na 1,1](#default-value-of-httprequestmessageversion-changed-to-11) | 3,0 |
| [Klient WebClient. CancelAsync nie zawsze anuluje natychmiast](#webclientcancelasync-doesnt-always-cancel-immediately) | 2,0 |

## <a name="net-50"></a>.NET 5,0

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

## <a name="net-core-30"></a>.NET Core 3.0

[!INCLUDE[Default value of HttpRequestMessage.Version changed to 1.1](~/includes/core-changes/networking/3.0/httprequestmessage-version-change.md)]

***

## <a name="net-core-20"></a>.NET Core 2.0

[!INCLUDE [behavior-change-webclient-cancelasync](../../../includes/core-changes/networking/2.0/behavior-change-webclient-cancelasync.md)]

***
