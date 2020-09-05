---
ms.openlocfilehash: e7001fcfdf88fd9e710fbb702f2ed39d63b1e080
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496251"
---
### <a name="systemuri-escaping-now-supports-rfc-3986"></a><span data-ttu-id="1f800-101">Ucieczka system. URI obsługuje teraz RFC 3986</span><span class="sxs-lookup"><span data-stu-id="1f800-101">System.Uri escaping now supports RFC 3986</span></span>

#### <a name="details"></a><span data-ttu-id="1f800-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="1f800-102">Details</span></span>

<span data-ttu-id="1f800-103">Ucieczka identyfikatorów URI została zmieniona w .NET Framework 4,5 w celu obsługi [specyfikacji RFC 3986](https://tools.ietf.org/html/rfc3986).</span><span class="sxs-lookup"><span data-stu-id="1f800-103">URI escaping has changed in .NET Framework 4.5 to support [RFC 3986](https://tools.ietf.org/html/rfc3986).</span></span> <span data-ttu-id="1f800-104">Określone zmiany obejmują:</span><span class="sxs-lookup"><span data-stu-id="1f800-104">Specific changes include:</span></span><ul><li><span data-ttu-id="1f800-105"><xref:System.Uri.EscapeDataString(System.String)?displayProperty=fullName> wyprowadza znaki zastrzeżone na podstawie RFC 3986.</span><span class="sxs-lookup"><span data-stu-id="1f800-105"><xref:System.Uri.EscapeDataString(System.String)?displayProperty=fullName> escapes reserved characters based on RFC 3986.</span></span></li><li><span data-ttu-id="1f800-106"><xref:System.Uri.EscapeUriString(System.String)?displayProperty=fullName> nie ma znaków zarezerwowanych.</span><span class="sxs-lookup"><span data-stu-id="1f800-106"><xref:System.Uri.EscapeUriString(System.String)?displayProperty=fullName> does not escape reserved characters.</span></span></li><li><span data-ttu-id="1f800-107"><xref:System.Uri.UnescapeDataString(System.String)?displayProperty=fullName> nie zgłasza wyjątku, jeśli napotka nieprawidłową sekwencję ucieczki.</span><span class="sxs-lookup"><span data-stu-id="1f800-107"><xref:System.Uri.UnescapeDataString(System.String)?displayProperty=fullName> does not throw an exception if it encounters an invalid escape sequence.</span></span></li><li><span data-ttu-id="1f800-108">Niezastrzeżone znaki ucieczki przestają być znakami ucieczki.</span><span class="sxs-lookup"><span data-stu-id="1f800-108">Unreserved escaped characters are un-escaped.</span></span></li></ul>

#### <a name="suggestion"></a><span data-ttu-id="1f800-109">Sugestia</span><span class="sxs-lookup"><span data-stu-id="1f800-109">Suggestion</span></span>

<ul><li><span data-ttu-id="1f800-110">Zaktualizuj aplikacje, aby nie polegać na zgłaszaniu <xref:System.Uri.UnescapeDataString(System.String)?displayProperty=fullName> w przypadku nieprawidłowej sekwencji ucieczki.</span><span class="sxs-lookup"><span data-stu-id="1f800-110">Update applications to not rely on <xref:System.Uri.UnescapeDataString(System.String)?displayProperty=fullName> to throw in the case of an invalid escape sequence.</span></span> <span data-ttu-id="1f800-111">Takie sekwencje muszą być wykrywane bezpośrednio.</span><span class="sxs-lookup"><span data-stu-id="1f800-111">Such sequences must be detected directly now.</span></span></li><li><span data-ttu-id="1f800-112">Podobnie, należy oczekiwać, że identyfikatory URI i niezmienionych ciągów i danych mogą się różnić od .NET Framework 4,0 i .NET Framework 4,5 i nie powinny być porównywane bezpośrednio między wersjami programu .NET.</span><span class="sxs-lookup"><span data-stu-id="1f800-112">Similarly, expect that Escaped and Unescaped URI and Data strings may vary from .NET Framework 4.0 and .NET Framework 4.5 and should not be compared across .NET versions directly.</span></span> <span data-ttu-id="1f800-113">Zamiast tego należy je analizować i znormalizować w jednej wersji platformy .NET przed dokonaniem jakichkolwiek porównań.</span><span class="sxs-lookup"><span data-stu-id="1f800-113">Instead, they should be parsed and normalized in a single .NET version before any comparisons are made.</span></span></li></ul>

| <span data-ttu-id="1f800-114">Nazwa</span><span class="sxs-lookup"><span data-stu-id="1f800-114">Name</span></span>    | <span data-ttu-id="1f800-115">Wartość</span><span class="sxs-lookup"><span data-stu-id="1f800-115">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="1f800-116">Zakres</span><span class="sxs-lookup"><span data-stu-id="1f800-116">Scope</span></span>   |<span data-ttu-id="1f800-117">Mały</span><span class="sxs-lookup"><span data-stu-id="1f800-117">Minor</span></span>|
|<span data-ttu-id="1f800-118">Wersja</span><span class="sxs-lookup"><span data-stu-id="1f800-118">Version</span></span>|<span data-ttu-id="1f800-119">4.5</span><span class="sxs-lookup"><span data-stu-id="1f800-119">4.5</span></span>|
|<span data-ttu-id="1f800-120">Typ</span><span class="sxs-lookup"><span data-stu-id="1f800-120">Type</span></span>|<span data-ttu-id="1f800-121">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="1f800-121">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="1f800-122">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="1f800-122">Affected APIs</span></span>

- <xref:System.Uri.EscapeDataString(System.String)?displayProperty=nameWithType>
- <xref:System.Uri.EscapeUriString(System.String)?displayProperty=nameWithType>
- <xref:System.Uri.UnescapeDataString(System.String)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Uri.EscapeDataString(System.String)`
- `M:System.Uri.EscapeUriString(System.String)`
- `M:System.Uri.UnescapeDataString(System.String)`

-->
