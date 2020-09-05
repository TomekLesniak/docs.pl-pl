---
ms.openlocfilehash: 904a6abee2b4b2cf2f5727fb70e286c8a1a592c4
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497279"
---
### <a name="aspnet-validationcontextmembername-is-not-null-when-using-custom-dataannotationsvalidationattribute"></a>ASP.NET ValidationContext. MemberName nie ma wartości NULL w przypadku używania niestandardowych elementów DataAnnotation. ValidationAttribute

#### <a name="details"></a>Szczegóły

W .NET Framework 4.7.2 i starszych wersjach, w przypadku użycia niestandardowej <xref:System.ComponentModel.DataAnnotations.ValidationAttribute?displayProperty=nameWithType> <xref:System.ComponentModel.DataAnnotations.ValidationContext.MemberName?displayProperty=nameWithType> Właściwość zwraca `null` . W wersji .NET Framework 4,8 wcześniejszej niż aktualizacja 2019 października zwróci nazwę elementu członkowskiego. Począwszy od [.NET Framework października 2019 wersji zapoznawczej jakości](https://devblogs.microsoft.com/dotnet/net-framework-october-2019-preview-of-quality-rollup/) dla .NET Framework 4,8, domyślnie zwraca wartość `null` , ale można zrezygnować z zwracania nazwy elementu członkowskiego.

#### <a name="suggestion"></a>Sugestia

Dodaj następujące ustawienie do pliku *web.config* , aby Właściwość zwracała nazwę elementu członkowskiego w [.NET Framework października 2019 Preview zestawienia jakości](https://devblogs.microsoft.com/dotnet/net-framework-october-2019-preview-of-quality-rollup/) dla .NET Framework 4,8 i nowszych wersji:<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;appSettings&gt;&#13;&#10;...&#13;&#10;&lt;add key=&quot;aspnet:GetValidationMemberName&quot;  value=&quot;true&quot;/&gt;&#13;&#10;...&#13;&#10;&lt;/appSettings&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>W wersji .NET Framework 4,8 wcześniejszej niż aktualizacja 2019 października, dodanie do pliku *web.config* przywraca poprzednie zachowanie i zwraca wartość właściwości `null` .

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Nieznane|
|Wersja|4,8|
|Typ|Środowisko uruchomieniowe|

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.ComponentModel.DataAnnotations.ValidationContext.MemberName?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.ComponentModel.DataAnnotations.ValidationContext.MemberName`

-->
