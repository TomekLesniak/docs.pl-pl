---
ms.openlocfilehash: b3cc04d5675ea63a0a6b967e293da8a1bd79830d
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032074"
---
### <a name="uribuilder-properties-no-longer-prepend-leading-characters"></a>Właściwości UriBuilder nie dołączają już znaków wiodących

<xref:System.UriBuilder.Fragment?displayProperty=nameWithType> nie dołącza już znaku wiodącego `#` i <xref:System.UriBuilder.Query?displayProperty=nameWithType> nie dołącza już znaku wiodącego, `?` gdy jeden już istnieje.

#### <a name="change-description"></a>Zmień opis

W .NET Framework <xref:System.UriBuilder.Fragment?displayProperty=nameWithType> <xref:System.UriBuilder.Query?displayProperty=nameWithType> właściwości i zawsze są poprzedzone `#` `?` znakiem lub, odpowiednio, do przechowywanej wartości. Takie zachowanie może skutkować wielokrotnym `#` `?` znakiem w wartości przechowywanej, jeśli ciąg zawiera już jeden z tych znaków wiodących. Na przykład wartość może być równa <xref:System.UriBuilder.Fragment?displayProperty=nameWithType> `##main` .

Począwszy od platformy .NET Core 1,0, te właściwości nie dołączają `#` lub `?` do przechowywanej wartości, jeśli jeden już występuje na początku ciągu.

#### <a name="version-introduced"></a>Wprowadzona wersja

1,0

#### <a name="recommended-action"></a>Zalecana akcja

Nie trzeba już jawnie usuwać żadnego z tych znaków wiodących podczas ustawiania wartości właściwości. Jest to szczególnie przydatne podczas dołączania wartości, ponieważ nie jest już konieczne usuwanie interlinii `#` lub `?` każdorazowe dołączanie.

Na przykład poniższy fragment kodu przedstawia różnicę zachowania między .NET Framework i .NET Core.

```csharp
var builder = new UriBuilder();
builder.Query = "one=1";
builder.Query += "&two=2";
builder.Query += "&three=3";
builder.Query += "&four=4";

Console.WriteLine(builder.Query);
```

- W .NET Framework dane wyjściowe to `????one=1&two=2&three=3&four=4` .
- W programie .NET Core dane wyjściowe to `?one=1&two=2&three=3&four=4` .

#### <a name="category"></a>Kategoria

Podstawowe biblioteki platformy .NET

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.UriBuilder.Fragment?displayProperty=fullName>
- <xref:System.UriBuilder.Query?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.UriBuilder.Fragment`
- `T:System.UriBuilder.Query`

-->
