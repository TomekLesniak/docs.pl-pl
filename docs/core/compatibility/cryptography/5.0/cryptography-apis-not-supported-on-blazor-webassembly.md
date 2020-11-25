---
title: 'Zmiana istotna: System. Security. Kryptografia API nie jest obsługiwana w zestawie webBlazor'
description: Dowiedz się więcej na temat istotnej zmiany w programie .NET 5,0, w której interfejsy API kryptografii zgłaszają wyjątek w przypadku uruchamiania w przeglądarce.
ms.date: 09/16/2020
ms.openlocfilehash: ec10fa777e91f641b5582378830536a0cfa8dd72
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761399"
---
# <a name="systemsecuritycryptography-apis-not-supported-on-blazor-webassembly"></a><span data-ttu-id="95498-103">Interfejsy API System. Security. Cryptography nie są obsługiwane w zestawie webassembly Blazor</span><span class="sxs-lookup"><span data-stu-id="95498-103">System.Security.Cryptography APIs not supported on Blazor WebAssembly</span></span>

<span data-ttu-id="95498-104"><xref:System.Security.Cryptography> Interfejsy API generują <xref:System.PlatformNotSupportedException> w czasie wykonywania w przypadku uruchamiania w przeglądarce.</span><span class="sxs-lookup"><span data-stu-id="95498-104"><xref:System.Security.Cryptography> APIs throw a <xref:System.PlatformNotSupportedException> at run time when run on a browser.</span></span>

## <a name="change-description"></a><span data-ttu-id="95498-105">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="95498-105">Change description</span></span>

<span data-ttu-id="95498-106">W poprzednich wersjach programu .NET większość <xref:System.Security.Cryptography> interfejsów API nie jest dostępna dla aplikacji Blazor webassembly.</span><span class="sxs-lookup"><span data-stu-id="95498-106">In previous .NET versions, most of the <xref:System.Security.Cryptography> APIs aren't available to Blazor WebAssembly apps.</span></span> <span data-ttu-id="95498-107">Począwszy od platformy .NET 5,0, Blazor aplikacje webassembly są przeznaczone dla całego obszaru interfejsu API platformy .NET 5, ale nie wszystkie interfejsy API programu .NET 5 są obsługiwane z powodu ograniczeń piaskownicy w przeglądarce.</span><span class="sxs-lookup"><span data-stu-id="95498-107">Starting in .NET 5.0, Blazor WebAssembly apps target the full .NET 5 API surface area, however, not all .NET 5 APIs are supported due to browser sandbox constraints.</span></span> <span data-ttu-id="95498-108">W programie .NET 5,0 i nowszych wersjach nieobsługiwane <xref:System.Security.Cryptography> interfejsy API zgłaszają <xref:System.PlatformNotSupportedException> podczas uruchamiania w zestawie webassembly.</span><span class="sxs-lookup"><span data-stu-id="95498-108">In .NET 5.0 and later versions, the unsupported <xref:System.Security.Cryptography> APIs throw a <xref:System.PlatformNotSupportedException> when running on WebAssembly.</span></span>

> [!TIP]
> <span data-ttu-id="95498-109">[Analizator zgodności platformy](../../code-analysis/5.0/ca1416-platform-compatibility-analyzer.md) będzie flagować wszystkie wywołania interfejsów API, których to dotyczy, podczas tworzenia projektu, który obsługuje platformę przeglądarki.</span><span class="sxs-lookup"><span data-stu-id="95498-109">The [Platform compatibility analyzer](../../code-analysis/5.0/ca1416-platform-compatibility-analyzer.md) will flag any calls to the affected APIs when you build a project that supports the browser platform.</span></span> <span data-ttu-id="95498-110">Ten analizator jest domyślnie uruchamiany w programie .NET 5,0 i nowszych aplikacjach.</span><span class="sxs-lookup"><span data-stu-id="95498-110">This analyzer runs by default in .NET 5.0 and later apps.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="95498-111">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="95498-111">Reason for change</span></span>

<span data-ttu-id="95498-112">Firma Microsoft nie może wydać OpenSSL jako zależności w konfiguracji Blazor webassembly.</span><span class="sxs-lookup"><span data-stu-id="95498-112">Microsoft is unable to ship OpenSSL as a dependency in the Blazor WebAssembly configuration.</span></span> <span data-ttu-id="95498-113">Podjęto próbę obejścia tego problemu, próbując przeprowadzić integrację z `SubtleCrypto` interfejsem API przeglądarki.</span><span class="sxs-lookup"><span data-stu-id="95498-113">We attempted to work around this by trying to integrate with the browser's `SubtleCrypto` API.</span></span> <span data-ttu-id="95498-114">Niestety, wymagało znaczących zmian interfejsu API, które zostały zbyt trudne do integracji.</span><span class="sxs-lookup"><span data-stu-id="95498-114">Unfortunately, it required significant API changes that made it too hard to integrate.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="95498-115">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="95498-115">Version introduced</span></span>

<span data-ttu-id="95498-116">5,0</span><span class="sxs-lookup"><span data-stu-id="95498-116">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="95498-117">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="95498-117">Recommended action</span></span>

<span data-ttu-id="95498-118">W tej chwili nie ma dobrego obejścia do zaproponowania.</span><span class="sxs-lookup"><span data-stu-id="95498-118">There are no good workarounds to suggest at this time.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="95498-119">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="95498-119">Affected APIs</span></span>

<span data-ttu-id="95498-120">Wszystkie <xref:System.Security.Cryptography?displayProperty=fullName> interfejsy API, z wyjątkiem następujących:</span><span class="sxs-lookup"><span data-stu-id="95498-120">All <xref:System.Security.Cryptography?displayProperty=fullName> APIs except the following:</span></span>

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

### Affected APIs

- `T:System.Security.Cryptography`

### Category

- ASP.NET Core
- Cryptography

-->
