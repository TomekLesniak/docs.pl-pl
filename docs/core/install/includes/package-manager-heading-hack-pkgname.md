---
ms.openlocfilehash: ab1006f706439bcf5129854da3d14538e5b690a2
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/11/2020
ms.locfileid: "94506881"
---

<span data-ttu-id="d8d18-101">Pakiety dodane do źródeł Menedżera pakietów są nazywane w formacie włamywania: `{product}-{type}-{version}` .</span><span class="sxs-lookup"><span data-stu-id="d8d18-101">The packages added to package manager feeds are named in a hackable format: `{product}-{type}-{version}`.</span></span>

- <span data-ttu-id="d8d18-102">**iloczyn**</span><span class="sxs-lookup"><span data-stu-id="d8d18-102">**product**</span></span>\
<span data-ttu-id="d8d18-103">Typ produktu .NET do zainstalowania.</span><span class="sxs-lookup"><span data-stu-id="d8d18-103">The type of .NET product to install.</span></span> <span data-ttu-id="d8d18-104">Prawidłowe opcje to:</span><span class="sxs-lookup"><span data-stu-id="d8d18-104">Valid options are:</span></span>

  - <span data-ttu-id="d8d18-105">dotnet</span><span class="sxs-lookup"><span data-stu-id="d8d18-105">dotnet</span></span>
  - <span data-ttu-id="d8d18-106">aspnetcore</span><span class="sxs-lookup"><span data-stu-id="d8d18-106">aspnetcore</span></span>

- <span data-ttu-id="d8d18-107">**Wprowadź**</span><span class="sxs-lookup"><span data-stu-id="d8d18-107">**type**</span></span>\
<span data-ttu-id="d8d18-108">Wybiera zestaw SDK lub środowisko uruchomieniowe.</span><span class="sxs-lookup"><span data-stu-id="d8d18-108">Chooses the SDK or the runtime.</span></span> <span data-ttu-id="d8d18-109">Prawidłowe opcje to:</span><span class="sxs-lookup"><span data-stu-id="d8d18-109">Valid options are:</span></span>

  - <span data-ttu-id="d8d18-110">sdk</span><span class="sxs-lookup"><span data-stu-id="d8d18-110">sdk</span></span>
  - <span data-ttu-id="d8d18-111">środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="d8d18-111">runtime</span></span>

- <span data-ttu-id="d8d18-112">**Wersja**</span><span class="sxs-lookup"><span data-stu-id="d8d18-112">**version**</span></span>\
<span data-ttu-id="d8d18-113">Wersja zestawu SDK lub środowiska uruchomieniowego do zainstalowania.</span><span class="sxs-lookup"><span data-stu-id="d8d18-113">The version of the SDK or runtime to install.</span></span> <span data-ttu-id="d8d18-114">Ten artykuł będzie zawsze zawierać instrukcje dotyczące najnowszej obsługiwanej wersji.</span><span class="sxs-lookup"><span data-stu-id="d8d18-114">This article will always give the instructions for the latest supported version.</span></span> <span data-ttu-id="d8d18-115">Prawidłowe opcje to wszystkie wydane wersje, takie jak:</span><span class="sxs-lookup"><span data-stu-id="d8d18-115">Valid options are any released version, such as:</span></span>

  - <span data-ttu-id="d8d18-116">5,0</span><span class="sxs-lookup"><span data-stu-id="d8d18-116">5.0</span></span>
  - <span data-ttu-id="d8d18-117">3,1</span><span class="sxs-lookup"><span data-stu-id="d8d18-117">3.1</span></span>
  - <span data-ttu-id="d8d18-118">3.0</span><span class="sxs-lookup"><span data-stu-id="d8d18-118">3.0</span></span>
  - <span data-ttu-id="d8d18-119">2.1</span><span class="sxs-lookup"><span data-stu-id="d8d18-119">2.1</span></span>

  <span data-ttu-id="d8d18-120">Możliwe, że zestaw SDK/środowisko uruchomieniowe, które próbujesz pobrać, nie jest dostępny dla dystrybucji systemu Linux.</span><span class="sxs-lookup"><span data-stu-id="d8d18-120">It's possible the SDK/runtime you're trying to download is not available for your Linux distribution.</span></span> <span data-ttu-id="d8d18-121">Aby zapoznać się z listą obsługiwanych dystrybucji, zobacz temat [zależności i wymagania dotyczące platformy .NET Core](../linux.md).</span><span class="sxs-lookup"><span data-stu-id="d8d18-121">For a list of supported distributions, see [.NET Core dependencies and requirements](../linux.md).</span></span>

### <a name="examples"></a><span data-ttu-id="d8d18-122">Przykłady</span><span class="sxs-lookup"><span data-stu-id="d8d18-122">Examples</span></span>

- <span data-ttu-id="d8d18-123">Zainstaluj środowisko uruchomieniowe ASP.NET Core 5,0: `aspnetcore-runtime-5.0`</span><span class="sxs-lookup"><span data-stu-id="d8d18-123">Install the ASP.NET Core 5.0 runtime: `aspnetcore-runtime-5.0`</span></span>
- <span data-ttu-id="d8d18-124">Zainstaluj środowisko uruchomieniowe programu .NET Core 2,1: `dotnet-runtime-2.1`</span><span class="sxs-lookup"><span data-stu-id="d8d18-124">Install the .NET Core 2.1 runtime: `dotnet-runtime-2.1`</span></span>
- <span data-ttu-id="d8d18-125">Zainstaluj zestaw .NET 5,0 SDK: `dotnet-sdk-5.0`</span><span class="sxs-lookup"><span data-stu-id="d8d18-125">Install the .NET 5.0 SDK: `dotnet-sdk-5.0`</span></span>
- <span data-ttu-id="d8d18-126">Zainstaluj zestaw SDK platformy .NET Core 3,1: `dotnet-sdk-3.1`</span><span class="sxs-lookup"><span data-stu-id="d8d18-126">Install the .NET Core 3.1 SDK: `dotnet-sdk-3.1`</span></span>

### <a name="package-missing"></a><span data-ttu-id="d8d18-127">Brak pakietu</span><span class="sxs-lookup"><span data-stu-id="d8d18-127">Package missing</span></span>

<span data-ttu-id="d8d18-128">Jeśli kombinacja pakiet-wersja nie działa, jest niedostępna.</span><span class="sxs-lookup"><span data-stu-id="d8d18-128">If the package-version combination doesn't work, it's not available.</span></span> <span data-ttu-id="d8d18-129">Na przykład nie istnieje zestaw SDK ASP.NET Core, składniki zestawu SDK są dołączone do zestawu .NET SDK.</span><span class="sxs-lookup"><span data-stu-id="d8d18-129">For example, there isn't an ASP.NET Core SDK, the SDK components are included with the .NET SDK.</span></span> <span data-ttu-id="d8d18-130">Wartość `aspnetcore-sdk-2.2` jest niepoprawna i powinna być `dotnet-sdk-2.2` .</span><span class="sxs-lookup"><span data-stu-id="d8d18-130">The value `aspnetcore-sdk-2.2` is incorrect and should be `dotnet-sdk-2.2`.</span></span> <span data-ttu-id="d8d18-131">Aby uzyskać listę dystrybucji systemu Linux obsługiwanych przez platformę .NET Core, zobacz [zależności i wymagania dotyczące platformy .NET](../linux.md).</span><span class="sxs-lookup"><span data-stu-id="d8d18-131">For a list of Linux distributions supported by .NET Core, see [.NET dependencies and requirements](../linux.md).</span></span>
