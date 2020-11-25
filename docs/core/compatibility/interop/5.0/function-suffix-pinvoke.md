---
title: 'Nieprzerwana zmiana: nie znaleziono sufiksu/W na platformach innych niż Windows'
description: Dowiedz się więcej o zmianie nieprzerwaności międzyoperacyjności w programie .NET 5,0, gdzie sufiksy nie są już dodawane do funkcji eksportowania nazw podczas sondowania dla P/Invoke na platformach innych niż Windows.
ms.date: 08/13/2020
ms.openlocfilehash: a4c612a81796faf80fa257df21232a54f7b95431
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761551"
---
# <a name="no-aw-suffix-probing-on-non-windows-platforms"></a>Brak podwyższenia poziomu sufiksu na platformach innych niż Windows

Środowisko uruchomieniowe platformy .NET nie dodaje już `A` `W` sufiksu lub do funkcji eksportu nazw podczas sondowania dla P/Invoke na platformach innych niż Windows.

## <a name="version-introduced"></a>Wprowadzona wersja

5,0

## <a name="change-description"></a>Zmień opis

[System Windows ma konwencję](/windows/win32/intl/conventions-for-function-prototypes) dodawania `A` `W` sufiksu lub do Windows SDK nazw funkcji, które są odpowiednio zgodne ze stroną kodową systemu Windows i wersjami Unicode.

We wcześniejszych wersjach programu .NET środowisko uruchomieniowe CoreCLR i mono dodaje `A` `W` sufiks lub do nazwy eksportu podczas odnajdywania eksportu dla P/Invoke *na wszystkich platformach*.

W programie .NET 5,0 i nowszych wersjach `A` sufiks lub `W` jest dodawany do nazwy eksportu podczas odnajdywania eksportu *tylko w systemie Windows*. Na platformach UNIX sufiks nie jest dodawany. Semantyka obu środowisk uruchomieniowych na platformie Windows pozostaje niezmieniona.

## <a name="reason-for-change"></a>Przyczyna zmiany

Ta zmiana została wprowadzona w celu uproszczenia sondowania międzyplatformowego. Nie należy tego robić, ponieważ platformy inne niż Windows nie zawierają tej semantyki.

## <a name="recommended-action"></a>Zalecana akcja

Aby wyeliminować zmianę, można ręcznie dodać żądany sufiks na platformach innych niż Windows. Na przykład:

```csharp
[DllImport(...)]
extern static void SetWindowTextW();
```

## <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName>

<!--

### Affected APIs

- `T:System.Runtime.InteropServices.DllImportAttribute`

### Category

Interop

-->
