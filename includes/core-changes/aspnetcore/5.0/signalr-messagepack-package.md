---
ms.openlocfilehash: ca0792a3fd05d28cecceac1d644e3e4bf64722bc
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/27/2020
ms.locfileid: "80345214"
---
### <a name="signalr-messagepack-hub-protocol-moved-to-messagepack-2x-package"></a><span data-ttu-id="eeb54-101">Sygnalizacja: przeniesiono protokół MessagePack Hub do pakietu MessagePack 2. x</span><span class="sxs-lookup"><span data-stu-id="eeb54-101">SignalR: MessagePack Hub Protocol moved to MessagePack 2.x package</span></span>

<span data-ttu-id="eeb54-102">Protokół ASP.NET Core sygnalizującego [MessagePack](/aspnet/core/signalr/messagepackhubprotocol) używa [pakietu NuGet MessagePack](https://www.nuget.org/packages/MessagePack) do serializacji MessagePack.</span><span class="sxs-lookup"><span data-stu-id="eeb54-102">The ASP.NET Core SignalR [MessagePack Hub Protocol](/aspnet/core/signalr/messagepackhubprotocol) uses the [MessagePack NuGet package](https://www.nuget.org/packages/MessagePack) for MessagePack serialization.</span></span> <span data-ttu-id="eeb54-103">ASP.NET Core 5,0 uaktualnia pakiet z 1. x do najnowszej wersji pakietu 2. x.</span><span class="sxs-lookup"><span data-stu-id="eeb54-103">ASP.NET Core 5.0 upgrades the package from 1.x to the latest 2.x package version.</span></span>

<span data-ttu-id="eeb54-104">Aby zapoznać się z omówieniem tego problemu, zobacz [dotnet/aspnetcore # 18692](https://github.com/dotnet/aspnetcore/issues/18692).</span><span class="sxs-lookup"><span data-stu-id="eeb54-104">For discussion on this issue, see [dotnet/aspnetcore#18692](https://github.com/dotnet/aspnetcore/issues/18692).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="eeb54-105">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="eeb54-105">Version introduced</span></span>

<span data-ttu-id="eeb54-106">5,0 wersja zapoznawcza 1</span><span class="sxs-lookup"><span data-stu-id="eeb54-106">5.0 Preview 1</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="eeb54-107">Stare zachowanie</span><span class="sxs-lookup"><span data-stu-id="eeb54-107">Old behavior</span></span>

<span data-ttu-id="eeb54-108">ASP.NET Core sygnalizujący użył pakietu MessagePack 1. x do serializacji i deserializacji komunikatów MessagePack.</span><span class="sxs-lookup"><span data-stu-id="eeb54-108">ASP.NET Core SignalR used the MessagePack 1.x package to serialize and deserialize MessagePack messages.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="eeb54-109">Nowe zachowanie</span><span class="sxs-lookup"><span data-stu-id="eeb54-109">New behavior</span></span>

<span data-ttu-id="eeb54-110">ASP.NET Core sygnalizujący używa pakietu MessagePack 2. x do serializacji i deserializacji komunikatów MessagePack.</span><span class="sxs-lookup"><span data-stu-id="eeb54-110">ASP.NET Core SignalR uses the MessagePack 2.x package to serialize and deserialize MessagePack messages.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="eeb54-111">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="eeb54-111">Reason for change</span></span>

<span data-ttu-id="eeb54-112">Najnowsze ulepszenia pakietu MessagePack 2. x umożliwiają dodawanie przydatnych funkcji.</span><span class="sxs-lookup"><span data-stu-id="eeb54-112">The latest improvements in the MessagePack 2.x package add useful functionality.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="eeb54-113">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="eeb54-113">Recommended action</span></span>

<span data-ttu-id="eeb54-114">Ta zmiana jest stosowana, gdy:</span><span class="sxs-lookup"><span data-stu-id="eeb54-114">This breaking change applies when:</span></span>

* <span data-ttu-id="eeb54-115">Ustawianie lub Konfigurowanie wartości w <xref:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions> .</span><span class="sxs-lookup"><span data-stu-id="eeb54-115">Setting or configuring values on <xref:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions>.</span></span>
* <span data-ttu-id="eeb54-116">Używanie interfejsów API MessagePack bezpośrednio i używanie protokołu ASP.NET Core sygnalizującego MessagePack w tym samym projekcie.</span><span class="sxs-lookup"><span data-stu-id="eeb54-116">Using the MessagePack APIs directly and using the ASP.NET Core SignalR MessagePack Hub Protocol in the same project.</span></span> <span data-ttu-id="eeb54-117">Nowsza wersja zostanie załadowana zamiast poprzedniej wersji.</span><span class="sxs-lookup"><span data-stu-id="eeb54-117">The newer version will be loaded instead of the previous version.</span></span>

<span data-ttu-id="eeb54-118">Aby uzyskać wskazówki dotyczące migracji z autorów pakietów, zobacz [Migrowanie z MessagePack v1. x do MessagePack v2. x](https://github.com/neuecc/MessagePack-CSharp/blob/master/doc/migration.md).</span><span class="sxs-lookup"><span data-stu-id="eeb54-118">For migration guidance from the package authors, see [Migrating from MessagePack v1.x to MessagePack v2.x](https://github.com/neuecc/MessagePack-CSharp/blob/master/doc/migration.md).</span></span> <span data-ttu-id="eeb54-119">Dotyczy to niektórych aspektów serializacji i deserializacji komunikatów.</span><span class="sxs-lookup"><span data-stu-id="eeb54-119">Some aspects of message serialization and deserialization are affected.</span></span> <span data-ttu-id="eeb54-120">W odróżnieniu od tego, [jakie wartości daty i godziny są serializowane, istnieją zmiany behawioralne](https://github.com/neuecc/MessagePack-CSharp/blob/master/doc/migration.md#behavioral-changes).</span><span class="sxs-lookup"><span data-stu-id="eeb54-120">Specifically, there are [behavioral changes to how DateTime values are serialized](https://github.com/neuecc/MessagePack-CSharp/blob/master/doc/migration.md#behavioral-changes).</span></span>

#### <a name="category"></a><span data-ttu-id="eeb54-121">Kategoria</span><span class="sxs-lookup"><span data-stu-id="eeb54-121">Category</span></span>

<span data-ttu-id="eeb54-122">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="eeb54-122">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="eeb54-123">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="eeb54-123">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions?displayProperty=nameWithType>

<!--

#### Affected APIs

`T:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions`

-->
