---
title: 'Zmiana podziału: NegotiateStream i SslStream umożliwiają wykonywanie kolejnych operacji BEGIN'
description: Zapoznaj się z istotną zmianą w programie .NET 5,0, w której przypadki błędów w strumieniach zabezpieczeń są obsługiwane inaczej, a kolejne wywołania do BeginAuthenticateAsServer lub BeginAuthenticateAsClient mogą przestać kończyć się niepowodzeniem.
ms.date: 10/18/2020
ms.openlocfilehash: e0226d0f5586efca050ca3497ca1490fa21fd943
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761436"
---
# <a name="negotiatestream-and-sslstream-allow-successive-begin-operations"></a><span data-ttu-id="93204-103">NegotiateStream i SslStream Zezwalaj na kolejne operacje BEGIN</span><span class="sxs-lookup"><span data-stu-id="93204-103">NegotiateStream and SslStream allow successive Begin operations</span></span>

<span data-ttu-id="93204-104">Przypadki błędów w strumieniach zabezpieczeń są obsługiwane inaczej, a kolejne wywołania `BeginAuthenticateAsServer` lub `BeginAuthenticateAsClient` mogą przestać kończyć się niepowodzeniem.</span><span class="sxs-lookup"><span data-stu-id="93204-104">Error cases on security streams are handled differently, and successive calls to `BeginAuthenticateAsServer` or `BeginAuthenticateAsClient` may no longer fail.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="93204-105">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="93204-105">Version introduced</span></span>

<span data-ttu-id="93204-106">5,0</span><span class="sxs-lookup"><span data-stu-id="93204-106">5.0</span></span>

## <a name="change-description"></a><span data-ttu-id="93204-107">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="93204-107">Change description</span></span>

<span data-ttu-id="93204-108">W poprzednich wersjach .NET, wywoływanie `BeginAuthenticateAsServer` lub `BeginAuthenticateAsClient` kolejno bez uprzedniego wywołania `EndAuthenticateAsServer` lub `EndAuthenticateAsClient` w wyniku <xref:System.NotSupportedException> .</span><span class="sxs-lookup"><span data-stu-id="93204-108">In previous .NET versions, calling `BeginAuthenticateAsServer` or `BeginAuthenticateAsClient` successively without first calling `EndAuthenticateAsServer` or `EndAuthenticateAsClient` results in a <xref:System.NotSupportedException>.</span></span> <span data-ttu-id="93204-109">Począwszy od platformy .NET 5,0, kolejne wywołania `BeginAuthenticateAsServer` lub `BeginAuthenticateAsClient` nie będą już powodować <xref:System.NotSupportedException> , ponieważ te interfejsy API są obsługiwane przez <xref:System.Threading.Tasks.Task> implementację opartą na bazie.</span><span class="sxs-lookup"><span data-stu-id="93204-109">Starting in .NET 5.0, successive calls to `BeginAuthenticateAsServer` or `BeginAuthenticateAsClient` no longer result in a <xref:System.NotSupportedException>, because these APIs are backed by a <xref:System.Threading.Tasks.Task>-based implementation.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="93204-110">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="93204-110">Reason for change</span></span>

<span data-ttu-id="93204-111">Przełączenie wewnętrznej implementacji z modelu programowania asynchronicznego (APM) na oparty na programie <xref:System.Threading.Tasks.Task> zwiększa wydajność i zmniejsza złożoność kodu.</span><span class="sxs-lookup"><span data-stu-id="93204-111">Switching the internal implementation from asynchronous programming model (APM) to <xref:System.Threading.Tasks.Task>-based improves performance and decreases code complexity.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="93204-112">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="93204-112">Recommended action</span></span>

<span data-ttu-id="93204-113">W części dewelopera nie jest wymagana żadna akcja.</span><span class="sxs-lookup"><span data-stu-id="93204-113">No action is required on the part of the developer.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="93204-114">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="93204-114">Affected APIs</span></span>

- <xref:System.Net.Security.SslStream.BeginAuthenticateAsServer%2A?displayProperty=fullName>
- <xref:System.Net.Security.SslStream.BeginAuthenticateAsClient%2A?displayProperty=fullName>
- <xref:System.Net.Security.NegotiateStream.BeginAuthenticateAsServer%2A?displayProperty=fullName>
- <xref:System.Net.Security.NegotiateStream.BeginAuthenticateAsClient%2A?displayProperty=fullName>

<!--

### Affected APIs

- `Overload:M:System.Net.Security.SslStream.BeginAuthenticateAsServer`
- `Overload:M:System.Net.Security.SslStream.BeginAuthenticateAsClient`
- `Overload:M:System.Net.Security.NegotiateStream.BeginAuthenticateAsServer`
- `Overload:M:System.Net.Security.NegotiateStream.BeginAuthenticateAsClient`

### Category

Networking

-->
