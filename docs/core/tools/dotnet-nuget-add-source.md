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
# <a name="dotnet-nuget-add-source"></a><span data-ttu-id="cacc8-103">dotnet nuget add source</span><span class="sxs-lookup"><span data-stu-id="cacc8-103">dotnet nuget add source</span></span>

<span data-ttu-id="cacc8-104">**Ten artykuł ma zastosowanie do:** ✔️ .NET Core 3.1.200 SDK i nowszych wersjach</span><span class="sxs-lookup"><span data-stu-id="cacc8-104">**This article applies to:** ✔️ .NET Core 3.1.200 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="cacc8-105">Nazwa</span><span class="sxs-lookup"><span data-stu-id="cacc8-105">Name</span></span>

<span data-ttu-id="cacc8-106">`dotnet nuget add source` -Dodaj źródło NuGet.</span><span class="sxs-lookup"><span data-stu-id="cacc8-106">`dotnet nuget add source` - Add a NuGet source.</span></span>

## <a name="synopsis"></a><span data-ttu-id="cacc8-107">Streszczenie</span><span class="sxs-lookup"><span data-stu-id="cacc8-107">Synopsis</span></span>

```dotnetcli
dotnet nuget add source <PACKAGE_SOURCE_PATH> [--name <SOURCE_NAME>] [--username <USER>]
    [--password <PASSWORD>] [--store-password-in-clear-text]
    [--valid-authentication-types <TYPES>] [--configfile <FILE>]

dotnet nuget add source -h|--help
```

## <a name="description"></a><span data-ttu-id="cacc8-108">Opis</span><span class="sxs-lookup"><span data-stu-id="cacc8-108">Description</span></span>

<span data-ttu-id="cacc8-109">`dotnet nuget add source`Polecenie dodaje nowe źródło pakietu do plików konfiguracyjnych programu NuGet.</span><span class="sxs-lookup"><span data-stu-id="cacc8-109">The `dotnet nuget add source` command adds a new package source to your NuGet configuration files.</span></span>

## <a name="arguments"></a><span data-ttu-id="cacc8-110">Argumenty</span><span class="sxs-lookup"><span data-stu-id="cacc8-110">Arguments</span></span>

- **`PACKAGE_SOURCE_PATH`**

  <span data-ttu-id="cacc8-111">Ścieżka do źródła pakietu.</span><span class="sxs-lookup"><span data-stu-id="cacc8-111">Path to the package source.</span></span>

## <a name="options"></a><span data-ttu-id="cacc8-112">Opcje</span><span class="sxs-lookup"><span data-stu-id="cacc8-112">Options</span></span>

- **`--configfile <FILE>`**

  <span data-ttu-id="cacc8-113">Plik konfiguracji programu NuGet.</span><span class="sxs-lookup"><span data-stu-id="cacc8-113">The NuGet configuration file.</span></span> <span data-ttu-id="cacc8-114">Jeśli zostanie określony, będą używane tylko ustawienia z tego pliku.</span><span class="sxs-lookup"><span data-stu-id="cacc8-114">If specified, only the settings from this file will be used.</span></span> <span data-ttu-id="cacc8-115">Jeśli nie zostanie określony, zostanie użyta hierarchia plików konfiguracji z bieżącego katalogu.</span><span class="sxs-lookup"><span data-stu-id="cacc8-115">If not specified, the hierarchy of configuration files from the current directory will be used.</span></span> <span data-ttu-id="cacc8-116">Aby uzyskać więcej informacji, zobacz [typowe konfiguracje NuGet](/nuget/consume-packages/configuring-nuget-behavior).</span><span class="sxs-lookup"><span data-stu-id="cacc8-116">For more information, see [Common NuGet Configurations](/nuget/consume-packages/configuring-nuget-behavior).</span></span>

- **`-n|--name <SOURCE_NAME>`**

  <span data-ttu-id="cacc8-117">Nazwa źródła.</span><span class="sxs-lookup"><span data-stu-id="cacc8-117">Name of the source.</span></span>

- **`-p|--password <PASSWORD>`**

  <span data-ttu-id="cacc8-118">Hasło, które ma być używane podczas nawiązywania połączenia z uwierzytelnionym źródłem.</span><span class="sxs-lookup"><span data-stu-id="cacc8-118">Password to be used when connecting to an authenticated source.</span></span>

