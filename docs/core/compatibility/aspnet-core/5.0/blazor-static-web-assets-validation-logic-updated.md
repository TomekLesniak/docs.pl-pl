---
title: 'Nieprzerwana zmiana: Blazor: Zaktualizowano logikę walidacji dla statycznych zasobów sieci Web'
description: 'Dowiedz się więcej o istotnej zmianie w ASP.NET Core 5,0 zatytułowanej Blazor: Zaktualizowano logikę walidacji dla statycznych zasobów sieci Web'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: f201818c0130739e8da4f42e7b1f3a1987f70d1c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761476"
---
# <a name="blazor-updated-validation-logic-for-static-web-assets"></a>Blazor: Zaktualizowano logikę walidacji dla statycznych zasobów sieci Web

Wystąpił problem podczas weryfikacji konfliktu dla statycznych zasobów sieci Web w ASP.NET Core 3,1 i Blazor webassembly 3,2. Problem:

* Uniemożliwiło prawidłowe wykrywanie konfliktów między zasobami i zasobami hosta z bibliotek klas Razor (RCLs) i Blazor aplikacji webassembly.
* W większości ma wpływ na aplikacje Blazor webassembly, ponieważ domyślnie statyczne zasoby sieci Web w RCLs są obsługiwane pod `_content/$(PackageId)` prefiksem.

## <a name="version-introduced"></a>Wprowadzona wersja

5,0

## <a name="old-behavior"></a>Stare zachowanie

Podczas opracowywania RCL statyczne zasoby sieci Web mogą zostać zastąpione w trybie dyskretnym zasobami projektu hosta na tym samym ścieżka hosta. Rozważmy RCL, który definiuje statyczny element zawartości sieci Web, który ma być obsługiwany w */folder/file.txt*. Jeśli host umieścił plik w *katalogu wwwroot/folder/file.txt*, plik na serwerze dyskretnie overrode plik w aplikacji RCL lub Blazor webassembly.

## <a name="new-behavior"></a>Nowe zachowanie

ASP.NET Core prawidłowo wykrywane, gdy ten problem wystąpi. Informuje użytkownika o konflikcie, dzięki czemu można wykonać odpowiednie działania.

## <a name="reason-for-change"></a>Przyczyna zmiany

Statyczne zasoby sieci Web nie były zamierzone dla plików na hoście *wwwroot* projektu. Umożliwienie przesłania tych plików może prowadzić do błędów, które są trudne do zdiagnozowania. Wynikiem mogą być niezdefiniowane zmiany zachowania w opublikowanych aplikacjach.

## <a name="recommended-action"></a>Zalecana akcja

Domyślnie nie ma powodów, dla których plik RCL powoduje konflikt z plikiem na hoście. Pliki RCL są poprzedzone prefiksem `_content/${PackageId}` . Pliki zestawu webassembly Blazor są umieszczane w katalogu głównym przestrzeni adresów URL hosta, co ułatwia konflikty. Na przykład aplikacje webassembly Blazor zawierają plik *favicon. ico* , który host może również znajdować się w folderze *wwwroot* .

Jeśli źródłem konfliktu jest plik RCL, często oznacza to, że kod kopiuje zasoby z biblioteki do folderu *wwwroot* projektu. Pisanie kodu w celu skopiowania plików obniża podstawowe cele statycznych zasobów internetowych. Ten cel ma na celu uzyskanie aktualizacji w przeglądarce, gdy zawartość jest aktualizowana bez konieczności wyzwalania nowej kompilacji.

Możesz zachować takie zachowanie i zachować plik na hoście. Aby to zrobić, usuń plik z listy statycznych zasobów internetowych z niestandardowym elementem docelowym programu MSBuild.

Aby użyć pliku RCL lub pliku aplikacji webassembly Blazor zamiast pliku projektu hosta, usuń plik z projektu hosta.

## <a name="affected-apis"></a>Dotyczy interfejsów API

Brak

<!--

### Category

ASP.NET Core

### Affected APIs

Not detectable via API analysis

-->
