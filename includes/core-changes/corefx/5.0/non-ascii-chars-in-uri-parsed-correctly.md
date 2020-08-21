---
ms.openlocfilehash: faf9459ab9002e6149560e2a3452265fa246bf6b
ms.sourcegitcommit: ef86c24c418439b8bb5e3e7d64bbdbe5e11c3e9c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/21/2020
ms.locfileid: "88720208"
---
### <a name="uri-paths-with-non-ascii-characters-parse-correctly-on-unix"></a><span data-ttu-id="d6511-101">Ścieżki URI zawierające znaki inne niż ASCII są analizowane prawidłowo w systemie UNIX</span><span class="sxs-lookup"><span data-stu-id="d6511-101">URI paths with non-ASCII characters parse correctly on Unix</span></span>

<span data-ttu-id="d6511-102">W klasie rozwiązano błąd <xref:System.Uri?displayProperty=fullName> , który umożliwia poprawne analizowanie bezwzględnych ścieżek URI zawierających znaki inne niż ASCII na platformach UNIX.</span><span class="sxs-lookup"><span data-stu-id="d6511-102">A bug was fixed in the <xref:System.Uri?displayProperty=fullName> class such that absolute URI paths that contain non-ASCII characters now parse correctly on Unix platforms.</span></span>

#### <a name="change-description"></a><span data-ttu-id="d6511-103">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="d6511-103">Change description</span></span>

<span data-ttu-id="d6511-104">W poprzednich wersjach programu .NET bezwzględne ścieżki identyfikatorów URI, które zawierają znaki inne niż ASCII, są nieprawidłowo analizowane na platformach UNIX, a segmenty ścieżki są zduplikowane.</span><span class="sxs-lookup"><span data-stu-id="d6511-104">In previous versions of .NET, absolute URI paths that contain non-ASCII characters are parsed incorrectly on Unix platforms, and segments of the path are duplicated.</span></span> <span data-ttu-id="d6511-105">(Ścieżki bezwzględne to te, które zaczynają się od "/"). Problem z analizą został rozwiązany dla programu .NET 5,0.</span><span class="sxs-lookup"><span data-stu-id="d6511-105">(Absolute paths are those that start with "/".) The parsing issue has been fixed for .NET 5.0.</span></span> <span data-ttu-id="d6511-106">Przejście z poprzedniej wersji programu .NET do programu .NET 5,0 lub nowszego spowoduje uzyskanie różnych wartości utworzonych przez <xref:System.Uri.AbsoluteUri?displayProperty=nameWithType> , <xref:System.Uri.ToString?displayProperty=nameWithType> i innych <xref:System.Uri> członków.</span><span class="sxs-lookup"><span data-stu-id="d6511-106">If you move from a previous version of .NET to .NET 5.0 or later, you'll get different values produced by <xref:System.Uri.AbsoluteUri?displayProperty=nameWithType>, <xref:System.Uri.ToString?displayProperty=nameWithType>, and other <xref:System.Uri> members.</span></span>

<span data-ttu-id="d6511-107">Podczas uruchamiania w systemie UNIX Rozważ użycie danych wyjściowych następującego kodu.</span><span class="sxs-lookup"><span data-stu-id="d6511-107">Consider the output of the following code when run on Unix.</span></span>

```csharp
var myUri = new Uri("/üri");

Console.WriteLine($"AbsoluteUri: {myUri.AbsoluteUri}");
Console.WriteLine($"ToString: {myUri.ToString()}");
```

<span data-ttu-id="d6511-108">Dane wyjściowe w poprzedniej wersji platformy .NET:</span><span class="sxs-lookup"><span data-stu-id="d6511-108">Output on previous .NET version:</span></span>

```text
AbsoluteUri: /%C3%BCri/%C3%BCri
ToString: /üri/üri
```

<span data-ttu-id="d6511-109">Dane wyjściowe w programie .NET 5,0 lub jego nowszej wersji:</span><span class="sxs-lookup"><span data-stu-id="d6511-109">Output on .NET 5.0 or later version:</span></span>

```text
AbsoluteUri: /%C3%BCri
ToString: /üri
```

#### <a name="version-introduced"></a><span data-ttu-id="d6511-110">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="d6511-110">Version introduced</span></span>

<span data-ttu-id="d6511-111">5.0</span><span class="sxs-lookup"><span data-stu-id="d6511-111">5.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="d6511-112">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="d6511-112">Recommended action</span></span>

<span data-ttu-id="d6511-113">Jeśli masz kod, który oczekuje i konta dla zduplikowanych segmentów ścieżki, możesz usunąć ten kod.</span><span class="sxs-lookup"><span data-stu-id="d6511-113">If you have code that expects and accounts for the duplicated path segments, you can remove that code.</span></span>

#### <a name="category"></a><span data-ttu-id="d6511-114">Kategoria</span><span class="sxs-lookup"><span data-stu-id="d6511-114">Category</span></span>

<span data-ttu-id="d6511-115">Podstawowe biblioteki platformy .NET</span><span class="sxs-lookup"><span data-stu-id="d6511-115">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="d6511-116">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="d6511-116">Affected APIs</span></span>

- <xref:System.Uri?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.Uri`

-->
