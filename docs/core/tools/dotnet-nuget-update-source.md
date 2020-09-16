---
title: polecenie dotyczące źródła aktualizacji NuGet dotnet
description: Polecenie Źródło aktualizacji NuGet programu dotnet aktualizuje istniejące źródło w plikach konfiguracji programu NuGet.
ms.date: 03/20/2020
ms.openlocfilehash: a8658c78c095ad4b9272d97200e1d6466cbe658b
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90537857"
---
# <a name="dotnet-nuget-update-source"></a>dotnet nuget update source

**Ten artykuł ma zastosowanie do:** ✔️ .NET Core 3.1.200 SDK i nowszych wersjach

## <a name="name"></a>Nazwa

`dotnet nuget update source` — Zaktualizuj źródło narzędzia NuGet.

## <a name="synopsis"></a>Streszczenie

```dotnetcli
dotnet nuget update source <NAME> [--source <SOURCE>] [--username <USER>]
    [--password <PASSWORD>] [--store-password-in-clear-text]
    [--valid-authentication-types <TYPES>] [--configfile <FILE>]

dotnet nuget update source -h|--help
```

## <a name="description"></a>Opis

`dotnet nuget update source`Polecenie aktualizuje istniejące źródło w plikach konfiguracji programu NuGet.

## <a name="arguments"></a>Argumenty

- **`NAME`**

  Nazwa źródła.

## <a name="options"></a>Opcje

- **`--configfile <FILE>`**

  Plik konfiguracji programu NuGet. Jeśli zostanie określony, będą używane tylko ustawienia z tego pliku. Jeśli nie zostanie określony, zostanie użyta hierarchia plików konfiguracji z bieżącego katalogu. Aby uzyskać więcej informacji, zobacz [typowe konfiguracje NuGet](/nuget/consume-packages/configuring-nuget-behavior).

- **`-p|--password <PASSWORD>`**

  Hasło, które ma być używane podczas nawiązywania połączenia z uwierzytelnionym źródłem.

- **`-s|--source <SOURCE>`**

  Ścieżka do źródła pakietu.

- **`--store-password-in-clear-text`**

  Umożliwia przechowywanie przenośnych poświadczeń źródłowych pakietów przez wyłączenie szyfrowania hasła.

- **`-u|--username <USER>`**

  Nazwa użytkownika do użycia podczas nawiązywania połączenia z uwierzytelnionym źródłem.

- **`--valid-authentication-types <TYPES>`**

  Rozdzielana przecinkami lista prawidłowych typów uwierzytelniania dla tego źródła. Ustaw tę opcję na `basic` , jeśli serwer anonsuje protokół NTLM lub Negocjuj, a Twoje poświadczenia muszą być wysyłane przy użyciu podstawowego mechanizmu, na przykład w przypadku korzystania z elementu "% Azure DevOps Server". Inne prawidłowe wartości to `negotiate` , `kerberos` , `ntlm` , i `digest` , ale te wartości są prawdopodobnie przydatne.

## <a name="examples"></a>Przykłady

- Zaktualizuj źródło o nazwie `mySource` :

  ```dotnetcli
  dotnet nuget update source mySource --source c:\packages
  ```

## <a name="see-also"></a>Zobacz także

- [Sekcje źródłowe pakietu w plikach NuGet.config](/nuget/reference/nuget-config-file#package-source-sections)

- [sources — polecenie (nuget.exe)](/nuget/reference/cli-reference/cli-ref-sources)
