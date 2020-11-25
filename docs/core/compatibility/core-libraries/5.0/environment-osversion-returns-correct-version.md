---
title: 'Istotna zmiana: Environment. OSVersion zwraca poprawną wersję systemu operacyjnego'
description: Dowiedz się więcej na temat istotnej zmiany w programie .NET 5,0 w bibliotekach podstawowych platformy .NET, gdzie Environment. OSVersion zwraca rzeczywistą wersję systemu operacyjnego, a na przykład system operacyjny wybrany do zapewnienia zgodności aplikacji.
ms.date: 11/01/2020
ms.openlocfilehash: b78ca1c7be50f76b99b5558a976d8f00e2f560c3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761722"
---
# <a name="environmentosversion-returns-the-correct-operating-system-version"></a><span data-ttu-id="a8681-103">Środowisko. OSVersion zwraca poprawną wersję systemu operacyjnego</span><span class="sxs-lookup"><span data-stu-id="a8681-103">Environment.OSVersion returns the correct operating system version</span></span>

<span data-ttu-id="a8681-104"><xref:System.Environment.OSVersion?displayProperty=nameWithType> zwraca rzeczywistą wersję systemu operacyjnego (OS) zamiast programu, na przykład systemu operacyjnego wybranego na potrzeby zgodności aplikacji.</span><span class="sxs-lookup"><span data-stu-id="a8681-104"><xref:System.Environment.OSVersion?displayProperty=nameWithType> returns the actual version of the operating system (OS) instead of, for example, the OS that's selected for application compatibility.</span></span>

## <a name="change-description"></a><span data-ttu-id="a8681-105">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="a8681-105">Change description</span></span>

<span data-ttu-id="a8681-106">W poprzednich wersjach programu .NET <xref:System.Environment.OSVersion?displayProperty=nameWithType> Funkcja zwraca wersję systemu operacyjnego, która może być niepoprawna, gdy aplikacja działa w trybie zgodności systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="a8681-106">In previous .NET versions, <xref:System.Environment.OSVersion?displayProperty=nameWithType> returns an OS version that may be incorrect when an application runs under Windows compatibility mode.</span></span> <span data-ttu-id="a8681-107">Aby uzyskać więcej informacji, zobacz [uwagi dotyczące funkcji GetVersionExA](/windows/win32/api/sysinfoapi/nf-sysinfoapi-getversionexa#remarks).</span><span class="sxs-lookup"><span data-stu-id="a8681-107">For more information, see [GetVersionExA function remarks](/windows/win32/api/sysinfoapi/nf-sysinfoapi-getversionexa#remarks).</span></span>

<span data-ttu-id="a8681-108">Począwszy od platformy .NET 5,0, <xref:System.Environment.OSVersion?displayProperty=nameWithType> zwraca rzeczywistą wersję systemu operacyjnego.</span><span class="sxs-lookup"><span data-stu-id="a8681-108">Starting in .NET 5.0, <xref:System.Environment.OSVersion?displayProperty=nameWithType> returns the actual version of the operating system.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="a8681-109">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="a8681-109">Reason for change</span></span>

<span data-ttu-id="a8681-110">Użytkownicy tej właściwości oczekują zwrócenia rzeczywistej wersji systemu operacyjnego.</span><span class="sxs-lookup"><span data-stu-id="a8681-110">Users of this property expect it to return the actual version of the operating system.</span></span> <span data-ttu-id="a8681-111">Większość aplikacji platformy .NET nie określa ich obsługiwanej wersji w manifeście aplikacji i w ten sposób uzyskuje domyślną obsługiwaną wersję z hosta dotnet.</span><span class="sxs-lookup"><span data-stu-id="a8681-111">Most .NET apps don't specify their supported version in their application manifest, and thus get the default supported version from the dotnet host.</span></span> <span data-ttu-id="a8681-112">W związku z tym podkładka dotycząca zgodności ma rzadko znaczenie dla aplikacji, która jest uruchomiona.</span><span class="sxs-lookup"><span data-stu-id="a8681-112">As a result, the compatibility shim is rarely meaningful for the app that's running.</span></span> <span data-ttu-id="a8681-113">Gdy system Windows zwalnia nową wersję, a starszy Host dotnet jest nadal używany, te aplikacje mogą uzyskać niepoprawną wersję systemu operacyjnego.</span><span class="sxs-lookup"><span data-stu-id="a8681-113">When Windows releases a new version and an older dotnet host is still in use, these apps may get an incorrect OS version.</span></span> <span data-ttu-id="a8681-114">Zwrócenie rzeczywistej wersji jest bardziej wbudowane z oczekiwaniami deweloperów tego interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="a8681-114">Returning the actual version is more inline with developers' expectations of this API.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="a8681-115">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="a8681-115">Version introduced</span></span>

<span data-ttu-id="a8681-116">5,0</span><span class="sxs-lookup"><span data-stu-id="a8681-116">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="a8681-117">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="a8681-117">Recommended action</span></span>

<span data-ttu-id="a8681-118">Przejrzyj i przetestuj każdy kod, który używa, <xref:System.Environment.OSVersion?displayProperty=nameWithType> Aby upewnić się, że działa zgodnie z potrzebami.</span><span class="sxs-lookup"><span data-stu-id="a8681-118">Review and test any code that uses <xref:System.Environment.OSVersion?displayProperty=nameWithType> to ensure it behaves as desired.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="a8681-119">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="a8681-119">Affected APIs</span></span>

- <xref:System.Environment.OSVersion?displayProperty=fullName>

<!--

### Category

Core .NET libraries

### Affected APIs

- `P:System.Environment.OSVersion`

-->
