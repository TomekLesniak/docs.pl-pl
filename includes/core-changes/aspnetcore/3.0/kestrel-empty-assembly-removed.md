---
ms.openlocfilehash: 1c9c899d77dd69e185281d98bfec18ce73d80815
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032808"
---
### <a name="kestrel-empty-https-assembly-removed"></a>Kestrel: Usunięto pusty zestaw HTTPS

Zestaw został <xref:Microsoft.AspNetCore.Server.Kestrel.Https?displayProperty=fullName> usunięty.

#### <a name="version-introduced"></a>Wprowadzona wersja

3.0

#### <a name="reason-for-change"></a>Przyczyna zmiany

W ASP.NET Core 2,1 zawartość `Microsoft.AspNetCore.Server.Kestrel.Https` została przeniesiona do lokalizacji <xref:Microsoft.AspNetCore.Server.Kestrel.Core?displayProperty=fullName> . Ta zmiana została wykonana w sposób rozdzielny przy użyciu `[TypeForwardedTo]` atrybutów.

#### <a name="recommended-action"></a>Zalecana akcja

- Biblioteki, do których odwołuje `Microsoft.AspNetCore.Server.Kestrel.Https` się 2,0, powinny aktualizować wszystkie zależności ASP.NET Core do 2,1 lub nowszych. W przeciwnym razie mogą wystąpić przerwy w przypadku załadowania do aplikacji ASP.NET Core 3,0.
- Aplikacje i biblioteki ukierunkowane na ASP.NET Core 2,1 i nowsze powinny usunąć wszystkie bezpośrednie odwołania do `Microsoft.AspNetCore.Server.Kestrel.Https` pakietu NuGet.

#### <a name="category"></a>Kategoria

ASP.NET Core

#### <a name="affected-apis"></a>Dotyczy interfejsów API

Brak

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
