---
title: 'Nieprzerwana zmiana: sygnalizująca: MessagePack typ opcji protokołu centrum danych zmieniony'
description: 'Dowiedz się więcej o istotnej zmianie w ASP.NET Core 5,0 z tytułem: opcje protokołu centrum MessagePack Zmieniono typ'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: b75dbec834699472f18b3058052274476bd9751d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761688"
---
# <a name="signalr-messagepack-hub-protocol-options-type-changed"></a><span data-ttu-id="9ebd8-103">Sygnalizacja: Zmieniono typ opcji protokołu MessagePack Hub</span><span class="sxs-lookup"><span data-stu-id="9ebd8-103">SignalR: MessagePack Hub Protocol options type changed</span></span>

<span data-ttu-id="9ebd8-104">Typ opcji protokołu MessagePack sygnalizującego "ASP.NET Core" został zmieniony z `IList<MessagePack.IFormatterResolver>` na typ biblioteki [MessagePack](https://www.nuget.org/packages/MessagePack) `MessagePackSerializerOptions` .</span><span class="sxs-lookup"><span data-stu-id="9ebd8-104">The ASP.NET Core SignalR MessagePack Hub Protocol options type has changed from `IList<MessagePack.IFormatterResolver>` to the [MessagePack](https://www.nuget.org/packages/MessagePack) library's `MessagePackSerializerOptions` type.</span></span>

<span data-ttu-id="9ebd8-105">Aby uzyskać więcej dyskusji na temat tej zmiany, zobacz [dotnet/aspnetcore # 20506](https://github.com/dotnet/aspnetcore/issues/20506).</span><span class="sxs-lookup"><span data-stu-id="9ebd8-105">For discussion on this change, see [dotnet/aspnetcore#20506](https://github.com/dotnet/aspnetcore/issues/20506).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="9ebd8-106">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="9ebd8-106">Version introduced</span></span>

<span data-ttu-id="9ebd8-107">5,0 wersja zapoznawcza 4</span><span class="sxs-lookup"><span data-stu-id="9ebd8-107">5.0 Preview 4</span></span>

## <a name="old-behavior"></a><span data-ttu-id="9ebd8-108">Stare zachowanie</span><span class="sxs-lookup"><span data-stu-id="9ebd8-108">Old behavior</span></span>

<span data-ttu-id="9ebd8-109">Możesz dodać do opcji, jak pokazano w następującym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="9ebd8-109">You can add to the options as shown in the following example:</span></span>

```csharp
services.AddSignalR()
    .AddMessagePackProtocol(options =>
    {
        options.FormatterResolvers.Add(MessagePack.Resolvers.StandardResolver.Instance);
    });
```

<span data-ttu-id="9ebd8-110">I Zastąp opcje w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="9ebd8-110">And replace the options as follows:</span></span>

```csharp
services.AddSignalR()
    .AddMessagePackProtocol(options =>
    {
        options.FormatterResolvers = new List<MessagePack.IFormatterResolver>()
        {
            MessagePack.Resolvers.StandardResolver.Instance
        };
    });
```

## <a name="new-behavior"></a><span data-ttu-id="9ebd8-111">Nowe zachowanie</span><span class="sxs-lookup"><span data-stu-id="9ebd8-111">New behavior</span></span>

<span data-ttu-id="9ebd8-112">Możesz dodać do opcji, jak pokazano w następującym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="9ebd8-112">You can add to the options as shown in the following example:</span></span>

```csharp
services.AddSignalR()
    .AddMessagePackProtocol(options =>
    {
        options.SerializerOptions =
            options.SerializeOptions.WithResolver(MessagePack.Resolvers.StandardResolver.Instance);
    });
```

<span data-ttu-id="9ebd8-113">I Zastąp opcje w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="9ebd8-113">And replace the options as follows:</span></span>

```csharp
services.AddSignalR()
    .AddMessagePackProtocol(options =>
    {
        options.SerializerOptions = MessagePackSerializerOptions
                .Standard
                .WithResolver(MessagePack.Resolvers.StandardResolver.Instance)
                .WithSecurity(MessagePackSecurity.UntrustedData);
    });
```

## <a name="reason-for-change"></a><span data-ttu-id="9ebd8-114">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="9ebd8-114">Reason for change</span></span>

<span data-ttu-id="9ebd8-115">Ta zmiana jest częścią przejścia do MessagePack v2. x, która została ogłoszona w polu [ASPNET/anonse # 404](https://github.com/aspnet/Announcements/issues/404).</span><span class="sxs-lookup"><span data-stu-id="9ebd8-115">This change is part of moving to MessagePack v2.x, which was announced in [aspnet/Announcements#404](https://github.com/aspnet/Announcements/issues/404).</span></span> <span data-ttu-id="9ebd8-116">Biblioteka v2. x dodała interfejs API opcji, który jest łatwiejszy do użycia i udostępnia więcej funkcji niż lista `MessagePack.IFormatterResolver` , która była uwidoczniona wcześniej.</span><span class="sxs-lookup"><span data-stu-id="9ebd8-116">The v2.x library has added an options API that's easier to use and provides more features than the list of `MessagePack.IFormatterResolver` that was exposed before.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="9ebd8-117">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="9ebd8-117">Recommended action</span></span>

<span data-ttu-id="9ebd8-118">Ta zmiana wpływa na wszystkich użytkowników, którzy konfigurują wartości <xref:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions> .</span><span class="sxs-lookup"><span data-stu-id="9ebd8-118">This breaking change affects anyone who is configuring values on <xref:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions>.</span></span> <span data-ttu-id="9ebd8-119">Jeśli używasz protokołu ASP.NET Core sygnalizującego MessagePack i modyfikowania opcji, zaktualizuj użycie, aby użyć nowego interfejsu API opcji, jak pokazano powyżej.</span><span class="sxs-lookup"><span data-stu-id="9ebd8-119">If you're using the ASP.NET Core SignalR MessagePack Hub Protocol and modifying the options, update your usage to use the new options API as shown above.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="9ebd8-120">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="9ebd8-120">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions?displayProperty=nameWithType>

<!--

### Category

ASP.NET Core

### Affected APIs

`T:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions`

-->
