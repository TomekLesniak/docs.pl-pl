---
title: 'Nieprzerwana zmiana: wewnętrzne testy nieobsługiwane przez sprzęt mogą się różnić w zależności od typów zagnieżdżonych'
description: Więcej informacji na temat istotnej zmiany w programie .NET 5,0 w bibliotekach podstawowych platformy .NET, w których jest sprawdzana wersja Funkcja issupport dla elementów wewnętrznych sprzętu może teraz generować inny wynik.
ms.date: 11/01/2020
ms.openlocfilehash: 9acef15860de76a9743621cb4c5edba5aac3931c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761555"
---
# <a name="hardware-intrinsic-issupported-checks-may-differ-for-nested-types"></a><span data-ttu-id="6d4fa-103">Wewnętrzne testy nieobsługiwane sprzętowo mogą się różnić w zależności od typów zagnieżdżonych</span><span class="sxs-lookup"><span data-stu-id="6d4fa-103">Hardware intrinsic IsSupported checks may differ for nested types</span></span>

<span data-ttu-id="6d4fa-104">Sprawdzanie `<Isa>.X64.IsSupported` , gdzie `<Isa>` odwołuje się do klas w <xref:System.Runtime.Intrinsics.X86?displayProperty=nameWithType> przestrzeni nazw, może teraz generować różne wyniki do poprzednich wersji platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="6d4fa-104">Checking `<Isa>.X64.IsSupported`, where `<Isa>` refers to the classes in the <xref:System.Runtime.Intrinsics.X86?displayProperty=nameWithType> namespace, may now produce a different result to previous versions of .NET.</span></span>

> [!TIP]
> <span data-ttu-id="6d4fa-105">Program *ISA* jest przeznaczony dla standardowej architektury branżowej.</span><span class="sxs-lookup"><span data-stu-id="6d4fa-105">*ISA* stands for industry standard architecture.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="6d4fa-106">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="6d4fa-106">Version introduced</span></span>

<span data-ttu-id="6d4fa-107">5,0</span><span class="sxs-lookup"><span data-stu-id="6d4fa-107">5.0</span></span>

## <a name="change-description"></a><span data-ttu-id="6d4fa-108">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="6d4fa-108">Change description</span></span>

<span data-ttu-id="6d4fa-109">W poprzednich wersjach programu .NET niektóre <xref:System.Runtime.Intrinsics.X86> Typy sprzętu — na przykład, <xref:System.Runtime.Intrinsics.X86.Aes?displayProperty=nameWithType> nie uwidaczniają klasy zagnieżdżonej `X64` .</span><span class="sxs-lookup"><span data-stu-id="6d4fa-109">In previous versions of .NET, some of the <xref:System.Runtime.Intrinsics.X86> hardware-intrinsic types, for example, <xref:System.Runtime.Intrinsics.X86.Aes?displayProperty=nameWithType>, didn't expose a nested `X64` class.</span></span> <span data-ttu-id="6d4fa-110">W przypadku tych typów wywoływanie `<Isa>.X64.IsSupported` został rozwiązany z `IsSupported` właściwością `X64` klasy zagnieżdżonej klasy nadrzędnej `<Isa>` .</span><span class="sxs-lookup"><span data-stu-id="6d4fa-110">For these types, calling `<Isa>.X64.IsSupported` resolved to an `IsSupported` property on a nested `X64` class of a parent class of `<Isa>`.</span></span> <span data-ttu-id="6d4fa-111">Oznacza to, że właściwość może zwrócić `true` nawet wtedy, gdy `<Isa>.IsSupported` zwraca `false` .</span><span class="sxs-lookup"><span data-stu-id="6d4fa-111">This meant that the property could return `true` even when `<Isa>.IsSupported` returns `false`.</span></span>

<span data-ttu-id="6d4fa-112">W programie .NET 5,0 i jego nowszych wersjach wszystkie <xref:System.Runtime.Intrinsics.X86> typy uwidaczniają zagnieżdżoną `X64` klasę, która odpowiednio obsługuje raporty.</span><span class="sxs-lookup"><span data-stu-id="6d4fa-112">In .NET 5.0 and later versions, all of the <xref:System.Runtime.Intrinsics.X86> types expose a nested `X64` class that appropriately reports support.</span></span> <span data-ttu-id="6d4fa-113">Dzięki temu ogólna hierarchia jest poprawna, a w `<Isa>.X64.IsSupported` przypadku `true` , gdy jest, `<Isa>.IsSupported` można również przyjąć, że jest to możliwe `true` .</span><span class="sxs-lookup"><span data-stu-id="6d4fa-113">This ensures that the general hierarchy remains correct, and that if `<Isa>.X64.IsSupported` is `true`, then `<Isa>.IsSupported` can also be assumed to be `true`.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="6d4fa-114">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="6d4fa-114">Reason for change</span></span>

<span data-ttu-id="6d4fa-115">Miało to `<Isa>.X64.IsSupported` `true` na celu, że `<Isa>.IsSupported` jest również implikowane `true` .</span><span class="sxs-lookup"><span data-stu-id="6d4fa-115">It was intended that if `<Isa>.X64.IsSupported` is `true`, `<Isa>.IsSupported` is also implied to be `true`.</span></span> <span data-ttu-id="6d4fa-116">Jednak ze względu na sposób, w jaki rozpoznawanie elementów członkowskich działa w języku C#, klasy, które nie miały klasy zagnieżdżonej, `X64` uwidaczniają sytuację, w której to nigdy nie było tak samo, i doprowadziło do błędów w kodzie użytkownika.</span><span class="sxs-lookup"><span data-stu-id="6d4fa-116">However, due to how member resolution works in C#, classes that didn't have a nested `X64` class exposed a situation where this wasn't always the case and led to bugs in user code.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="6d4fa-117">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="6d4fa-117">Recommended action</span></span>

<span data-ttu-id="6d4fa-118">W razie potrzeby dostosuj kod, który sprawdza, czy `IsSupported` ma być sprawdzana odpowiednia wartość ISA.</span><span class="sxs-lookup"><span data-stu-id="6d4fa-118">If necessary, adjust code that checks `IsSupported` to check for the appropriate ISA.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="6d4fa-119">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="6d4fa-119">Affected APIs</span></span>

- <xref:System.Runtime.Intrinsics.X86.Aes.X64.IsSupported?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Avx.X64.IsSupported?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Avx2.X64.IsSupported?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Fma.X64.IsSupported?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Pclmulqdq.X64.IsSupported?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Sse3.X64.IsSupported?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Ssse3.X64.IsSupported?displayProperty=fullName>

<!--

### Category

Core .NET libraries

### Affected APIs

- `P:System.Runtime.Intrinsics.X86.Aes.X64.IsSupported`
- `P:System.Runtime.Intrinsics.X86.Avx.X64.IsSupported`
- `P:System.Runtime.Intrinsics.X86.Avx2.X64.IsSupported`
- `P:System.Runtime.Intrinsics.X86.Fma.X64.IsSupported`
- `P:System.Runtime.Intrinsics.X86.Pclmulqdq.X64.IsSupported`
- `P:System.Runtime.Intrinsics.X86.Sse3.X64.IsSupported`
- `P:System.Runtime.Intrinsics.X86.Ssse3.X64.IsSupported`

-->
