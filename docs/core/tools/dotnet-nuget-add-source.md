---
title: polecenie Add Source NuGet narzędzia dotnet
description: Polecenie Dodaj źródło NuGet programu dotnet powoduje dodanie nowego źródła pakietu do plików konfiguracji programu NuGet.
ms.date: 03/20/2020
ms.openlocfilehash: b847d987de2d88cb3452d32d1bc84232a1e20b6e
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90537976"
---
# <a name="dotnet-nuget-add-source"></a>dotnet nuget add source

**Ten artykuł ma zastosowanie do:** ✔️ .NET Core 3.1.200 SDK i nowszych wersjach

## <a name="name"></a>Nazwa

`dotnet nuget add source` -Dodaj źródło NuGet.

## <a name="synopsis"></a>Streszczenie

```dotnetcli
dotnet nuget add source <PACKAGE_SOURCE_PATH> [--name <SOURCE_NAME>] [--username <USER>]
    [--password <PASSWORD>] [--store-password-in-clear-text]
    [--valid-authentication-types <TYPES>] [--configfile <FILE>]

dotnet nuget add source -h|--help
```

## <a name="description"></a>Opis

`dotnet nuget add source`Polecenie dodaje nowe źródło pakietu do plików konfiguracyjnych programu NuGet.

## <a name="arguments"></a>Argumenty

- **`PACKAGE_SOURCE_PATH`**

  Ścieżka do źródła pakietu.

## <a name="options"></a>Opcje

- **`--configfile <FILE>`**

  Plik konfiguracji programu NuGet. Jeśli zostanie określony, będą używane tylko ustawienia z tego pliku. Jeśli nie zostanie określony, zostanie użyta hierarchia plików konfiguracji z bieżącego katalogu. Aby uzyskać więcej informacji, zobacz [typowe konfiguracje NuGet](/nuget/consume-packages/configuring-nuget-behavior).

- **`-n|--name <SOURCE_NAME>`**

  Nazwa źródła.

- **`-p|--password <PASSWORD>`**

  Hasło, które ma być używane podczas nawiązywania połączenia z uwierzytelnionym źródłem.

- **`--store-password-in-clear-text`**

  Umożliwia przechowywanie przenośnych poświadczeń źródłowych pakietów przez wyłączenie szyfrowania hasła.

- **`-u|--username <USER>`**

  Nazwa użytkownika do użycia podczas nawiązywania połączenia z uwierzytelnionym źródłem.

- **`--valid-authentication-types <TYPES>`**

  Rozdzielana przecinkami lista prawidłowych typów uwierzytelniania dla tego źródła. Ustaw tę opcję na `basic` , jeśli serwer anonsuje protokół NTLM lub Negocjuj, a Twoje poświadczenia muszą być wysyłane przy użyciu podstawowego mechanizmu, na przykład w przypadku korzystania z elementu "% Azure DevOps Server". Inne prawidłowe wartości to `negotiate` , `kerberos` , `ntlm` , i `digest` , ale te wartości są prawdopodobnie przydatne.

## <a name="examples"></a>Przykłady

- Dodaj `nuget.org` jako Źródło:

  ```dotnetcli
  dotnet nuget add source https://api.nuget.org/v3/index.json -n nuget.org
  ```

- Dodaj `c:\packages` jako źródło lokalne:

  ```dotnetcli
  dotnet nuget add source c:\packages
  ```

- Dodaj źródło, które wymaga uwierzytelniania:

  ```dotnetcli
  dotnet nuget add source https://someServer/myTeam -n myTeam -u myUsername -p myPassword --store-password-in-clear-text
  ```

- Dodaj źródło, które wymaga uwierzytelniania (przejdź do pozycji zainstaluj dostawcę poświadczeń):

  ```dotnetcli
  dotnet nuget add source https://azureartifacts.microsoft.com/myTeam -n myTeam
  ```

## <a name="see-also"></a>Zobacz także

- [Sekcje źródłowe pakietu w plikach NuGet.config](/nuget/reference/nuget-config-file#package-source-sections)

- [sources — polecenie (nuget.exe)](/nuget/reference/cli-reference/cli-ref-sources)
