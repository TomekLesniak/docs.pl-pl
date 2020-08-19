---
ms.openlocfilehash: ccd056f23d26e6cce4cc691542784792bffe9fc6
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/18/2020
ms.locfileid: "88558188"
---
### <a name="environmentosversion-returns-the-correct-operating-system-version"></a><span data-ttu-id="663d4-101">Środowisko. OSVersion zwraca poprawną wersję systemu operacyjnego</span><span class="sxs-lookup"><span data-stu-id="663d4-101">Environment.OSVersion returns the correct operating system version</span></span>

<span data-ttu-id="663d4-102"><xref:System.Environment.OSVersion?displayProperty=nameWithType> zwraca rzeczywistą wersję systemu operacyjnego (OS) zamiast programu, na przykład systemu operacyjnego wybranego na potrzeby zgodności aplikacji.</span><span class="sxs-lookup"><span data-stu-id="663d4-102"><xref:System.Environment.OSVersion?displayProperty=nameWithType> returns the actual version of the operating system (OS) instead of, for example, the OS that's selected for application compatibility.</span></span>

#### <a name="change-description"></a><span data-ttu-id="663d4-103">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="663d4-103">Change description</span></span>

<span data-ttu-id="663d4-104">W poprzednich wersjach programu .NET <xref:System.Environment.OSVersion?displayProperty=nameWithType> Funkcja zwraca wersję systemu operacyjnego, która może być niepoprawna, gdy aplikacja działa w trybie zgodności systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="663d4-104">In previous .NET versions, <xref:System.Environment.OSVersion?displayProperty=nameWithType> returns an OS version that may be incorrect when an application runs under Windows compatibility mode.</span></span> <span data-ttu-id="663d4-105">Aby uzyskać więcej informacji, zobacz [uwagi dotyczące funkcji GetVersionExA](/windows/win32/api/sysinfoapi/nf-sysinfoapi-getversionexa#remarks).</span><span class="sxs-lookup"><span data-stu-id="663d4-105">For more information, see [GetVersionExA function remarks](/windows/win32/api/sysinfoapi/nf-sysinfoapi-getversionexa#remarks).</span></span>

<span data-ttu-id="663d4-106">Począwszy od platformy .NET 5,0, <xref:System.Environment.OSVersion?displayProperty=nameWithType> zwraca rzeczywistą wersję systemu operacyjnego.</span><span class="sxs-lookup"><span data-stu-id="663d4-106">Starting in .NET 5.0, <xref:System.Environment.OSVersion?displayProperty=nameWithType> returns the actual version of the operating system.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="663d4-107">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="663d4-107">Reason for change</span></span>

<span data-ttu-id="663d4-108">Użytkownicy tej właściwości oczekują zwrócenia rzeczywistej wersji systemu operacyjnego.</span><span class="sxs-lookup"><span data-stu-id="663d4-108">Users of this property expect it to return the actual version of the operating system.</span></span> <span data-ttu-id="663d4-109">Większość aplikacji platformy .NET nie określa ich obsługiwanej wersji w manifeście aplikacji i w ten sposób uzyskuje domyślną obsługiwaną wersję z hosta dotnet.</span><span class="sxs-lookup"><span data-stu-id="663d4-109">Most .NET apps don't specify their supported version in their application manifest, and thus get the default supported version from the dotnet host.</span></span> <span data-ttu-id="663d4-110">W związku z tym podkładka dotycząca zgodności ma rzadko znaczenie dla aplikacji, która jest uruchomiona.</span><span class="sxs-lookup"><span data-stu-id="663d4-110">As a result, the compatibility shim is rarely meaningful for the app that's running.</span></span> <span data-ttu-id="663d4-111">Gdy system Windows zwalnia nową wersję, a starszy Host dotnet jest nadal używany, te aplikacje mogą uzyskać niepoprawną wersję systemu operacyjnego.</span><span class="sxs-lookup"><span data-stu-id="663d4-111">When Windows releases a new version and an older dotnet host is still in use, these apps may get an incorrect OS version.</span></span> <span data-ttu-id="663d4-112">Zwrócenie rzeczywistej wersji jest bardziej wbudowane z oczekiwaniami deweloperów tego interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="663d4-112">Returning the actual version is more inline with developers' expectations of this API.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="663d4-113">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="663d4-113">Version introduced</span></span>

<span data-ttu-id="663d4-114">5.0</span><span class="sxs-lookup"><span data-stu-id="663d4-114">5.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="663d4-115">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="663d4-115">Recommended action</span></span>

<span data-ttu-id="663d4-116">Przejrzyj i przetestuj każdy kod, który używa, <xref:System.Environment.OSVersion?displayProperty=nameWithType> Aby upewnić się, że działa zgodnie z potrzebami.</span><span class="sxs-lookup"><span data-stu-id="663d4-116">Review and test any code that uses <xref:System.Environment.OSVersion?displayProperty=nameWithType> to ensure it behaves as desired.</span></span>

#### <a name="category"></a><span data-ttu-id="663d4-117">Kategoria</span><span class="sxs-lookup"><span data-stu-id="663d4-117">Category</span></span>

<span data-ttu-id="663d4-118">Podstawowe biblioteki platformy .NET</span><span class="sxs-lookup"><span data-stu-id="663d4-118">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="663d4-119">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="663d4-119">Affected APIs</span></span>

- <xref:System.Environment.OSVersion?displayProperty=fullName>

<!--

#### Affected APIs

- `P:System.Environment.OSVersion`

-->
