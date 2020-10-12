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
# <a name="dotnet-nuget-verify"></a><span data-ttu-id="b356c-103">Weryfikacja NuGet narzędzia dotnet</span><span class="sxs-lookup"><span data-stu-id="b356c-103">dotnet nuget verify</span></span>

<span data-ttu-id="b356c-104">**Ten artykuł ma zastosowanie do:** ✔️ .NET 5.0.100-RC. 2. x SDK i nowszych wersjach</span><span class="sxs-lookup"><span data-stu-id="b356c-104">**This article applies to:** ✔️ .NET 5.0.100-rc.2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="b356c-105">Nazwa</span><span class="sxs-lookup"><span data-stu-id="b356c-105">Name</span></span>

<span data-ttu-id="b356c-106">`dotnet nuget verify` -Weryfikuje podpisany pakiet NuGet.</span><span class="sxs-lookup"><span data-stu-id="b356c-106">`dotnet nuget verify` - Verifies a signed NuGet package.</span></span>

## <a name="synopsis"></a><span data-ttu-id="b356c-107">Streszczenie</span><span class="sxs-lookup"><span data-stu-id="b356c-107">Synopsis</span></span>

```dotnetcli
dotnet nuget verify [<package-path(s)>]
    [--all]
    [--certificate-fingerprint <FINGERPRINT>]
    [-v|--verbosity <LEVEL>]

dotnet nuget verify -h|--help
```

## <a name="description"></a><span data-ttu-id="b356c-108">Opis</span><span class="sxs-lookup"><span data-stu-id="b356c-108">Description</span></span>

<span data-ttu-id="b356c-109">`dotnet nuget verify`Polecenie weryfikuje podpisany pakiet NuGet.</span><span class="sxs-lookup"><span data-stu-id="b356c-109">The `dotnet nuget verify` command verifies a signed NuGet package.</span></span>

## <a name="arguments"></a><span data-ttu-id="b356c-110">Argumenty</span><span class="sxs-lookup"><span data-stu-id="b356c-110">Arguments</span></span>

- **`package-path(s)`**

  <span data-ttu-id="b356c-111">Określa ścieżkę pliku do pakietów do zweryfikowania.</span><span class="sxs-lookup"><span data-stu-id="b356c-111">Specifies the file path to the package(s) to be verified.</span></span> <span data-ttu-id="b356c-112">Aby zweryfikować wiele pakietów, można przekazywać wiele argumentów pozycji.</span><span class="sxs-lookup"><span data-stu-id="b356c-112">Multiple position arguments can be passed in to verify multiple packages.</span></span>

## <a name="options"></a><span data-ttu-id="b356c-113">Opcje</span><span class="sxs-lookup"><span data-stu-id="b356c-113">Options</span></span>

- **`--all`**

  <span data-ttu-id="b356c-114">Określa, że wszystkie możliwe weryfikacje powinny być wykonywane na pakietach.</span><span class="sxs-lookup"><span data-stu-id="b356c-114">Specifies that all verifications possible should be performed on the package(s).</span></span> <span data-ttu-id="b356c-115">Domyślnie tylko `signatures` są weryfikowane.</span><span class="sxs-lookup"><span data-stu-id="b356c-115">By default, only `signatures` are verified.</span></span>

> [!NOTE]
> <span data-ttu-id="b356c-116">To polecenie aktualnie obsługuje tylko `signature` weryfikację.</span><span class="sxs-lookup"><span data-stu-id="b356c-116">This command currently supports only `signature` verification.</span></span>

- **`--certificate-fingerprint <FINGERPRINT>`**

  <span data-ttu-id="b356c-117">Sprawdź, czy certyfikat osoby podpisującej jest zgodny z jednym z określonych `SHA256` odcisków palców.</span><span class="sxs-lookup"><span data-stu-id="b356c-117">Verify that the signer certificate matches with one of the specified `SHA256` fingerprints.</span></span> <span data-ttu-id="b356c-118">Tę opcję można podać wiele razy, aby zapewnić wiele odcisków palców.</span><span class="sxs-lookup"><span data-stu-id="b356c-118">This option can be supplied multiple times to provide multiple fingerprints.</span></span>

* **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="b356c-119">Ustawia poziom szczegółowości programu MSBuild.</span><span class="sxs-lookup"><span data-stu-id="b356c-119">Sets the MSBuild verbosity level.</span></span> <span data-ttu-id="b356c-120">Dozwolone wartości to `q[uiet]` , `m[inimal]` , `n[ormal]` , `d[etailed]` i `diag[nostic]` .</span><span class="sxs-lookup"><span data-stu-id="b356c-120">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="b356c-121">Wartość domyślna to `normal`.</span><span class="sxs-lookup"><span data-stu-id="b356c-121">The default is `normal`.</span></span>

* **`-h|--help`**

  <span data-ttu-id="b356c-122">Drukuje krótką pomoc dla polecenia.</span><span class="sxs-lookup"><span data-stu-id="b356c-122">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="b356c-123">Przykłady</span><span class="sxs-lookup"><span data-stu-id="b356c-123">Examples</span></span>

- <span data-ttu-id="b356c-124">Sprawdź *foo. nupkg*:</span><span class="sxs-lookup"><span data-stu-id="b356c-124">Verify *foo.nupkg*:</span></span>

  ```dotnetcli
  dotnet nuget verify foo.nupkg
  ```

- <span data-ttu-id="b356c-125">Sprawdź wiele pakietów NuGet — *foo. nupkg* i *wszystkie pliki. NUPKG w określonym katalogu*:</span><span class="sxs-lookup"><span data-stu-id="b356c-125">Verify multiple NuGet packages - *foo.nupkg* and *all .nupkg files in the directory specified*:</span></span>

  ```dotnetcli
  dotnet nuget verify foo.nupkg c:\mydir\*.nupkg
  ```

- <span data-ttu-id="b356c-126">Sprawdź, czy sygnatura *foo. nupkg* jest zgodna z podanym odciskem palca certyfikatu:</span><span class="sxs-lookup"><span data-stu-id="b356c-126">Verify *foo.nupkg* signature matches with the specified certificate fingerprint:</span></span>

  ```dotnetcli
  dotnet nuget verify foo.nupkg --certificate-fingerprint CE40881FF5F0AD3E58965DA20A9F571EF1651A56933748E1BF1C99E537C4E039
  ```

- <span data-ttu-id="b356c-127">Sprawdź, czy sygnatura *foo. nupkg* jest zgodna z jednym z określonych odcisków palca certyfikatu:</span><span class="sxs-lookup"><span data-stu-id="b356c-127">Verify *foo.nupkg* signature matches with one of the specified certificate fingerprints:</span></span>

  ```dotnetcli
  dotnet nuget verify foo.nupkg --certificate-fingerprint CE40881FF5F0AD3E58965DA20A9F571EF1651A56933748E1BF1C99E537C4E039 --certificate-fingerprint EC10992GG5F0AD3E58965DA20A9F571EF1651A56933748E1BF1C99E537C4E027
  ```
