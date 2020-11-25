---
title: 'Istotna zmiana: Socket. LocalEndPoint został zaktualizowany po wywołaniu SendToAsync'
description: Dowiedz się więcej o istotnej zmianie w programie .NET 5,0, gdzie SendToAsync teraz aktualizuje wartość właściwości Local Endpoint do adresu lokalnego gniazda.
ms.date: 10/18/2020
ms.openlocfilehash: 53d7da350eac6e65832012331044427fd90fe796
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761443"
---
# <a name="socketlocalendpoint-is-updated-after-calling-sendtoasync"></a>Gniazdo. LocalEndPoint zostało zaktualizowane po wywołaniu SendToAsync

<xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)?displayProperty=nameWithType> teraz aktualizuje wartość <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType> właściwości do adresu lokalnego gniazda.

## <a name="version-introduced"></a>Wprowadzona wersja

5,0

## <a name="change-description"></a>Zmień opis

W poprzednich wersjach programu .NET program nie <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)?displayProperty=nameWithType> zmienia wartości <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType> właściwości w wystąpieniu gniazda. Począwszy od programu .NET 5,0, po <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)> pomyślnym zakończeniu, wartość <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType> jest adresem lokalnym niejawnie powiązanego gniazda. To nowe zachowanie jest spójne z zachowaniem <xref:System.Net.Sockets.Socket.SendTo(System.Byte[],System.Net.EndPoint)> i <xref:System.Net.Sockets.Socket.BeginSendTo(System.Byte[],System.Int32,System.Int32,System.Net.Sockets.SocketFlags,System.Net.EndPoint,System.AsyncCallback,System.Object)> / <xref:System.Net.Sockets.Socket.EndSendTo(System.IAsyncResult)> .

## <a name="reason-for-change"></a>Przyczyna zmiany

Ta zmiana [eliminuje usterkę](https://github.com/dotnet/runtime/issues/915) i sprawia, że zachowanie jest spójne dla różnych `SendTo` wariantów.

## <a name="recommended-action"></a>Zalecana akcja

Zmień dowolny kod, który założono, że <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)> nie zmieni wartości <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType> .

## <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)?displayProperty=fullName>

<!--

### Affected APIs

- `M:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)`

### Category

Networking

-->
