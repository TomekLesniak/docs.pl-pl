---
title: 'Istotna zmiana: wektor <T> zgłasza NotSupportedException'
description: Więcej informacji na temat istotnej zmiany w programie .NET 5,0 w bibliotekach podstawowych platformy .NET, w których wektor <T> zawsze zgłasza wyjątek dla nieobsługiwanych parametrów typu.
ms.date: 11/01/2020
ms.openlocfilehash: 63db7c6b720735b180ed11098227b31a14008f74
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761516"
---
# <a name="vectort-always-throws-notsupportedexception-for-unsupported-types"></a><span data-ttu-id="2f32c-103">Wektor \<T> zawsze zgłasza NotSupportedException dla nieobsługiwanych typów</span><span class="sxs-lookup"><span data-stu-id="2f32c-103">Vector\<T> always throws NotSupportedException for unsupported types</span></span>

<span data-ttu-id="2f32c-104"><xref:System.Numerics.Vector%601?displayProperty=nameWithType> teraz zawsze jest zgłaszany <xref:System.NotSupportedException> dla nieobsługiwanych parametrów typu.</span><span class="sxs-lookup"><span data-stu-id="2f32c-104"><xref:System.Numerics.Vector%601?displayProperty=nameWithType> now always throws a <xref:System.NotSupportedException> for unsupported type parameters.</span></span>

## <a name="change-description"></a><span data-ttu-id="2f32c-105">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="2f32c-105">Change description</span></span>

<span data-ttu-id="2f32c-106">Wcześniej elementy członkowskie <xref:System.Numerics.Vector%601> nie zawsze zgłaszają <xref:System.NotSupportedException> `T` [nieobsługiwany typ](#unsupported-types).</span><span class="sxs-lookup"><span data-stu-id="2f32c-106">Previously, members of <xref:System.Numerics.Vector%601> would not always throw a <xref:System.NotSupportedException> when `T` was an [unsupported type](#unsupported-types).</span></span> <span data-ttu-id="2f32c-107">Wyjątek nie został zawsze wygenerowany ze względu na ścieżki kodu obsługujące przyspieszenie sprzętowe.</span><span class="sxs-lookup"><span data-stu-id="2f32c-107">The exception wasn't always thrown because of code paths that supported hardware acceleration.</span></span> <span data-ttu-id="2f32c-108">Na przykład `Vector<bool> + Vector<bool>` `default` zamiast zgłaszać wyjątek na platformach, które nie mają przyspieszenia sprzętowego, takiego jak ARM32.</span><span class="sxs-lookup"><span data-stu-id="2f32c-108">For example, `Vector<bool> + Vector<bool>` returned `default` instead of throwing an exception on platforms that have no hardware acceleration, such as ARM32.</span></span> <span data-ttu-id="2f32c-109">W przypadku nieobsługiwanych typów <xref:System.Numerics.Vector%601> elementy członkowskie wykazują niespójne zachowanie na różnych platformach i konfiguracjach sprzętu.</span><span class="sxs-lookup"><span data-stu-id="2f32c-109">For unsupported types, <xref:System.Numerics.Vector%601> members exhibited inconsistent behavior across different platforms and hardware configurations.</span></span>

<span data-ttu-id="2f32c-110">Począwszy od platformy .NET 5,0, <xref:System.Numerics.Vector%601> członkowie zawsze zgłaszają <xref:System.NotSupportedException> wszystkie konfiguracje sprzętu, gdy `T` nie jest to obsługiwanego typu.</span><span class="sxs-lookup"><span data-stu-id="2f32c-110">Starting in .NET 5.0, <xref:System.Numerics.Vector%601> members always throw a <xref:System.NotSupportedException> on all hardware configurations when `T` is not a supported type.</span></span>

### <a name="unsupported-types"></a><span data-ttu-id="2f32c-111">Nieobsługiwane typy</span><span class="sxs-lookup"><span data-stu-id="2f32c-111">Unsupported types</span></span>

<span data-ttu-id="2f32c-112">Obsługiwane typy dla parametru typu <xref:System.Numerics.Vector%601> są:</span><span class="sxs-lookup"><span data-stu-id="2f32c-112">The supported types for the type parameter of <xref:System.Numerics.Vector%601> are:</span></span>

- `byte`
- `sbyte`
- `short`
- `ushort`
- `int`
- `uint`
- `long`
- `ulong`
- `float`
- `double`

<span data-ttu-id="2f32c-113">Obsługiwane typy nie uległy zmianie, ale mogą ulec zmianie w przyszłości.</span><span class="sxs-lookup"><span data-stu-id="2f32c-113">The supported types have not changed, however, they may change in the future.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="2f32c-114">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="2f32c-114">Version introduced</span></span>

<span data-ttu-id="2f32c-115">5,0</span><span class="sxs-lookup"><span data-stu-id="2f32c-115">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="2f32c-116">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="2f32c-116">Recommended action</span></span>

<span data-ttu-id="2f32c-117">Nie używaj nieobsługiwanego typu dla parametru typu <xref:System.Numerics.Vector%601> .</span><span class="sxs-lookup"><span data-stu-id="2f32c-117">Don't use an unsupported type for the type parameter of <xref:System.Numerics.Vector%601>.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="2f32c-118">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="2f32c-118">Affected APIs</span></span>

- <span data-ttu-id="2f32c-119"><xref:System.Numerics.Vector%601?displayProperty=fullName> i wszystkie jej elementy członkowskie</span><span class="sxs-lookup"><span data-stu-id="2f32c-119"><xref:System.Numerics.Vector%601?displayProperty=fullName> and all its members</span></span>

<!--

#### Category

Core .NET libraries

### Affected APIs

- ``T:System.Numerics.Vector`1``

-->
