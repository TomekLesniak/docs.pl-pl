---
title: polecenie pomocy dotnet
description: Polecenie pomocy dotnet zawiera bardziej szczegółową dokumentację w trybie online dla określonego polecenia.
ms.date: 02/14/2020
ms.openlocfilehash: d583142edabb24df972bdf9a06dbfe04688f9d97
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/15/2020
ms.locfileid: "94634471"
---
# <a name="dotnet-help-reference"></a>informacje pomocy dotyczące dotnet

**Ten artykuł ma zastosowanie do:** ✔️ .net Core 2,0 SDK i nowszych wersjach

## <a name="name"></a>Nazwa

`dotnet help` -Wyświetla bardziej szczegółową dokumentację w trybie online dla określonego polecenia.

## <a name="synopsis"></a>Streszczenie

```dotnetcli
dotnet help <COMMAND_NAME> [-h|--help]
```

## <a name="description"></a>Opis

`dotnet help`Polecenie otwiera stronę referencyjną, aby uzyskać bardziej szczegółowe informacje na temat określonego polecenia w docs.Microsoft.com.

## <a name="arguments"></a>Argumenty

- **`COMMAND_NAME`**

  Nazwa polecenie interfejsu wiersza polecenia platformy .NET. Aby uzyskać listę prawidłowych poleceń interfejsu wiersza polecenia, zobacz [poleceń interfejsu wiersza polecenia](index.md#cli-commands).

## <a name="options"></a>Opcje

- **`-h|--help`**

  Drukuje krótką pomoc dla polecenia.

## <a name="examples"></a>Przykłady

- Otwiera stronę dokumentacji dla nowego polecenia [dotnet](dotnet-new.md) :

  ```dotnetcli
  dotnet help new
  ```
