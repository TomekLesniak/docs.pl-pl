---
ms.openlocfilehash: 88a0b7e04c7015ca3fa5abd8a6897dafcbe41c49
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/18/2020
ms.locfileid: "88557971"
---
### <a name="multicastoptiongroup-doesnt-accept-a-null-value"></a><span data-ttu-id="47254-101">MulticastOption. Group nie akceptuje wartości null</span><span class="sxs-lookup"><span data-stu-id="47254-101">MulticastOption.Group doesn't accept a null value</span></span>

<span data-ttu-id="47254-102"><xref:System.Net.Sockets.MulticastOption.Group?displayProperty=nameWithType> nie akceptuje już wartości `null` .</span><span class="sxs-lookup"><span data-stu-id="47254-102"><xref:System.Net.Sockets.MulticastOption.Group?displayProperty=nameWithType> no longer accepts a value of `null`.</span></span> <span data-ttu-id="47254-103">Jeśli właściwość zostanie ustawiona na `null` , <xref:System.ArgumentNullException> zostanie zgłoszony.</span><span class="sxs-lookup"><span data-stu-id="47254-103">If you set the property to `null`, an <xref:System.ArgumentNullException> is thrown.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="47254-104">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="47254-104">Version introduced</span></span>

<span data-ttu-id="47254-105">5.0</span><span class="sxs-lookup"><span data-stu-id="47254-105">5.0</span></span>

#### <a name="change-description"></a><span data-ttu-id="47254-106">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="47254-106">Change description</span></span>

<span data-ttu-id="47254-107">We wcześniejszych wersjach programu .NET można ustawić <xref:System.Net.Sockets.MulticastOption.Group?displayProperty=nameWithType> Właściwość na `null` .</span><span class="sxs-lookup"><span data-stu-id="47254-107">In previous versions of .NET, you can set the <xref:System.Net.Sockets.MulticastOption.Group?displayProperty=nameWithType> property to `null`.</span></span> <span data-ttu-id="47254-108">Jeśli <xref:System.Net.Sockets.MulticastOption> przeszedł później do <xref:System.Net.Sockets.Socket.SetSocketOption%2A?displayProperty=nameWithType> , środowisko uruchomieniowe wygeneruje <xref:System.NullReferenceException> .</span><span class="sxs-lookup"><span data-stu-id="47254-108">If the <xref:System.Net.Sockets.MulticastOption> is later passed to <xref:System.Net.Sockets.Socket.SetSocketOption%2A?displayProperty=nameWithType>, the runtime throws a <xref:System.NullReferenceException>.</span></span>

<span data-ttu-id="47254-109">W programie .NET 5,0 i nowszych <xref:System.ArgumentNullException> jest zgłaszany, jeśli właściwość zostanie ustawiona na `null` .</span><span class="sxs-lookup"><span data-stu-id="47254-109">In .NET 5.0 and later, an <xref:System.ArgumentNullException> is thrown if you set the property to `null`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="47254-110">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="47254-110">Reason for change</span></span>

<span data-ttu-id="47254-111">Aby zachować zgodność ze wskazówkami dotyczącymi projektowania struktury, właściwość została zaktualizowana w celu wygenerowania <xref:System.ArgumentNullException> wartości `null` .</span><span class="sxs-lookup"><span data-stu-id="47254-111">To be consistent with the Framework Design Guidelines, the property has been updated to throw an <xref:System.ArgumentNullException> if the value is `null`.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="47254-112">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="47254-112">Recommended action</span></span>

<span data-ttu-id="47254-113">Upewnij się, że nie ustawiono <xref:System.Net.Sockets.MulticastOption.Group?displayProperty=nameWithType> opcji `null` .</span><span class="sxs-lookup"><span data-stu-id="47254-113">Make sure that you don't set <xref:System.Net.Sockets.MulticastOption.Group?displayProperty=nameWithType> to `null`.</span></span>

#### <a name="category"></a><span data-ttu-id="47254-114">Kategoria</span><span class="sxs-lookup"><span data-stu-id="47254-114">Category</span></span>

<span data-ttu-id="47254-115">Networking</span><span class="sxs-lookup"><span data-stu-id="47254-115">Networking</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="47254-116">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="47254-116">Affected APIs</span></span>

- <xref:System.Net.Sockets.MulticastOption.Group?displayProperty=fullName>

<!--

#### Affected APIs

- `P:System.Net.Sockets.MulticastOption.Group`

-->
