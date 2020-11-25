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
# <a name="signalr-messagepack-hub-protocol-moved-to-messagepack-2x-package"></a>Sygnalizacja: przeniesiono protokół MessagePack Hub do pakietu MessagePack 2. x

Protokół ASP.NET Core sygnalizującego [MessagePack](/aspnet/core/signalr/messagepackhubprotocol) używa [pakietu NuGet MessagePack](https://www.nuget.org/packages/MessagePack) do serializacji MessagePack. ASP.NET Core 5,0 uaktualnia pakiet z 1. x do najnowszej wersji pakietu 2. x.

Aby zapoznać się z omówieniem tego problemu, zobacz [dotnet/aspnetcore # 18692](https://github.com/dotnet/aspnetcore/issues/18692).

## <a name="version-introduced"></a>Wprowadzona wersja

5,0 wersja zapoznawcza 1

## <a name="old-behavior"></a>Stare zachowanie

ASP.NET Core sygnalizujący użył pakietu MessagePack 1. x do serializacji i deserializacji komunikatów MessagePack.

## <a name="new-behavior"></a>Nowe zachowanie

ASP.NET Core sygnalizujący używa pakietu MessagePack 2. x do serializacji i deserializacji komunikatów MessagePack.

## <a name="reason-for-change"></a>Przyczyna zmiany

Najnowsze ulepszenia pakietu MessagePack 2. x umożliwiają dodawanie przydatnych funkcji.

## <a name="recommended-action"></a>Zalecana akcja

Ta zmiana jest stosowana, gdy:

* Ustawianie lub Konfigurowanie wartości w <xref:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions> .
* Używanie interfejsów API MessagePack bezpośrednio i używanie protokołu ASP.NET Core sygnalizującego MessagePack w tym samym projekcie. Nowsza wersja zostanie załadowana zamiast poprzedniej wersji.

Aby uzyskać wskazówki dotyczące migracji z autorów pakietów, zobacz [Migrowanie z MessagePack v1. x do MessagePack v2. x](https://github.com/neuecc/MessagePack-CSharp/blob/master/doc/migration.md). Dotyczy to niektórych aspektów serializacji i deserializacji komunikatów. W odróżnieniu od tego, [jakie wartości daty i godziny są serializowane, istnieją zmiany behawioralne](https://github.com/neuecc/MessagePack-CSharp/blob/master/doc/migration.md#behavioral-changes).

## <a name="affected-apis"></a>Dotyczy interfejsów API

<xref:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions?displayProperty=nameWithType>

<!--

### Category

ASP.NET Core

### Affected APIs

`T:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions`

-->
