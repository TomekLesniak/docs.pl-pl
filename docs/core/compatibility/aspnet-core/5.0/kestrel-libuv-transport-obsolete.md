---
title: 'Zmiana podziału: Kestrel: Libuv transport oznaczony jako przestarzały'
description: 'Dowiedz się więcej o istotnej zmianie w ASP.NET Core 5,0 zatytułowanej Kestrel: Libuv transport oznaczony jako przestarzały'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: f66b9b646671e07957e6d30a95333d392eb29617
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761520"
---
# <a name="kestrel-libuv-transport-marked-as-obsolete"></a><span data-ttu-id="0ff95-103">Kestrel: transport Libuv oznaczony jako przestarzały</span><span class="sxs-lookup"><span data-stu-id="0ff95-103">Kestrel: Libuv transport marked as obsolete</span></span>

<span data-ttu-id="0ff95-104">We wcześniejszych wersjach ASP.NET Core Libuv jako szczegóły implementacji, jak asynchroniczne dane wejściowe i wyjściowe zostały wykonane.</span><span class="sxs-lookup"><span data-stu-id="0ff95-104">Earlier versions of ASP.NET Core used Libuv as an implementation detail of how asynchronous input and output was performed.</span></span> <span data-ttu-id="0ff95-105">W ASP.NET Core 2,0 został opracowany alternatywny <xref:System.Net.Sockets.Socket> transport oparty na bazie.</span><span class="sxs-lookup"><span data-stu-id="0ff95-105">In ASP.NET Core 2.0, an alternative, <xref:System.Net.Sockets.Socket>-based transport was developed.</span></span> <span data-ttu-id="0ff95-106">W ASP.NET Core 2,1 Kestrel przełączać się do korzystania z `Socket` transportu opartego na protokole domyślnym.</span><span class="sxs-lookup"><span data-stu-id="0ff95-106">In ASP.NET Core 2.1, Kestrel switched to using the `Socket`-based transport by default.</span></span> <span data-ttu-id="0ff95-107">Obsługa Libuv została zachowana ze względu na zgodność.</span><span class="sxs-lookup"><span data-stu-id="0ff95-107">Libuv support was maintained for compatibility reasons.</span></span>

<span data-ttu-id="0ff95-108">W tym momencie korzystanie z `Socket` transportu opartego na bazie jest znacznie bardziej powszechne niż transport Libuv.</span><span class="sxs-lookup"><span data-stu-id="0ff95-108">At this point, use of the `Socket`-based transport is far more common than the Libuv transport.</span></span> <span data-ttu-id="0ff95-109">W związku z tym pomoc techniczna Libuv jest oznaczona jako przestarzała w programie .NET 5,0 i zostanie usunięta całkowicie w programie .NET 6,0.</span><span class="sxs-lookup"><span data-stu-id="0ff95-109">Consequently, Libuv support is marked as obsolete in .NET 5.0 and will be removed entirely in .NET 6.0.</span></span>

<span data-ttu-id="0ff95-110">W ramach tej zmiany Libuv obsługę nowych platform systemu operacyjnego (na przykład Windows ARM64) nie zostaną dodane w przedziale czasu .NET 5,0.</span><span class="sxs-lookup"><span data-stu-id="0ff95-110">As part of this change, Libuv support for new operating system platforms (like Windows ARM64) won't be added in the .NET 5.0 timeframe.</span></span>

