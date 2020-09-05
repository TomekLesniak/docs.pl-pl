---
ms.openlocfilehash: 3c32d2e13447f8fd9aa6b185b5fc7e60f9e1bb61
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496267"
---
### <a name="support-special-relative-uri-notation-when-unicode-is-present"></a><span data-ttu-id="f5ef8-101">Obsługa specjalnej notacji względnych identyfikatorów URI, gdy występuje Unicode</span><span class="sxs-lookup"><span data-stu-id="f5ef8-101">Support special relative URI notation when Unicode is present</span></span>

#### <a name="details"></a><span data-ttu-id="f5ef8-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="f5ef8-102">Details</span></span>

<span data-ttu-id="f5ef8-103"><xref:System.Uri> nie będzie już zgłaszać <xref:System.NullReferenceException> w przypadku wywołania <xref:System.Uri.TryCreate%2A> określonych względnych identyfikatorów URI zawierających Unicode.</span><span class="sxs-lookup"><span data-stu-id="f5ef8-103"><xref:System.Uri> will no longer throw a <xref:System.NullReferenceException> when calling <xref:System.Uri.TryCreate%2A> on certain relative URIs containing Unicode.</span></span> <span data-ttu-id="f5ef8-104">Najprostsza reprodukcja <xref:System.NullReferenceException> znajduje się poniżej, przy czym dwie instrukcje są równoważne:</span><span class="sxs-lookup"><span data-stu-id="f5ef8-104">The simplest reproduction of the <xref:System.NullReferenceException> is below, with the two statements being equivalent:</span></span><pre><code class="lang-csharp">bool success = Uri.TryCreate(&quot;http:%C3%A8&quot;, UriKind.RelativeOrAbsolute, out Uri href);&#13;&#10;bool success = Uri.TryCreate(&quot;http:&#232;&quot;, UriKind.RelativeOrAbsolute, out Uri href);&#13;&#10;</code></pre><span data-ttu-id="f5ef8-105">Aby odtworzyć <xref:System.NullReferenceException> , należy wykonać następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="f5ef8-105">To reproduce the <xref:System.NullReferenceException>, the following items must be true:</span></span><ul><li><span data-ttu-id="f5ef8-106">Identyfikator URI musi być określony jako względny przez zaczekanie z "http:" i nie jest następujący z "//".</span><span class="sxs-lookup"><span data-stu-id="f5ef8-106">The URI must be specified as relative by prepending it with ‘http:’ and not following it with ‘//’.</span></span></li><li><span data-ttu-id="f5ef8-107">Identyfikator URI musi zawierać zakodowane w procentach symbole Unicode lub unzastrzeżone.</span><span class="sxs-lookup"><span data-stu-id="f5ef8-107">The URI must contain percent-encoded Unicode or unreserved symbols.</span></span></li></ul>

#### <a name="suggestion"></a><span data-ttu-id="f5ef8-108">Sugestia</span><span class="sxs-lookup"><span data-stu-id="f5ef8-108">Suggestion</span></span>

<span data-ttu-id="f5ef8-109">Użytkownicy w zależności od tego zachowania, aby nie zezwalać na względne identyfikatory URI, należy zamiast tego określić <xref:System.UriKind.Absolute?displayProperty=nameWithType> podczas tworzenia identyfikatora URI.</span><span class="sxs-lookup"><span data-stu-id="f5ef8-109">Users depending on this behavior to disallow relative URIs should instead specify <xref:System.UriKind.Absolute?displayProperty=nameWithType> when creating a URI.</span></span>

| <span data-ttu-id="f5ef8-110">Nazwa</span><span class="sxs-lookup"><span data-stu-id="f5ef8-110">Name</span></span>    | <span data-ttu-id="f5ef8-111">Wartość</span><span class="sxs-lookup"><span data-stu-id="f5ef8-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="f5ef8-112">Zakres</span><span class="sxs-lookup"><span data-stu-id="f5ef8-112">Scope</span></span>   |<span data-ttu-id="f5ef8-113">Edge</span><span class="sxs-lookup"><span data-stu-id="f5ef8-113">Edge</span></span>|
|<span data-ttu-id="f5ef8-114">Wersja</span><span class="sxs-lookup"><span data-stu-id="f5ef8-114">Version</span></span>|<span data-ttu-id="f5ef8-115">4.7.2</span><span class="sxs-lookup"><span data-stu-id="f5ef8-115">4.7.2</span></span>|
|<span data-ttu-id="f5ef8-116">Typ</span><span class="sxs-lookup"><span data-stu-id="f5ef8-116">Type</span></span>|<span data-ttu-id="f5ef8-117">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="f5ef8-117">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="f5ef8-118">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="f5ef8-118">Affected APIs</span></span>

- <xref:System.Uri.TryCreate(System.Uri,System.Uri,System.Uri@)?displayProperty=nameWithType>
- <xref:System.Uri.TryCreate(System.String,System.UriKind,System.Uri@)?displayProperty=nameWithType>
- <xref:System.Uri.TryCreate(System.Uri,System.String,System.Uri@)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Uri.TryCreate(System.Uri,System.Uri,System.Uri@)`
- `M:System.Uri.TryCreate(System.String,System.UriKind,System.Uri@)`
- `M:System.Uri.TryCreate(System.Uri,System.String,System.Uri@)`

-->
