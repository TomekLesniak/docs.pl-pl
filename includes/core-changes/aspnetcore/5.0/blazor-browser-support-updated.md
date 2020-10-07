---
ms.openlocfilehash: 584014572ab799e1e3ab2f02c9fbf4fe6b0c17e7
ms.sourcegitcommit: 636af37170ae75a11c4f7d1ecd770820e7dfe7bd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/07/2020
ms.locfileid: "91804932"
---
### <a name="blazor-updated-browser-support"></a>Blazor: Zaktualizowano obsługę przeglądarki

W ASP.NET Core 5,0 wprowadzono [nowe funkcje Blazor](https://github.com/dotnet/aspnetcore/issues/21514), a niektóre z nich są niezgodne ze starszymi przeglądarkami. Lista przeglądarek obsługiwanych przez Blazor w ASP.NET Core 5,0 została odpowiednio zaktualizowana.

Aby zapoznać się z omówieniem, zobacz sekcję dotyczącą usługi GitHub wydaj [/aspnetcore # 26475](https://github.com/dotnet/aspnetcore/issues/26475).

#### <a name="version-introduced"></a>Wprowadzona wersja

5,0

#### <a name="old-behavior"></a>Stare zachowanie

Serwer Blazor obsługuje program Microsoft Internet Explorer 11 z odpowiednimi wypełnieniami. Blazor Server i Blazor webassembly działają również w [starszej wersji programu Microsoft Edge](https://support.microsoft.com/help/4533505/what-is-microsoft-edge-legacy).

#### <a name="new-behavior"></a>Nowe zachowanie

Serwer Blazor w ASP.NET Core 5,0 nie jest obsługiwany przez program Microsoft Internet Explorer 11. Blazor Server i Blazor webassembly nie działają w pełni ze starszymi wersjami programu Microsoft Edge.

#### <a name="reason-for-change"></a>Przyczyna zmiany

Nowe funkcje Blazor w ASP.NET Core 5,0 są niezgodne ze starszymi przeglądarkami, a korzystanie z tych starszych przeglądarek jest zmniejszane. Więcej informacji można znaleźć w następujących zasobach:

* [Obsługa systemu Windows dla starszej wersji programu Microsoft Edge kończy się również 9 marca 2021](https://support.microsoft.com/help/4533505/what-is-microsoft-edge-legacy)
* [Microsoft 365 aplikacje i usługi zakończą obsługę programu Microsoft Internet Explorer 11 do 17 sierpnia 2021](/lifecycle/announcements/m365-ie11-microsoft-edge-legacy)

#### <a name="recommended-action"></a>Zalecana akcja

Uaktualnij te starsze przeglądarki do [nowej, opartej na formacie chromu Microsoft Edge](https://www.microsoft.com/edge). W przypadku aplikacji Blazor, które muszą obsługiwać te starsze przeglądarki, użyj ASP.NET Core 3,1. Lista obsługiwanych przeglądarek dla Blazor w ASP.NET Core 3,1 nie zmieniła się i została udokumentowana na [obsługiwanych platformach](/aspnet/core/blazor/supported-platforms?view=aspnetcore-3.1).

#### <a name="category"></a>Kategoria

ASP.NET Core

#### <a name="affected-apis"></a>Dotyczy interfejsów API

Brak

<!--

#### Affected APIs

Not detectable via API analysis

-->
