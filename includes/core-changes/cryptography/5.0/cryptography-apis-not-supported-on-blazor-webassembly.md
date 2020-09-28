---
ms.openlocfilehash: 6c2aff4abf558307d599ff7533c82286e037bc71
ms.sourcegitcommit: 1274a1a4a4c7e2eaf56b38da76ef7cec789726ef
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/28/2020
ms.locfileid: "91406154"
---
### <a name="systemsecuritycryptography-apis-not-supported-on-blazor-webassembly"></a><span data-ttu-id="e6d6d-101">Interfejsy API System. Security. Cryptography nie są obsługiwane w zestawie webassembly Blazor</span><span class="sxs-lookup"><span data-stu-id="e6d6d-101">System.Security.Cryptography APIs not supported on Blazor WebAssembly</span></span>

<span data-ttu-id="e6d6d-102"><xref:System.Security.Cryptography> Interfejsy API generują <xref:System.PlatformNotSupportedException> w czasie wykonywania w przypadku uruchamiania w przeglądarce.</span><span class="sxs-lookup"><span data-stu-id="e6d6d-102"><xref:System.Security.Cryptography> APIs throw a <xref:System.PlatformNotSupportedException> at run time when run on a browser.</span></span>

#### <a name="change-description"></a><span data-ttu-id="e6d6d-103">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="e6d6d-103">Change description</span></span>

<span data-ttu-id="e6d6d-104">W poprzednich wersjach programu .NET większość <xref:System.Security.Cryptography> interfejsów API nie jest dostępna dla aplikacji Blazor webassembly.</span><span class="sxs-lookup"><span data-stu-id="e6d6d-104">In previous .NET versions, most of the <xref:System.Security.Cryptography> APIs aren't available to Blazor WebAssembly apps.</span></span> <span data-ttu-id="e6d6d-105">Począwszy od platformy .NET 5,0, Blazor aplikacje webassembly są przeznaczone dla całego obszaru interfejsu API platformy .NET 5, ale nie wszystkie interfejsy API programu .NET 5 są obsługiwane z powodu ograniczeń piaskownicy w przeglądarce.</span><span class="sxs-lookup"><span data-stu-id="e6d6d-105">Starting in .NET 5.0, Blazor WebAssembly apps target the full .NET 5 API surface area, however, not all .NET 5 APIs are supported due to browser sandbox constraints.</span></span> <span data-ttu-id="e6d6d-106">W programie .NET 5,0 i nowszych wersjach nieobsługiwane <xref:System.Security.Cryptography> interfejsy API zgłaszają <xref:System.PlatformNotSupportedException> podczas uruchamiania w zestawie webassembly.</span><span class="sxs-lookup"><span data-stu-id="e6d6d-106">In .NET 5.0 and later versions, the unsupported <xref:System.Security.Cryptography> APIs throw a <xref:System.PlatformNotSupportedException> when running on WebAssembly.</span></span>

> [!TIP]
> <span data-ttu-id="e6d6d-107">[Analizator zgodności platformy](../../../../docs/core/compatibility/code-analysis.md#ca1416-platform-compatibility) będzie flagować wszystkie wywołania interfejsów API, których to dotyczy, podczas tworzenia projektu, który obsługuje platformę przeglądarki.</span><span class="sxs-lookup"><span data-stu-id="e6d6d-107">The [Platform compatibility analyzer](../../../../docs/core/compatibility/code-analysis.md#ca1416-platform-compatibility) will flag any calls to the affected APIs when you build a project that supports the browser platform.</span></span> <span data-ttu-id="e6d6d-108">Ten analizator jest domyślnie uruchamiany w programie .NET 5,0 i nowszych aplikacjach.</span><span class="sxs-lookup"><span data-stu-id="e6d6d-108">This analyzer runs by default in .NET 5.0 and later apps.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="e6d6d-109">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="e6d6d-109">Reason for change</span></span>

<span data-ttu-id="e6d6d-110">Firma Microsoft nie może wydać OpenSSL jako zależności w konfiguracji Blazor webassembly.</span><span class="sxs-lookup"><span data-stu-id="e6d6d-110">Microsoft is unable to ship OpenSSL as a dependency in the Blazor WebAssembly configuration.</span></span> <span data-ttu-id="e6d6d-111">Podjęto próbę obejścia tego problemu, próbując przeprowadzić integrację z `SubtleCrypto` interfejsem API przeglądarki.</span><span class="sxs-lookup"><span data-stu-id="e6d6d-111">We attempted to work around this by trying to integrate with the browser's `SubtleCrypto` API.</span></span> <span data-ttu-id="e6d6d-112">Niestety, wymagało znaczących zmian interfejsu API, które zostały zbyt trudne do integracji.</span><span class="sxs-lookup"><span data-stu-id="e6d6d-112">Unfortunately, it required significant API changes that made it too hard to integrate.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="e6d6d-113">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="e6d6d-113">Version introduced</span></span>

<span data-ttu-id="e6d6d-114">5,0 RC1</span><span class="sxs-lookup"><span data-stu-id="e6d6d-114">5.0 RC1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="e6d6d-115">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="e6d6d-115">Recommended action</span></span>

<span data-ttu-id="e6d6d-116">W tej chwili nie ma dobrego obejścia do zaproponowania.</span><span class="sxs-lookup"><span data-stu-id="e6d6d-116">There are no good workarounds to suggest at this time.</span></span>

#### <a name="category"></a><span data-ttu-id="e6d6d-117">Kategoria</span><span class="sxs-lookup"><span data-stu-id="e6d6d-117">Category</span></span>

- <span data-ttu-id="e6d6d-118">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e6d6d-118">ASP.NET Core</span></span>
- <span data-ttu-id="e6d6d-119">Kryptografia</span><span class="sxs-lookup"><span data-stu-id="e6d6d-119">Cryptography</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="e6d6d-120">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="e6d6d-120">Affected APIs</span></span>

<span data-ttu-id="e6d6d-121">Wszystkie <xref:System.Security.Cryptography?displayProperty=fullName> interfejsy API, z wyjątkiem następujących:</span><span class="sxs-lookup"><span data-stu-id="e6d6d-121">All <xref:System.Security.Cryptography?displayProperty=fullName> APIs except the following:</span></span>

- `System.Security.Cryptography.RandomNumberGenerator`
- `System.Security.Cryptography.IncrementalHash`
- `System.Security.Cryptography.SHA1`
- `System.Security.Cryptography.SHA256`
- `System.Security.Cryptography.SHA384`
- `System.Security.Cryptography.SHA512`
- `System.Security.Cryptography.SHA1Managed`
- `System.Security.Cryptography.SHA256Managed`
- `System.Security.Cryptography.SHA384Managed`
- `System.Security.Cryptography.SHA512Managed`

<!--

#### Affected APIs

- `T:System.Security.Cryptography`

-->
