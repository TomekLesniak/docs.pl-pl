---
ms.openlocfilehash: eb5c032a020799fa19cc0a8cfaabb56e01417ff4
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496952"
---
### <a name="contentdisposition-datetimes-returns-slightly-different-string"></a><span data-ttu-id="89ab8-101">ContentDisposition DateTimes zwraca nieco inny ciąg</span><span class="sxs-lookup"><span data-stu-id="89ab8-101">ContentDisposition DateTimes returns slightly different string</span></span>

#### <a name="details"></a><span data-ttu-id="89ab8-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="89ab8-102">Details</span></span>

<span data-ttu-id="89ab8-103">Reprezentacje ciągów dla <xref:System.Net.Mime.ContentDisposition?displayProperty=fullName> zostały zaktualizowane, począwszy od 4,6, do zawsze reprezentujące składnik godziny z <xref:System.DateTime?displayProperty=fullName> dwoma cyframi.</span><span class="sxs-lookup"><span data-stu-id="89ab8-103">String representations of <xref:System.Net.Mime.ContentDisposition?displayProperty=fullName>'s have been updated, beginning in 4.6, to always represent the hour component of a <xref:System.DateTime?displayProperty=fullName> with two digits.</span></span> <span data-ttu-id="89ab8-104">Jest to zgodne z [RFC822](https://www.ietf.org/rfc/rfc0822.txt) i [RFC2822](https://www.ietf.org/rfc/rfc2822.txt).</span><span class="sxs-lookup"><span data-stu-id="89ab8-104">This is to comply with [RFC822](https://www.ietf.org/rfc/rfc0822.txt) and [RFC2822](https://www.ietf.org/rfc/rfc2822.txt).</span></span> <span data-ttu-id="89ab8-105">Powoduje to <xref:System.Net.Mime.ContentDisposition.ToString> zwrócenie nieco innego ciągu w 4,6 w scenariuszach, w których jeden z elementów czasu dyspozycji był wcześniejszy niż 10:00 am.</span><span class="sxs-lookup"><span data-stu-id="89ab8-105">This causes <xref:System.Net.Mime.ContentDisposition.ToString> to return a slightly different string in 4.6 in scenarios where one of the disposition's time elements was before 10:00 AM.</span></span> <span data-ttu-id="89ab8-106">Należy zauważyć, że ContentDispositions są czasami serializowane przez konwersję do ciągów, więc <xref:System.Net.Mime.ContentDisposition.ToString> należy przejrzeć wszystkie wywołania operacji, serializacji lub GetHashCode.</span><span class="sxs-lookup"><span data-stu-id="89ab8-106">Note that ContentDispositions are sometimes serialized via converting them to strings, so any <xref:System.Net.Mime.ContentDisposition.ToString> operations, serialization, or GetHashCode calls should be reviewed.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="89ab8-107">Sugestia</span><span class="sxs-lookup"><span data-stu-id="89ab8-107">Suggestion</span></span>

<span data-ttu-id="89ab8-108">Nie należy oczekiwać, że reprezentacje ciągów ContentDispositions z różnych wersji .NET Framework będą prawidłowo porównywane ze sobą.</span><span class="sxs-lookup"><span data-stu-id="89ab8-108">Do not expect that string representations of ContentDispositions from different .NET Framework versions will correctly compare to one another.</span></span> <span data-ttu-id="89ab8-109">Przed przeprowadzeniem porównania przekonwertuj ciągi z powrotem do ContentDispositions, jeśli jest to możliwe.</span><span class="sxs-lookup"><span data-stu-id="89ab8-109">Convert the strings back to ContentDispositions, if possible, before conducting a comparison.</span></span>

| <span data-ttu-id="89ab8-110">Nazwa</span><span class="sxs-lookup"><span data-stu-id="89ab8-110">Name</span></span>    | <span data-ttu-id="89ab8-111">Wartość</span><span class="sxs-lookup"><span data-stu-id="89ab8-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="89ab8-112">Zakres</span><span class="sxs-lookup"><span data-stu-id="89ab8-112">Scope</span></span>   |<span data-ttu-id="89ab8-113">Mały</span><span class="sxs-lookup"><span data-stu-id="89ab8-113">Minor</span></span>|
|<span data-ttu-id="89ab8-114">Wersja</span><span class="sxs-lookup"><span data-stu-id="89ab8-114">Version</span></span>|<span data-ttu-id="89ab8-115">4,6</span><span class="sxs-lookup"><span data-stu-id="89ab8-115">4.6</span></span>|
|<span data-ttu-id="89ab8-116">Typ</span><span class="sxs-lookup"><span data-stu-id="89ab8-116">Type</span></span>|<span data-ttu-id="89ab8-117">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="89ab8-117">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="89ab8-118">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="89ab8-118">Affected APIs</span></span>

- <xref:System.Net.Mime.ContentDisposition.ToString?displayProperty=nameWithType>
- <xref:System.Net.Mime.ContentDisposition.GetHashCode?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Net.Mime.ContentDisposition.ToString`
- `M:System.Net.Mime.ContentDisposition.GetHashCode`

-->
