---
title: 'Zmiana istotna: ścieżki URI z niestandardowymi znakami ASCII są analizowane prawidłowo w systemie UNIX'
description: Więcej informacji na temat istotnej zmiany w programie .NET 5,0 w bibliotekach podstawowych platformy .NET, w których bezwzględne ścieżki identyfikatorów URI, które zawierają znaki inne niż ASCII, są teraz analizowane poprawnie na platformach UNIX
ms.date: 11/01/2020
ms.openlocfilehash: 94de4e0eb94a11153d873871d4003422a4286a0c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761376"
---
# <a name="uri-paths-with-non-ascii-characters-parse-correctly-on-unix"></a><span data-ttu-id="ec826-103">Ścieżki URI zawierające znaki inne niż ASCII są analizowane prawidłowo w systemie UNIX</span><span class="sxs-lookup"><span data-stu-id="ec826-103">URI paths with non-ASCII characters parse correctly on Unix</span></span>

<span data-ttu-id="ec826-104">W klasie rozwiązano błąd <xref:System.Uri?displayProperty=fullName> , który umożliwia poprawne analizowanie bezwzględnych ścieżek URI zawierających znaki inne niż ASCII na platformach UNIX.</span><span class="sxs-lookup"><span data-stu-id="ec826-104">A bug was fixed in the <xref:System.Uri?displayProperty=fullName> class such that absolute URI paths that contain non-ASCII characters now parse correctly on Unix platforms.</span></span>

## <a name="change-description"></a><span data-ttu-id="ec826-105">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="ec826-105">Change description</span></span>

<span data-ttu-id="ec826-106">W poprzednich wersjach programu .NET bezwzględne ścieżki identyfikatorów URI, które zawierają znaki inne niż ASCII, są nieprawidłowo analizowane na platformach UNIX, a segmenty ścieżki są zduplikowane.</span><span class="sxs-lookup"><span data-stu-id="ec826-106">In previous versions of .NET, absolute URI paths that contain non-ASCII characters are parsed incorrectly on Unix platforms, and segments of the path are duplicated.</span></span> <span data-ttu-id="ec826-107">(Ścieżki bezwzględne to te, które zaczynają się od "/"). Problem z analizą został rozwiązany dla programu .NET 5,0.</span><span class="sxs-lookup"><span data-stu-id="ec826-107">(Absolute paths are those that start with "/".) The parsing issue has been fixed for .NET 5.0.</span></span> <span data-ttu-id="ec826-108">Przejście z poprzedniej wersji programu .NET do programu .NET 5,0 lub nowszego spowoduje uzyskanie różnych wartości utworzonych przez <xref:System.Uri.AbsoluteUri?displayProperty=nameWithType> , <xref:System.Uri.ToString?displayProperty=nameWithType> i innych <xref:System.Uri> członków.</span><span class="sxs-lookup"><span data-stu-id="ec826-108">If you move from a previous version of .NET to .NET 5.0 or later, you'll get different values produced by <xref:System.Uri.AbsoluteUri?displayProperty=nameWithType>, <xref:System.Uri.ToString?displayProperty=nameWithType>, and other <xref:System.Uri> members.</span></span>

<span data-ttu-id="ec826-109">Podczas uruchamiania w systemie UNIX Rozważ użycie danych wyjściowych następującego kodu.</span><span class="sxs-lookup"><span data-stu-id="ec826-109">Consider the output of the following code when run on Unix.</span></span>

```csharp
var myUri = new Uri("/üri");

Console.WriteLine($"AbsoluteUri: {myUri.AbsoluteUri}");
Console.WriteLine($"ToString: {myUri.ToString()}");
```

<span data-ttu-id="ec826-110">Dane wyjściowe w poprzedniej wersji platformy .NET:</span><span class="sxs-lookup"><span data-stu-id="ec826-110">Output on previous .NET version:</span></span>

```text
AbsoluteUri: /%C3%BCri/%C3%BCri
ToString: /üri/üri
```

<span data-ttu-id="ec826-111">Dane wyjściowe w programie .NET 5,0 lub jego nowszej wersji:</span><span class="sxs-lookup"><span data-stu-id="ec826-111">Output on .NET 5.0 or later version:</span></span>

```text
AbsoluteUri: /%C3%BCri
ToString: /üri
```

## <a name="version-introduced"></a><span data-ttu-id="ec826-112">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="ec826-112">Version introduced</span></span>

<span data-ttu-id="ec826-113">5,0</span><span class="sxs-lookup"><span data-stu-id="ec826-113">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="ec826-114">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="ec826-114">Recommended action</span></span>

<span data-ttu-id="ec826-115">Jeśli masz kod, który oczekuje i konta dla zduplikowanych segmentów ścieżki, możesz usunąć ten kod.</span><span class="sxs-lookup"><span data-stu-id="ec826-115">If you have code that expects and accounts for the duplicated path segments, you can remove that code.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="ec826-116">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="ec826-116">Affected APIs</span></span>

- <xref:System.Uri?displayProperty=fullName>

<!--

### Category

Core .NET libraries

### Affected APIs

- `T:System.Uri`

-->
