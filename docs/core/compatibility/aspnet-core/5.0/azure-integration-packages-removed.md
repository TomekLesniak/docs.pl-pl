---
title: 'Istotna zmiana: Azure: Usunięto wstępnie naprawione pakiety integracji platformy Azure'
description: 'Dowiedz się więcej o istotnej zmianie w ASP.NET Core 5,0 zatytułowanej Azure: pakiety integracji platformy Azure z prefiksem firmy Microsoft zostały usunięte'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: b9f685b8c9fdcd73044f78840f2732809a0de710
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761664"
---
# <a name="azure-microsoft-prefixed-azure-integration-packages-removed"></a><span data-ttu-id="51b83-103">Azure: Usunięto wstępnie ustalone pakiety integracji platformy Azure</span><span class="sxs-lookup"><span data-stu-id="51b83-103">Azure: Microsoft-prefixed Azure integration packages removed</span></span>

<span data-ttu-id="51b83-104">Następujące `Microsoft.*` pakiety zapewniające integrację między ASP.NET Core i zestawami SDK platformy Azure nie są uwzględnione w ASP.NET Core 5,0:</span><span class="sxs-lookup"><span data-stu-id="51b83-104">The following `Microsoft.*` packages that provide integration between ASP.NET Core and Azure SDKs aren't included in ASP.NET Core 5.0:</span></span>

