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
# <a name="signalr-messagepack-hub-protocol-options-type-changed"></a>Sygnalizacja: Zmieniono typ opcji protokołu MessagePack Hub

Typ opcji protokołu MessagePack sygnalizującego "ASP.NET Core" został zmieniony z `IList<MessagePack.IFormatterResolver>` na typ biblioteki [MessagePack](https://www.nuget.org/packages/MessagePack) `MessagePackSerializerOptions` .

Aby uzyskać więcej dyskusji na temat tej zmiany, zobacz [dotnet/aspnetcore # 20506](https://github.com/dotnet/aspnetcore/issues/20506).

## <a name="version-introduced"></a>Wprowadzona wersja

5,0 wersja zapoznawcza 4

## <a name="old-behavior"></a>Stare zachowanie

Możesz dodać do opcji, jak pokazano w następującym przykładzie:

```csharp
services.AddSignalR()
    .AddMessagePackProtocol(options =>
    {
        options.FormatterResolvers.Add(MessagePack.Resolvers.StandardResolver.Instance);
    });
```

I Zastąp opcje w następujący sposób:

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

## <a name="new-behavior"></a>Nowe zachowanie

Możesz dodać do opcji, jak pokazano w następującym przykładzie:

```csharp
services.AddSignalR()
    .AddMessagePackProtocol(options =>
    {
        options.SerializerOptions =
            options.SerializeOptions.WithResolver(MessagePack.Resolvers.StandardResolver.Instance);
    });
```

I Zastąp opcje w następujący sposób:

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

## <a name="reason-for-change"></a>Przyczyna zmiany

Ta zmiana jest częścią przejścia do MessagePack v2. x, która została ogłoszona w polu [ASPNET/anonse # 404](https://github.com/aspnet/Announcements/issues/404). Biblioteka v2. x dodała interfejs API opcji, który jest łatwiejszy do użycia i udostępnia więcej funkcji niż lista `MessagePack.IFormatterResolver` , która była uwidoczniona wcześniej.

## <a name="recommended-action"></a>Zalecana akcja

Ta zmiana wpływa na wszystkich użytkowników, którzy konfigurują wartości <xref:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions> . Jeśli używasz protokołu ASP.NET Core sygnalizującego MessagePack i modyfikowania opcji, zaktualizuj użycie, aby użyć nowego interfejsu API opcji, jak pokazano powyżej.

## <a name="affected-apis"></a>Dotyczy interfejsów API

<xref:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions?displayProperty=nameWithType>

<!--

### Category

ASP.NET Core

### Affected APIs

`T:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions`

-->
