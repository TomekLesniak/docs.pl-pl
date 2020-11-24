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
# <a name="networking-breaking-changes-in-net-core-20-and-30"></a>Wprowadzanie zmian w sieci w programie .NET Core 2,0 i 3,0

Następujące istotne zmiany zostały udokumentowane na tej stronie:

| Zmiana podziału | Wprowadzona wersja |
| - | - |
| [Wartość domyślna HttpRequestMessage. Version została zmieniona na 1,1](#default-value-of-httprequestmessageversion-changed-to-11) | 3.0 |
| [Klient WebClient. CancelAsync nie zawsze anuluje natychmiast](#webclientcancelasync-doesnt-always-cancel-immediately) | 2,0 |

## <a name="net-core-30"></a>.NET Core 3.0

[!INCLUDE[Default value of HttpRequestMessage.Version changed to 1.1](~/includes/core-changes/networking/3.0/httprequestmessage-version-change.md)]

***

## <a name="net-core-20"></a>.NET Core 2.0

[!INCLUDE [behavior-change-webclient-cancelasync](../../../includes/core-changes/networking/2.0/behavior-change-webclient-cancelasync.md)]

***