<span data-ttu-id="0ff95-111">Aby uzyskać więcej dyskusji na temat blokowania problemów, które wymagają użycia transportu Libuv, zobacz problem z usługą GitHub w usłudze [dotnet/aspnetcore # 23409](https://github.com/dotnet/aspnetcore/issues/23409).</span><span class="sxs-lookup"><span data-stu-id="0ff95-111">For discussion on blocking issues that require the use of the Libuv transport, see the GitHub issue at [dotnet/aspnetcore#23409](https://github.com/dotnet/aspnetcore/issues/23409).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="0ff95-112">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="0ff95-112">Version introduced</span></span>

<span data-ttu-id="0ff95-113">5,0 wersja zapoznawcza 8</span><span class="sxs-lookup"><span data-stu-id="0ff95-113">5.0 Preview 8</span></span>

## <a name="old-behavior"></a><span data-ttu-id="0ff95-114">Stare zachowanie</span><span class="sxs-lookup"><span data-stu-id="0ff95-114">Old behavior</span></span>

<span data-ttu-id="0ff95-115">Interfejsy API Libuv nie są oznaczone jako przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="0ff95-115">The Libuv APIs aren't marked as obsolete.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="0ff95-116">Nowe zachowanie</span><span class="sxs-lookup"><span data-stu-id="0ff95-116">New behavior</span></span>

<span data-ttu-id="0ff95-117">Interfejsy API Libuv są oznaczone jako przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="0ff95-117">The Libuv APIs are marked as obsolete.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="0ff95-118">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="0ff95-118">Reason for change</span></span>

<span data-ttu-id="0ff95-119">`Socket`Domyślnym ustawieniem jest transport oparty na protokole.</span><span class="sxs-lookup"><span data-stu-id="0ff95-119">The `Socket`-based transport is the default.</span></span> <span data-ttu-id="0ff95-120">Nie ma żadnych istotnych powodów, aby nadal korzystać z transportu Libuv.</span><span class="sxs-lookup"><span data-stu-id="0ff95-120">There aren't any compelling reasons to continue using the Libuv transport.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="0ff95-121">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="0ff95-121">Recommended action</span></span>

<span data-ttu-id="0ff95-122">Zaprzestanie korzystania z [pakietu Libuv](https://www.nuget.org/packages/Libuv) i metod rozszerzających.</span><span class="sxs-lookup"><span data-stu-id="0ff95-122">Discontinue use of the [Libuv package](https://www.nuget.org/packages/Libuv) and extension methods.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="0ff95-123">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="0ff95-123">Affected APIs</span></span>

- [<span data-ttu-id="0ff95-124">WebHostBuilderLibuvExtensions</span><span class="sxs-lookup"><span data-stu-id="0ff95-124">WebHostBuilderLibuvExtensions</span></span>](/dotnet/api/microsoft.aspnetcore.hosting.webhostbuilderlibuvextensions?view=aspnetcore-3.0)
- [<span data-ttu-id="0ff95-125">WebHostBuilderLibuvExtensions.UseLibuv</span><span class="sxs-lookup"><span data-stu-id="0ff95-125">WebHostBuilderLibuvExtensions.UseLibuv</span></span>](/dotnet/api/microsoft.aspnetcore.hosting.webhostbuilderlibuvextensions.uselibuv?view=aspnetcore-3.0)
- [<span data-ttu-id="0ff95-126">Microsoft. AspNetCore. Server. Kestrel. transport. Libuv. LibuvTransportOptions</span><span class="sxs-lookup"><span data-stu-id="0ff95-126">Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions</span></span>](/dotnet/api/microsoft.aspnetcore.server.kestrel.transport.libuv.libuvtransportoptions?view=aspnetcore-3.0)
- [<span data-ttu-id="0ff95-127">Microsoft. AspNetCore. Server. Kestrel. transport. Libuv. LibuvTransportOptions. ThreadCount</span><span class="sxs-lookup"><span data-stu-id="0ff95-127">Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.ThreadCount</span></span>](/dotnet/api/microsoft.aspnetcore.server.kestrel.transport.libuv.libuvtransportoptions.threadcount?view=aspnetcore-3.0)
- [<span data-ttu-id="0ff95-128">Microsoft. AspNetCore. Server. Kestrel. transport. Libuv. LibuvTransportOptions. NoDelay</span><span class="sxs-lookup"><span data-stu-id="0ff95-128">Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.NoDelay</span></span>](/dotnet/api/microsoft.aspnetcore.server.kestrel.transport.libuv.libuvtransportoptions.nodelay?view=aspnetcore-3.0)
- [<span data-ttu-id="0ff95-129">Microsoft. AspNetCore. Server. Kestrel. transport. Libuv. LibuvTransportOptions. MaxWriteBufferSize</span><span class="sxs-lookup"><span data-stu-id="0ff95-129">Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.MaxWriteBufferSize</span></span>](/dotnet/api/microsoft.aspnetcore.server.kestrel.transport.libuv.libuvtransportoptions.maxwritebuffersize?view=aspnetcore-3.0)
- [<span data-ttu-id="0ff95-130">Microsoft. AspNetCore. Server. Kestrel. transport. Libuv. LibuvTransportOptions. MaxReadBufferSize</span><span class="sxs-lookup"><span data-stu-id="0ff95-130">Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.MaxReadBufferSize</span></span>](/dotnet/api/microsoft.aspnetcore.server.kestrel.transport.libuv.libuvtransportoptions.maxreadbuffersize?view=aspnetcore-3.0)
- `Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.Backlog`

<!--

### Category

ASP.NET Core

### Affected APIs

- `T:Microsoft.AspNetCore.Hosting.WebHostBuilderLibuvExtensions`
- `Overload:Microsoft.AspNetCore.Hosting.WebHostBuilderLibuvExtensions.UseLibuv`
- `T:Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions`
- `P:Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.ThreadCount`
- `P:Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.NoDelay`
- `P:Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.MaxWriteBufferSize`
- `P:Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.MaxReadBufferSize`
- `P:Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.Backlog`

-->
