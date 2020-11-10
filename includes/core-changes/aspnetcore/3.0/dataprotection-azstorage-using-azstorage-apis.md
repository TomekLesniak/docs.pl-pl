---
ms.openlocfilehash: f6e4c3d5c5fd020562e48515554136e0f8b6785c
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/10/2020
ms.locfileid: "94440427"
---
### <a name="data-protection-dataprotectionblobs-uses-new-azure-storage-apis"></a><span data-ttu-id="af470-101">Ochrona danych: dataprotection. obiekty blob używają nowych interfejsów API usługi Azure Storage</span><span class="sxs-lookup"><span data-stu-id="af470-101">Data Protection: DataProtection.Blobs uses new Azure Storage APIs</span></span>

<span data-ttu-id="af470-102">`Azure.Extensions.AspNetCore.DataProtection.Blobs` zależy od [bibliotek usługi Azure Storage](https://github.com/Azure/azure-storage-net).</span><span class="sxs-lookup"><span data-stu-id="af470-102">`Azure.Extensions.AspNetCore.DataProtection.Blobs` depends on the [Azure Storage libraries](https://github.com/Azure/azure-storage-net).</span></span> <span data-ttu-id="af470-103">Te biblioteki zmieniły swoje zestawy, pakiety i przestrzenie nazw.</span><span class="sxs-lookup"><span data-stu-id="af470-103">These libraries renamed their assemblies, packages, and namespaces.</span></span> <span data-ttu-id="af470-104">Począwszy od ASP.NET Core 3,0, program `Azure.Extensions.AspNetCore.DataProtection.Blobs` używa nowych `Azure.Storage.` prefiksów interfejsów API i pakietów.</span><span class="sxs-lookup"><span data-stu-id="af470-104">Starting in ASP.NET Core 3.0, `Azure.Extensions.AspNetCore.DataProtection.Blobs` uses the new `Azure.Storage.`-prefixed APIs and packages.</span></span>

<span data-ttu-id="af470-105">Pytania dotyczące interfejsów API usługi Azure Storage można używać <https://github.com/Azure/azure-storage-net> .</span><span class="sxs-lookup"><span data-stu-id="af470-105">For questions about the Azure Storage APIs, use <https://github.com/Azure/azure-storage-net>.</span></span> <span data-ttu-id="af470-106">Aby zapoznać się z omówieniem tego problemu, zobacz [dotnet/aspnetcore # 19570](https://github.com/dotnet/aspnetcore/issues/19570).</span><span class="sxs-lookup"><span data-stu-id="af470-106">For discussion on this issue, see [dotnet/aspnetcore#19570](https://github.com/dotnet/aspnetcore/issues/19570).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="af470-107">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="af470-107">Version introduced</span></span>

<span data-ttu-id="af470-108">3.0</span><span class="sxs-lookup"><span data-stu-id="af470-108">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="af470-109">Stare zachowanie</span><span class="sxs-lookup"><span data-stu-id="af470-109">Old behavior</span></span>

<span data-ttu-id="af470-110">Pakiet przywoływany do `WindowsAzure.Storage` pakietu NuGet.</span><span class="sxs-lookup"><span data-stu-id="af470-110">The package referenced the `WindowsAzure.Storage` NuGet package.</span></span>
<span data-ttu-id="af470-111">Pakiet odwołuje się do `Microsoft.Azure.Storage.Blob` pakietu NuGet.</span><span class="sxs-lookup"><span data-stu-id="af470-111">The package references the `Microsoft.Azure.Storage.Blob` NuGet package.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="af470-112">Nowe zachowanie</span><span class="sxs-lookup"><span data-stu-id="af470-112">New behavior</span></span>

<span data-ttu-id="af470-113">Pakiet odwołuje się do `Azure.Storage.Blob` pakietu NuGet.</span><span class="sxs-lookup"><span data-stu-id="af470-113">The package references the `Azure.Storage.Blob` NuGet package.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="af470-114">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="af470-114">Reason for change</span></span>

<span data-ttu-id="af470-115">Ta zmiana umożliwia `Azure.Extensions.AspNetCore.DataProtection.Blobs` Migrowanie do zalecanych pakietów usługi Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="af470-115">This change allows `Azure.Extensions.AspNetCore.DataProtection.Blobs` to migrate to the recommended Azure Storage packages.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="af470-116">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="af470-116">Recommended action</span></span>

<span data-ttu-id="af470-117">Jeśli nadal potrzebujesz użyć starszych interfejsów API usługi Azure Storage z ASP.NET Core 3,0, Dodaj bezpośrednią zależność do pakietu [windowsazure. Storage](https://www.nuget.org/packages/WindowsAzure.Storage/) lub [Microsoft. Azure. Storage](https://www.nuget.org/packages/Microsoft.Azure.Storage.Blob/).</span><span class="sxs-lookup"><span data-stu-id="af470-117">If you still need to use the older Azure Storage APIs with ASP.NET Core 3.0, add a direct dependency to the package [WindowsAzure.Storage](https://www.nuget.org/packages/WindowsAzure.Storage/) or [Microsoft.Azure.Storage](https://www.nuget.org/packages/Microsoft.Azure.Storage.Blob/).</span></span> <span data-ttu-id="af470-118">Ten pakiet można zainstalować obok nowych `Azure.Storage` interfejsów API.</span><span class="sxs-lookup"><span data-stu-id="af470-118">This package can be installed alongside the new `Azure.Storage` APIs.</span></span>

<span data-ttu-id="af470-119">W wielu przypadkach uaktualnienie obejmuje jedynie zmianę `using` instrukcji w celu użycia nowych przestrzeni nazw:</span><span class="sxs-lookup"><span data-stu-id="af470-119">In many cases, the upgrade only involves changing the `using` statements to use the new namespaces:</span></span>

```diff
- using Microsoft.WindowsAzure.Storage;
- using Microsoft.WindowsAzure.Storage.Blob;
- using Microsoft.Azure.Storage;
- using Microsoft.Azure.Storage.Blob;
+ using Azure.Storage;
+ using Azure.Storage.Blobs;
```

#### <a name="category"></a><span data-ttu-id="af470-120">Kategoria</span><span class="sxs-lookup"><span data-stu-id="af470-120">Category</span></span>

<span data-ttu-id="af470-121">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="af470-121">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="af470-122">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="af470-122">Affected APIs</span></span>

<span data-ttu-id="af470-123">Brak</span><span class="sxs-lookup"><span data-stu-id="af470-123">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
