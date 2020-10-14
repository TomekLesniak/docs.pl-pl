---
ms.openlocfilehash: 80d13609f1b02ae0ac875b2028e745670bb8f503
ms.sourcegitcommit: 39b1d5f2978be15409c189a66ab30781d9082cd8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/14/2020
ms.locfileid: "92050572"
---
### <a name="frameworkdescriptions-value-is-net-instead-of-net-core"></a>FrameworkDescription jest wartością .NET zamiast .NET Core

<xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> teraz zwraca wartość ".NET" zamiast ".NET Core".

#### <a name="change-description"></a>Zmień opis

W poprzednich wersjach programu .NET <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> zwraca wartość ".NET Core" jako część ciągu opisu, na przykład `.NET Core 3.1.1` .

Począwszy od platformy .NET 5,0, <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> zwraca ".NET" jako część ciągu opisu, na przykład `.NET 5.0.0` .

#### <a name="reason-for-change"></a>Przyczyna zmiany

Program .NET 5 `netcoreapp` jest zastępowany przez `net` krótką moniker struktury Target. W celu zapewnienia spójności Opis został również zaktualizowany. Zmiana jest Kosmetyka, ponieważ `FrameworkName` nie jest zaszyfrowana w dowolnym miejscu niż we <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> właściwości.

#### <a name="version-introduced"></a>Wprowadzona wersja

5,0

#### <a name="recommended-action"></a>Zalecana akcja

Zaktualizuj dowolny kod, który wyszukuje ".NET Core" w ciągu zwracanym przez <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription> .

#### <a name="category"></a>Kategoria

Podstawowe biblioteki platformy .NET

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=fullName>

<!--

#### Affected APIs

- `P:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription`

-->
