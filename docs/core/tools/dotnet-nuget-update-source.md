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
# <a name="dotnet-nuget-update-source"></a><span data-ttu-id="d6226-103">dotnet nuget update source</span><span class="sxs-lookup"><span data-stu-id="d6226-103">dotnet nuget update source</span></span>

<span data-ttu-id="d6226-104">**Ten artykuł ma zastosowanie do:** ✔️ .NET Core 3.1.200 SDK i nowszych wersjach</span><span class="sxs-lookup"><span data-stu-id="d6226-104">**This article applies to:** ✔️ .NET Core 3.1.200 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="d6226-105">Nazwa</span><span class="sxs-lookup"><span data-stu-id="d6226-105">Name</span></span>

<span data-ttu-id="d6226-106">`dotnet nuget update source` — Zaktualizuj źródło narzędzia NuGet.</span><span class="sxs-lookup"><span data-stu-id="d6226-106">`dotnet nuget update source` - Update a NuGet source.</span></span>

## <a name="synopsis"></a><span data-ttu-id="d6226-107">Streszczenie</span><span class="sxs-lookup"><span data-stu-id="d6226-107">Synopsis</span></span>

```dotnetcli
dotnet nuget update source <NAME> [--source <SOURCE>] [--username <USER>]
    [--password <PASSWORD>] [--store-password-in-clear-text]
    [--valid-authentication-types <TYPES>] [--configfile <FILE>]

dotnet nuget update source -h|--help
```

## <a name="description"></a><span data-ttu-id="d6226-108">Opis</span><span class="sxs-lookup"><span data-stu-id="d6226-108">Description</span></span>

<span data-ttu-id="d6226-109">`dotnet nuget update source`Polecenie aktualizuje istniejące źródło w plikach konfiguracji programu NuGet.</span><span class="sxs-lookup"><span data-stu-id="d6226-109">The `dotnet nuget update source` command updates an existing source in your NuGet configuration files.</span></span>

## <a name="arguments"></a><span data-ttu-id="d6226-110">Argumenty</span><span class="sxs-lookup"><span data-stu-id="d6226-110">Arguments</span></span>

- **`NAME`**

  <span data-ttu-id="d6226-111">Nazwa źródła.</span><span class="sxs-lookup"><span data-stu-id="d6226-111">Name of the source.</span></span>

## <a name="options"></a><span data-ttu-id="d6226-112">Opcje</span><span class="sxs-lookup"><span data-stu-id="d6226-112">Options</span></span>

- **`--configfile <FILE>`**

  <span data-ttu-id="d6226-113">Plik konfiguracji programu NuGet.</span><span class="sxs-lookup"><span data-stu-id="d6226-113">The NuGet configuration file.</span></span> <span data-ttu-id="d6226-114">Jeśli zostanie określony, będą używane tylko ustawienia z tego pliku.</span><span class="sxs-lookup"><span data-stu-id="d6226-114">If specified, only the settings from this file will be used.</span></span> <span data-ttu-id="d6226-115">Jeśli nie zostanie określony, zostanie użyta hierarchia plików konfiguracji z bieżącego katalogu.</span><span class="sxs-lookup"><span data-stu-id="d6226-115">If not specified, the hierarchy of configuration files from the current directory will be used.</span></span> <span data-ttu-id="d6226-116">Aby uzyskać więcej informacji, zobacz [typowe konfiguracje NuGet](/nuget/consume-packages/configuring-nuget-behavior).</span><span class="sxs-lookup"><span data-stu-id="d6226-116">For more information, see [Common NuGet Configurations](/nuget/consume-packages/configuring-nuget-behavior).</span></span>

- **`-p|--password <PASSWORD>`**

  <span data-ttu-id="d6226-117">Hasło, które ma być używane podczas nawiązywania połączenia z uwierzytelnionym źródłem.</span><span class="sxs-lookup"><span data-stu-id="d6226-117">Password to be used when connecting to an authenticated source.</span></span>

- **`-s|--source <SOURCE>`**

  <span data-ttu-id="d6226-118">Ścieżka do źródła pakietu.</span><span class="sxs-lookup"><span data-stu-id="d6226-118">Path to the package source.</span></span>

- **`--store-password-in-clear-text`**

  <span data-ttu-id="d6226-119">Umożliwia przechowywanie przenośnych poświadczeń źródłowych pakietów przez wyłączenie szyfrowania hasła.</span><span class="sxs-lookup"><span data-stu-id="d6226-119">Enables storing portable package source credentials by disabling password encryption.</span></span>

- **`-u|--username <USER>`**

  <span data-ttu-id="d6226-120">Nazwa użytkownika do użycia podczas nawiązywania połączenia z uwierzytelnionym źródłem.</span><span class="sxs-lookup"><span data-stu-id="d6226-120">Username to be used when connecting to an authenticated source.</span></span>

- **`--valid-authentication-types <TYPES>`**

  <span data-ttu-id="d6226-121">Rozdzielana przecinkami lista prawidłowych typów uwierzytelniania dla tego źródła.</span><span class="sxs-lookup"><span data-stu-id="d6226-121">Comma-separated list of valid authentication types for this source.</span></span> <span data-ttu-id="d6226-122">Ustaw tę opcję na `basic` , jeśli serwer anonsuje protokół NTLM lub Negocjuj, a Twoje poświadczenia muszą być wysyłane przy użyciu podstawowego mechanizmu, na przykład w przypadku korzystania z elementu "% Azure DevOps Server".</span><span class="sxs-lookup"><span data-stu-id="d6226-122">Set this to `basic` if the server advertises NTLM or Negotiate and your credentials must be sent using the Basic mechanism, for instance when using a PAT with on-premises Azure DevOps Server.</span></span> <span data-ttu-id="d6226-123">Inne prawidłowe wartości to `negotiate` , `kerberos` , `ntlm` , i `digest` , ale te wartości są prawdopodobnie przydatne.</span><span class="sxs-lookup"><span data-stu-id="d6226-123">Other valid values include `negotiate`, `kerberos`, `ntlm`, and `digest`, but these values are unlikely to be useful.</span></span>

## <a name="examples"></a><span data-ttu-id="d6226-124">Przykłady</span><span class="sxs-lookup"><span data-stu-id="d6226-124">Examples</span></span>

- <span data-ttu-id="d6226-125">Zaktualizuj źródło o nazwie `mySource` :</span><span class="sxs-lookup"><span data-stu-id="d6226-125">Update a source with name of `mySource`:</span></span>

  ```dotnetcli
  dotnet nuget update source mySource --source c:\packages
  ```

## <a name="see-also"></a><span data-ttu-id="d6226-126">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="d6226-126">See also</span></span>

- [<span data-ttu-id="d6226-127">Sekcje źródłowe pakietu w plikach NuGet.config</span><span class="sxs-lookup"><span data-stu-id="d6226-127">Package source sections in NuGet.config files</span></span>](/nuget/reference/nuget-config-file#package-source-sections)

- [<span data-ttu-id="d6226-128">sources — polecenie (nuget.exe)</span><span class="sxs-lookup"><span data-stu-id="d6226-128">sources command (nuget.exe)</span></span>](/nuget/reference/cli-reference/cli-ref-sources)
