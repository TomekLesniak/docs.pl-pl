---
title: 'Nieprzerwana zmiana: sygnalizująca: protokół MessagePack Hub przeniesiony do MessagePack 2. x pakietu'
description: 'Dowiedz się więcej o istotnej zmianie w ASP.NET Core 5,0 z tytułem: protokół centrum MessagePack przeniesiony do MessagePack 2. x'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: 1e666c40d7046233c9fb06af819b901fd1251b06
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761687"
---
# <a name="signalr-messagepack-hub-protocol-moved-to-messagepack-2x-package"></a><span data-ttu-id="78bec-103">Sygnalizacja: przeniesiono protokół MessagePack Hub do pakietu MessagePack 2. x</span><span class="sxs-lookup"><span data-stu-id="78bec-103">SignalR: MessagePack Hub Protocol moved to MessagePack 2.x package</span></span>

<span data-ttu-id="78bec-104">Protokół ASP.NET Core sygnalizującego [MessagePack](/aspnet/core/signalr/messagepackhubprotocol) używa [pakietu NuGet MessagePack](https://www.nuget.org/packages/MessagePack) do serializacji MessagePack.</span><span class="sxs-lookup"><span data-stu-id="78bec-104">The ASP.NET Core SignalR [MessagePack Hub Protocol](/aspnet/core/signalr/messagepackhubprotocol) uses the [MessagePack NuGet package](https://www.nuget.org/packages/MessagePack) for MessagePack serialization.</span></span> <span data-ttu-id="78bec-105">ASP.NET Core 5,0 uaktualnia pakiet z 1. x do najnowszej wersji pakietu 2. x.</span><span class="sxs-lookup"><span data-stu-id="78bec-105">ASP.NET Core 5.0 upgrades the package from 1.x to the latest 2.x package version.</span></span>

<span data-ttu-id="78bec-106">Aby zapoznać się z omówieniem tego problemu, zobacz [dotnet/aspnetcore # 18692](https://github.com/dotnet/aspnetcore/issues/18692).</span><span class="sxs-lookup"><span data-stu-id="78bec-106">For discussion on this issue, see [dotnet/aspnetcore#18692](https://github.com/dotnet/aspnetcore/issues/18692).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="78bec-107">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="78bec-107">Version introduced</span></span>

<span data-ttu-id="78bec-108">5,0 wersja zapoznawcza 1</span><span class="sxs-lookup"><span data-stu-id="78bec-108">5.0 Preview 1</span></span>

## <a name="old-behavior"></a><span data-ttu-id="78bec-109">Stare zachowanie</span><span class="sxs-lookup"><span data-stu-id="78bec-109">Old behavior</span></span>

<span data-ttu-id="78bec-110">ASP.NET Core sygnalizujący użył pakietu MessagePack 1. x do serializacji i deserializacji komunikatów MessagePack.</span><span class="sxs-lookup"><span data-stu-id="78bec-110">ASP.NET Core SignalR used the MessagePack 1.x package to serialize and deserialize MessagePack messages.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="78bec-111">Nowe zachowanie</span><span class="sxs-lookup"><span data-stu-id="78bec-111">New behavior</span></span>

<span data-ttu-id="78bec-112">ASP.NET Core sygnalizujący używa pakietu MessagePack 2. x do serializacji i deserializacji komunikatów MessagePack.</span><span class="sxs-lookup"><span data-stu-id="78bec-112">ASP.NET Core SignalR uses the MessagePack 2.x package to serialize and deserialize MessagePack messages.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="78bec-113">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="78bec-113">Reason for change</span></span>

<span data-ttu-id="78bec-114">Najnowsze ulepszenia pakietu MessagePack 2. x umożliwiają dodawanie przydatnych funkcji.</span><span class="sxs-lookup"><span data-stu-id="78bec-114">The latest improvements in the MessagePack 2.x package add useful functionality.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="78bec-115">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="78bec-115">Recommended action</span></span>

<span data-ttu-id="78bec-116">Ta zmiana jest stosowana, gdy:</span><span class="sxs-lookup"><span data-stu-id="78bec-116">This breaking change applies when:</span></span>

* <span data-ttu-id="78bec-117">Ustawianie lub Konfigurowanie wartości w <xref:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions> .</span><span class="sxs-lookup"><span data-stu-id="78bec-117">Setting or configuring values on <xref:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions>.</span></span>
* <span data-ttu-id="78bec-118">Używanie interfejsów API MessagePack bezpośrednio i używanie protokołu ASP.NET Core sygnalizującego MessagePack w tym samym projekcie.</span><span class="sxs-lookup"><span data-stu-id="78bec-118">Using the MessagePack APIs directly and using the ASP.NET Core SignalR MessagePack Hub Protocol in the same project.</span></span> <span data-ttu-id="78bec-119">Nowsza wersja zostanie załadowana zamiast poprzedniej wersji.</span><span class="sxs-lookup"><span data-stu-id="78bec-119">The newer version will be loaded instead of the previous version.</span></span>

<span data-ttu-id="78bec-120">Aby uzyskać wskazówki dotyczące migracji z autorów pakietów, zobacz [Migrowanie z MessagePack v1. x do MessagePack v2. x](https://github.com/neuecc/MessagePack-CSharp/blob/master/doc/migration.md).</span><span class="sxs-lookup"><span data-stu-id="78bec-120">For migration guidance from the package authors, see [Migrating from MessagePack v1.x to MessagePack v2.x](https://github.com/neuecc/MessagePack-CSharp/blob/master/doc/migration.md).</span></span> <span data-ttu-id="78bec-121">Dotyczy to niektórych aspektów serializacji i deserializacji komunikatów.</span><span class="sxs-lookup"><span data-stu-id="78bec-121">Some aspects of message serialization and deserialization are affected.</span></span> <span data-ttu-id="78bec-122">W odróżnieniu od tego, [jakie wartości daty i godziny są serializowane, istnieją zmiany behawioralne](https://github.com/neuecc/MessagePack-CSharp/blob/master/doc/migration.md#behavioral-changes).</span><span class="sxs-lookup"><span data-stu-id="78bec-122">Specifically, there are [behavioral changes to how DateTime values are serialized](https://github.com/neuecc/MessagePack-CSharp/blob/master/doc/migration.md#behavioral-changes).</span></span>

## <a name="affected-apis"></a><span data-ttu-id="78bec-123">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="78bec-123">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions?displayProperty=nameWithType>

<!--

### Category

ASP.NET Core

### Affected APIs

`T:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions`

-->
