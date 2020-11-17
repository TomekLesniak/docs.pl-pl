---
title: Przegląd bibliotek środowiska uruchomieniowego
description: Dowiedz się, co znajduje się w sekcji biblioteki środowiska uruchomieniowego spisu treści.
author: tdykstra
ms.date: 11/12/2020
ms.openlocfilehash: 5a8f888e1778553e2968277738cfef5134f11589
ms.sourcegitcommit: 34968a61e9bac0f6be23ed6ffb837f52d2390c85
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/17/2020
ms.locfileid: "94687895"
---
# <a name="runtime-libraries-overview"></a>Przegląd bibliotek środowiska uruchomieniowego

[Środowisko uruchomieniowe platformy .NET](../core/introduction.md#sdk-and-runtimes), które jest zainstalowane na maszynie do użytku [przez aplikacje zależne od platformy](../core/introduction.md#deployment-models), ma standardowy zestaw klas rozległych, znane jako [biblioteki środowiska uruchomieniowego](glossary.md#runtime), [biblioteki struktury](glossary.md#framework-libraries)lub [Biblioteka klas bazowych (BCL)](glossary.md#bcl). Ponadto istnieją rozszerzenia bibliotek środowiska uruchomieniowego udostępniane w pakietach NuGet.

Te biblioteki zapewniają implementacje dla wielu typów ogólnych i specyficznych dla aplikacji, algorytmów i funkcji narzędzi.

## <a name="runtime-libraries"></a>Biblioteki środowiska uruchomieniowego

Te biblioteki zapewniają podstawowe typy i funkcje narzędziowe, a stanowią podstawę wszystkich innych bibliotek klas platformy .NET. Przykładem jest <xref:System.String?displayProperty=nameWithType> Klasa, która udostępnia interfejsy API do pracy z ciągami. Innym przykładem są [biblioteki serializacji](serialization/index.md).

## <a name="extensions-to-the-runtime-libraries"></a>Rozszerzenia bibliotek środowiska uruchomieniowego

Niektóre biblioteki są udostępniane w pakietach NuGet, a nie dołączone do [udostępnionej struktury](glossary.md#shared-framework)środowiska uruchomieniowego. Przykład:

* [Rejestrowanie](../core/extensions/logging.md)
* [Wstrzykiwanie zależności](../core/extensions/dependency-injection.md)
* [Konfiguracja](../core/extensions/configuration.md)

## <a name="see-also"></a>Zobacz także

* [Wprowadzenie do platformy .NET](../core/introduction.md)
* [Zainstaluj zestaw .NET SDK lub środowisko uruchomieniowe](../core/install/index.yml)
* [Wybierz zainstalowany zestaw .NET SDK lub wersję środowiska uruchomieniowego do użycia](../core/versions/selection.md)
* [Publikowanie aplikacji zależnych od platformy](../core/deploying/index.md#publish-framework-dependent)
