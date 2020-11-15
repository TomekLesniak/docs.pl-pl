---
title: Uruchom polecenie Narzędzia dotnet
description: Polecenie Uruchom narzędzie dotnet wywołuje narzędzie lokalne.
ms.date: 02/14/2020
ms.openlocfilehash: 116ecb61748a0ca70ed385b279b11b939748f4a8
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/15/2020
ms.locfileid: "94634158"
---
# <a name="dotnet-tool-run"></a>dotnet tool run

**Ten artykuł ma zastosowanie do:** ✔️ .net Core 3,0 SDK i nowszych wersjach

## <a name="name"></a>Nazwa

`dotnet tool run` -Wywołuje narzędzie lokalne.

## <a name="synopsis"></a>Streszczenie

```dotnetcli
dotnet tool run <COMMAND NAME>

dotnet tool run -h|--help
```

## <a name="description"></a>Opis

`dotnet tool run`Polecenie przeszukuje pliki manifestu narzędzia, które znajdują się w zakresie dla bieżącego katalogu. Po znalezieniu odwołania do określonego narzędzia zostanie uruchomione narzędzie. Aby uzyskać więcej informacji, zobacz [wywoływanie narzędzia lokalnego](global-tools.md#invoke-a-local-tool).

## <a name="arguments"></a>Argumenty

- **`COMMAND_NAME`**

  Nazwa polecenia narzędzia do uruchomienia.

## <a name="options"></a>Opcje

- **`-h|--help`**

  Drukuje krótką pomoc dla polecenia.

## <a name="example"></a>Przykład

- **`dotnet tool run dotnetsay`**

  Uruchamia `dotnetsay` Narzędzie lokalne.

## <a name="see-also"></a>Zobacz też

- [Narzędzia .NET](global-tools.md)
- [Samouczek: Instalowanie i używanie lokalnego narzędzia .NET przy użyciu interfejsu wiersza polecenia platformy .NET](local-tools-how-to-use.md)
