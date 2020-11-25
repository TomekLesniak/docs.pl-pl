---
title: 'Zmiana podziału: WinHttpHandler usunięty z środowiska uruchomieniowego platformy .NET'
description: Dowiedz się więcej na temat istotnej zmiany w programie .NET 5,0, gdzie WinHttpHandler został usunięty z środowiska uruchomieniowego platformy .NET.
ms.date: 10/18/2020
ms.openlocfilehash: f8b9910ade8d459133791a23704d624a91cc5dff
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761435"
---
# <a name="winhttphandler-removed-from-net-runtime"></a><span data-ttu-id="48b4e-103">WinHttpHandler usunięte z środowiska uruchomieniowego platformy .NET</span><span class="sxs-lookup"><span data-stu-id="48b4e-103">WinHttpHandler removed from .NET runtime</span></span>

<span data-ttu-id="48b4e-104">`WinHttpHandler`Klasa została usunięta z zestawu *System.Net.Http.dll* .</span><span class="sxs-lookup"><span data-stu-id="48b4e-104">The `WinHttpHandler` class was removed from the *System.Net.Http.dll* assembly.</span></span> <span data-ttu-id="48b4e-105">Jest ona teraz dostępna tylko jako [pakiet NuGet](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/)poza pasmem (OOB).</span><span class="sxs-lookup"><span data-stu-id="48b4e-105">It's now available only as an out-of-band (OOB) [NuGet package](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="48b4e-106">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="48b4e-106">Version introduced</span></span>

<span data-ttu-id="48b4e-107">5,0</span><span class="sxs-lookup"><span data-stu-id="48b4e-107">5.0</span></span>

## <a name="change-description"></a><span data-ttu-id="48b4e-108">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="48b4e-108">Change description</span></span>

<span data-ttu-id="48b4e-109">W poprzednich wersjach .NET <xref:System.Net.Http.WinHttpHandler> Klasa jest dostępna jako część podstawowych bibliotek .NET.</span><span class="sxs-lookup"><span data-stu-id="48b4e-109">In previous .NET versions, the <xref:System.Net.Http.WinHttpHandler> class is available as part of the core .NET libraries.</span></span> <span data-ttu-id="48b4e-110">Począwszy od platformy .NET 5,0, <xref:System.Net.Http.WinHttpHandler> Klasa jest dostępna tylko jako oddzielnie zainstalowany [pakiet NuGet](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/).</span><span class="sxs-lookup"><span data-stu-id="48b4e-110">Starting in .NET 5.0, the <xref:System.Net.Http.WinHttpHandler> class is only available as a separately installed [NuGet package](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/).</span></span>

## <a name="recommended-action"></a><span data-ttu-id="48b4e-111">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="48b4e-111">Recommended action</span></span>

<span data-ttu-id="48b4e-112">Zainstaluj [pakiet NuGet system .NET. http. WinHttpHandler](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/).</span><span class="sxs-lookup"><span data-stu-id="48b4e-112">Install the [System.Net.Http.WinHttpHandler NuGet package](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/).</span></span> <span data-ttu-id="48b4e-113">Lub, jeśli nie są wymagane funkcje dotyczące usługi WinHTTP, użyj <xref:System.Net.Http.SocketsHttpHandler> zamiast tego.</span><span class="sxs-lookup"><span data-stu-id="48b4e-113">Or, if you don't require WinHTTP-specific features, use <xref:System.Net.Http.SocketsHttpHandler> instead.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="48b4e-114">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="48b4e-114">Affected APIs</span></span>

- <xref:System.Net.Http.WinHttpHandler?displayProperty=fullName>

<!--

### Affected APIs

- `T:System.Net.Http.WinHttpHandler`

### Category

Networking

-->
