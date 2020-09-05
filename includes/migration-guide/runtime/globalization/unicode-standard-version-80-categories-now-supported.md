---
ms.openlocfilehash: f389a9e9bcf4ac1777db66731a085d74889c4a98
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496131"
---
### <a name="unicode-standard-version-80-categories-now-supported"></a><span data-ttu-id="b395b-101">Kategorie Unicode w wersji Standard 8,0 są teraz obsługiwane</span><span class="sxs-lookup"><span data-stu-id="b395b-101">Unicode standard version 8.0 categories now supported</span></span>

#### <a name="details"></a><span data-ttu-id="b395b-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="b395b-102">Details</span></span>

<span data-ttu-id="b395b-103">W .NET Framework 4.6.2 dane Unicode zostały uaktualnione z wersji standard Unicode 6,3 do wersji 8,0.</span><span class="sxs-lookup"><span data-stu-id="b395b-103">In .NET Framework 4.6.2, Unicode data has been upgraded from Unicode Standard version 6.3 to version 8.0.</span></span>  <span data-ttu-id="b395b-104">Podczas żądania kategorii znaków Unicode w .NET Framework 4.6.2 niektóre wyniki mogą być niezgodne z wynikami w poprzednich .NET Framework wersjach.</span><span class="sxs-lookup"><span data-stu-id="b395b-104">When requesting Unicode character categories in .NET Framework 4.6.2, some results might not match the results in previous .NET Framework versions.</span></span>  <span data-ttu-id="b395b-105">Ta zmiana głównie ma wpływ na sylaby czirokeski i nowe znaki samogłosek artość oraz znaki tonu.</span><span class="sxs-lookup"><span data-stu-id="b395b-105">This change mostly affects Cherokee syllables and New Tai Lue vowels signs and tone marks.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="b395b-106">Sugestia</span><span class="sxs-lookup"><span data-stu-id="b395b-106">Suggestion</span></span>

<span data-ttu-id="b395b-107">Przejrzyj kod i Usuń lub Zmień logikę, która zależy od zakodowanych kategorii znaków Unicode.</span><span class="sxs-lookup"><span data-stu-id="b395b-107">Review code and remove/change logic that depends on hard-coded Unicode character categories.</span></span>

| <span data-ttu-id="b395b-108">Nazwa</span><span class="sxs-lookup"><span data-stu-id="b395b-108">Name</span></span>    | <span data-ttu-id="b395b-109">Wartość</span><span class="sxs-lookup"><span data-stu-id="b395b-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="b395b-110">Zakres</span><span class="sxs-lookup"><span data-stu-id="b395b-110">Scope</span></span>   |<span data-ttu-id="b395b-111">Mały</span><span class="sxs-lookup"><span data-stu-id="b395b-111">Minor</span></span>|
|<span data-ttu-id="b395b-112">Wersja</span><span class="sxs-lookup"><span data-stu-id="b395b-112">Version</span></span>|<span data-ttu-id="b395b-113">4.6.2</span><span class="sxs-lookup"><span data-stu-id="b395b-113">4.6.2</span></span>|
|<span data-ttu-id="b395b-114">Typ</span><span class="sxs-lookup"><span data-stu-id="b395b-114">Type</span></span>|<span data-ttu-id="b395b-115">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="b395b-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="b395b-116">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="b395b-116">Affected APIs</span></span>

- <xref:System.Char.GetUnicodeCategory(System.Char)?displayProperty=nameWithType>
- <xref:System.Globalization.CharUnicodeInfo.GetUnicodeCategory(System.Char)?displayProperty=nameWithType>
- <xref:System.Globalization.CharUnicodeInfo.GetUnicodeCategory(System.String,System.Int32)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Char.GetUnicodeCategory(System.Char)`
- `M:System.Globalization.CharUnicodeInfo.GetUnicodeCategory(System.Char)`
- `M:System.Globalization.CharUnicodeInfo.GetUnicodeCategory(System.String,System.Int32)`

-->
