---
title: 'Istotna zmiana: pliki Directory. Packages. props są importowane domyślnie'
description: Dowiedz się więcej o istotnej zmianie w programie .NET 5,0, gdzie pliki. props programu NuGet są automatycznie importowane plik o nazwie Directory. Packages. props, jeśli znajduje się w folderze projektu.
ms.date: 09/17/2020
ms.openlocfilehash: ee8a2999b801e81750d96a0bc985e3c8169224a9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761459"
---
# <a name="directorypackagesprops-files-is-imported-by-default"></a>Pliki Directory. Packages. props są importowane domyślnie

Pliki *. props* programu NuGet automatycznie importują plik o nazwie *Directory. Packages. props* , jeśli znajduje się w folderze projektu lub w dowolnym jego elemencie nadrzędnym.

## <a name="version-introduced"></a>Wprowadzona wersja

5,0

## <a name="change-description"></a>Zmień opis

W poprzednich wersjach programu .NET może istnieć plik o nazwie *Directory. Packages. props* w pliku projektu i nie zostanie on automatycznie zaimportowany przez plik *. props* programu NuGet w czasie kompilacji.

Począwszy od platformy .NET 5,0, taki plik *jest* automatycznie importowany, jeśli istnieje w folderze projektu lub w dowolnym z jego elementów nadrzędnych. Jeśli w folderze projektu znajduje się plik o tej nazwie, ten Automatyczny import może zmienić zachowanie kompilacji. Na przykład plik zostanie zaimportowany, ale nie był wcześniej lub kolejność, w której zaimportowano, może ulec zmianie, jeśli zostanie zaimportowany.

## <a name="reason-for-change"></a>Przyczyna zmiany

Ta zmiana została wprowadzona w celu obsługi [centralnej wersji pakietu](https://github.com/NuGet/Home/wiki/Centrally-managing-NuGet-package-versions) dla programu NuGet.

## <a name="recommended-action"></a>Zalecana akcja

Zmień nazwę istniejącego *katalogu. Packages. props* , jeśli nie powinien być importowany automatycznie.

## <a name="affected-apis"></a>Dotyczy interfejsów API

Nie dotyczy

<!--

### Affected APIs

Not detectable via API analysis.

### Category

MSBuild

-->
