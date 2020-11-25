---
title: 'Zmiana istotna: Rozpoznawanie identyfikatorów URI ścieżek UNC w systemie UNIX'
description: Dowiedz się więcej na temat istotnej zmiany w programie .NET 5,0 w bibliotekach podstawowych platformy .NET, w których Klasa URI rozpoznaje teraz ciągi, które zaczynają się od dwóch ukośników jako ścieżki UNC w systemie UNIX.
ms.date: 11/01/2020
ms.openlocfilehash: 0d5d9cd8dd869f24e94d15724e5e16eaddf6ed47
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761387"
---
# <a name="uri-recognition-of-unc-paths-on-unix"></a>Rozpoznawanie identyfikatorów URI ścieżek UNC w systemie UNIX

<xref:System.Uri>Klasa rozpoznaje teraz ciągi, które zaczynają się od dwóch ukośników ( `//` ) jako ścieżki uniwersalnej konwencji nazewnictwa (UNC) w systemach operacyjnych UNIX. Ta zmiana powoduje, że zachowanie takich ciągów jest spójne na wszystkich platformach.

## <a name="change-description"></a>Zmień opis

W poprzednich wersjach programu .NET <xref:System.Uri> Klasa rozpoznaje ciągi, które zaczynają się od dwóch ukośników do przodu, na przykład `//contoso` jako bezwzględne ścieżki plików w systemach operacyjnych UNIX. Jednak w systemie Windows takie ciągi są rozpoznawane jako ścieżki UNC.

Począwszy od platformy .NET 5,0, <xref:System.Uri> Klasa rozpoznaje ciągi zaczynające się od dwóch ukośników do przodu jako ścieżki UNC na wszystkich platformach, w tym w systemie UNIX. Ponadto właściwości zachowują się zgodnie z semantyką UNC:

- <xref:System.Uri.IsUnc?displayProperty=nameWithType> Zwraca wartość `true` .
- Ukośniki odwrotne w ścieżce są zastępowane ukośnikami. Na przykład, `//first\second` staje się `//first/second`.
- <xref:System.Uri.LocalPath?displayProperty=nameWithType> nie ma znaków "%-Encode". Na przykład `//first/\uFFF0` *nie* jest konwertowany na `//first/%EF%BF%B0` .

## <a name="version-introduced"></a>Wprowadzona wersja

5,0

## <a name="recommended-action"></a>Zalecana akcja

W części dewelopera nie jest wymagana żadna akcja.

## <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Uri?displayProperty=fullName>

<!--

#### Category

Core .NET libraries

### Affected APIs

- `T:System.Uri`

-->
