---
ms.openlocfilehash: 18718ebc934e0175c20411055b8c0a90ef6b175f
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90539488"
---
### <a name="globalization-apis-use-icu-libraries-on-windows"></a><span data-ttu-id="8b369-101">Interfejsy API globalizacji korzystają z bibliotek ICU w systemie Windows</span><span class="sxs-lookup"><span data-stu-id="8b369-101">Globalization APIs use ICU libraries on Windows</span></span>

<span data-ttu-id="8b369-102">.NET 5,0 i nowsze wersje używają [międzynarodowych składników dla bibliotek Unicode (ICU)](http://site.icu-project.org/home) do obsługi funkcji globalizacji w przypadku uruchamiania w systemie Windows 10 maja 2019 Update lub nowszym.</span><span class="sxs-lookup"><span data-stu-id="8b369-102">.NET 5.0 and later versions use [International Components for Unicode (ICU)](http://site.icu-project.org/home) libraries for globalization functionality when running on Windows 10 May 2019 Update or later.</span></span>

#### <a name="change-description"></a><span data-ttu-id="8b369-103">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="8b369-103">Change description</span></span>

<span data-ttu-id="8b369-104">Wcześniej biblioteki platformy .NET używały interfejsów API [obsługi języka narodowego (NLS)](/windows/win32/intl/national-language-support) dla funkcji globalizacji.</span><span class="sxs-lookup"><span data-stu-id="8b369-104">Previously, .NET libraries used [National Language Support (NLS)](/windows/win32/intl/national-language-support) APIs for globalization functionality.</span></span> <span data-ttu-id="8b369-105">Na przykład funkcje NLS były używane do pobierania danych kultury, takich jak wzorce formatu daty i godziny, porównywania ciągów i wykonywania wielkich liter w odpowiedniej kulturze.</span><span class="sxs-lookup"><span data-stu-id="8b369-105">For example, NLS functions were used to get culture data, such as date and time format patterns, compare strings, and perform string casing in the appropriate culture.</span></span>

<span data-ttu-id="8b369-106">Począwszy od platformy .NET 5,0, jeśli aplikacja działa w systemie Windows 2019 10 z aktualizacją Update lub nowszym, biblioteki platformy .NET używają interfejsów API [ICU](http://site.icu-project.org/home) globalizacji.</span><span class="sxs-lookup"><span data-stu-id="8b369-106">Starting in .NET 5.0, if an app is running on Windows 10 May 2019 Update or later, .NET libraries use [ICU](http://site.icu-project.org/home) globalization APIs.</span></span> <span data-ttu-id="8b369-107">System Windows 10 maja 2019 Update i nowsze wersje są dostarczane z natywną biblioteką ICU.</span><span class="sxs-lookup"><span data-stu-id="8b369-107">Windows 10 May 2019 Update and later versions ship with the ICU native library.</span></span> <span data-ttu-id="8b369-108">Jeśli środowisko uruchomieniowe platformy .NET nie może załadować ICU, zamiast tego używa środowiska NLS.</span><span class="sxs-lookup"><span data-stu-id="8b369-108">If the .NET runtime can't load ICU, it uses NLS instead.</span></span>

<span data-ttu-id="8b369-109">Ta zmiana została wprowadzona z dwóch powodów:</span><span class="sxs-lookup"><span data-stu-id="8b369-109">This change was introduced for two reasons:</span></span>

- <span data-ttu-id="8b369-110">Aplikacje mają takie samo zachowanie globalizacji między platformami, w tym Linux, macOS i Windows.</span><span class="sxs-lookup"><span data-stu-id="8b369-110">Apps have the same globalization behavior across platforms, including Linux, macOS, and Windows.</span></span>
- <span data-ttu-id="8b369-111">Aplikacje mogą kontrolować zachowanie globalizacji przy użyciu niestandardowych bibliotek ICU.</span><span class="sxs-lookup"><span data-stu-id="8b369-111">Apps can control globalization behavior by using custom ICU libraries.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="8b369-112">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="8b369-112">Version introduced</span></span>

<span data-ttu-id="8b369-113">.NET 5,0 (wersja zapoznawcza 4)</span><span class="sxs-lookup"><span data-stu-id="8b369-113">.NET 5.0 Preview 4</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="8b369-114">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="8b369-114">Recommended action</span></span>

<span data-ttu-id="8b369-115">W części dewelopera nie jest wymagana żadna akcja.</span><span class="sxs-lookup"><span data-stu-id="8b369-115">No action is required on the part of the developer.</span></span> <span data-ttu-id="8b369-116">Jeśli jednak chcesz kontynuować korzystanie z interfejsów API globalizacji NLS, możesz ustawić [przełącznik czasu wykonywania](../../../../docs/core/run-time-config/globalization.md#nls) w celu przywrócenia tego zachowania.</span><span class="sxs-lookup"><span data-stu-id="8b369-116">However, if you wish to continue using NLS globalization APIs, you can set a [run-time switch](../../../../docs/core/run-time-config/globalization.md#nls) to revert to that behavior.</span></span> <span data-ttu-id="8b369-117">Aby uzyskać więcej informacji na temat dostępnych przełączników, zobacz artykuł [globalizacja i ICU platformy .NET](../../../../docs/standard/globalization-localization/globalization-icu.md) .</span><span class="sxs-lookup"><span data-stu-id="8b369-117">For more information about the available switches, see the [.NET globalization and ICU](../../../../docs/standard/globalization-localization/globalization-icu.md) article.</span></span>

#### <a name="category"></a><span data-ttu-id="8b369-118">Kategoria</span><span class="sxs-lookup"><span data-stu-id="8b369-118">Category</span></span>

<span data-ttu-id="8b369-119">Globalizacja</span><span class="sxs-lookup"><span data-stu-id="8b369-119">Globalization</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="8b369-120">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="8b369-120">Affected APIs</span></span>

- <xref:System.Span%601?displayProperty=fullName>
- <xref:System.String?displayProperty=fullName>
- <span data-ttu-id="8b369-121">Większość typów w <xref:System.Globalization?displayProperty=fullName> przestrzeni nazw</span><span class="sxs-lookup"><span data-stu-id="8b369-121">Most types in the <xref:System.Globalization?displayProperty=fullName> namespace</span></span>

<!--

#### Affected APIs

- ``T:System.Span`1``
- `T:System.String`
- `N:System.Globalization`

-->
