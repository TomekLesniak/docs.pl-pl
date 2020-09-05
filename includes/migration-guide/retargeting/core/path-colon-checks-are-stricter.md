---
ms.openlocfilehash: 6af63c0a58a3273aa98fa70f22e3637b481806b4
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497224"
---
### <a name="path-colon-checks-are-stricter"></a><span data-ttu-id="6e609-101">Sprawdzanie dwukropek ścieżki jest bardziej rygorystyczne</span><span class="sxs-lookup"><span data-stu-id="6e609-101">Path colon checks are stricter</span></span>

#### <a name="details"></a><span data-ttu-id="6e609-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="6e609-102">Details</span></span>

<span data-ttu-id="6e609-103">W .NET Framework 4.6.2 wprowadzono wiele zmian do obsługi wcześniej nieobsługiwanych ścieżek (zarówno w formacie długości, jak i formatu).</span><span class="sxs-lookup"><span data-stu-id="6e609-103">In .NET Framework 4.6.2, a number of changes were made to support previously unsupported paths (both in length and format).</span></span> <span data-ttu-id="6e609-104">Sprawdza, czy składnia separatora dysku (dwukropek) była bardziej poprawna, co spowodowało zablokowanie niektórych ścieżek URI w kilku interfejsów API do wybierania ścieżek, w których zostały wcześniej tolerowane.</span><span class="sxs-lookup"><span data-stu-id="6e609-104">Checks for proper drive separator (colon) syntax were made more correct, which had the side effect of blocking some URI paths in a few select Path APIs where they were previously tolerated.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="6e609-105">Sugestia</span><span class="sxs-lookup"><span data-stu-id="6e609-105">Suggestion</span></span>

<span data-ttu-id="6e609-106">W przypadku przekazywania identyfikatora URI do odpowiednich interfejsów API należy najpierw zmodyfikować ciąg tak, aby był on ścieżką prawną.</span><span class="sxs-lookup"><span data-stu-id="6e609-106">If passing a URI to affected APIs, modify the string to be a legal path first.</span></span>

- <span data-ttu-id="6e609-107">Ręcznie usuń schemat z adresów URL (na przykład Usuń `file://` z adresów URL).</span><span class="sxs-lookup"><span data-stu-id="6e609-107">Remove the scheme from URLs manually (for example, remove `file://` from URLs).</span></span>

- <span data-ttu-id="6e609-108">Przekaż identyfikator URI do <xref:System.Uri> klasy i Użyj <xref:System.Uri.LocalPath> .</span><span class="sxs-lookup"><span data-stu-id="6e609-108">Pass the URI to the <xref:System.Uri> class and use <xref:System.Uri.LocalPath>.</span></span>

<span data-ttu-id="6e609-109">Alternatywnie możesz zrezygnować z nowej normalizacji ścieżki, ustawiając `Switch.System.IO.UseLegacyPathHandling` przełącznik AppContext na `true` .</span><span class="sxs-lookup"><span data-stu-id="6e609-109">Alternatively, you can opt out of the new path normalization by setting the `Switch.System.IO.UseLegacyPathHandling` AppContext switch to `true`.</span></span>

| <span data-ttu-id="6e609-110">Nazwa</span><span class="sxs-lookup"><span data-stu-id="6e609-110">Name</span></span>    | <span data-ttu-id="6e609-111">Wartość</span><span class="sxs-lookup"><span data-stu-id="6e609-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="6e609-112">Zakres</span><span class="sxs-lookup"><span data-stu-id="6e609-112">Scope</span></span>   | <span data-ttu-id="6e609-113">Edge</span><span class="sxs-lookup"><span data-stu-id="6e609-113">Edge</span></span>        |
| <span data-ttu-id="6e609-114">Wersja</span><span class="sxs-lookup"><span data-stu-id="6e609-114">Version</span></span> | <span data-ttu-id="6e609-115">4.6.2</span><span class="sxs-lookup"><span data-stu-id="6e609-115">4.6.2</span></span>       |
| <span data-ttu-id="6e609-116">Typ</span><span class="sxs-lookup"><span data-stu-id="6e609-116">Type</span></span>    | <span data-ttu-id="6e609-117">Przekierowanie</span><span class="sxs-lookup"><span data-stu-id="6e609-117">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="6e609-118">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="6e609-118">Affected APIs</span></span>

- <xref:System.IO.Path.GetDirectoryName(System.String)?displayProperty=nameWithType>
- <xref:System.IO.Path.GetPathRoot(System.String)?displayProperty=nameWithType>
