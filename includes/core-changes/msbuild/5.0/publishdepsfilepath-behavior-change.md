---
ms.openlocfilehash: 077eadb05ab16f5cec8817b89bc771de0c94aefa
ms.sourcegitcommit: aa6d8a90a4f5d8fe0f6e967980b8c98433f05a44
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/16/2020
ms.locfileid: "90679333"
---
### <a name="publishdepsfilepath-behavior-change"></a>PublishDepsFilePath zmiana zachowania

`PublishDepsFilePath`Właściwość programu MSBuild jest pusta dla aplikacji jednoplikowych. Ponadto w przypadku aplikacji innych niż Jednoplikowe *deps.jsw* pliku nie mogą być kopiowane do katalogu wyjściowego do późniejszej kompilacji.

#### <a name="version-introduced"></a>Wprowadzona wersja

5,0

#### <a name="change-description"></a>Zmień opis

W poprzednich wersjach programu .NET `PublishDepsFilePath` Właściwość programu MSBuild jest ścieżką do *deps.jsaplikacji w* pliku w katalogu wyjściowym dla aplikacji nienależących do jednego pliku i ścieżka w katalogu pośrednim dla aplikacji jednoplikowych.

Począwszy od platformy .NET 5,0, `PublishDepsFilePath` jest pusty dla aplikacji jednoplikowych, a nowa `IntermediateDepsFilePath` właściwość określa *deps.jsw* lokalizacji w katalogu pośrednim. Ponadto w przypadku aplikacji innych niż Jednoplikowe *deps.jsw* pliku nie można skopiować do katalogu wyjściowego (czyli ścieżki określonej przez `PublishDepsFilePath` ) do późniejszej kompilacji.

#### <a name="reason-for-change"></a>Przyczyna zmiany

Ta zmiana została wprowadzona z kilku powodów:

- Ze względu na refaktoryzację logiki publikowania w celu obsługi [ulepszonych aplikacji jednoplikowych](https://github.com/dotnet/designs/blob/master/accepted/2020/single-file/design.md) w programie .NET 5.

- W aplikacjach jednoplikowych, aby pomóc w ochronie przed obiektami docelowymi, które próbują ponownie zapisać *deps.jsna* pliku po powiązaniu *deps.jsna, w* ten sposób dyskretnie nie wpływa na aplikację. Z tego powodu `PublishDepsFilePath` jest puste dla aplikacji jednoplikowych.

#### <a name="recommended-action"></a>Zalecana akcja

Cele, które ponownie zapisują *deps.jsw* pliku, powinny zasadniczo używać `IntermediateDepsFilePath` właściwości.

#### <a name="category"></a>Kategoria

MSBuild

#### <a name="affected-apis"></a>Dotyczy interfejsów API

Brak

<!--

#### Affected APIs

Not detectable via API analysis.

-->
