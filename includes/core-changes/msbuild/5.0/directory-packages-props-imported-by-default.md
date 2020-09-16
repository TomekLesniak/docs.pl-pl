---
ms.openlocfilehash: 4a916a4178535763712ebd58fde1a81e456da0d1
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90538825"
---
### <a name="directorypackagesprops-files-is-imported-by-default"></a>Pliki Directory. Packages. props są importowane domyślnie

Pliki *. props* programu NuGet automatycznie importują plik o nazwie *Directory. Packages. props* , jeśli znajduje się w folderze projektu lub w dowolnym jego elemencie nadrzędnym.

#### <a name="version-introduced"></a>Wprowadzona wersja

5,0 wersja zapoznawcza 8

#### <a name="change-description"></a>Zmień opis

W poprzednich wersjach programu .NET może istnieć plik o nazwie *Directory. Packages. props* w pliku projektu i nie zostanie on automatycznie zaimportowany przez plik *. props* programu NuGet w czasie kompilacji.

Począwszy od platformy .NET 5,0, taki plik *jest* automatycznie importowany, jeśli istnieje w folderze projektu lub w dowolnym z jego elementów nadrzędnych. Jeśli w folderze projektu znajduje się plik o tej nazwie, ten Automatyczny import może zmienić zachowanie kompilacji. Na przykład plik zostanie zaimportowany, ale nie był wcześniej lub kolejność, w której zaimportowano, może ulec zmianie, jeśli zostanie zaimportowany.

#### <a name="reason-for-change"></a>Przyczyna zmiany

Ta zmiana została wprowadzona w celu obsługi [centralnej wersji pakietu](https://github.com/NuGet/Home/wiki/Centrally-managing-NuGet-package-versions) dla programu NuGet.

#### <a name="recommended-action"></a>Zalecana akcja

Zmień nazwę istniejącego *katalogu. Packages. props* , jeśli nie powinien być importowany automatycznie.

#### <a name="category"></a>Kategoria

MSBuild

#### <a name="affected-apis"></a>Dotyczy interfejsów API

Brak

<!--

#### Affected APIs

Not detectable via API analysis.

-->
