---
title: Przegląd bibliotek środowiska uruchomieniowego
description: Dowiedz się, co znajduje się w sekcji biblioteki środowiska uruchomieniowego spisu treści.
author: tdykstra
ms.date: 11/10/2020
ms.technology: dotnet-standard
ms.openlocfilehash: 64bbc13f8c3df3c0c9a02fee4560c9ee3fcc5d62
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/11/2020
ms.locfileid: "94507612"
---
# <a name="runtime-libraries-overview"></a>Przegląd bibliotek środowiska uruchomieniowego

[Środowisko uruchomieniowe platformy .NET](../core/introduction.md#sdk-and-runtimes), które jest zainstalowane na maszynie do użytku przez [aplikacje zależne od platformy](../core/introduction.md#deployment-models), ma standardowy zestaw klas rozległych:

* Zestaw podstawowy, uwzględniony w czasie wykonywania i znany jako [biblioteki klas bazowych (BCL)](glossary.md#bcl).
* Kompletny zestaw obejmujący środowisko uruchomieniowe i znane jako biblioteki [środowiska uruchomieniowego](glossary.md#runtime) lub [biblioteki struktury](glossary.md#framework).
* Rozszerzenia bibliotek środowiska uruchomieniowego, które znajdują się w pakietach NuGet.

Te biblioteki zapewniają implementacje dla wielu typów ogólnych i specyficznych dla aplikacji, algorytmów i funkcji narzędzi.

## <a name="base-class-libraries"></a>Biblioteki klas bazowych

BCL udostępnia podstawowe typy i funkcje narzędziowe, a także jest podstawą wszystkich innych bibliotek klas platformy .NET. Przykładem jest <xref:System.String?displayProperty=nameWithType> Klasa, która udostępnia interfejsy API do pracy z ciągami.

## <a name="runtime-libraries"></a>Biblioteki środowiska uruchomieniowego

Znane również jako biblioteki środowiskowe, biblioteki środowiska uruchomieniowego kompilują się w BCL, aby zapewnić interfejsy API narzędzi dla typowych zadań. Przykładem są [biblioteki serializacji](serialization/index.md).

## <a name="extensions-to-the-runtime-libraries"></a>Rozszerzenia bibliotek środowiska uruchomieniowego

Niektóre biblioteki środowiska uruchomieniowego są udostępniane w pakietach NuGet, a nie wbudowane w środowisko uruchomieniowe, które jest instalowane dla aplikacji zależnych od platformy. Przykładem jest [interfejs API rejestrowania programu .NET](../core/extensions/logging.md).

## <a name="see-also"></a>Zobacz także

* [Wprowadzenie do platformy .NET](../core/introduction.md)
* [Zainstaluj zestaw .NET SDK lub środowisko uruchomieniowe](../core/install/index.yml)
* [Wybierz zainstalowany zestaw .NET SDK lub wersję środowiska uruchomieniowego do użycia](../core/versions/selection.md)
* [Publikowanie aplikacji zależnych od platformy](../core/deploying/index.md#publish-framework-dependent)