* <span data-ttu-id="51b83-105">[Microsoft.Extensions.Configwersja. AzureKeyVault](https://www.nuget.org/packages/Microsoft.Extensions.Configuration.AzureKeyVault/), która integruje [Azure Key Vault](/azure/key-vault/) do [systemu konfiguracji](/aspnet/core/fundamentals/configuration/).</span><span class="sxs-lookup"><span data-stu-id="51b83-105">[Microsoft.Extensions.Configuration.AzureKeyVault](https://www.nuget.org/packages/Microsoft.Extensions.Configuration.AzureKeyVault/), which integrates [Azure Key Vault](/azure/key-vault/) into the [Configuration system](/aspnet/core/fundamentals/configuration/).</span></span>
* <span data-ttu-id="51b83-106">[Microsoft. AspNetCore. dataprotection. AzureKeyVault](https://www.nuget.org/packages/Microsoft.AspNetCore.DataProtection.AzureKeyVault/), który integruje Azure Key Vault z [ASP.NET Core systemem ochrony danych](/aspnet/core/security/data-protection/introduction).</span><span class="sxs-lookup"><span data-stu-id="51b83-106">[Microsoft.AspNetCore.DataProtection.AzureKeyVault](https://www.nuget.org/packages/Microsoft.AspNetCore.DataProtection.AzureKeyVault/), which integrates Azure Key Vault into the [ASP.NET Core Data Protection system](/aspnet/core/security/data-protection/introduction).</span></span>
* <span data-ttu-id="51b83-107">[Microsoft. AspNetCore. dataprotection. AzureStorage](https://www.nuget.org/packages/Microsoft.AspNetCore.DataProtection.AzureStorage/), który integruje [BLOB Storage platformy Azure](/azure/storage/blobs/) z systemem ochrony danych ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="51b83-107">[Microsoft.AspNetCore.DataProtection.AzureStorage](https://www.nuget.org/packages/Microsoft.AspNetCore.DataProtection.AzureStorage/), which integrates [Azure Blob Storage](/azure/storage/blobs/) into the ASP.NET Core Data Protection system.</span></span>

<span data-ttu-id="51b83-108">Aby zapoznać się z omówieniem tego problemu, zobacz [dotnet/aspnetcore # 19570](https://github.com/dotnet/aspnetcore/issues/19570).</span><span class="sxs-lookup"><span data-stu-id="51b83-108">For discussion on this issue, see [dotnet/aspnetcore#19570](https://github.com/dotnet/aspnetcore/issues/19570).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="51b83-109">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="51b83-109">Version introduced</span></span>

<span data-ttu-id="51b83-110">5,0 wersja zapoznawcza 1</span><span class="sxs-lookup"><span data-stu-id="51b83-110">5.0 Preview 1</span></span>

## <a name="old-behavior"></a><span data-ttu-id="51b83-111">Stare zachowanie</span><span class="sxs-lookup"><span data-stu-id="51b83-111">Old behavior</span></span>

<span data-ttu-id="51b83-112">`Microsoft.*`Pakiety zintegrowane z usługami platformy Azure z interfejsami API konfiguracji i ochrony danych.</span><span class="sxs-lookup"><span data-stu-id="51b83-112">The `Microsoft.*` packages integrated Azure services with the Configuration and Data Protection APIs.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="51b83-113">Nowe zachowanie</span><span class="sxs-lookup"><span data-stu-id="51b83-113">New behavior</span></span>

<span data-ttu-id="51b83-114">Nowe `Azure.*` pakiety integrują usługi platformy Azure z interfejsami API konfiguracji i ochrony danych.</span><span class="sxs-lookup"><span data-stu-id="51b83-114">New `Azure.*` packages integrate Azure services with the Configuration and Data Protection APIs.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="51b83-115">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="51b83-115">Reason for change</span></span>

<span data-ttu-id="51b83-116">Wprowadzono zmianę, ponieważ `Microsoft.*` pakiety:</span><span class="sxs-lookup"><span data-stu-id="51b83-116">The change was made because the `Microsoft.*` packages were:</span></span>

* <span data-ttu-id="51b83-117">Korzystanie z nieaktualnych wersji zestawu Azure SDK.</span><span class="sxs-lookup"><span data-stu-id="51b83-117">Using outdated versions of the Azure SDK.</span></span> <span data-ttu-id="51b83-118">Proste aktualizacje nie były możliwe, ponieważ nowe wersje zestawu Azure SDK obejmowały istotne zmiany.</span><span class="sxs-lookup"><span data-stu-id="51b83-118">Simple updates weren't possible because the new versions of the Azure SDK included breaking changes.</span></span>
* <span data-ttu-id="51b83-119">Powiązane z harmonogramem wersji platformy .NET Core.</span><span class="sxs-lookup"><span data-stu-id="51b83-119">Tied to the .NET Core release schedule.</span></span> <span data-ttu-id="51b83-120">Przeniesienie własności pakietów do zespołu zestawu Azure SDK umożliwia aktualizowanie pakietów w miarę aktualizowania zestawu Azure SDK.</span><span class="sxs-lookup"><span data-stu-id="51b83-120">Transferring ownership of the packages to the Azure SDK team enables package updates as the Azure SDK is updated.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="51b83-121">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="51b83-121">Recommended action</span></span>

<span data-ttu-id="51b83-122">W ASP.NET Core 2,1 lub nowszych projektach Zastąp stary `Microsoft.*` z nowymi `Azure.*` pakietami.</span><span class="sxs-lookup"><span data-stu-id="51b83-122">In ASP.NET Core 2.1 or later projects, replace the old `Microsoft.*` with the new `Azure.*` packages.</span></span>

| <span data-ttu-id="51b83-123">Starsze</span><span class="sxs-lookup"><span data-stu-id="51b83-123">Old</span></span> | <span data-ttu-id="51b83-124">Nowy</span><span class="sxs-lookup"><span data-stu-id="51b83-124">New</span></span> |
|--|--|
| `Microsoft.AspNetCore.DataProtection.AzureKeyVault` | [<span data-ttu-id="51b83-125">Azure. Extensions. AspNetCore. dataprotection. Keys</span><span class="sxs-lookup"><span data-stu-id="51b83-125">Azure.Extensions.AspNetCore.DataProtection.Keys</span></span>](https://www.nuget.org/packages/Azure.Extensions.AspNetCore.DataProtection.Keys) |
| `Microsoft.AspNetCore.DataProtection.AzureStorage` | [<span data-ttu-id="51b83-126">Azure. Extensions. AspNetCore. dataprotection. Blobs</span><span class="sxs-lookup"><span data-stu-id="51b83-126">Azure.Extensions.AspNetCore.DataProtection.Blobs</span></span>](https://www.nuget.org/packages/Azure.Extensions.AspNetCore.DataProtection.Blobs) |
| `Microsoft.Extensions.Configuration.AzureKeyVault` | [<span data-ttu-id="51b83-127">Azure.Extensions.AspNetCore.Configwersja. Klucz</span><span class="sxs-lookup"><span data-stu-id="51b83-127">Azure.Extensions.AspNetCore.Configuration.Secrets</span></span>](https://www.nuget.org/packages/Azure.Extensions.AspNetCore.Configuration.Secrets) |

<span data-ttu-id="51b83-128">Nowe pakiety korzystają z nowej wersji zestawu Azure SDK, która zawiera istotne zmiany.</span><span class="sxs-lookup"><span data-stu-id="51b83-128">The new packages use a new version of the Azure SDK that includes breaking changes.</span></span> <span data-ttu-id="51b83-129">Wzorce użycia ogólne nie są zmieniane.</span><span class="sxs-lookup"><span data-stu-id="51b83-129">The general usage patterns are unchanged.</span></span> <span data-ttu-id="51b83-130">Niektóre przeciążenia i opcje mogą się różnić w zależności od zmian w bazowych interfejsach API zestawu Azure SDK.</span><span class="sxs-lookup"><span data-stu-id="51b83-130">Some overloads and options may differ to adapt to changes in the underlying Azure SDK APIs.</span></span>

<span data-ttu-id="51b83-131">Stare pakiety będą:</span><span class="sxs-lookup"><span data-stu-id="51b83-131">The old packages will:</span></span>

* <span data-ttu-id="51b83-132">Być obsługiwane przez zespół ASP.NET Core w okresie istnienia .NET Core 2,1 i 3,1.</span><span class="sxs-lookup"><span data-stu-id="51b83-132">Be supported by the ASP.NET Core team for the lifetime of .NET Core 2.1 and 3.1.</span></span>
* <span data-ttu-id="51b83-133">Nie jest uwzględniony w programie .NET 5.</span><span class="sxs-lookup"><span data-stu-id="51b83-133">Not be included in .NET 5.</span></span>

<span data-ttu-id="51b83-134">Podczas uaktualniania projektu do programu .NET 5 Przejdź do pakietów, `Azure.*` Aby zachować pomoc techniczną.</span><span class="sxs-lookup"><span data-stu-id="51b83-134">When upgrading your project to .NET 5, transition to the `Azure.*` packages to maintain support.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="51b83-135">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="51b83-135">Affected APIs</span></span>

- <xref:Microsoft.Extensions.Configuration.AzureKeyVaultConfigurationExtensions.AddAzureKeyVault%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.DataProtection.AzureDataProtectionBuilderExtensions.ProtectKeysWithAzureKeyVault%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.DataProtection.AzureDataProtectionBuilderExtensions.PersistKeysToAzureBlobStorage%2A?displayProperty=nameWithType>

<!--

### Category

ASP.NET Core

### Affected APIs

- `Overload:Microsoft.Extensions.Configuration.AzureKeyVaultConfigurationExtensions.AddAzureKeyVault`
- `Overload:Microsoft.AspNetCore.DataProtection.AzureDataProtectionBuilderExtensions.ProtectKeysWithAzureKeyVault`
- `Overload:Microsoft.AspNetCore.DataProtection.AzureDataProtectionBuilderExtensions.PersistKeysToAzureBlobStorage`

-->
