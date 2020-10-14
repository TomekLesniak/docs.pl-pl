---
ms.openlocfilehash: 16994e9cd97b31a30c8c5ce49d2042ff79b3f60b
ms.sourcegitcommit: 39b1d5f2978be15409c189a66ab30781d9082cd8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/14/2020
ms.locfileid: "92050529"
---
### <a name="negotiatestream-and-sslstream-allow-successive-begin-operations"></a><span data-ttu-id="b3777-101">NegotiateStream i SslStream Zezwalaj na kolejne operacje BEGIN</span><span class="sxs-lookup"><span data-stu-id="b3777-101">NegotiateStream and SslStream allow successive Begin operations</span></span>

<span data-ttu-id="b3777-102">Przypadki błędów w strumieniach zabezpieczeń są obsługiwane inaczej, a kolejne wywołania `BeginAuthenticateAsServer` lub `BeginAuthenticateAsClient` mogą przestać kończyć się niepowodzeniem.</span><span class="sxs-lookup"><span data-stu-id="b3777-102">Error cases on security streams are handled differently, and successive calls to `BeginAuthenticateAsServer` or `BeginAuthenticateAsClient` may no longer fail.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="b3777-103">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="b3777-103">Version introduced</span></span>

<span data-ttu-id="b3777-104">5,0 RC1</span><span class="sxs-lookup"><span data-stu-id="b3777-104">5.0 RC1</span></span>

#### <a name="change-description"></a><span data-ttu-id="b3777-105">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="b3777-105">Change description</span></span>

<span data-ttu-id="b3777-106">W poprzednich wersjach .NET, wywoływanie `BeginAuthenticateAsServer` lub `BeginAuthenticateAsClient` kolejno bez uprzedniego wywołania `EndAuthenticateAsServer` lub `EndAuthenticateAsClient` w wyniku <xref:System.NotSupportedException> .</span><span class="sxs-lookup"><span data-stu-id="b3777-106">In previous .NET versions, calling `BeginAuthenticateAsServer` or `BeginAuthenticateAsClient` successively without first calling `EndAuthenticateAsServer` or `EndAuthenticateAsClient` results in a <xref:System.NotSupportedException>.</span></span> <span data-ttu-id="b3777-107">Począwszy od platformy .NET 5,0, kolejne wywołania `BeginAuthenticateAsServer` lub `BeginAuthenticateAsClient` nie będą już powodować <xref:System.NotSupportedException> , ponieważ te interfejsy API są obsługiwane przez <xref:System.Threading.Tasks.Task> implementację opartą na bazie.</span><span class="sxs-lookup"><span data-stu-id="b3777-107">Starting in .NET 5.0, successive calls to `BeginAuthenticateAsServer` or `BeginAuthenticateAsClient` no longer result in a <xref:System.NotSupportedException>, because these APIs are backed by a <xref:System.Threading.Tasks.Task>-based implementation.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="b3777-108">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="b3777-108">Reason for change</span></span>

<span data-ttu-id="b3777-109">Przełączenie wewnętrznej implementacji z modelu programowania asynchronicznego (APM) na oparty na programie <xref:System.Threading.Tasks.Task> zwiększa wydajność i zmniejsza złożoność kodu.</span><span class="sxs-lookup"><span data-stu-id="b3777-109">Switching the internal implementation from asynchronous programming model (APM) to <xref:System.Threading.Tasks.Task>-based improves performance and decreases code complexity.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="b3777-110">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="b3777-110">Recommended action</span></span>

<span data-ttu-id="b3777-111">W części dewelopera nie jest wymagana żadna akcja.</span><span class="sxs-lookup"><span data-stu-id="b3777-111">No action is required on the part of the developer.</span></span>

#### <a name="category"></a><span data-ttu-id="b3777-112">Kategoria</span><span class="sxs-lookup"><span data-stu-id="b3777-112">Category</span></span>

<span data-ttu-id="b3777-113">Sieć</span><span class="sxs-lookup"><span data-stu-id="b3777-113">Networking</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="b3777-114">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="b3777-114">Affected APIs</span></span>

- <xref:System.Net.Security.SslStream.BeginAuthenticateAsServer%2A?displayProperty=fullName>
- <xref:System.Net.Security.SslStream.BeginAuthenticateAsClient%2A?displayProperty=fullName>
- <xref:System.Net.Security.NegotiateStream.BeginAuthenticateAsServer%2A?displayProperty=fullName>
- <xref:System.Net.Security.NegotiateStream.BeginAuthenticateAsClient%2A?displayProperty=fullName>

<!--

#### Affected APIs

- `Overload:M:System.Net.Security.SslStream.BeginAuthenticateAsServer`
- `Overload:M:System.Net.Security.SslStream.BeginAuthenticateAsClient`
- `Overload:M:System.Net.Security.NegotiateStream.BeginAuthenticateAsServer`
- `Overload:M:System.Net.Security.NegotiateStream.BeginAuthenticateAsClient`

-->
