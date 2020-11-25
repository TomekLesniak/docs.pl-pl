---
title: 'Zmiana istotna: Rozpoznawanie identyfikatorów URI ścieżek UNC w systemie UNIX'
description: Dowiedz się więcej na temat istotnej zmiany w programie .NET 5,0 w bibliotekach podstawowych platformy .NET, w których Klasa URI rozpoznaje teraz ciągi, które zaczynają się od dwóch ukośników jako ścieżki UNC w systemie UNIX.
ms.date: 11/01/2020
ms.openlocfilehash: 0d5d9cd8dd869f24e94d15724e5e16eaddf6ed47
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761387"
---
# <a name="uri-recognition-of-unc-paths-on-unix"></a><span data-ttu-id="b2432-103">Rozpoznawanie identyfikatorów URI ścieżek UNC w systemie UNIX</span><span class="sxs-lookup"><span data-stu-id="b2432-103">Uri recognition of UNC paths on Unix</span></span>

<span data-ttu-id="b2432-104"><xref:System.Uri>Klasa rozpoznaje teraz ciągi, które zaczynają się od dwóch ukośników ( `//` ) jako ścieżki uniwersalnej konwencji nazewnictwa (UNC) w systemach operacyjnych UNIX.</span><span class="sxs-lookup"><span data-stu-id="b2432-104">The <xref:System.Uri> class now recognizes strings that start with two forward slashes (`//`) as universal naming convention (UNC) paths on Unix operating systems.</span></span> <span data-ttu-id="b2432-105">Ta zmiana powoduje, że zachowanie takich ciągów jest spójne na wszystkich platformach.</span><span class="sxs-lookup"><span data-stu-id="b2432-105">This change makes the behavior for such strings consistent across all platforms.</span></span>

## <a name="change-description"></a><span data-ttu-id="b2432-106">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="b2432-106">Change description</span></span>

<span data-ttu-id="b2432-107">W poprzednich wersjach programu .NET <xref:System.Uri> Klasa rozpoznaje ciągi, które zaczynają się od dwóch ukośników do przodu, na przykład `//contoso` jako bezwzględne ścieżki plików w systemach operacyjnych UNIX.</span><span class="sxs-lookup"><span data-stu-id="b2432-107">In previous versions of .NET, the <xref:System.Uri> class recognizes strings that start with two forward slashes, for example, `//contoso`, as absolute file paths on Unix operating systems.</span></span> <span data-ttu-id="b2432-108">Jednak w systemie Windows takie ciągi są rozpoznawane jako ścieżki UNC.</span><span class="sxs-lookup"><span data-stu-id="b2432-108">However, on Windows, such strings are recognized as UNC paths.</span></span>

<span data-ttu-id="b2432-109">Począwszy od platformy .NET 5,0, <xref:System.Uri> Klasa rozpoznaje ciągi zaczynające się od dwóch ukośników do przodu jako ścieżki UNC na wszystkich platformach, w tym w systemie UNIX.</span><span class="sxs-lookup"><span data-stu-id="b2432-109">Starting in .NET 5.0,  the <xref:System.Uri> class recognizes strings that start with two forward slashes as UNC paths on all platforms, including Unix.</span></span> <span data-ttu-id="b2432-110">Ponadto właściwości zachowują się zgodnie z semantyką UNC:</span><span class="sxs-lookup"><span data-stu-id="b2432-110">In addition, properties behave according to UNC semantics:</span></span>

- <span data-ttu-id="b2432-111"><xref:System.Uri.IsUnc?displayProperty=nameWithType> Zwraca wartość `true` .</span><span class="sxs-lookup"><span data-stu-id="b2432-111"><xref:System.Uri.IsUnc?displayProperty=nameWithType> returns `true`.</span></span>
- <span data-ttu-id="b2432-112">Ukośniki odwrotne w ścieżce są zastępowane ukośnikami.</span><span class="sxs-lookup"><span data-stu-id="b2432-112">Backslashes in the path are replaced with forward slashes.</span></span> <span data-ttu-id="b2432-113">Na przykład, `//first\second` staje się `//first/second`.</span><span class="sxs-lookup"><span data-stu-id="b2432-113">For example, `//first\second` becomes `//first/second`.</span></span>
- <span data-ttu-id="b2432-114"><xref:System.Uri.LocalPath?displayProperty=nameWithType> nie ma znaków "%-Encode".</span><span class="sxs-lookup"><span data-stu-id="b2432-114"><xref:System.Uri.LocalPath?displayProperty=nameWithType> doesn't percent-encode characters.</span></span> <span data-ttu-id="b2432-115">Na przykład `//first/\uFFF0` *nie* jest konwertowany na `//first/%EF%BF%B0` .</span><span class="sxs-lookup"><span data-stu-id="b2432-115">For example, `//first/\uFFF0` is *not* converted to `//first/%EF%BF%B0`.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="b2432-116">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="b2432-116">Version introduced</span></span>

<span data-ttu-id="b2432-117">5,0</span><span class="sxs-lookup"><span data-stu-id="b2432-117">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="b2432-118">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="b2432-118">Recommended action</span></span>

<span data-ttu-id="b2432-119">W części dewelopera nie jest wymagana żadna akcja.</span><span class="sxs-lookup"><span data-stu-id="b2432-119">No action is required on the part of the developer.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="b2432-120">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="b2432-120">Affected APIs</span></span>

- <xref:System.Uri?displayProperty=fullName>

<!--

#### Category

Core .NET libraries

### Affected APIs

- `T:System.Uri`

-->
