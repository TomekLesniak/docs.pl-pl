---
ms.openlocfilehash: 0246f325a6274082b7fb0d5590cec7c80687ae85
ms.sourcegitcommit: ef86c24c418439b8bb5e3e7d64bbdbe5e11c3e9c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/21/2020
ms.locfileid: "88720206"
---
### <a name="uri-recognition-of-unc-paths-on-unix"></a><span data-ttu-id="34bb7-101">Rozpoznawanie identyfikatorów URI ścieżek UNC w systemie UNIX</span><span class="sxs-lookup"><span data-stu-id="34bb7-101">Uri recognition of UNC paths on Unix</span></span>

<span data-ttu-id="34bb7-102"><xref:System.Uri>Klasa rozpoznaje teraz ciągi, które zaczynają się od dwóch ukośników ( `//` ) jako ścieżki uniwersalnej konwencji nazewnictwa (UNC) w systemach operacyjnych UNIX.</span><span class="sxs-lookup"><span data-stu-id="34bb7-102">The <xref:System.Uri> class now recognizes strings that start with two forward slashes (`//`) as universal naming convention (UNC) paths on Unix operating systems.</span></span> <span data-ttu-id="34bb7-103">Ta zmiana powoduje, że zachowanie takich ciągów jest spójne na wszystkich platformach.</span><span class="sxs-lookup"><span data-stu-id="34bb7-103">This change makes the behavior for such strings consistent across all platforms.</span></span>

#### <a name="change-description"></a><span data-ttu-id="34bb7-104">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="34bb7-104">Change description</span></span>

<span data-ttu-id="34bb7-105">W poprzednich wersjach programu .NET <xref:System.Uri> Klasa rozpoznaje ciągi, które zaczynają się od dwóch ukośników, na przykład, `//contoso` jako bezwzględne ścieżki plików w systemach operacyjnych UNIX.</span><span class="sxs-lookup"><span data-stu-id="34bb7-105">In previous versions of .NET, the <xref:System.Uri> class recognizes strings that start with with two forward slashes, for example, `//contoso`, as absolute file paths on Unix operating systems.</span></span> <span data-ttu-id="34bb7-106">Jednak w systemie Windows takie ciągi są rozpoznawane jako ścieżki UNC.</span><span class="sxs-lookup"><span data-stu-id="34bb7-106">However, on Windows, such strings are recognized as UNC paths.</span></span>

<span data-ttu-id="34bb7-107">Począwszy od platformy .NET 5,0, <xref:System.Uri> Klasa rozpoznaje ciągi, które zaczynają się od od dwóch ukośników do przodu jako ścieżki UNC na wszystkich platformach, w tym UNIX.</span><span class="sxs-lookup"><span data-stu-id="34bb7-107">Starting in .NET 5.0,  the <xref:System.Uri> class recognizes strings that start with with two forward slashes as UNC paths on all platforms, including Unix.</span></span> <span data-ttu-id="34bb7-108">Ponadto właściwości zachowują się zgodnie z semantyką UNC:</span><span class="sxs-lookup"><span data-stu-id="34bb7-108">In addition, properties behave according to UNC semantics:</span></span>

- <span data-ttu-id="34bb7-109"><xref:System.Uri.IsUnc?displayProperty=nameWithType> Zwraca wartość `true` .</span><span class="sxs-lookup"><span data-stu-id="34bb7-109"><xref:System.Uri.IsUnc?displayProperty=nameWithType> returns `true`.</span></span>
- <span data-ttu-id="34bb7-110">Ukośniki odwrotne w ścieżce są zastępowane ukośnikami.</span><span class="sxs-lookup"><span data-stu-id="34bb7-110">Backslashes in the path are replaced with forward slashes.</span></span> <span data-ttu-id="34bb7-111">Na przykład, `//first\second` staje się `//first/second`.</span><span class="sxs-lookup"><span data-stu-id="34bb7-111">For example, `//first\second` becomes `//first/second`.</span></span>
- <span data-ttu-id="34bb7-112"><xref:System.Uri.LocalPath?displayProperty=nameWithType> nie ma znaków "%-Encode".</span><span class="sxs-lookup"><span data-stu-id="34bb7-112"><xref:System.Uri.LocalPath?displayProperty=nameWithType> doesn't percent-encode characters.</span></span> <span data-ttu-id="34bb7-113">Na przykład `//first/\uFFF0` *nie* jest konwertowany na `//first/%EF%BF%B0` .</span><span class="sxs-lookup"><span data-stu-id="34bb7-113">For example, `//first/\uFFF0` is *not* converted to `//first/%EF%BF%B0`.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="34bb7-114">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="34bb7-114">Version introduced</span></span>

<span data-ttu-id="34bb7-115">5.0</span><span class="sxs-lookup"><span data-stu-id="34bb7-115">5.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="34bb7-116">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="34bb7-116">Recommended action</span></span>

<span data-ttu-id="34bb7-117">W części dewelopera nie jest wymagana żadna akcja.</span><span class="sxs-lookup"><span data-stu-id="34bb7-117">No action is required on the part of the developer.</span></span>

#### <a name="category"></a><span data-ttu-id="34bb7-118">Kategoria</span><span class="sxs-lookup"><span data-stu-id="34bb7-118">Category</span></span>

<span data-ttu-id="34bb7-119">Podstawowe biblioteki platformy .NET</span><span class="sxs-lookup"><span data-stu-id="34bb7-119">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="34bb7-120">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="34bb7-120">Affected APIs</span></span>

- <xref:System.Uri?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.Uri`

-->
