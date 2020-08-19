---
ms.openlocfilehash: 115cd6be935ae12a1293f948a0f899c6c3ff0d78
ms.sourcegitcommit: cbb19e56d48cf88375d35d0c27554d4722761e0d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/19/2020
ms.locfileid: "88608467"
---
### <a name="winhttphandler-removed-from-net-runtime"></a><span data-ttu-id="3206c-101">WinHttpHandler usunięte z środowiska uruchomieniowego platformy .NET</span><span class="sxs-lookup"><span data-stu-id="3206c-101">WinHttpHandler removed from .NET runtime</span></span>

<span data-ttu-id="3206c-102">`WinHttpHandler`Klasa została usunięta z zestawu *System.Net.Http.dll* .</span><span class="sxs-lookup"><span data-stu-id="3206c-102">The `WinHttpHandler` class was removed from the *System.Net.Http.dll* assembly.</span></span> <span data-ttu-id="3206c-103">Jest ona teraz dostępna tylko jako [pakiet NuGet](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/)poza pasmem (OOB).</span><span class="sxs-lookup"><span data-stu-id="3206c-103">It's now available only as an out-of-band (OOB) [NuGet package](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="3206c-104">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="3206c-104">Version introduced</span></span>

<span data-ttu-id="3206c-105">5.0</span><span class="sxs-lookup"><span data-stu-id="3206c-105">5.0</span></span>

#### <a name="change-description"></a><span data-ttu-id="3206c-106">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="3206c-106">Change description</span></span>

<span data-ttu-id="3206c-107">W poprzednich wersjach .NET <xref:System.Net.Http.WinHttpHandler> Klasa jest dostępna jako część podstawowych bibliotek .NET.</span><span class="sxs-lookup"><span data-stu-id="3206c-107">In previous .NET versions, the <xref:System.Net.Http.WinHttpHandler> class is available as part of the core .NET libraries.</span></span> <span data-ttu-id="3206c-108">Począwszy od platformy .NET 5,0, <xref:System.Net.Http.WinHttpHandler> Klasa jest dostępna tylko jako oddzielnie zainstalowany [pakiet NuGet](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/).</span><span class="sxs-lookup"><span data-stu-id="3206c-108">Starting in .NET 5.0, the <xref:System.Net.Http.WinHttpHandler> class is only available as a separately installed [NuGet package](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/).</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="3206c-109">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="3206c-109">Recommended action</span></span>

<span data-ttu-id="3206c-110">Zainstaluj [pakiet NuGet system .NET. http. WinHttpHandler](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/).</span><span class="sxs-lookup"><span data-stu-id="3206c-110">Install the [System.Net.Http.WinHttpHandler NuGet package](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/).</span></span> <span data-ttu-id="3206c-111">Lub, jeśli nie są wymagane funkcje dotyczące usługi WinHTTP, użyj <xref:System.Net.Http.SocketsHttpHandler> zamiast tego.</span><span class="sxs-lookup"><span data-stu-id="3206c-111">Or, if you don't require WinHTTP-specific features, use <xref:System.Net.Http.SocketsHttpHandler> instead.</span></span>

#### <a name="category"></a><span data-ttu-id="3206c-112">Kategoria</span><span class="sxs-lookup"><span data-stu-id="3206c-112">Category</span></span>

<span data-ttu-id="3206c-113">Networking</span><span class="sxs-lookup"><span data-stu-id="3206c-113">Networking</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="3206c-114">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="3206c-114">Affected APIs</span></span>

- <xref:System.Net.Http.WinHttpHandler?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.Net.Http.WinHttpHandler`

-->
