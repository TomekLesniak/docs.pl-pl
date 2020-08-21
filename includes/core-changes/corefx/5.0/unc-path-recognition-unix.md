---
ms.openlocfilehash: 0246f325a6274082b7fb0d5590cec7c80687ae85
ms.sourcegitcommit: ef86c24c418439b8bb5e3e7d64bbdbe5e11c3e9c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/21/2020
ms.locfileid: "88720206"
---
### <a name="uri-recognition-of-unc-paths-on-unix"></a>Rozpoznawanie identyfikatorów URI ścieżek UNC w systemie UNIX

<xref:System.Uri>Klasa rozpoznaje teraz ciągi, które zaczynają się od dwóch ukośników ( `//` ) jako ścieżki uniwersalnej konwencji nazewnictwa (UNC) w systemach operacyjnych UNIX. Ta zmiana powoduje, że zachowanie takich ciągów jest spójne na wszystkich platformach.

#### <a name="change-description"></a>Zmień opis

W poprzednich wersjach programu .NET <xref:System.Uri> Klasa rozpoznaje ciągi, które zaczynają się od dwóch ukośników, na przykład, `//contoso` jako bezwzględne ścieżki plików w systemach operacyjnych UNIX. Jednak w systemie Windows takie ciągi są rozpoznawane jako ścieżki UNC.

Począwszy od platformy .NET 5,0, <xref:System.Uri> Klasa rozpoznaje ciągi, które zaczynają się od od dwóch ukośników do przodu jako ścieżki UNC na wszystkich platformach, w tym UNIX. Ponadto właściwości zachowują się zgodnie z semantyką UNC:

- <xref:System.Uri.IsUnc?displayProperty=nameWithType> Zwraca wartość `true` .
- Ukośniki odwrotne w ścieżce są zastępowane ukośnikami. Na przykład, `//first\second` staje się `//first/second`.
- <xref:System.Uri.LocalPath?displayProperty=nameWithType> nie ma znaków "%-Encode". Na przykład `//first/\uFFF0` *nie* jest konwertowany na `//first/%EF%BF%B0` .

#### <a name="version-introduced"></a>Wprowadzona wersja

5.0

#### <a name="recommended-action"></a>Zalecana akcja

W części dewelopera nie jest wymagana żadna akcja.

#### <a name="category"></a>Kategoria

Podstawowe biblioteki platformy .NET

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Uri?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.Uri`

-->
