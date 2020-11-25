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
# <a name="socketlocalendpoint-is-updated-after-calling-sendtoasync"></a><span data-ttu-id="011ef-103">Gniazdo. LocalEndPoint zostało zaktualizowane po wywołaniu SendToAsync</span><span class="sxs-lookup"><span data-stu-id="011ef-103">Socket.LocalEndPoint is updated after calling SendToAsync</span></span>

<span data-ttu-id="011ef-104"><xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)?displayProperty=nameWithType> teraz aktualizuje wartość <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType> właściwości do adresu lokalnego gniazda.</span><span class="sxs-lookup"><span data-stu-id="011ef-104"><xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)?displayProperty=nameWithType> now updates the value of the <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType> property to the socket's local address.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="011ef-105">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="011ef-105">Version introduced</span></span>

<span data-ttu-id="011ef-106">5,0</span><span class="sxs-lookup"><span data-stu-id="011ef-106">5.0</span></span>

## <a name="change-description"></a><span data-ttu-id="011ef-107">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="011ef-107">Change description</span></span>

<span data-ttu-id="011ef-108">W poprzednich wersjach programu .NET program nie <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)?displayProperty=nameWithType> zmienia wartości <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType> właściwości w wystąpieniu gniazda.</span><span class="sxs-lookup"><span data-stu-id="011ef-108">In previous .NET versions, <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)?displayProperty=nameWithType> does not alter the value of the <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType> property on the socket instance.</span></span> <span data-ttu-id="011ef-109">Począwszy od programu .NET 5,0, po <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)> pomyślnym zakończeniu, wartość <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType> jest adresem lokalnym niejawnie powiązanego gniazda.</span><span class="sxs-lookup"><span data-stu-id="011ef-109">Starting in .NET 5.0, when <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)> successfully completes, the value of <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType> is the implicitly bound socket's local address.</span></span> <span data-ttu-id="011ef-110">To nowe zachowanie jest spójne z zachowaniem <xref:System.Net.Sockets.Socket.SendTo(System.Byte[],System.Net.EndPoint)> i <xref:System.Net.Sockets.Socket.BeginSendTo(System.Byte[],System.Int32,System.Int32,System.Net.Sockets.SocketFlags,System.Net.EndPoint,System.AsyncCallback,System.Object)> / <xref:System.Net.Sockets.Socket.EndSendTo(System.IAsyncResult)> .</span><span class="sxs-lookup"><span data-stu-id="011ef-110">This new behavior is consistent with the behavior of <xref:System.Net.Sockets.Socket.SendTo(System.Byte[],System.Net.EndPoint)> and <xref:System.Net.Sockets.Socket.BeginSendTo(System.Byte[],System.Int32,System.Int32,System.Net.Sockets.SocketFlags,System.Net.EndPoint,System.AsyncCallback,System.Object)>/<xref:System.Net.Sockets.Socket.EndSendTo(System.IAsyncResult)>.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="011ef-111">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="011ef-111">Reason for change</span></span>

<span data-ttu-id="011ef-112">Ta zmiana [eliminuje usterkę](https://github.com/dotnet/runtime/issues/915) i sprawia, że zachowanie jest spójne dla różnych `SendTo` wariantów.</span><span class="sxs-lookup"><span data-stu-id="011ef-112">This change [fixes a bug](https://github.com/dotnet/runtime/issues/915) and makes the behavior consistent across `SendTo` variants.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="011ef-113">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="011ef-113">Recommended action</span></span>

<span data-ttu-id="011ef-114">Zmień dowolny kod, który założono, że <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)> nie zmieni wartości <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="011ef-114">Alter any code that assumes that <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)> won't alter the value of <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType>.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="011ef-115">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="011ef-115">Affected APIs</span></span>

- <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)?displayProperty=fullName>

<!--

### Affected APIs

- `M:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)`

### Category

Networking

-->