- **`--store-password-in-clear-text`**

  <span data-ttu-id="cacc8-119">Umożliwia przechowywanie przenośnych poświadczeń źródłowych pakietów przez wyłączenie szyfrowania hasła.</span><span class="sxs-lookup"><span data-stu-id="cacc8-119">Enables storing portable package source credentials by disabling password encryption.</span></span>

- **`-u|--username <USER>`**

  <span data-ttu-id="cacc8-120">Nazwa użytkownika do użycia podczas nawiązywania połączenia z uwierzytelnionym źródłem.</span><span class="sxs-lookup"><span data-stu-id="cacc8-120">Username to be used when connecting to an authenticated source.</span></span>

- **`--valid-authentication-types <TYPES>`**

  <span data-ttu-id="cacc8-121">Rozdzielana przecinkami lista prawidłowych typów uwierzytelniania dla tego źródła.</span><span class="sxs-lookup"><span data-stu-id="cacc8-121">Comma-separated list of valid authentication types for this source.</span></span> <span data-ttu-id="cacc8-122">Ustaw tę opcję na `basic` , jeśli serwer anonsuje protokół NTLM lub Negocjuj, a Twoje poświadczenia muszą być wysyłane przy użyciu podstawowego mechanizmu, na przykład w przypadku korzystania z elementu "% Azure DevOps Server".</span><span class="sxs-lookup"><span data-stu-id="cacc8-122">Set this to `basic` if the server advertises NTLM or Negotiate and your credentials must be sent using the Basic mechanism, for instance when using a PAT with on-premises Azure DevOps Server.</span></span> <span data-ttu-id="cacc8-123">Inne prawidłowe wartości to `negotiate` , `kerberos` , `ntlm` , i `digest` , ale te wartości są prawdopodobnie przydatne.</span><span class="sxs-lookup"><span data-stu-id="cacc8-123">Other valid values include `negotiate`, `kerberos`, `ntlm`, and `digest`, but these values are unlikely to be useful.</span></span>

## <a name="examples"></a><span data-ttu-id="cacc8-124">Przykłady</span><span class="sxs-lookup"><span data-stu-id="cacc8-124">Examples</span></span>

- <span data-ttu-id="cacc8-125">Dodaj `nuget.org` jako Źródło:</span><span class="sxs-lookup"><span data-stu-id="cacc8-125">Add `nuget.org` as a source:</span></span>

  ```dotnetcli
  dotnet nuget add source https://api.nuget.org/v3/index.json -n nuget.org
  ```

- <span data-ttu-id="cacc8-126">Dodaj `c:\packages` jako źródło lokalne:</span><span class="sxs-lookup"><span data-stu-id="cacc8-126">Add `c:\packages` as a local source:</span></span>

  ```dotnetcli
  dotnet nuget add source c:\packages
  ```

- <span data-ttu-id="cacc8-127">Dodaj źródło, które wymaga uwierzytelniania:</span><span class="sxs-lookup"><span data-stu-id="cacc8-127">Add a source that needs authentication:</span></span>

  ```dotnetcli
  dotnet nuget add source https://someServer/myTeam -n myTeam -u myUsername -p myPassword --store-password-in-clear-text
  ```

- <span data-ttu-id="cacc8-128">Dodaj źródło, które wymaga uwierzytelniania (przejdź do pozycji zainstaluj dostawcę poświadczeń):</span><span class="sxs-lookup"><span data-stu-id="cacc8-128">Add a source that needs authentication (then go install credential provider):</span></span>

  ```dotnetcli
  dotnet nuget add source https://azureartifacts.microsoft.com/myTeam -n myTeam
  ```

## <a name="see-also"></a><span data-ttu-id="cacc8-129">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="cacc8-129">See also</span></span>

- [<span data-ttu-id="cacc8-130">Sekcje źródłowe pakietu w plikach NuGet.config</span><span class="sxs-lookup"><span data-stu-id="cacc8-130">Package source sections in NuGet.config files</span></span>](/nuget/reference/nuget-config-file#package-source-sections)

- [<span data-ttu-id="cacc8-131">sources — polecenie (nuget.exe)</span><span class="sxs-lookup"><span data-stu-id="cacc8-131">sources command (nuget.exe)</span></span>](/nuget/reference/cli-reference/cli-ref-sources)
