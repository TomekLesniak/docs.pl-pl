---
ms.openlocfilehash: 8de70b0c445aa48fc4c3249ccfc8c095890fb14c
ms.sourcegitcommit: 39b1d5f2978be15409c189a66ab30781d9082cd8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/14/2020
ms.locfileid: "92050530"
---
### <a name="socketlocalendpoint-is-updated-after-calling-sendtoasync"></a><span data-ttu-id="dc0b6-101">Gniazdo. LocalEndPoint zostało zaktualizowane po wywołaniu SendToAsync</span><span class="sxs-lookup"><span data-stu-id="dc0b6-101">Socket.LocalEndPoint is updated after calling SendToAsync</span></span>

<span data-ttu-id="dc0b6-102"><xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)?displayProperty=nameWithType> teraz aktualizuje wartość <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType> właściwości do adresu lokalnego gniazda.</span><span class="sxs-lookup"><span data-stu-id="dc0b6-102"><xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)?displayProperty=nameWithType> now updates the value of the <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType> property to the socket's local address.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="dc0b6-103">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="dc0b6-103">Version introduced</span></span>

<span data-ttu-id="dc0b6-104">5,0 RC1</span><span class="sxs-lookup"><span data-stu-id="dc0b6-104">5.0 RC1</span></span>

#### <a name="change-description"></a><span data-ttu-id="dc0b6-105">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="dc0b6-105">Change description</span></span>

<span data-ttu-id="dc0b6-106">W poprzednich wersjach programu .NET program nie <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)?displayProperty=nameWithType> zmienia wartości <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType> właściwości w wystąpieniu gniazda.</span><span class="sxs-lookup"><span data-stu-id="dc0b6-106">In previous .NET versions, <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)?displayProperty=nameWithType> does not alter the value of the <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType> property on the socket instance.</span></span> <span data-ttu-id="dc0b6-107">Począwszy od programu .NET 5,0, po <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)> pomyślnym zakończeniu, wartość <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType> jest adresem lokalnym niejawnie powiązanego gniazda.</span><span class="sxs-lookup"><span data-stu-id="dc0b6-107">Starting in .NET 5.0, when <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)> successfully completes, the value of <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType> is the implicitly bound socket's local address.</span></span> <span data-ttu-id="dc0b6-108">To nowe zachowanie jest spójne z zachowaniem <xref:System.Net.Sockets.Socket.SendTo(System.Byte[],System.Net.EndPoint)> i <xref:System.Net.Sockets.Socket.BeginSendTo(System.Byte[],System.Int32,System.Int32,System.Net.Sockets.SocketFlags,System.Net.EndPoint,System.AsyncCallback,System.Object)> / <xref:System.Net.Sockets.Socket.EndSendTo(System.IAsyncResult)> .</span><span class="sxs-lookup"><span data-stu-id="dc0b6-108">This new behavior is consistent with the behavior of <xref:System.Net.Sockets.Socket.SendTo(System.Byte[],System.Net.EndPoint)> and <xref:System.Net.Sockets.Socket.BeginSendTo(System.Byte[],System.Int32,System.Int32,System.Net.Sockets.SocketFlags,System.Net.EndPoint,System.AsyncCallback,System.Object)>/<xref:System.Net.Sockets.Socket.EndSendTo(System.IAsyncResult)>.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="dc0b6-109">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="dc0b6-109">Reason for change</span></span>

<span data-ttu-id="dc0b6-110">Ta zmiana [eliminuje usterkę](https://github.com/dotnet/runtime/issues/915) i sprawia, że zachowanie jest spójne dla różnych `SendTo` wariantów.</span><span class="sxs-lookup"><span data-stu-id="dc0b6-110">This change [fixes a bug](https://github.com/dotnet/runtime/issues/915) and makes the behavior consistent across `SendTo` variants.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="dc0b6-111">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="dc0b6-111">Recommended action</span></span>

<span data-ttu-id="dc0b6-112">Zmień dowolny kod, który założono, że <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)> nie zmieni wartości <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="dc0b6-112">Alter any code that assumes that <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)> won't alter the value of <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType>.</span></span>

#### <a name="category"></a><span data-ttu-id="dc0b6-113">Kategoria</span><span class="sxs-lookup"><span data-stu-id="dc0b6-113">Category</span></span>

<span data-ttu-id="dc0b6-114">Sieć</span><span class="sxs-lookup"><span data-stu-id="dc0b6-114">Networking</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="dc0b6-115">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="dc0b6-115">Affected APIs</span></span>

- <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)`

-->
