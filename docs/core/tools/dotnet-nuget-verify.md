---
title: polecenie weryfikacji NuGet narzędzia dotnet
description: Polecenie weryfikacji NuGet programu dotnet weryfikuje podpisany pakiet.
author: kartheekp-ms
ms.date: 10/08/2020
ms.openlocfilehash: 6cb368e2b6c203f3774b4450c0831c5d6b2dc0e8
ms.sourcegitcommit: b59237ca4ec763969a0dd775a3f8f39f8c59fe24
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2020
ms.locfileid: "91957168"
---
# <a name="dotnet-nuget-verify"></a>Weryfikacja NuGet narzędzia dotnet

**Ten artykuł ma zastosowanie do:** ✔️ .NET 5.0.100-RC. 2. x SDK i nowszych wersjach

## <a name="name"></a>Nazwa

`dotnet nuget verify` -Weryfikuje podpisany pakiet NuGet.

## <a name="synopsis"></a>Streszczenie

```dotnetcli
dotnet nuget verify [<package-path(s)>]
    [--all]
    [--certificate-fingerprint <FINGERPRINT>]
    [-v|--verbosity <LEVEL>]

dotnet nuget verify -h|--help
```

## <a name="description"></a>Opis

`dotnet nuget verify`Polecenie weryfikuje podpisany pakiet NuGet.

## <a name="arguments"></a>Argumenty

- **`package-path(s)`**

  Określa ścieżkę pliku do pakietów do zweryfikowania. Aby zweryfikować wiele pakietów, można przekazywać wiele argumentów pozycji.

## <a name="options"></a>Opcje

- **`--all`**

  Określa, że wszystkie możliwe weryfikacje powinny być wykonywane na pakietach. Domyślnie tylko `signatures` są weryfikowane.

> [!NOTE]
> To polecenie aktualnie obsługuje tylko `signature` weryfikację.

- **`--certificate-fingerprint <FINGERPRINT>`**

  Sprawdź, czy certyfikat osoby podpisującej jest zgodny z jednym z określonych `SHA256` odcisków palców. Tę opcję można podać wiele razy, aby zapewnić wiele odcisków palców.

* **`-v|--verbosity <LEVEL>`**

  Ustawia poziom szczegółowości programu MSBuild. Dozwolone wartości to `q[uiet]` , `m[inimal]` , `n[ormal]` , `d[etailed]` i `diag[nostic]` . Wartość domyślna to `normal`.

* **`-h|--help`**

  Drukuje krótką pomoc dla polecenia.

## <a name="examples"></a>Przykłady

- Sprawdź *foo. nupkg*:

  ```dotnetcli
  dotnet nuget verify foo.nupkg
  ```

- Sprawdź wiele pakietów NuGet — *foo. nupkg* i *wszystkie pliki. NUPKG w określonym katalogu*:

  ```dotnetcli
  dotnet nuget verify foo.nupkg c:\mydir\*.nupkg
  ```

- Sprawdź, czy sygnatura *foo. nupkg* jest zgodna z podanym odciskem palca certyfikatu:

  ```dotnetcli
  dotnet nuget verify foo.nupkg --certificate-fingerprint CE40881FF5F0AD3E58965DA20A9F571EF1651A56933748E1BF1C99E537C4E039
  ```

- Sprawdź, czy sygnatura *foo. nupkg* jest zgodna z jednym z określonych odcisków palca certyfikatu:

  ```dotnetcli
  dotnet nuget verify foo.nupkg --certificate-fingerprint CE40881FF5F0AD3E58965DA20A9F571EF1651A56933748E1BF1C99E537C4E039 --certificate-fingerprint EC10992GG5F0AD3E58965DA20A9F571EF1651A56933748E1BF1C99E537C4E027
  ```
