---
title: 'Istotna zmiana: PublishDepsFilePath zmiana zachowania'
description: Dowiedz się więcej na temat istotnej zmiany w programie .NET 5,0, w której właściwość MSBuild PublishDepsFilePath jest pusta dla aplikacji jednoplikowych.
ms.date: 09/17/2020
ms.openlocfilehash: 70631beff31aa3388e59f3b79875ef437351451a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761734"
---
# <a name="publishdepsfilepath-behavior-change"></a>PublishDepsFilePath zmiana zachowania

`PublishDepsFilePath`Właściwość programu MSBuild jest pusta dla aplikacji jednoplikowych. Ponadto w przypadku aplikacji innych niż Jednoplikowe *deps.jsw* pliku nie mogą być kopiowane do katalogu wyjściowego do późniejszej kompilacji.

## <a name="version-introduced"></a>Wprowadzona wersja

5,0

## <a name="change-description"></a>Zmień opis

W poprzednich wersjach programu .NET `PublishDepsFilePath` Właściwość programu MSBuild jest ścieżką do *deps.jsaplikacji w* pliku w katalogu wyjściowym dla aplikacji nienależących do jednego pliku i ścieżka w katalogu pośrednim dla aplikacji jednoplikowych.

Począwszy od platformy .NET 5,0, `PublishDepsFilePath` jest pusty dla aplikacji jednoplikowych, a nowa `IntermediateDepsFilePath` właściwość określa *deps.jsw* lokalizacji w katalogu pośrednim. Ponadto w przypadku aplikacji innych niż Jednoplikowe *deps.jsw* pliku nie można skopiować do katalogu wyjściowego (czyli ścieżki określonej przez `PublishDepsFilePath` ) do późniejszej kompilacji.

## <a name="reason-for-change"></a>Przyczyna zmiany

Ta zmiana została wprowadzona z kilku powodów:

- Ze względu na refaktoryzację logiki publikowania w celu obsługi [ulepszonych aplikacji jednoplikowych](https://github.com/dotnet/designs/blob/master/accepted/2020/single-file/design.md) w programie .NET 5.

- W aplikacjach jednoplikowych, aby pomóc w ochronie przed obiektami docelowymi, które próbują ponownie zapisać *deps.jsna* pliku po powiązaniu *deps.jsna, w* ten sposób dyskretnie nie wpływa na aplikację. Z tego powodu `PublishDepsFilePath` jest puste dla aplikacji jednoplikowych.

## <a name="recommended-action"></a>Zalecana akcja

Cele, które ponownie zapisują *deps.jsw* pliku, powinny zasadniczo używać `IntermediateDepsFilePath` właściwości.

## <a name="affected-apis"></a>Dotyczy interfejsów API

Nie dotyczy

<!--

### Affected APIs

Not detectable via API analysis.

### Category

MSBuild

-->
